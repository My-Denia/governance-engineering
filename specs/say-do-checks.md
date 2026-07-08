# Spec: say-do reconciliation (checks c1-c6)

Status: describes the mechanism as of 2026-07-08 [E: claude/skill
checkpoint-format document + validator behavior description, grade M].
Abstract specification; no implementation is included in this repository.

## Premise

A run's state file SAYS things; its artifacts SHOW things. The validator
cross-checks the two. The checks target divergence classes actually observed
in the archived corpus — the single most pervasive defect was execution logs
abandoned mid-run while state advanced (in one archived case, a log asserting
no deletions beside a state recording tens of gigabytes freed) [E: claude/
skill source-notes v4 archaeology entry, grade M].

## The six checks

- **c1 — checkpoint monotonicity.** Checkpoint timestamps must be
  non-decreasing. Out-of-order stamps indicate hand-edited or backfilled
  history.
- **c2 — terminal coherence.** A terminal status (completed / blocked /
  needs-owner-decision) must match the last checkpoint's status. A run that
  says "completed" whose last checkpoint says "executing" is claiming an
  ending its own record does not contain.
- **c3 — silent advance.** State updated more than a threshold (6 h) after
  the last execution-log heading: work happened that the log never saw.
- **c4 — frozen handoff.** A terminal run whose handoff still contains the
  init template's placeholders: the run ended but nobody wrote the handoff.
- **c5 — unrecorded stance.** The log claims a gate outcome ("plan audit:
  pass") that state does not hold.
- **c6 — unrecorded dispatch.** Subagent-completion lines appear in the log
  (written by a lifecycle hook, not by the agent) with no corresponding
  result recorded in state: a dispatch happened that bookkeeping missed.

## Severity policy (deliberate, load-bearing)

c1 and c2 are ERRORS at the current schema version and warnings for older
runs — historical archives keep the compliance status they were written
under; retroactive hardening punishes exactly the runs honest enough to
leave evidence. c3-c6 are PERMANENTLY warnings: promoting them was
considered and rejected as severity inflation, itself a documented failure
mode of rule systems. A warning that fires on honest runs teaches agents to
stop leaving evidence.

## Feeding the checks

c6 depends on an independent witness: a platform lifecycle hook appends one
line per subagent completion to the run's execution log. The agent cannot
omit what it never writes. The hook is append-only, never touches state,
fails open, and acts only on runs carrying the harness's ownership marker.
