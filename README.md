# Claude Skills

### Skills & tools I used to build these

![Prompt Engineering](https://img.shields.io/badge/Prompt_Engineering-412991?style=for-the-badge&logo=openai&logoColor=white)
![Generative AI](https://img.shields.io/badge/Generative_AI-8E75B2?style=for-the-badge&logo=googlegemini&logoColor=white)
![Claude](https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=anthropic&logoColor=white)
![LLMs](https://img.shields.io/badge/LLMs-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)
![NLP](https://img.shields.io/badge/Natural_Language_Processing-005571?style=for-the-badge&logo=spacy&logoColor=white)

![Agent Skills](https://img.shields.io/badge/Agent_Skills-1A1A1A?style=for-the-badge&logo=claude&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white)
![Technical Writing](https://img.shields.io/badge/Technical_Writing-2EA44F?style=for-the-badge&logo=readthedocs&logoColor=white)
![Copywriting](https://img.shields.io/badge/Copywriting-0A66C2?style=for-the-badge&logo=ghost&logoColor=white)
![UI/UX Design](https://img.shields.io/badge/UI%2FUX_Design-F24E1E?style=for-the-badge&logo=figma&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

These are the skills I built for Claude out of the repetitive work I do every day, things like job hunting, writing outreach, cleaning up my drafts, and designing interfaces. Each one is a small instruction file that teaches Claude how to do a single job well, so I don't have to keep re-explaining myself every time I open a new chat.

A skill is really just a Markdown file with a short description at the top. Claude reads that description first and only loads the full instructions when my request actually matches it, so nothing weighs the model down until it's the right moment for it.

There are 11 skills in here. A few are packaged as ready-to-install `.skill` files, and the rest are plain `.md` instruction files you can drop in yourself.

## Skills at a glance

[![ATS Optimizer](https://img.shields.io/badge/ATS_Optimizer-0A66C2?style=for-the-badge&logo=readthedocs&logoColor=white)](resume-ats-optimizer.md)
[![Bullet Writer](https://img.shields.io/badge/Bullet_Writer-0A66C2?style=for-the-badge&logo=markdown&logoColor=white)](resume-bullet-writer.md)
[![Quantifier](https://img.shields.io/badge/Quantifier-0A66C2?style=for-the-badge&logo=chartdotjs&logoColor=white)](resume-quantifier.md)
[![Resume Tailor](https://img.shields.io/badge/Resume_Tailor-0A66C2?style=for-the-badge&logo=target&logoColor=white)](resume-tailor.md)
[![Tech Resume](https://img.shields.io/badge/Tech_Resume-0A66C2?style=for-the-badge&logo=github&logoColor=white)](tech-resume-optimizer.md)
[![Cover Letter](https://img.shields.io/badge/Cover_Letter-0A66C2?style=for-the-badge&logo=gmail&logoColor=white)](Cover_letter_Generator.md)

[![Cold Email](https://img.shields.io/badge/Cold_Email-2EA44F?style=for-the-badge&logo=maildotru&logoColor=white)](cold-email.skill)
[![Humanizer](https://img.shields.io/badge/Humanizer-2EA44F?style=for-the-badge&logo=openai&logoColor=white)](humanizer.skill)

[![Frontend Design](https://img.shields.io/badge/Frontend_Design-8957E5?style=for-the-badge&logo=css3&logoColor=white)](frontend-design.skill)
[![UI/UX Pro Max](https://img.shields.io/badge/UI%2FUX_Pro_Max-8957E5?style=for-the-badge&logo=figma&logoColor=white)](ui_ux_pro_max.md)
[![Teach](https://img.shields.io/badge/Teach-8957E5?style=for-the-badge&logo=googleclassroom&logoColor=white)](teach.skill)

## What's inside

### Job search and resumes

| Skill | What it does |
|-------|--------------|
| [resume-ats-optimizer](resume-ats-optimizer.md) | Rewrites a resume so it gets past Applicant Tracking Systems. Checks keyword match, formatting, and the reasons applications get auto-rejected. |
| [resume-bullet-writer](resume-bullet-writer.md) | Turns flat job duties into achievement bullets with real impact, using the X-Y-Z formula ("accomplished X, measured by Y, by doing Z"). |
| [resume-quantifier](resume-quantifier.md) | Finds places to add numbers to your bullets, and helps you estimate them honestly when you don't have exact figures. |
| [resume-tailor](resume-tailor.md) | Customizes a resume for one specific job posting by surfacing the experience that matters most, without inventing anything. |
| [tech-resume-optimizer](tech-resume-optimizer.md) | Same idea, tuned for software, PM, data, and other technical roles. Handles skills sections, projects, and the order recruiters expect. |
| [cover-letter-generator](Cover_letter_Generator.md) | Writes a personalized cover letter from your resume and the job description. Short, specific, and not full of clichés. |

### Writing and outreach

| Skill | What it does |
|-------|--------------|
| [cold-email](cold-email.skill) | Drafts cold emails that get responses using proven copywriting frameworks (AIDA, PAS, BAB). Keeps them between 50 and 125 words with a real personalized opener. |
| [humanizer](humanizer.skill) | Edits text to remove the signs of AI writing, based on Wikipedia's "Signs of AI writing" guide. Catches em-dash overuse, the rule of three, filler phrases, and vague attributions. |

### Design and learning

| Skill | What it does |
|-------|--------------|
| [frontend-design](frontend-design.skill) | Pushes Claude toward distinctive, intentional UI instead of templated defaults. Guidance on palette, typography, and taking one justified aesthetic risk. |
| [ui-ux-pro-max](ui_ux_pro_max.md) | A full design knowledge base: 50+ styles, 161 color palettes, 57 font pairings, UX guidelines, and chart types across 10 stacks. |
| [teach](teach.skill) | Turns a workspace into a personal tutor. Builds lessons, reference sheets, and learning records so a topic can be learned across many sessions. |

## How to use these in Claude

The files come in two shapes, so there are two ways to install them.

### Files ending in `.skill`

These are already packaged and ready to install (`cold-email`, `frontend-design`, `humanizer`, `teach`).

- **Claude desktop app or Cowork:** download the `.skill` file, open **Settings → Capabilities → Skills**, and install it. That's it.
- **Claude Code:** a `.skill` file is just a zipped folder. Unzip it into `~/.claude/skills/` and restart Claude Code.

### Files ending in `.md`

These are the raw skill instructions (the contents of a `SKILL.md`). Two simple ways to use them:

- **Claude Code:** make a folder named after the skill inside `~/.claude/skills/`, then save the file inside it as `SKILL.md`. For example, `~/.claude/skills/resume-tailor/SKILL.md`. Restart Claude Code and the skill is live.
- **Any Claude chat or Project:** paste the contents in as instructions, or add the file to a Project so Claude can pull from it.

Once a skill is installed, I never have to call it by name. Claude notices when a request matches the skill's description and loads it on its own.

## How each file is written

Every skill opens with a short header and then the instructions:

```
---
name: cold-email
description: Write cold emails that get replies using proven frameworks (AIDA, PAS, BAB).
---

# Write Cold Email

Generate a cold email that gets responses using proven copywriting frameworks.
...
```

The `description` is the part that matters most. It's the only thing Claude reads before deciding whether to load the skill, so I keep it specific and concrete, the way I'd describe the skill to a coworker.

## License

These are shared for personal and educational use. A couple of the skills carry their own license note inside the file; where they do, that note wins.

---

Built by me, [@harshachinthala](https://github.com/harshachinthala). If one of these saves you some time, a star is appreciated.
