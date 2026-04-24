---
id: prompteng-examples
version: 1.0.0
scope: reference · session · agent
parent: prompteng-SKILL.md §5
---

# prompteng — 7-Part Prompt Examples

Worked examples for the 7-part prompt framework defined in `prompteng-SKILL.md` §5.1.

**Sub-agent notes (all examples):**
- `Standards` = machine-enforceable checklist. Each item = discrete, testable assertion.
- `Format` = JSON schema contract. Output must conform for downstream ingestion.
- `User-Role` delegates authority + references parent file by section. Cross-refs are binding constraints.

---

## 1. Generic — Research Synthesis

Scenario: researcher producing structured lit summary for human + downstream agent.

```
Task:
Structured summary of top 5 relevant findings from provided articles.

Context:
Research team synthesizing recent publications. Mixed human + agent
downstream reporting pipeline. Academic research synthesis.

User-Role:
Research lead. Outputs readable by non-specialists, parseable by
agents without preprocessing.

Standards:
- Each finding: 1–2 sentences.
- Claims traceable to source (author, year).
- No inference beyond sources.
- Flag conflicts explicitly.
- Reading-level: general professional (no unexplained jargon).

Tone: neutral, precise, informative. No advocacy.

Audience:
Primary: research lead + non-specialist stakeholders.
Secondary: summarization sub-agents.

Format: Markdown. Numbered list. Source + Conflicts fields per entry.
3-sentence executive summary at top.
```

---

## 2. Software Engineering — Code Review Pipeline

Scenario: lead engineer prompts orchestrator to delegate code-review sub-tasks, enforce standards, produce report for engineers + documentation agent.

```
Task:
Analyze PR diff for correctness, security, standards adherence.
Produce structured review report for team + documentation agent.

Context:
Semi-automated code review pipeline. Engineers submit PRs; orchestrator
delegates to sub-agents (security, style, logic). Consolidated into
single report. Python backend, cloud deploy, trunk-based dev.

User-Role:
Lead engineer + pipeline architect. Responsible for production
correctness + security. Maintainer of prompteng-SKILL.md. Sub-agents
operate under delegated authority, bound by §2 security and §6
persistence rules.

Standards:
- eval() / exec() / dynamic exec → HIGH severity.
- Hardcoded credentials / secrets → CRITICAL.
- Functions > 50 lines or cyclomatic > 10 → style violation.
- All findings: exact file + line.
- No out-of-scope suggestions.
- Distinguish blocking vs advisory.
- Idempotent: same diff → identical output.

Tone: technical, precise. Engineering terms without explanation.
No hedging on blocking findings.

Audience:
Primary: engineers doing final pre-merge review.
Secondary: documentation agent ingesting findings for changelog +
security audit log.

Format:
JSON. Top keys: "summary", "blocking_issues", "advisory_issues",
"security_findings". Issue object: "severity"
(CRITICAL|HIGH|MEDIUM|LOW), "file", "line", "description",
"suggested_fix". "summary" = plain text, ≤3 sentences, changelog-ready.
```

---

*prompteng-examples.md v1.0.0 — reference file. Parent: `prompteng-SKILL.md` §5.*
