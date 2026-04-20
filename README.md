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

## Install

- Claude.ai: upload `prompteng.skill` via skill settings (recommended). Or add `prompteng-SKILL.md` contents to Personal Preferences via `Settings > General`.

- Claude Code: copy contents of this folder into `~/.claude/skills/prompteng/`.

- Other platforms: adapt this set of files to your `harness+model`. Star or Fork the git repo if you like. 

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

- `[RULES]` 
- `[ACTIONS]` 
- `[HUMAN ACTIONS]`

## Version

v2.0.0 — modular peer references, no bundled sub-skills.

## License

See [LICENSE](./LICENSE).

---
README.md v2.0.0 - Human Approved
