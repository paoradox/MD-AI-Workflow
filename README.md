# MD-AI-Workflow

[![Built with](https://img.shields.io/badge/built_with-Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white)](https://www.markdownguide.org/)
[![Use case](https://img.shields.io/badge/use_case-AI_%2F_AI_Agent_Instructions-6E56CF?style=for-the-badge)](#)

Reusable Markdown operating specs and `SKILL.md` files for AI coding, design, README generation, environment handling, and Node.js-to-Electron portability workflows.

The repository keeps both the original prompt/spec files and skill-ready versions that can be used by ChatGPT, Codex, Claude, Claude Code, DeepSeek, Gemini, and other AI agents.

---

## Repository Structure

```text
.
├── Code
│   ├── AI_CODE++.md
│   └── SKILL.md
├── Design
│   ├── AI_DESIGN++.md
│   └── SKILL.md
├── Electron-Portable
│   ├── APP_PORTABILITY_PROMPT.md
│   └── SKILL.md
└── README.md
```

---

## What's Included

| Folder | Original File | Skill File | Use It When |
| --- | --- | --- | --- |
| `Code/` | `AI_CODE++.md` | `Code/SKILL.md` | You need consistent coding-agent behavior, scoped implementation, README generation, `.env` / `.gitignore` handling, validation, and action-first responses. |
| `Design/` | `AI_DESIGN++.md` | `Design/SKILL.md` | You are working on UI/UX design, frontend implementation, design systems, accessibility reviews, interface audits, visual content architecture, or design README generation. |
| `Electron-Portable/` | `APP_PORTABILITY_PROMPT.md` | `Electron-Portable/SKILL.md` | You want to wrap an existing JavaScript/Node.js/Express-based web app as a portable, editable Electron desktop app with a thin launcher, LAN URLs, shortcuts, and port controls. |

The original `.md` files are preserved as readable source prompts. The `SKILL.md` files add skill frontmatter, cross-agent installation notes, and invocation aliases.

---

## Skill Overview

### Code Skill

`Code/SKILL.md`

- Skill name: `ai-code-plus-plus`
- Source file: `Code/AI_CODE++.md`
- Invocation aliases:
  - `/code`
  - `/code-readme`
  - `/code-env`

Use this skill for coding tasks that need strict scope control, project-convention awareness, maintainable code, validation, README generation, or safe secret/environment handling.

### Design Skill

`Design/SKILL.md`

- Skill name: `ai-design-plus-plus`
- Source file: `Design/AI_DESIGN++.md`
- Invocation aliases:
  - `/design`
  - `/design-readme`

Use this skill for interface design, frontend implementation, redesigns, design audits, accessibility-aware reviews, design systems, and README files for design-heavy or frontend projects.

### Electron Portable Skill

`Electron-Portable/SKILL.md`

- Skill name: `nodejs-electron-portability`
- Source file: `Electron-Portable/APP_PORTABILITY_PROMPT.md`
- Invocation alias:
  - `/electron-portable`

Use this skill when converting an existing JavaScript/Node.js/Express-based web app into a double-clickable Electron desktop app while keeping the app's actual server/frontend source editable outside the packaged launcher.

---

## Installation And Use

### Option 1: Use As Plain Prompt Files

Upload or paste the relevant original `.md` file or `SKILL.md` into your AI tool, then explicitly ask the agent to follow it.

Examples:

```text
Follow Code/SKILL.md and use /code to revise this project.
```

```text
Follow Design/SKILL.md and use /design to audit this interface.
```

```text
Follow Electron-Portable/SKILL.md and use /electron-portable to convert this Express app into a portable Electron launcher.
```

### Option 2: Install As Skill Folders

For tools that support skill folders, copy the skill folder contents into the tool's skills directory or project instruction area.

Recommended folder names:

```text
ai-code-plus-plus/
  SKILL.md

ai-design-plus-plus/
  SKILL.md

nodejs-electron-portability/
  SKILL.md
```

If your tool expects one skill per folder, copy each `SKILL.md` into a folder matching its skill name.

### Option 3: Use With Claude, Claude Code, Gemini, DeepSeek, Or Similar Agents

If the platform supports project instructions, paste the `SKILL.md` body into the project instruction area.

If the platform does not support YAML frontmatter, keep the important values as plain text:

```text
Name: ai-code-plus-plus
Description: Use for coding-agent tasks that need consistent implementation behavior, scoped code changes, README generation, environment/secret handling, validation, and concise action-first responses.
```

The slash aliases are optional shortcuts. The actual skill identity is the `name` field, and automatic activation depends on the `description`.

---

## Trigger And Invocation Reference

| Task | Skill | Alias |
| --- | --- | --- |
| Code implementation, bug fixes, refactors within scope, validation | `ai-code-plus-plus` | `/code` |
| Code-project README generation | `ai-code-plus-plus` | `/code-readme` |
| `.env.example`, `.gitignore`, and secret-handling setup | `ai-code-plus-plus` | `/code-env` |
| UI/UX design, frontend implementation, redesigns, accessibility audits | `ai-design-plus-plus` | `/design` |
| README generation for frontend/design-heavy projects | `ai-design-plus-plus` | `/design-readme` |
| JavaScript/Node.js/Express-based app to portable Electron launcher workflow | `nodejs-electron-portability` | `/electron-portable` |

---

## Core Behaviors

Across the skills, the specs emphasize:

- Action-first responses with no filler preamble or vague closers.
- Scoped work that follows existing project structure, conventions, and dependencies.
- No invented features, commands, URLs, screenshots, accessibility claims, licenses, or test results.
- Plain failure reporting: what failed, why it failed, and what fixes it.
- Validation when possible, with unperformed checks stated honestly.

---

## Notes For Agents

- System, developer, safety, and tool instructions override these skills.
- Destructive actions still require explicit confirmation before execution.
- Real API keys, passwords, tokens, and credentials must never be generated, displayed, or committed.
- Automated accessibility results are evidence, not proof of full WCAG conformance.
- Slash commands such as `/code` or `/design` are aliases only; they are not required for the underlying skill to work.

---

## Validation

The current `SKILL.md` files were checked with the official skill validator:

```text
Code/SKILL.md                 Skill is valid!
Design/SKILL.md               Skill is valid!
Electron-Portable/SKILL.md    Skill is valid!
```

---

## Acknowledgements

This workflow's communication rules, including action-first responses, numbered steps, no filler closers, surfaced uncertainty, and verification-oriented output, were shaped by:

- [Andrej Karpathy](https://x.com/karpathy), especially observations on common LLM coding pitfalls.
- [multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills), whose principles around thinking before coding, simplicity, surgical changes, and goal-driven execution informed the code workflow.
- [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd), whose ADHD-friendly output patterns influenced the action-first communication rules.
- J. Russell Ramsay and Anthony L. Rostain, authors of *The Adult ADHD Tool Kit*, loosely informing the low-friction communication style.

Additional influences on design and accessibility:

- [Nutlope/hallmark](https://github.com/Nutlope/hallmark), especially the stance against generic AI-generated layouts.
- [clawhub.ai/turbolego/skills/wcag-skill](https://clawhub.ai/turbolego/skills/wcag-skill), especially the distinction between automated accessibility findings, manual testing, and formal conformance claims.

---

## License

Apache License 2.0

---

**AI Workflow** - Instructions that make AI act first and explain later · 2026
