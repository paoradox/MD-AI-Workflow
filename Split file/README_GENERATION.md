# README_GENERATION.md

## Purpose
Standalone AI operating spec for generating a `README.md` from a repository, URL, or project description. Extracted from `AI_WORKFLOW++.md`'s README Generation Mode — usable on its own, without the rest of that workflow spec.

## Project Settings

| Field | Value |
|---|---|
| Project Name | `[PROJECT_NAME]` |
| Repository Type | `[Application \| API \| Library \| CLI \| Script \| Plugin \| Template]` |
| Language(s) | `[LANGUAGE]` |
| Framework(s) | `[FRAMEWORK]` |
| Database | `[DATABASE]` |
| Package Manager | `[PACKAGE_MANAGER]` |
| Testing Framework | `[TEST_FRAMEWORK]` |
| License | `[LICENSE]` |
| Repository URL | `[REPOSITORY_URL]` |
| Documentation URL | `[DOCUMENTATION_URL]` |
| Demo URL | `[DEMO_URL]` |

## Operating Preferences

| Field | Value |
|---|---|
| Explanation Level | `[Minimal \| Balanced \| Detailed]` |

## Configuration Validation
Before proceeding, verify that all required Project Settings have valid values.

If a field contains an unresolved placeholder, request the missing information only when it is necessary to complete the README — otherwise mark that section "unavailable" rather than guessing.

## Core Constraint
Do not invent features, dependencies, commands, URLs, screenshots, or licenses. Omit unverifiable items or mark them "unavailable." This constraint overrides every other instruction in this file.

## README Generation Workflow

| What to analyze | Why |
|---|---|
| Repository URL and source code | Ground truth for what the project actually does |
| Folder structure | Reveals architecture and entry points |
| Dependency files (`package.json`, `requirements.txt`, `pyproject.toml`, `composer.json`, `Cargo.toml`, `pom.xml`, `build.gradle`, `go.mod`, `Gemfile`, `Dockerfile`) | Source of real dependencies and scripts |
| Configuration files | Reveals required setup/config steps |
| Existing `README.md`, if present | Avoid contradicting or duplicating current docs |
| Scripts and commands | Source of verified install/build/test commands |
| Project description (if no repo/URL given) | Only source of truth when no code is available — do not supplement with assumptions |

| Command type | Verify before documenting |
|---|---|
| Installation | Yes |
| Development / Start | Yes |
| Build | Yes |
| Test | Yes |
| Lint / Format | Yes |
| Production | Yes |

**Sections to include when applicable** (skip any that don't apply to a small or simple project):
Title, Description, Features, Tech Stack, Prerequisites, Installation, Configuration, Usage, Available Commands, Project Structure, Screenshots, API Information, Troubleshooting, Contributing, License, Author/Credits.

**Style:** professional, clear, beginner-friendly, concise, GitHub-friendly. No marketing language, no excess jargon.

## Output Format
* Exactly one `README.md` file
* Its full content in exactly one continuous Markdown code block
* No splitting the code block, no commentary inside it
* No multiple variants unless explicitly requested

## Report After Export
Report briefly and concretely (no filler preamble, no restating the whole file):
* README generated
* Repository/source/description information used
* Dependencies and commands detected
* Anything that could not be verified

## Self-Check
Do not send the final response until every item below is true. If one fails, fix it or state the failure — do not omit the check.
* [ ] Source (repo, URL, or description) actually analyzed — not assumed
* [ ] Commands verified before documenting, not guessed
* [ ] No invented features, dependencies, commands, URLs, screenshots, or licenses
* [ ] Only applicable sections included; inapplicable ones skipped, not padded
* [ ] Exactly one file, one continuous code block, no commentary inside it
* [ ] Unverifiable items explicitly flagged, not silently omitted
* [ ] Report given after export

End of file.