# prompteng

**v2.0.0** — prompt engineering configuration skill for AI agents and orchestrators.

Skill file that loads at chat start, codifying security rules, session initialization, the 7-Part Prompt Framework, and session-persistence protocols. Readable by both humans and AI sub-agents. Intended for software engineers and the agents they orchestrate.

> `prompteng` is a deliberate misspelling of "prompting," alluding to prompt engineering.

## Contents

| File | Purpose |
|---|---|
| `SKILL.md` | Load-order index. Points to core skill + peer skills. |
| `prompteng-SKILL.md` | Core configuration — security, session init, 7-Part framework, persistence rules. |
| `LICENSE` | MIT. |

## Install

Two deployment targets:

**Claude.ai web / desktop / mobile** — 

**Claude Code / API** — 

## Relationship to `claude.md`

`prompteng` governs prompt construction and session lifecycle. `claude.md` ([ecological-ai/user-prefs](https://github.com/ecological-ai/user-prefs)) governs context-window efficiency and memory precedence. The two are companion skills — `prompteng` §2.5 references `claude.md` §7 as the canonical source for the memory trust model.

## Peer skills (load on demand)

- `trusted-hosts.md` — URL allowlist for outbound API calls.
- `captureng-SKILL.md` — session-knowledge capture; checkpoints.
- `packageng-SKILL.md` — `.skill` file validation and distribution.
- `safe-skill-creator-SKILL.md` — skill design and iteration.

Peers are standalone — not bundled in this repo.

## Directive conventions

Three block types appear throughout `prompteng-SKILL.md`:

- **`[RULES]`** — enforceable by agents at runtime.
- **`[ACTIONS]`** — agent-executed steps.
- **`[HUMAN ACTIONS]`** — require human action in the platform UI; agents skip silently.

Aligned to `claude.md v1.5.2+` style conventions.

## Changelog

**v2.0.0** — directive blocks restyled (`[RULES]` / `[ACTIONS]` / `[HUMAN ACTIONS]`) to match `claude.md` v1.5.2; added References section; metadata expanded with `parent` + `references` rows. Content unchanged from v1.5.0.

## License

MIT. See [`LICENSE`](./LICENSE).
