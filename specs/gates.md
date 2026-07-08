# Spec: gates

Status: describes the mechanism as of 2026-07-08 [E: claude/skill SKILL
document + hook behavior descriptions, grade M]. Abstract specification; no
implementation is included in this repository.

## Two blocking gates

1. **Plan gate.** Before any mutation outside the run folder: the plan is
   audited by an agent with an ISOLATED context — it receives the goal
   contract, the plan, non-goals, and raw evidence references; never the
   planner's reasoning or expected findings. Decision enum: pass,
   needs-replan, blocked, needs-owner-decision. Execution cannot begin
   until pass.
2. **Execution gate.** Before any completion claim: an execution auditor
   (isolated context, read-only plus the ability to RE-RUN validation
   commands itself) receives the contract, approved plan, diff, and raw
   evidence. Decision enum adds needs-fix. Completed status is invalid
   without a recorded pass.

Auditor verdicts are recorded at the moment they return, in the run state,
with an evidence reference. A missing, failed, or pending required auditor
means blocked or needs-owner-decision — never completed. Waiting N rounds
and skipping a required auditor is prohibited.

## Runtime enforcement

The gates are not merely instructions to the model. Two hooks make them
mechanical:

- A **pre-mutation hook** denies file edits outside the run folder while the
  owning run is pre-plan-gate (or has unresolved risk). Writes to the run
  folder and backup areas are always allowed so the orchestrator can operate
  the gate itself.
- A **stop hook** intercepts the session's attempt to end: if the run claims
  completion but its state fails validation (or state says completed while
  artifacts disagree), the turn is blocked with the validator's reasons.

Both hooks are FAIL-OPEN (any error, missing data, or absent run allows the
action), carry a kill switch, respect the ownership marker, and observe a
freshness window so stale runs cannot gate new work. They are quality gates,
not a security boundary: they can fail silently, do not bind external
processes, and are documented as such.

## Escalation is bounded

Gate loops terminate: after two consecutive needs-replan rounds, a third
failure escalates to needs-owner-decision with the disagreement summarized.
Unbounded plan-audit churn was observed in real runs and is designed out.

## A pass is not permission

An audit pass is a QUALITY judgment. Owner-only boundaries — push, publish,
credentials, payment, destructive or irreversible actions — pause the run
even when every gate is green. The gate system and the permission system are
deliberately separate axes.
