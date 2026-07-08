# Spec: rule lifecycle (the framework taxing itself)

Status: describes the mechanism as of 2026-07-08 [E: claude/skill ledger
schema + source-notes v5 entry, grade M]. Abstract specification; the live
ledger contents are not included in this repository.

## Premise

Every standing rule, check, and piece of machinery in the framework has a
cost: context tokens on every run, maintenance, false-positive noise, and
the credibility tax of rules nobody follows. A framework that only ever adds
rules converges on being ignored. Anti-bloat is therefore a GOVERNANCE
problem with mechanisms, not a style preference — the owner's formulation:
over-redundancy is itself a failure mode.

## The test: tax or tool

Before any component enters the framework, and periodically afterward, it
must answer: does this pay rent? Rent is paid in observable events — a check
that fires on real defects, a rule whose absence produced a documented
incident, machinery invoked by real runs. A component that cannot name its
rent is a tax.

## The ledger

A machine-readable ledger records, per component:

- **provenance** — why it was added, dated, citing the run or finding that
  motivated it;
- **hit count** — how many times it has actually fired or been used,
  incremented by the trajectory miner as it digests the run corpus;
- **status** — active, ON PROBATION, or retired.

## Lifecycle transitions

- **Promotion.** Candidate rules are mined from the run corpus and emitted as
  a REPORT-ONLY checklist. A candidate becomes a rule only when the owner
  ticks it. The miner never writes rules; automation proposes, the owner
  disposes.
- **Probation.** A component whose rent is doubtful enters ON PROBATION —
  visibly marked, fully functional, and scheduled for judgment by evidence.
  The framework applied this to itself at birth: one v5 component (a
  concurrent-actor drift probe) was placed on probation by the same audit
  that shipped it, because its rent case was the weakest of the batch
  [E: claude/skill ledger provenance fields, grade M].
- **Retirement.** Components with zero recorded hits over a mining window
  appear on the retirement candidates list of every mining report. Removal
  is an owner tick, like promotion. Retirement is a normal outcome, not a
  failure: a rule that never fires either guarded against something that
  stopped happening (success — retire it) or never guarded anything (waste —
  retire it).

## Severity inflation is banned

Upgrading a warning to an error because warnings get ignored is the
rule-system equivalent of shouting. The framework pins designated checks as
permanently warning-level; the record of that decision cites the rationale:
hardening checks that fire on honest behavior teaches agents to hide the
behavior, not to fix it.
