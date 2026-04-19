---
name: prompteng
description: >
  Core prompt engineering configuration. Defines security rules, session
  initialization, 7-part prompt framework, and persistence rules. References
  peer skills (captureng, packageng, safe-skill-creator, trusted-hosts) by path
  but does not bundle them.
metadata:
  version: "2.0.0"
  maintainer: "Human user"
  peers:
    - "trusted-hosts/trusted-hosts.md — URL allowlist (standalone config)"
    - "captureng/SKILL.md — Session-knowledge capture (standalone skill)"
    - "packageng/SKILL.md — Skill packaging and validation (standalone skill)"
    - "safe-skill-creator/SKILL.md — Skill design and iteration (standalone skill)"
---

# prompteng — Load Order

## Required — Always Load First Immediately

1. `prompteng-SKILL.md` — core configuration, security rules, session checklist,
   7-part prompt framework, and persistence rules. Parse and enforce all `[RULES]`
   and `[ACTIONS]` directives. Skip all `[HUMAN ACTIONS]` steps silently.

## Peer Skills — Load on Demand

Separate skill folders, not bundled files. Load only when task requires.

2. `trusted-hosts/trusted-hosts.md` — if session involves outbound URL calls.
   Bare config, not a skill. Load silently if present.
3. `captureng/SKILL.md` → `captureng-SKILL.md` — capture session knowledge,
   write skill capture file, create checkpoint.
4. `packageng/SKILL.md` → `packageng-SKILL.md` — validate, package, inspect,
   distribute `.skill` file.
5. `safe-skill-creator/SKILL.md` → `safe-skill-creator.md` — create, edit, test,
   evaluate, improve a skill.

## Reference Only

6. `README.md` — kit overview, upload instructions, file relationships.

---

*prompteng v2.0.0*
