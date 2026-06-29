# Claude Skills

A collection of reusable [Agent Skills](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) for Claude. Each skill is a self-contained folder with a `SKILL.md` file that teaches Claude how to do one job well, whether that's writing a cold email that actually gets a reply or pulling the AI tells out of a draft.

Skills load on demand. Claude reads the short description up front, and only pulls in the full instructions when your request matches. That keeps the model fast and focused while still giving it deep, specialized know-how the moment it's needed.

## What's inside

There are 11 skills here, grouped by what they help you do.

### Job search and resumes

| Skill | What it does |
|-------|--------------|
| [`resume-ats-optimizer`](skills/resume-ats-optimizer/SKILL.md) | Rewrites a resume so it gets past Applicant Tracking Systems. Checks keyword match, formatting, and the reasons applications get auto-rejected. |
| [`resume-bullet-writer`](skills/resume-bullet-writer/SKILL.md) | Turns flat job duties into achievement bullets with real impact, using the X-Y-Z formula ("accomplished X, measured by Y, by doing Z"). |
| [`resume-quantifier`](skills/resume-quantifier/SKILL.md) | Finds places to add numbers to your bullets, and helps you estimate them honestly when you don't have exact figures. |
| [`resume-tailor`](skills/resume-tailor/SKILL.md) | Customizes a resume for one specific job posting by surfacing the experience that matters most, without inventing anything. |
| [`tech-resume-optimizer`](skills/tech-resume-optimizer/SKILL.md) | Same idea, tuned for software, PM, data, and other technical roles. Handles skills sections, projects, and the order recruiters expect. |
| [`cover-letter-generator`](skills/cover-letter-generator/SKILL.md) | Writes a personalized cover letter from your resume and the job description. Short, specific, and not full of clichés. |

### Writing and outreach

| Skill | What it does |
|-------|--------------|
| [`cold-email`](skills/cold-email/SKILL.md) | Drafts cold emails that get responses using proven copywriting frameworks (AIDA, PAS, BAB). Keeps them between 50 and 125 words with a real personalized opener. |
| [`humanizer`](skills/humanizer/SKILL.md) | Edits text to remove the signs of AI writing, based on Wikipedia's "Signs of AI writing" guide. Catches em-dash overuse, the rule of three, filler phrases, and vague attributions. |

### Design and learning

| Skill | What it does |
|-------|--------------|
| [`frontend-design`](skills/frontend-design/SKILL.md) | Pushes Claude toward distinctive, intentional UI instead of templated defaults. Guidance on palette, typography, and taking one justified aesthetic risk. |
| [`ui-ux-pro-max`](skills/ui-ux-pro-max/SKILL.md) | A full design knowledge base: 50+ styles, 161 color palettes, 57 font pairings, UX guidelines, and chart types across 10 stacks. |
| [`teach`](skills/teach/SKILL.md) | Turns a workspace into a personal tutor. Builds lessons, reference sheets, and learning records so a topic can be learned across many sessions. |

## How a skill is built

Every skill follows the same simple shape:

```
skills/
└── cold-email/
    └── SKILL.md
```

The `SKILL.md` file starts with a small YAML header and then plain Markdown instructions:

```markdown
---
name: cold-email
description: Write cold emails that get replies using proven frameworks (AIDA, PAS, BAB).
---

# Write Cold Email

Generate a cold email that gets responses using proven copywriting frameworks.
...
```

The `name` is the skill's ID. The `description` is what Claude reads to decide whether the skill is relevant to your request, so it's worth writing clearly. Everything below the header is the actual playbook Claude follows once the skill is loaded.

## Using these skills

Pick whichever path matches how you work with Claude. Full setup and cloud deployment steps are in [DEPLOYMENT.md](DEPLOYMENT.md).

**Claude Code (local).** Drop a skill folder into `~/.claude/skills/` and it's available in every session.

**Claude apps (Cowork / desktop).** Zip a skill folder into a `.skill` file and install it from Settings, or share it directly.

**The API.** Reference a skill's instructions in your system prompt, or load them through the Agent SDK so your own application can use them.

A skill triggers on its own when your request matches its description. You don't have to name it.

## Adding your own

1. Create a new folder under `skills/` named after your skill (lowercase, dashes for spaces).
2. Add a `SKILL.md` with a `name` and `description` in the header, then your instructions below.
3. Keep the description concrete and specific. It's the only thing Claude sees before deciding to load the skill, so write it the way you'd describe the skill to a coworker.
4. Open a pull request.

## License

Each skill keeps the license noted in its own file where one is specified. Unless a skill says otherwise, the contents of this repository are shared for personal and educational use.

---

Maintained by [@harshachinthala](https://github.com/harshachinthala). If a skill saves you time, a star is appreciated.
