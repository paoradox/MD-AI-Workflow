# MD-AI-Workflow

[![Built with](https://img.shields.io/badge/built_with-Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white)](https://www.markdownguide.org/)
[![Use case](https://img.shields.io/badge/use_case-AI_%2F_AI_Agent_Instructions-6E56CF?style=for-the-badge)](#)

A set of markdown operating specs for AI coding assistants and agents (ChatGPT, DeepSeek, Claude, and similar tools) — built to enforce action-first, no-filler responses, numbered steps, honest failure states, and accurate README generation with zero invented information.

---

## 📁 Repository Structure

```
.
├── Master file/
│   └── AI_WORKFLOW++.md        # Full spec — coding behavior, communication rules,
│                                # README generation, and .env/.gitignore handling, all in one file
│
└── Split file/
    ├── AI_WORKFLOW+.md          # Same as above, minus README generation
    └── README_GENERATION.md     # README generation only — usable independently,
                                  # with no dependency on the file above
```

---

## ✨ What's Included

| File | Use it when... |
|---|---|
| **`Master file/AI_WORKFLOW++.md`** | You want one file that governs coding behavior *and* README generation together |
| **`Split file/AI_WORKFLOW+.md`** | You want coding-behavior rules only, without README generation bundled in |
| **`Split file/README_GENERATION.md`** | You just need a README generated — for any project, with or without the rest of the workflow spec |

**Core behaviors enforced across all specs:**
- Action-first responses — no "Let's think about this" openers, no "Hope this helps!" closers
- Numbered steps for any multi-step task
- Plain, unsoftened failure states — what broke, why, and the fix, in that order
- No invented dependencies, commands, URLs, screenshots, or licenses — ever
- Destructive actions (force push, migrations, drops, overwrites) always get a confirmation step

**Task handling** (`AI_WORKFLOW++.md` / `AI_WORKFLOW+.md`):
- Analyze the actual goal and constraints before proposing a solution — ask only when critical info is missing
- Plan medium/large tasks with a task summary, approach, files affected, risks, success criteria, and a concrete time estimate
- Preview changes before major modifications; ask for approval per the configured Change Policy
- Restate progress each turn on multi-step work — which step just finished, which is next

**Code generation:**
- Follows existing architecture, folder structure, naming conventions, and approved dependencies — no new frameworks or libraries without approval
- Scoped strictly to what was requested — no unrequested refactors, optimizations, or extra features
- Readable and beginner-friendly by default; comments only where logic, business rules, or future maintenance genuinely need them
- Validated before being called done — tests/lint/type checks run when possible, failures stated plainly, never claimed without being run

**Security handling:**
- Every task considers input validation, error handling, authentication, authorization, and secret management
- First introduction of an API key, password, token, or credential in a task auto-triggers `.env.example` + `.gitignore` generation alongside the requested deliverable
- Real secrets are never generated, displayed, or committed — only placeholder values
- An existing `.env` not already in `.gitignore` gets flagged immediately as an exposure risk, with a reminder to rotate any keys already committed to git history

---

## 🚀 Getting Started

1. **Pick a file (or two)** based on the table above.
2. **Upload it to your AI chat session**, or place it in your repo if you're using an agentic coding tool that reads project files directly. Example for Claude Code — copy the spec in as the file it reads automatically:
   ```bash
   cp "Split file/AI_WORKFLOW+.md" ./CLAUDE.md
   ```
   Or keep the original filename and point Claude Code at it directly:
   ```bash
   cp "Master file/AI_WORKFLOW++.md" ./AI_WORKFLOW++.md
   ```
   ```
   Follow the instructions in AI_WORKFLOW++.md for this project.
   ```
3. **Reference it explicitly in your request** — uploading a file does not make an AI automatically apply it. Say so directly, for example:
   ```
   Generate a README for this project in accordance with README_GENERATION.md.
   ```
4. **Re-attach the file(s) each new session.** Files don't persist across separate chats unless you're using a project/workspace feature that stores them, or the files live in the repo an agentic tool is already reading.

---

## 🧩 Master vs. Split — Which to Use

| Situation | Use |
|---|---|
| Working on a coding project and also want README generation | `Master file/AI_WORKFLOW++.md` |
| Working on a coding project but don't need README generation | `Split file/AI_WORKFLOW+.md` |
| Just need a README for something unrelated to the rest of your workflow | `Split file/README_GENERATION.md` on its own |
| Want both behaviors, but edited/versioned independently | Both `Split file/` files, uploaded together |

---

## 🙏 Acknowledgements

This workflow's core communication rules — action first, numbered steps, no "Hope this helps!," surfacing confusion instead of silently guessing, and treating every response as something to verify rather than assume — were shaped in large part by the ideas in:

- **[Andrej Karpathy](https://x.com/karpathy)**, whose observations on common LLM coding pitfalls are the original source the above repo draws from.
- **[multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills)** — *"A single CLAUDE.md file to improve Claude Code behavior, derived from Andrej Karpathy's observations on LLM coding pitfalls."* Its four principles (Think Before Coding, Simplicity First, Surgical Changes, Goal-Driven Execution) directly informed how this repo's specs push back on models burying the answer, overcomplicating solutions, or making silent assumptions.
  > *"Don't assume. Don't hide confusion. Surface tradeoffs."*
- **[ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd)** — *"A skill to stop your coding agent from burying the answer. ADHD-friendly output."* Its rule set (lead with the action, cap lists, no preamble, no "Hope this helps!") is the direct source of this repo's Communication Rules and Response Format sections.
  > *"Action first. Steps numbered. No 'Hope this helps!'"*
- **J. Russell Ramsay and Anthony L. Rostain**, authors of *The Adult ADHD Tool Kit* — the above repo credits its approach as loosely based on this book, adapted for how an LLM should respond rather than how a human should organize their day.

---

## 📄 License

License not yet finalized for this repository — check back or open an issue if you're planning to reuse these specs.

---

**AI Workflow** — Instructions that make AI act first and explain later · 2026
