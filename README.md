# prompteng

Prompt engineering configuration skill for AI agents and orchestrators.

> `prompteng` is a deliberate misspelling of "prompting", alluding to prompt engineering.

## Introduction

Session init, security rules, 7-part prompt framework, persistence rules.

Core skill in a family of 4 interconnected standalone skills. Load first; loads peers on demand.

## Set of files

| File | Purpose |
|---|---|
| `SKILL.md` | Router — load order, peer references |
| `prompteng-SKILL.md` | Content — rules, framework, checklists |
| `prompteng.skill` | Packaged archive for upload to SKILL directory |
| `README.md` | Explanatory instructions and overview for this software package |

## Install

- **claude.ai web platform:** upload `prompteng.skill` via skill settings (recommended). Or add `prompteng-SKILL.md` contents to Personal Preferences via `Settings > General`.

- **Claude Code desktop app:** copy contents of this folder into `~/.claude/skills/prompteng/`.

- **Other platforms:** adapt this set of files to your `harness+model`. Star or Fork the git repo if you like. 

## Quickstart

**Step 1 — Upload.** In Claude.ai → Project Knowledge → upload `prompteng-SKILL.md`.

**Step 2 — Init session.** First message:
```
Initialize session as per claude.md
```
Agent loads skill, outputs UTC timestamp, proposes chat title, initialises session file registry.

**Step 3 — Verify.** Confirm `prompteng-SKILL.md` appears in registry table with MD5 + token cost. If missing → re-upload + retry.

> **Claude Code:** place `prompteng-SKILL.md` in `.claude/` or project root, reference in `CLAUDE.md`. Same init message.

## When It Triggers

- Unless loaded explicitly, it will not trigger as required or will under-trigger. 
- If the `claude.md` companion file is installed, this skill will be loaded at beginning of every new session.  

## Peer Skills

Load on demand when task requires:

- **[captureng](https://github.com/ecological-codes/captureng)** — session-knowledge capture, CHECKPOINT mode
- **[packageng](https://github.com/ecological-codes/packageng)** — `.skill` file validation + packaging
- **[safe-skill-creator](https://github.com/ecological-codes/safe-skill-creator)** — skill design + iteration

## Companion Files

Available in - **[ecological-codes/user-prefs](https://github.com/ecological-codes/user-prefs)**

- `claude.md` — system-wide self-instruction loaded via Personal Preferences. Defines file registry, re-read protocol, memory precedence (4-tier). Paste into `Settings > General > Personal Preferences` for every-session application.

- `trusted-hosts.md` — project-wide allow-list for egress into internet via system tools like `bash`.

## Style Convention

Directives use the following section headers with numbered lists, shared across all 4 peer skills: 

- **[RULES]** — enforceable constraints applied at runtime.
- **[ACTIONS]** — autonomous steps agent executes in normal workflow.
- **[HUMAN ACTIONS]** — UI actions; agent skips, cannot delegate.

## License

See [LICENSE](./LICENSE).

---
README.md v2.1.0 - Human Approved
