# Deployment Guide

This guide covers how to get these skills running, from a laptop to a cloud setup that your whole team can share. Pick the section that matches where you want the skills to live.

## 1. Local use with Claude Code

The fastest way to try a skill.

```bash
# Clone the repo
git clone https://github.com/harshachinthala/claude-skills.git
cd claude-skills

# Copy a skill into your personal skills folder
mkdir -p ~/.claude/skills
cp -r skills/cold-email ~/.claude/skills/

# Or symlink the whole folder so updates flow through automatically
ln -s "$(pwd)/skills/cold-email" ~/.claude/skills/cold-email
```

Restart Claude Code and the skill is live. It activates on its own when a request matches its description.

To install every skill at once:

```bash
cp -r skills/* ~/.claude/skills/
```

## 2. Project-scoped skills (shared with a team)

If you want a skill available only inside one project, and versioned with that project's code, keep it in the repo itself:

```
your-project/
└── .claude/
    └── skills/
        └── cold-email/
            └── SKILL.md
```

Anyone who clones the project gets the skill. This is the cleanest way to share skills across a team, since the skill travels with the codebase and goes through normal code review.

## 3. Claude desktop and Cowork

The desktop apps install skills as `.skill` files, which are just a zipped skill folder.

```bash
# Zip a single skill into an installable .skill file
cd skills
zip -r cold-email.skill cold-email
```

Then in the app, open **Settings → Capabilities → Skills** and install the `.skill` file, or share the file directly with someone and have them install it.

## 4. Using skills through the API and Agent SDK

Skills are plain Markdown, so you can feed their instructions to Claude through the API in two ways.

**Inline in the system prompt.** Read a `SKILL.md` and include its body as part of your system prompt. Good for one or two skills.

```python
import anthropic

with open("skills/cold-email/SKILL.md") as f:
    skill = f.read()

client = anthropic.Anthropic()
message = client.messages.create(
    model="claude-sonnet-4-6",
    max_tokens=1024,
    system=f"You have access to the following skill.\n\n{skill}",
    messages=[{"role": "user", "content": "Write a cold email to a VP of Sales at a fintech startup, goal is a 15-min intro call."}],
)
print(message.content[0].text)
```

**Through the Agent SDK.** For an agent that should pick skills on its own, load each skill's `name` and `description`, expose them as a lightweight index, and inject the full `SKILL.md` only when the agent selects it. This mirrors how Claude Code loads skills on demand and keeps your token usage low.

## 5. Cloud deployment for a shared service

To run an agent backed by these skills as an always-on service, the pattern is the same regardless of provider.

**Step 1 — Containerize.** Add a `Dockerfile` that copies the skills in alongside your agent code.

```dockerfile
FROM python:3.12-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY skills/ ./skills/
COPY app/ ./app/
ENV ANTHROPIC_API_KEY=""
CMD ["python", "-m", "app.server"]
```

**Step 2 — Store the API key as a secret.** Never bake `ANTHROPIC_API_KEY` into the image. Use the platform's secret manager:

- AWS: Secrets Manager or SSM Parameter Store, injected into ECS/Lambda as an environment variable
- Google Cloud: Secret Manager, mounted into Cloud Run
- Azure: Key Vault, referenced from Container Apps
- Fly.io / Render / Railway: the built-in secrets or environment settings

**Step 3 — Deploy.** Any container host works. A few common choices:

```bash
# Google Cloud Run
gcloud run deploy claude-skills-agent \
  --source . \
  --set-secrets ANTHROPIC_API_KEY=anthropic-api-key:latest \
  --region us-central1 --allow-unauthenticated

# Fly.io
fly launch
fly secrets set ANTHROPIC_API_KEY=sk-ant-...
fly deploy
```

**Step 4 — Keep skills in sync.** Because skills are versioned in this repo, point a CI job at it. When the repo updates, rebuild the image so the deployed agent always runs the latest skill instructions. A simple GitHub Actions workflow that builds and pushes on every commit to `main` is enough to make this automatic.

## A few good habits

- Treat `SKILL.md` files like code. Review changes, since a small edit to the instructions changes the agent's behavior.
- Keep each skill focused on one job. A skill that tries to do everything triggers at the wrong times.
- Watch your secrets. The only credential these skills need is your Anthropic API key, and it should always come from a secret store, never the repo.
