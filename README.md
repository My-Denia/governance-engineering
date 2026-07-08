# Governance engineering

Harness engineering equips a run; loop engineering drives runs; governance
engineering is what keeps the loops honest: state authority, say/do
reconciliation, and rule lifecycle.

This repository is a disclosure package for governance engineering as a
built system — an execution-governance layer for autonomous LLM agents,
built and used in private between May and July 2026. It documents the design thinking (essays/), the mechanism
specifications (specs/), and a verifiable development chronology
(CHRONOLOGY.md). Implementation code is deliberately withheld
(DISCLOSURE-MAP.md explains the tiering).

## The problem layer

Prompt engineering shaped what a model is asked. Context engineering shaped
what it knows while answering. Harness engineering shaped the machinery an
agent acts through. Loop engineering shaped how long-running work continues
across turns. Above all of these sits an unshaped layer: **what makes an
autonomous run trustworthy** — not whether the agent CAN do the work, but
whether what it claims about the work is true, whether its plan survived
contact with reality, and whether the rules governing it are themselves
governed.

This package documents one worked answer, built as a running system rather
than a proposal:

- **Two blocking audit gates** — a plan is audited by an isolated-context
  auditor before execution; execution is audited before "done" is allowed
  (specs/gates.md). Enforced at runtime by hooks, not by asking nicely.
- **Say-do reconciliation** — six machine checks that diff what the run's
  state CLAIMS against what its artifacts SHOW (specs/say-do-checks.md).
- **A four-cell deviation taxonomy** — every checkpoint can classify what
  the plan met: on-plan, detour, grind, or escalate — classified by the
  response the deviation licenses (specs/four-cell-taxonomy.md).
- **Evidence-graded state** — claims carry their anchor quality (weak /
  medium / strong); completion requires medium or better
  (specs/run-state.md).
- **A self-taxing rule lifecycle** — every rule and mechanism must pay
  rent; promotion needs an owner's tick, doubtful machinery goes on
  probation, dead rules get retired (specs/rule-lifecycle.md).

## Why the chronology is the way it is

The package's value rests entirely on claim credibility, so CHRONOLOGY.md
holds itself to an uncomfortable standard: every date is "existed no later
than", every claim carries a graded citation, each anchor's grade is
stated where it is used (four claims carry externally held S-grade
anchors; everything else is local evidence, and says so), and claims that
only the owner can attest are quarantined in their own section.
NEEDS-OWNER.md lists the evidence that would upgrade the rest.

## Licensing

Prose (essays, chronology, specs, this README): CC BY-SA 4.0 — see
[docs/LICENSE-DOCS.md](docs/LICENSE-DOCS.md). Code and skill files (none
staged at initial publication; implementation is withheld per
[DISCLOSURE-MAP.md](DISCLOSURE-MAP.md)): AGPL-3.0-or-later — see
[LICENSE](LICENSE).

## Status

The name (governance engineering) and licenses are settled owner rulings;
any release of withheld implementation remains a per-item owner decision.
Contributions are not being accepted until after first publication.
