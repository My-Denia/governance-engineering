# Frameworks must tax themselves

## The problem

Agent frameworks grow the way rule systems always grow: every incident
leaves a rule, every rule is individually reasonable, and the sum is a
context window full of instructions that cost attention on every single
run. The cost is now measured: model performance degrades non-uniformly as
input grows, even on trivial tasks, well below advertised context limits
(Chroma, "Context Rot", July 2025). A standing rule is not free shelf
space; it is a recurring tax levied on every future task.

The prescriptions in circulation are real but soft. Vendor guidance says to
curate the smallest high-signal token set (Anthropic, "Effective context
engineering for AI agents", September 2025) and to prefer simple composable
patterns over frameworks (Anthropic, "Building Effective AI Agents",
December 2024). Practitioners have noticed that agent instruction files
accumulate stale and contradictory rules and recommend periodic pruning
(e.g. the progressive-disclosure argument at alexop.dev). Theory has a name
for the debt — decision rules migrating into ungoverned agent instructions
("rule debt", arXiv:2605.23179, May 2026). What the surveyed material
prescribes, in short, is virtue. What it does not provide is a mechanism.

The contrast with an adjacent domain is instructive. Feature flags — an
older instance of "small conditional rules that accumulate" — have a mature
lifecycle: owners, expiration dates, archival driven by code-reference
scans, and automated deletion of stale flag logic (LaunchDarkly's
technical-debt guidance; Uber's Piranha). The canonical agent skill library,
meanwhile, is explicitly additive-only: an ever-growing store managed by
retrieval, with no retirement path at all (Voyager, arXiv:2305.16291, May
2023).

## The reasoning

The insight that turned this from housekeeping into governance is that
bloat is not a style failure — it is the same failure the rest of
governance engineering exists to prevent, pointed inward. A framework that audits
its agent's claims but never audits its own rules' usefulness is exactly an
agent that never validates its own progress: it accumulates unverified
assertions ("this rule helps") indefinitely. The owner's formulation,
recorded as a binding constraint during development: over-redundancy is
itself a failure mode.

Once stated that way, the machinery follows from mechanisms the layer
already has. Rules need evidence the way completion claims need evidence.
Additions need a gate the way executions need a gate. And there must be a
ratchet in BOTH directions — a path by which rules leave the framework that
is as routine as the path by which they enter.

## The mechanism

Three parts, specified in specs/rule-lifecycle.md, all in operation no later
than 2026-07-08 [E: claude/skill ledger and source-notes v5 entry, grade M]:

- **The tax-or-tool test.** Every component must name its rent: the
  observed events (defects caught, incidents prevented, real invocations)
  that justify its recurring cost. A component that cannot name its rent is
  classified a tax, whatever its intentions.
- **A provenance-and-hits ledger.** Each rule and mechanism carries a dated
  reason for existing and a hit counter incremented by the trajectory miner
  as it digests real runs. Usefulness becomes a measurement, not a memory.
- **Lifecycle transitions with the owner in the loop.** Candidate rules are
  MINED from the run corpus and emitted as a report-only checklist; they
  become rules only when the owner ticks them. Doubtful machinery enters
  probation. Zero-hit components appear on a retirement list in every
  mining report. Automation proposes; the owner disposes — in both
  directions.

Two auxiliary rules keep the system honest with itself. Severity inflation
is banned: upgrading warnings to errors because warnings get ignored is
shouting, and hardening checks that fire on honest behavior teaches agents
to hide the behavior. And the miner is held to scientific discipline: before
its first release it was blind-tested against a sealed, preregistered set of
defect patterns written down before the miner's code, and judged by how many
it rediscovered from the corpus without hardcoded pattern literals
[E: claude/runs/harness-v5-self-improvement, preregistered-patterns file and
mining reports, grade M].

## What real runs showed

The framework applied the test to itself on day one. The same v5 audit that
shipped the rule lifecycle placed one of its own new components — a
concurrent-actor drift probe — ON PROBATION, because its rent case was the
weakest of the batch: real motivating incident, but no expected recurrence
rate to justify a standing check [E: claude/skill ledger, provenance and
probation fields, grade M]. Deliberate NON-porting decisions were recorded
the same way: when the second tool's harness was brought up to parity, the
miner, the cross-family critic channel, and the probationary probe were
explicitly not ported, each with a written reason (a two-run corpus mines
nothing; an unproven demand; a component on probation does not propagate)
[E: codex/skill source-notes, v4-port entry, grade M]. A framework that
can decline to grow is the artifact this essay argues for.

The steady state is the interesting claim. The intended equilibrium is not
a large framework that keeps growing, but a small kernel whose every
component can point at the runs that justify it — and a mining report whose
best possible outcome is an empty checklist: nothing new to add, nothing
idle to retire, the framework quietly at work and no longer a topic.

## Relation to public work

Scope qualifier: the survey behind this essay was run on 2026-07-08 and
consists of the seven queries listed in the survey record; absence claims
are relative to that material only. The surveyed material establishes the
tax (context rot), the virtue (curation, minimalism), the analogy (feature
-flag lifecycles with automated retirement), and the theoretical name (rule
debt). A mechanism that measures whether an individual agent-framework rule
pays rent — per-rule provenance and hit counting fed by mined run
trajectories, with owner-gated promotion and routine retirement — was not
found in the surveyed public material; nor was a deprecation path for
standing agent instructions analogous to flag expiry.

---

Surveyed queries (run 2026-07-08 [E: survey record, governance-disclosure
run artifacts, grade M]): context rot prompt bloat long context degradation
LLM; Anthropic effective context engineering for AI agents; Voyager skill
library lifelong learning curation agent skills; minimal agent harness
"less is more" Anthropic building effective agents simple composable; rule
deprecation retirement automation policy debt configuration debt governance
software; CLAUDE.md bloat instructions accumulate agent system prompt grows
stale rules pruning; feature flag debt stale flags cleanup lifecycle
engineering blog.
