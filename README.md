# MD-AI-Workflow

[![Built with](https://img.shields.io/badge/built_with-Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white)](https://www.markdownguide.org/)
[![Use case](https://img.shields.io/badge/use_case-AI_%2F_AI_Agent_Instructions-6E56CF?style=for-the-badge)](#)

A pair of markdown operating specs for AI coding and design assistants (ChatGPT, DeepSeek, Claude, and similar tools) — built to enforce action-first, no-filler responses, numbered steps, honest failure states, accessibility-aware design, and accurate README generation with zero invented information.

---

## 📁 Repository Structure

```
.
├── 📁 Code
│ ├── 📁 Master file
│ │ └── 📝 AI_CODE++.md
│ └── 📁 Split file
│ ├── 📝 AI_CODE+.md
│ └── 📝 README_GENERATION.md
├── 📁 Design
│ └── 📝 AI_DESIGN++.md
└── 📝 README.md
```

---

## ✨ What's Included

| File | Use it when... |
|---|---|
| **`Code/Master file/AI_WORKFLOW++.md`** | You want one file that governs coding behavior *and* README generation together |
| **`Code/Split file/AI_WORKFLOW+.md`** | You want coding-behavior rules only, without README generation bundled in |
| **`Code/Split file/README_GENERATION.md`** | You just need a README generated — for any project, with or without the rest of the workflow spec |
| **`Design/AI_DESIGN++.md`** | You're working on UI/UX design, frontend implementation, design systems, accessibility reviews, or interface audits |

**Core behaviors enforced across all specs:**
- Action-first responses — no "Let's think about this" openers, no "Hope this helps!" closers
- Numbered steps for any multi-step task
- Plain, unsoftened failure states — what broke, why, and the fix, in that order
- No invented dependencies, commands, URLs, screenshots, design tokens, or licenses — ever
- Destructive actions (force push, migrations, drops, overwrites) always get a confirmation step

**Coding behavior** (`AI_CODE++.md and AI_CODE+.md`):
- Follows existing architecture, folder structure, naming conventions, and approved dependencies — no new frameworks or libraries without approval
- Scoped strictly to what was requested — no unrequested refactors, optimizations, or extra features
- Readable and beginner-friendly by default; comments only where logic, business rules, or future maintenance genuinely need them
- Validated before being called done — tests/lint/type checks run when possible, failures stated plainly, never claimed without being run

**Design behavior** (`AI_DESIGN++.md`):
- Design-before-code: user goal, primary task, critical content, and primary action resolved before any layout is proposed
- Content-first hierarchy built from real content; placeholders and fake metrics/ testimonials never presented as real
- Actively avoids generic AI-generated layouts (cookie-cutter SaaS pages, repetitive card grids, meaningless hero sections, decorative gradients)
- Accessibility treated as a mandatory design consideration — semantic HTML, keyboard interaction, focus states, contrast, form labelling, and non-color-dependent meaning — not bolted on after visual development

**README generation** (AI_CODE++.md, AI_DESIGN++.md):
- Documented only from verifiable source — no invented features, dependencies, commands, URLs, screenshots, or accessibility claims
- Design READMEs additionally document design system, pages/screens, components, responsive behavior, and implemented accessibility features without overstating WCAG conformance
- Exported as a single continuous Markdown code block, directly copyable into `README.md`

**Security handling** (`AI_CODE++.md and AI_CODE+.md`):
- Every task considers input validation, error handling, authentication, authorization, and secret management
- First introduction of an API key, password, token, or credential in a task auto-triggers `.env.example` + `.gitignore` generation alongside the requested deliverable
- Real secrets are never generated, displayed, or committed — only placeholder values
- An existing `.env` not already in `.gitignore` gets flagged immediately as an exposure risk, with a reminder to rotate any keys already committed to git history

---

## 🚀 Getting Started

1. **Pick the spec that matches your task** using the table above.
2. **Upload it to your AI chat session**, or place it in your repo if you're using an agentic coding tool that reads project files directly. Example for Claude Code:
   ```bash
   cp AI_CODE++.md ./CLAUDE.md
   ```
   Or keep the original filename and reference it explicitly:
   ```
   Follow the instructions in AI_CODE++.md for this project.
   ```
3. **Reference the file explicitly in your request** — uploading a file does not make an AI automatically apply it. Say so directly, for example:
   ```
   Generate a README for this project in accordance with AI_CODE+.md.
   ```
   ```
   Redesign this dashboard in accordance with AI_DESIGN++.md.
   ```
4. **Re-attach the file each new session.** Files don't persist across separate chats unless you're using a project/workspace feature that stores them, or the files live in the repo an agentic tool is already reading.

---

## 🧩 Which File to Use

| Situation | Use |
|---|---|
| Writing, modifying, or reviewing code | `AI_CODE++.md` |
| Generating a README for a code project | `AI_CODE++.md and/or README_GENERATION.md or` (README Generation Mode) |
| Setting up `.env` / `.gitignore` or handling secrets | `AI_CODE++.md and/or AI_CODE+.md` |
| Designing or implementing a UI, page, dashboard, or landing page | `AI_DESIGN++.md` |
| Want both behaviors, but edited/versioned independently | Both `Code/Split file/` files, uploaded together |
| Auditing an existing interface for usability or accessibility | `AI_DESIGN++.md` |
| Generating a README for a design-heavy or frontend project | `AI_DESIGN++.md` (README Generation Mode) |
| Working on a full product with both code and UI concerns | Both `AI_CODE++.md and AI_DESIGN++.md` files, uploaded together |

---

## 🙏 Acknowledgements

This workflow's core communication rules — action first, numbered steps, no "Hope this helps!," surfacing confusion instead of silently guessing, and treating every response as something to verify rather than assume — were shaped in large part by the ideas in:

- **[Andrej Karpathy](https://x.com/karpathy)**, whose observations on common LLM coding pitfalls are the original source the above repo draws from.
- **[multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills)** — *"A single CLAUDE.md file to improve Claude Code behavior, derived from Andrej Karpathy's observations on LLM coding pitfalls."* Its four principles (Think Before Coding, Simplicity First, Surgical Changes, Goal-Driven Execution) directly informed how this repo's specs push back on models burying the answer, overcomplicating solutions, or making silent assumptions.
  > *"Don't assume. Don't hide confusion. Surface tradeoffs."*
- **[ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd)** — *"A skill to stop your coding agent from burying the answer. ADHD-friendly output."* Its rule set (lead with the action, cap lists, no preamble, no "Hope this helps!") is the direct source of this repo's Communication Rules and Response Format sections.
  > *"Action first. Steps numbered. No 'Hope this helps!'"*
- **J. Russell Ramsay and Anthony L. Rostain**, authors of *The Adult ADHD Tool Kit* — the above repo credits its approach as loosely based on this book, adapted for how an LLM should respond rather than how a human should organize their day.

Additional influences on the design and accessibility specs:

- **[Nutlope/hallmark](https://github.com/Nutlope/hallmark)** — informed the design principles and quality rules in `AI_DESIGN++.md`, particularly the stance against generic AI-generated layouts and the push for project-specific visual identity.
- **[clawhub.ai/turbolego/skills/wcag-skill](https://clawhub.ai/turbolego/skills/wcag-skill)** — informed the accessibility requirements and accessibility validation sections in `AI_DESIGN++.md`, including the distinction between automated findings, manual testing, and formal WCAG conformance claims.

---

## 📄 License

Apache License 2.0

---

**AI Workflow** — Instructions that make AI act first and explain later · 2026
