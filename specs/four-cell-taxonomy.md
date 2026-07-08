# Spec: the four-cell checkpoint taxonomy

Status: describes the mechanism as of 2026-07-08 [E: claude/skill
checkpoint-format document, grade M]. The taxonomy is the owner's design;
the Chinese terms are original to it. Abstract specification.

## Definition

Every checkpoint MAY carry a `cell` classifying what the step met when it
met reality:

- **on-plan (按计划)** — the step went as planned. The plan survived
  contact.
- **detour (绕行)** — the same acceptance criteria were reached by a
  DIFFERENT PATH than planned. The goal held; the route didn't.
- **grind (硬啃)** — the SAME PATH was held through unexpected resistance:
  legitimate sustained effort on a hard step, distinguished from unproductive
  looping by the fact that it terminates with the planned validation passing.
- **escalate (上报)** — the step needs the owner. REQUIRES a note stating
  what decision is needed and why; an escalation without a stated question
  is a status update wearing an alarm.

## The classification is about the licensed response

The public taxonomies surveyed for this package classify deviations by what
broke or by repair locality (survey and citations in
essays/02-when-plans-meet-reality.md). This taxonomy classifies by WHAT
RESPONSE THE DEVIATION LICENSES:
continue, adapt the route, push through, or stop and ask. Two deviations
with identical causes can license different responses depending on the
contract; the cell records the judgment actually made, at the moment it was
made.

## Misclassification costs are asymmetric

- Calling a detour "on-plan" hides route changes from the plan's postmortem.
- Calling a grind a "detour" hides that the plan's difficulty model was
  wrong.
- Calling an escalate anything else is the expensive one: an owner decision
  was owed and not requested. This is why escalate alone has a mandatory
  note, enforced mechanically (a checkpoint claiming escalate without a note
  is rejected at write time).
- The cheap failure — over-filing escalate — is bounded by the note
  requirement: writing the question forces discovering whether there is one.

## Optionality is deliberate

Cells are OPTIONAL at routine checkpoints. A mandatory-classification rule
was considered and rejected: forced filing at every checkpoint breeds
rubber-stamping ("on-plan, on-plan, on-plan") and destroys the signal. The
taxonomy earns its keep in trajectory mining — aggregate cell distributions
across many runs reveal where plans systematically meet resistance — not as
per-checkpoint bureaucracy. Enforcement is intentionally minimal in v1 of
the taxonomy: only escalate-requires-note is mechanical [E: claude/skill
source-notes v5 entry, grade M].
