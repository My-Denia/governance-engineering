# Spec: run state

Status: describes the mechanism as of 2026-07-08 [E: claude/skill references,
checkpoint-format document, grade M]. Abstract specification; no
implementation is included in this repository.

## Object

Every governed piece of work runs inside a **run folder** containing exactly
four artifacts:

- `plan.md` — milestones, assumptions, validation matrix, rollback notes.
- `execution-log.md` — append-only log of commands, edits, and results,
  with timestamped headings.
- `handoff.md` — enough for a fresh agent to continue; contains one
  machine-regenerated block (delimited by markers) that mirrors state, plus
  free prose that is never machine-touched.
- `state.json` — the ONLY canonical status. All prose points at it; prose
  never forks from it.

## State fields (schema concept)

- `schema_version` — integer. Validators accept a declared range; a NEWER
  unknown schema degrades to a warning with known-subset validation (never a
  hard failure), because a validator that hard-fails on its successor's
  output punishes upgrades.
- `runner` — ownership marker naming which harness stamped the run. Runtime
  gates act ONLY on runs carrying their own marker; foreign and legacy run
  folders sharing the same trees are never gated. Rationale: mixed-tool
  archives are the observed norm, and schema-shape sniffing cannot
  discriminate ownership.
- `status` — enum over the run lifecycle: planning, plan-reviewing,
  executing, execution-reviewing, replanning, completed, blocked,
  needs-owner-decision. The last three are terminal.
- `plan_gate`, `execution_gate` — gate decisions (see specs/gates.md).
- `risk_level`, `size`, `audit_mode`, `delegation_mode` — triage outputs
  that determine which gates are mandatory.
- `checkpoints[]` — append-only status transitions: timestamp, status,
  summary, optional `cell` (see specs/four-cell-taxonomy.md), optional note.
- `subagent_results[]` — append-only record of every dispatched auditor or
  worker: name, role, required flag, decision, evidence reference. Latest
  entry per role wins; history is never rewritten.
- `acceptance_criteria[]`, `non_goals[]` — the contract.
- `created_at_utc`, `updated_at_utc` — ISO timestamps; every sanctioned
  mutation bumps `updated_at_utc` automatically.

## Mutation contract

State is mutated ONLY through a single sanctioned helper: one command per
change, enum-validated against the validator's own tables (one source of
truth), atomic write (temp file, fsync, rename), automatic timestamp bump.
Whole-file rewrites are prohibited: across the archived corpus they were the
top documented cause of state corruption — stale acceptance criteria,
statuses frozen behind reality, forgotten timestamp bumps [E: claude/skill
source-notes, v4 entry, grade M].

## Evidence grading

Any claim about a run is graded by its anchor: filesystem mtime = weak;
content-internal dates, dated filenames, append-only logs, state timestamps
= medium; externally held records = strong. Completion claims must cite
medium-or-better evidence.
