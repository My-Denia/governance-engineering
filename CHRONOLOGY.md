# Chronology

This file is the attribution record for governance engineering (the name
was chosen by the owner after the collision-check dossier in
[NAMING.md](NAMING.md), which is preserved unchanged as the record of a
deliberate choice). It exists because twice
before, implementation preceded public naming and the attribution was lost
for lack of a public timestamped record. The rules it follows:

1. Every dated claim in the **Verified timeline** is phrased "existed no
   later than DATE" and carries an evidence citation `[E: ...]`.
2. Citations use pseudo-paths into the owner's local archive (`claude/`,
   `codex/`, `runs/p1..p8/`); the mapping to real paths is held privately and
   available to auditors on request. Project trees `p1-p8` are anonymized;
   framework-run names are disclosed.
3. Evidence grades: **W** = filesystem modification time only (weak, never
   load-bearing alone). **M** = content-internal date, dated filename,
   append-only log line, or run-state timestamp. **S** = externally anchored.
4. **Four S-grade anchors exist; everything else is local.** The earliest
   run's deliverable has an institution-held submission timestamp, and two
   platform-held conversation snapshots (with per-message server
   timestamps) anchor the mid-June design record — see the v1 and
   design-record sections. The snapshot records are privately held by
   owner decision; the platform holds their timestamps independently of
   the owner, and they are shown to designated reviewers on request. All other claims rest on local artifacts that
   are mutually consistent but not externally verifiable.
   [NEEDS-OWNER.md](NEEDS-OWNER.md) lists what would upgrade them. This is
   stated plainly rather than papered over, because an overclaimed
   chronology would destroy the package's purpose.
5. Claims that cannot be anchored even at grade M live ONLY in the
   **Owner-attested** section and are never merged into the verified
   timeline.

## Verified timeline (local-evidence grades)

### Pre-history of the mechanisms

- Independent plan-auditor and execution-auditor agent definitions carry
  file times of 2026-05-14 [E: claude/agents/plan-auditor.md,
  execution-auditor.md — file mtimes, grade W — a W-only anchor, so this
  entry is indicative rather than load-bearing; it is corroborated in kind
  (not date) by the dated source-check entry of 2026-05-14 in the skill's
  provenance notes, E: claude/skill/references/source-notes.md, grade M].
  The three-role separation (planner / independent plan audit / independent
  execution audit) predates every later version label.
- A subagent lifecycle log has been appending since 2026-05-29T05:07:41Z
  [E: codex/logs/subagent.jsonl first line, append-only, grade M] — the
  delegation substrate the later gates govern.
- A safety-hook cohort (dangerous-command block, credential-write block,
  secret scan) carries file times of 2026-05-29 [E: claude/hooks/ and
  codex/hooks/ file mtimes, grade W — W-only, indicative rather than
  load-bearing; consistent with the M-grade subagent-log start the same day].

### v1 — the harness in use

- The EARLIEST verifiable run — disclosed by the owner after the initial
  sweep, in a ninth tree — is an academic-coursework run (institution,
  module, and platform names withheld) whose state file, while marked
  completed, still lists the owner's upload before the submission deadline
  of 2026-05-26T12:00+01:00 as a REMAINING obligation: the run therefore
  finished before that deadline. The harness was in use no later than
  2026-05-26 [E: runs/p8/earliest-run state.json, content logic on the
  deadline field, grade M; the files carry mtimes of 2026-05-19, grade W,
  consistent but not load-bearing].
- The anchor tightens and hardens via the institution's submission portal:
  the assignment was SUBMITTED at 02:42 on 2026-05-24 (portal-displayed
  local time), with feedback returned 2026-06-24 — timestamps held by the
  institution's servers, outside the owner's control [E: submission-portal
  record, owner-held screenshot dated 2026-07-08, archive pending — grade S
  for the SUBMISSION EVENT]. The link from that submission to this run is
  the local state file, which names the submitted deliverable, its final
  word count, and the same deadline [E: runs/p8/earliest-run state.json
  deliverables and word_count_final fields, grade M]. Chained claim,
  grades stated separately: the governed run's deliverable was submitted
  2026-05-24 (S), and the run that produced it — with the full gate loop —
  is the one recorded locally (M). The harness was therefore in use no
  later than 2026-05-24.
- The same state file shows the FULL gate loop already operating at that
  date: independent-subagents audit mode; a plan audit that returned
  needs-replan in round 1 and pass in round 2; an execution audit that
  returned needs-fix in round 1 (with named findings, including a
  wrong-author citation) and pass in round 2; and explicit owner-only
  boundaries — the state lists the submission upload as an action the
  harness must not perform, plus a did-not list (paraphrased; the literal
  strings name the withheld platform)
  [E: runs/p8/earliest-run state.json audit_trail and
  owner_only_actions_remaining fields, grade M]. The two-gate,
  two-round-loop, owner-boundary design is not a later addition — it is
  present in the earliest run found.
- Within the ORIGINAL eight-tree sweep, the earliest run is
  2026-06-02T00:33:23Z [E: runs/p1 earliest run, execution-log heading
  corroborated by the slug-embedded timestamp, grade M].
- The word "harness" for this system appears in a plan file on
  2026-06-02 [E: runs/p1 second run, plan.md, grade M].
- Between 2026-05-26 and 2026-07-08 the archive accumulated 93 run folders
  across 9 project trees (92 found by the systematic sweep of 8 trees; one
  more disclosed by the owner immediately after) [E: corpus sweep recorded
  in the run governance-disclosure-20260708 + post-sweep disclosure,
  per-tree tables in the private inventory, grade M/W mixed]. These runs are
  ordinary engineering and academic work — the harness's operating history,
  not demos.

### The mid-June design record (platform-held conversation snapshots)

Two cloud conversations, retrieved via the platform's snapshot records
(per-message server timestamps). The records are privately held by owner
decision — the owner's remarks in those conversations are not for
publication; the platform retains the authoritative timestamps
independently of the owner, and the records are shown to designated
reviewers on request:

- No later than 2026-06-14: the owner describes, in a contemporaneous
  conversation, the goal skill as the automation carrying all of their
  real work, iteratively hardened through practice including
  pull-request-level deliverables (paraphrased translation; original in
  Chinese), and names the multi-agent collaborative-audit idea. The
  snapshot was SHARED the same evening — 2026-06-14T22:53Z — so its
  contents are platform-frozen from that moment, weeks before this
  disclosure package existed [E: platform snapshot record, private
  archive, grade S for content-as-of-date].
- No later than 2026-06-15T19:15Z: the skill's exact name —
  goal-autopilot-harness — appears verbatim in a pasted invocation inside
  a conversation about long-running autonomous work [E: platform snapshot
  record, message timestamp, grade S].
- On 2026-06-15T18:58Z the owner opens a conversation observing that the
  public term "harness engineering" was being superseded by "loop
  engineering" — establishing these as PUBLIC terms the owner tracked,
  not terms coined in that conversation — and at 19:44Z states,
  contemporaneously, that they built their harness skill when harness
  engineering first appeared publicly and believed their implementation
  to be earlier (paraphrased translation) [E: platform snapshot record,
  message timestamps, grade S for WHEN the statement was made; the
  statement itself remains testimony about earlier events]. The
  conversation continues through 2026-06-18 [E: same record, last-message
  timestamp, grade S].

### Sibling layer

- A sibling skill driving the platform's native workflow/goal continuation
  ("the loop layer" in the owner's naming lineage) was documented and
  doc-verified no later than 2026-06-04 [E: claude/skill-nwa/SKILL.md,
  content line "Last verified against docs: 2026-06-04", grade M].

### v2 line (Codex side): delegation and fan-out

- A pre-v2 baseline labeled "current-codex-mech" existed no later than
  2026-06-14T00:42 [E: codex/backups/old-baks/
  SKILL.md.bak-current-codex-mech-20260614-004247 — dated filename, grade M].
- The v2 delegation redesign (delegation modes, read-only sidecar fan-out,
  model tiers) was cut no later than 2026-07-07T01:08 [E: codex/backups/
  old-baks, eight files labeled -v2-delegation-20260707-010853, grade M].
- Three v2 audit-fix hardening passes followed within 42 minutes, at
  2026-07-07T01:40, 01:45, and 01:50 [E: codex/backups/old-baks, auditfix
  filename labels, grade M] — the audit-gate loop being applied to the
  harness itself.
- The consolidated label "v2.3" for this line appears in the live Codex-side
  skill [E: codex/skill/SKILL.md, version paragraph, grade M].
- A v2.3-line run (state schema 4) completed 2026-07-07T03:02-04:08Z
  [E: runs/p4/goal-autopilot-v2-3-fanout state.json, grade M]; a quota-aware
  schema-5 run followed at 2026-07-07T04:50Z
  [E: runs/p4/goal-autopilot-quota-aware-fanout state.json, grade M].

### v3 — the theory-driven operating-layer redesign

- The v3 redesign, codenamed "agent-operating-layer", was cut at
  2026-07-07T02:10:40 — anchored by TWO independent dated backup filenames,
  one on each tool's side [E: claude/skill/
  SKILL.md.bak-agent-operating-layer-v3-20260707-021040 and codex/backups/
  old-baks same label, grade M]. v3 split a ~25 KB monolithic rule file into
  a minimal kernel plus a skill router [E: claude/skill/references/
  source-notes.md, dated entry 2026-07-07, grade M].
- The Codex-side global kernel titled "v3" went live the same night, no later
  than 2026-07-07 [E: codex/kernel title (the clock time on that file is
  mtime-only, grade W, and is not used) + corroborating run
  codex-global-kernel-v3, runs/p4, state date 2026-07-07, grade M —
  clock-time caveat below].
- The system's first machine-enforced completion gate (a Stop hook
  validating run state before a session may claim completion) first fired at
  2026-07-07T02:28:42Z [E: codex/logs/goal_stop_validate.jsonl first line,
  append-only, grade M]; its "goal-stop-mvp" configuration backup is labeled
  2026-07-07T03:27 [E: codex hooks.json.bak-goal-stop-mvp-20260707-032755,
  dated filename, grade M].
- The Claude-side v3 kernel refactor ran 2026-07-07T02:49-05:12Z
  [E: claude/runs/refactor-...-v3-kernel state.json, grade M].

### v4 — runtime enforcement

- A ground-up audit ("one-sentence-to-result") ran 2026-07-08T16:09-17:09Z
  [E: claude/runs/harness-audit-v4 state.json, grade M; backup manifest
  created 2026-07-08T16:46:59Z, E: claude/backups/
  harness-audit-v4-20260708-1757/manifest.json, grade M]. Its inputs included
  an archaeology pass over the run archive (recorded at the time as 88 runs)
  [E: claude/skill/references/source-notes.md v4 entry, grade M].
- v4 shipped: a sole sanctioned state mutator (whole-file rewrites documented
  as the top corruption cause), runtime plan/completion gates as hooks, and a
  runner-ownership marker so gates act only on runs the harness owns
  [E: claude/skill/references/source-notes.md v4 entry; hook files carry
  internal "verified 2026-07-08" dates, grade M].

### v5 — the self-improvement loop

- The v5 run executed 2026-07-08T17:22-18:13Z [E: claude/runs/
  harness-v5-self-improvement state.json, grade M; backup manifest
  2026-07-08T17:39:51Z, E: claude/backups/harness-v5-20260708/manifest.json,
  grade M].
- v5 shipped, all dated 2026-07-08 [E: claude/skill ledger/rules-ledger.json,
  every entry "added":"2026-07-08"; claude/skill/references/source-notes.md
  v5 entry; both grade M]:
  - say-do reconciliation checks c1-c6 (claimed progress vs artifacts), with
    severity deliberately capped for c3-c6 [E: claude/skill/references/
    checkpoint-format.md, grade M];
  - the four-cell checkpoint taxonomy — on-plan / detour (绕行) / grind
    (硬啃) / escalate — optional at routine checkpoints by design
    [E: claude/skill/references/checkpoint-format.md, grade M];
  - a trajectory miner blind-tested against sealed, preregistered patterns.
    The sealed file's own stamp reads literally "Sealed at: 2026-07-08T18:4x
    UTC" — a stamp belonging to the BST-mislabel erratum class disclosed in
    the known-defects section, so its CLOCK TIME is not usable; the mining
    reports are filename-timestamped 17:47:43Z and 17:47:45Z. The
    seal-before-mine ordering therefore does NOT rest on these clock stamps;
    it is corroborated by filesystem order (sealed file mtime 17:36Z precedes
    the mining reports, grade W) and by the run's own log narrative
    [E: claude/runs/harness-v5-self-improvement/preregistered-patterns.md,
    mining/ report filenames, and execution log — date grade M; intra-day
    ordering grade W, stated as such];
  - a rule-lifecycle ledger with promotion by owner sign-off, probation, and
    retirement — one component (a concurrent-actor probe) entered ON
    PROBATION at birth per the tax-or-tool test [E: claude/skill/ledger/
    rules-ledger.json provenance fields, grade M];
  - a cross-family critic channel; the v5 run itself records six critic
    verdicts [E: claude/runs/harness-v5-self-improvement/
    critic-verdict-1..6.json, grade M].
- The v5 run's final state is needs-owner-decision — the framework's own
  completion gate refused a pass the evidence did not support, and the run
  is parked pending an owner ruling [E: claude/runs/
  harness-v5-self-improvement/state.json status field, grade M]. This is
  disclosed deliberately: the record shows the gates binding their author.

### Cross-side port

- The v4 discipline was ported to the second tool's harness the same evening,
  2026-07-08T18:43-19:15Z [E: claude/runs/codex-harness-v4-port-20260708
  state.json; codex/backups/codex-harness-v4-20260708/manifest.json created
  2026-07-08T18:43:32Z; codex/skill/SKILL.md "v4 (2026-07-08)" line; all
  grade M]. The port's test fixtures appear in the append-only stop-gate log
  through 2026-07-08T19:13:30Z [E: codex/logs/goal_stop_validate.jsonl,
  grade M].

### Publication (the first PUBLIC anchor)

- This package was published at
  https://github.com/My-Denia/governance-engineering on 2026-07-08: first
  push acknowledged 23:31:13Z (the owner captured GitHub's pushedAt as
  23:31:14Z at that moment; that API field moves with every later push
  and is not re-checkable — the STABLE public anchors are the two that
  follow). Release v1.0 published 23:32:13Z (GitHub API publishedAt,
  stable and publicly queryable). Independent third-party snapshots were
  taken by the Internet Archive at 23:33Z:
  https://web.archive.org/web/20260708233319/https://github.com/My-Denia/governance-engineering
  (repository) and
  https://web.archive.org/web/20260708233347/https://github.com/My-Denia/governance-engineering/releases/tag/v1.0
  (release page)
  [E: the release's publishedAt and the two Internet Archive snapshot
  URLs — grade S, PUBLICLY verifiable by anyone, today].
  Every entry in this file up to this point was written before this
  anchor existed and carries the grade it states; every change committed
  after this point in time is itself publicly timestamped by the public
  repository's history.

## Owner-attested (not independently verifiable)

The following claims lack independent anchors. They are the owner's
testimony, recorded as such. (Two items originally in this section were
resolved by the platform snapshots of 2026-07-08 and moved or refined —
noted below for the record.)

1. **Thought origin.** The plan-execute-audit design (gates, auditor
   separation, run folders) was worked out in design conversations before
   the first archived run. The earliest verifiable artifact remains the
   first run itself (owner-attested; would upgrade via needs-owner item 2).
2. **RESOLVED, with correction.** This section previously carried an
   owner-attested claim that a conversation dated 2026-06-18 "named and
   developed loop engineering". The platform record (see the mid-June
   design-record section) shows the conversation STARTED 2026-06-15 and ran
   through 2026-06-18, and that it discussed "loop engineering" as an
   already-public term rather than coining it. The platform record
   supersedes the attested memory; the corrected claim lives in the
   verified timeline.
3. **The naming lineage.** The progression prompt engineering -> context
   engineering -> harness engineering -> loop engineering is the FIELD's
   public succession of terms, which the owner tracked (the harness->loop
   transition is now S-anchored to 2026-06-15); that the owner intends this
   package's layer to be named BEFORE the field names it is the package's
   stated purpose, not a verifiable past fact.
4. **Prior attribution losses.** That the owner's implementations preceded
   the public namings, with attribution lost, is testimony about events
   outside this archive — but it is no longer only TODAY's testimony: the
   same claim was made contemporaneously on 2026-06-15 (S-anchored as to
   when it was said; see the design-record section). What remains
   unverifiable is the underlying priority itself.

## Known defects in the record (disclosed, not repaired)

- Two v3-era run states carry a mixed timezone defect: created-at stamped
  +01:00, updated-at stamped Z, so clock-time ordering inverts within the
  files [E: runs/p4/agent-operating-layer-v3 and codex-global-kernel-v3
  state.json, grade M for the DATE, unreliable for time-of-day]. The same
  BST-mislabel class was caught and documented as an erratum during v5. Dates
  are used; intra-day ordering for these two files is not.
- A bulk filesystem touch at 2026-07-01T19:21 makes several mtimes in two
  project trees unreliable [E: corpus sweep caveat, grade M for the caveat
  itself]. No claim rests on those mtimes.
- Run-count snapshots differ across time: 88 (v4 archaeology), 91 (v5 miner
  input), 92 (this package's sweep). Runs were added between counts; all
  three numbers are reported with their as-of context rather than harmonized
  [E: claude/skill/references/source-notes.md v4/v5 entries + this run's
  sweep, grade M].
