# What a plan meets when it meets reality

## The problem

Plans for autonomous work are written before contact with the environment,
and the environment gets a vote. The question every agent framework must
answer — usually implicitly — is what happens at the moment of contact.

The mainstream answer is a binary. Plan-and-execute frameworks re-enter a
replanner after each step, which decides: finish, or emit a new plan
(LangChain, "Plan-and-Execute Agents", February 2024). The opposite extreme
plans the whole tool chain upfront and never observes at all (ReWOO,
arXiv:2305.18323, May 2023). Between them, adaptive planners distinguish
in-plan refinement from out-of-plan revision (AdaPlanner, arXiv:2305.16653,
NeurIPS 2023) — a two-way split, graded by repair locality. More recent
work grades recovery levels more finely, still by locality of repair
(arXiv:2606.20487, June 2026), or learns when replanning is worth the
compute (arXiv:2509.03581, September 2025). Exception taxonomies exist too,
organized by what broke and where (SHIELDA's 36 exception types across 12
artifacts, arXiv:2508.07935, August 2025).

What these classifications share: they describe the deviation. None of
them, in the material surveyed for this essay, classifies the thing a
governance system actually needs classified — what response the deviation
LICENSES.

## The reasoning

When a step deviates, exactly four responses are available to a governed
agent, and they form the complete set: continue as planned (the deviation
was noise), reach the same acceptance criteria by a different route, hold
the route and push through the resistance, or stop and put a decision in
front of the owner. Cause does not determine response: the same failed
command can license a detour in one contract (any route to green is fine)
and an escalation in another (the route was the point — a security-sensitive
path, say). So a taxonomy keyed to causes, artifacts, or repair locality
cannot be the record of governance; the record has to capture the JUDGMENT,
at the moment it was made.

The four cells also have sharply asymmetric misclassification costs, which
is what makes the classification worth writing down at all. Mislabeling a
detour as on-plan quietly corrupts the postmortem: the plan looks better
than it was. Mislabeling a grind as a detour hides that the plan's
difficulty model was wrong. But mislabeling an escalation as anything else
is the expensive one — an owner decision was owed and never requested,
which is precisely the failure that makes autonomous systems untrustworthy.
The design conclusion: enforcement effort should concentrate on the
escalate boundary and almost nowhere else.

## The mechanism

In governance engineering, every checkpoint may carry a cell: on-plan
(按计划), detour (绕行), grind (硬啃), or escalate (上报) — defined and
in operation no later than 2026-07-08 [E: claude/skill checkpoint-format
document and rules ledger, grade M; the taxonomy and its Chinese terms are
the owner's design]. Two enforcement decisions follow the cost asymmetry:

- Escalate REQUIRES a note stating the question the owner must answer,
  rejected mechanically at write time otherwise. An escalation without a
  stated question is a status update wearing an alarm; forcing the note
  also bounds the cheap failure mode (over-escalation), because writing the
  question forces discovering whether there is one.
- Everything else is OPTIONAL. A mandatory-classification rule was
  considered and rejected: forced filing breeds rubber-stamped "on-plan"
  entries and destroys the signal. The cells earn their keep in aggregate —
  a trajectory miner digests cell distributions across the run corpus to
  find where plans systematically meet resistance — not as per-checkpoint
  paperwork [E: claude/skill source-notes, v5 entry, grade M].

"Grind" deserves a note, because the surveyed public material does not name
it as a positive category — its nearest public relative is the negative
framing of "loop drift" to be detected and capped. But sustained legitimate
effort on a hard step is a real and common trajectory shape, and a
governance record that cannot distinguish it from unproductive looping will
either interrupt honest work or wave through stuck work. The cell's
definition carries its own discriminator: a grind terminates with the
planned validation passing; a loop does not terminate.

## What real runs showed

The taxonomy generated live data on the day it shipped: the v5
self-improvement run used all four cells with real referents [E: claude/
runs/harness-v5-self-improvement, checkpoint records, grade M] — on-plan
for milestones landing as planned; a DETOUR when an adversarial-critic veto
forced a changed fix path while the acceptance criteria held; a GRIND when
a second veto was answered by holding the path and fixing through
successive rounds; and an ESCALATE whose note put a genuine gate
disagreement in front of the owner — a run whose state remains parked on
that owner decision rather than smoothed over. A subsequent run the same
evening classified all seven of its checkpoints on-plan [E: claude/runs/
codex-harness-v4-port-20260708 checkpoint records, grade M], which is its
own data point: when the plan holds, the honest distribution is boring.
The aggregate analysis — whether voluntary filing rates are high enough to
sustain the mining signal — is deliberately deferred until the corpus is
large enough to answer it; the framework's own rule lifecycle will judge
the taxonomy by that evidence.

## Relation to public work

Scope qualifier: the survey behind this essay was run on 2026-07-08 and
consists of the five queries listed in the survey record; absence claims
are relative to that material only. Within it, deviation handling is
binary (replan-or-finish), two-way by repair locality, graded by repair
hierarchy, or taxonomized by failure artifact; escalation-to-human appears
as scattered heuristics (retry counts, confidence thresholds) rather than
as a first-class cell in a deviation taxonomy. A classification of live
deviations by licensed response — with asymmetric enforcement concentrated
on the escalation boundary — was not found in the surveyed public material.

---

Surveyed queries (run 2026-07-08 [E: survey record, governance-disclosure
run artifacts, grade M]): LLM agent replanning survey adaptive plan repair;
plan-and-execute agents LangGraph ReWOO Plan-and-Solve replan step;
taxonomy of plan deviations exception handling agent workflow escalation to
human criteria; LLM agent failure taxonomy where do agents fail multi-agent
systems; when should an agent abandon its plan retry versus replan versus
ask human LLM.
