# Naming dossier

The layer needs a name that states the engineered object, following the
lineage prompt engineering -> context engineering -> harness engineering ->
loop engineering -> (this layer). All drafts in this package use the
placeholder "the governance layer"; the final choice is owner-only.

Collision checks were run by live web search on 2026-07-08 [E: naming survey
recorded in the run governance-disclosure-20260708; queries listed per
candidate]. For each candidate: two or more searches (exact phrase, and with
LLM / AI-agents qualifiers).

## Candidates

### 1. governance engineering
- Queries: `"governance engineering"`; `"governance engineering" LLM AI agents`
- Found: an established movement in regulated software delivery (Kosli, IT
  Revolution, The New Stack; dedicated sites goveng.io,
  governanceengineering.io) — automated compliance controls and evidence
  gathering. Heavy "AI governance" gravity toward enterprise policy.
- Collision: strong-adjacent-field. Notably, that field's core pitch —
  proving you did what you promised — is conceptually close to say-do
  reconciliation.
- Fit: excellent for gates, say-do, rule lifecycle; risks reading as
  org-level policy rather than runtime mechanics.
- Elevator: building the machine-enforced control plane that gates an
  agent's plan, audits its execution, and reconciles what it says against
  what it did.

### 2. gate engineering
- Queries: `"gate engineering"`; `"gate engineering" AI agents LLM`
- Found: unrelated companies (GATE Energy; Engineers Gate) and semiconductor
  gate engineering. The concept space — quality gates for agents — is
  occupied under other names (agent-gates repos, gatekeeper protocols,
  harness-engineering guides describing phase-boundary gates).
- Collision: weak-unrelated for the compound; concept space active.
- Fit: nails the two audit gates; too narrow for the taxonomy, evidence
  grading, and rule lifecycle. Confusable with "AI gateway" products.
- Elevator: designing the mandatory checkpoints an autonomous agent must
  pass — plan audit before execution, execution audit before completion.

### 3. verifier engineering / verification engineering
- Queries: `"verifier engineering"`; `"verification engineering" LLM AI agents`
- Found: DIRECT SAME-FIELD COLLISION — "verifier engineering" is an
  established term in the LLM literature meaning post-training
  feedback-signal design
  (arXiv 2411.11504 and successors); "verification engineering" is a
  long-standing hardware/EDA job family.
- Collision: strong-same-field, different meaning. Disqualifying: readers
  would assume the post-training sense.
- Fit: (moot).

### 4. oversight engineering
- Queries: `"oversight engineering"`; `"oversight engineering" AI agents LLM`
- Found: the bare phrase is a construction-industry role; the compound is
  essentially unclaimed as a discipline name. "Oversight" itself is heavily
  and CONSISTENTLY invested by the alignment community (scalable oversight,
  agentic oversight, regulatory human-oversight requirements) with the
  intended meaning.
- Collision: weak for the compound; the semantic gravity is aligned with,
  not against, the intended meaning.
- Fit: the only candidate that plausibly covers all five mechanisms (gates,
  say-do, taxonomy incl. escalate, evidence grading, rule lifecycle as
  engineering-the-overseer). Mild human-in-the-loop connotation, neutralized
  by the "machine-enforced" framing.
- Elevator: building machine-enforced supervision for autonomous agents —
  audit gates, claim-vs-artifact reconciliation, and graded evidence that
  decide whether the agent proceeds, detours, or escalates.

### 5. trajectory engineering
- Queries: `"trajectory engineering"`; `"trajectory engineering" LLM agents`
- Found: aerospace trajectory design; and "trajectory" already means the
  agent's action sequence inside the agent literature (trajectory-aware
  benchmarks, trajectory SFT).
- Collision: weak for the compound; strong same-field load on the word with
  a different (training/steering) sense.
- Fit: maps the deviation taxonomy beautifully; misses gates, evidence,
  lifecycle. Reads as steering, not governing.
- Elevator: constraining and correcting the path an agent actually takes —
  classifying every deviation as proceed, detour, grind, or escalate.

### 6. evidence engineering
- Queries: `"evidence engineering"`; `"evidence engineering" LLM AI agents`
- Found: scattered unrelated uses (evidence-based software engineering,
  biomedical evidence pipelines); in agents, the compound is unused while
  the adjacent idea (execution provenance as first-class infrastructure) is
  rising in the survey literature.
- Collision: none-to-weak — the cleanest profile of all eight.
- Fit: directly names the most distinctive mechanism (evidence-graded state;
  no artifact, no progress). Names the substrate of governance rather than
  the governing act; taxonomy and lifecycle feel bolted on.
- Elevator: making an agent's every claim carry graded, machine-checkable
  evidence — no artifact, no progress.

### 7. discipline engineering
- Queries: `"discipline engineering"`; `"discipline engineering" AI agents LLM`
- Found: mostly grammar accidents of "engineering discipline(s)"; agent
  vendors use "discipline" as a descriptor, not a name.
- Collision: weak but the compound is semantically vacuous.
- Fit: metaphorical only; its one hook (the framework disciplining itself)
  is too cute to carry a layer name.
- Elevator: imposing enforced work discipline on an agent — and on the rules
  that enforce it.

### 8. audit engineering
- Queries: `"audit engineering"`; `"audit engineering" LLM AI agents`
- Found: accounting/internal-audit job families; in AI, "auditing" is active
  as a verb (alignment-auditing agents, auditable-agents workshops) but not
  as this compound.
- Collision: weak-unrelated for the compound; moderate connotation drag
  (quarterly, after-the-fact; and the alignment sense audits the MODEL, not
  the run).
- Fit: the most literal match for the two gates and say-do (an audit is
  claims-vs-records); evidence grading is native audit vocabulary. Undersells
  the in-line, blocking character.
- Elevator: wiring mandatory machine-run audits into an agent's execution
  loop — the plan is audited before work starts, the work before "done" is
  allowed.

## Dark horses surfaced during the scan

- **assurance engineering** — safety-engineering pedigree ("assurance case"
  is an established artifact); covers evidence + gates; moderate collision
  with the growing "AI assurance" testing space. The stronger dark horse.
- **accountability engineering** — strong fit for say-do and traceability;
  long, moralized, drifting toward enterprise-GRC marketing.

## Advisory ranking

1. **oversight engineering** — unclaimed compound, aligned semantic gravity,
   only full-coverage candidate.
2. **audit engineering** — most literal; loses on retrospective connotation.
3. **evidence engineering** — cleanest collisions; names substrate, not act.
4. governance engineering — best conceptual kinship, doubly encumbered.
5. gate engineering; 6. trajectory engineering; 7. verifier engineering
   (disqualified); 8. discipline engineering.

The ranking weighs collision risk and mechanism coverage equally. The owner
holds context the ranking cannot see (the lineage's rhythm, personal voice,
existing informal usage); the decision is theirs alone.
