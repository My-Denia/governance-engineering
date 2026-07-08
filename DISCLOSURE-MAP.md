# Tiered disclosure map

Tier 1 = design thought — publish. Tier 2 = specs and schemas — publish.
Tier 3 = implementation (scripts, hooks, validators) — WITHHELD by default;
the owner decides per item. No Tier 3 content appears anywhere in this
repository; specs are abstract rewrites, not copies.

## Staged in this repository (Tier 1-2)

| artifact | tier | evidence grade | recommendation | rationale |
|---|---|---|---|---|
| README.md | 1 | — | publish | orientation, no sensitive content |
| CHRONOLOGY.md | 1 | M (self-describing) | publish | the attribution record itself |
| NEEDS-OWNER.md | 1 | — | publish | shows the evidence discipline openly |
| NAMING.md | 1 | — | publish | dated collision scan; placeholder discipline |
| DISCLOSURE-MAP.md | 1 | — | publish | this file |
| essays/01-say-do-gap.md | 1 | M + web citations | publish | design thought, cited |
| essays/02-when-plans-meet-reality.md | 1 | M + web citations | publish | design thought, cited |
| essays/03-frameworks-must-tax-themselves.md | 1 | M + web citations | publish | design thought, cited |
| specs/run-state.md | 2 | M | publish | field semantics, no code |
| specs/gates.md | 2 | M | publish | gate semantics, no code |
| specs/say-do-checks.md | 2 | M | publish | c1-c6 semantics, no code |
| specs/four-cell-taxonomy.md | 2 | M | publish | taxonomy definition |
| specs/rule-lifecycle.md | 2 | M | publish | ledger/probation/retirement semantics |
| LICENSE (AGPL-3.0, placeholder copyright) | — | — | publish after owner confirms license + attribution | license text is owner-pending |
| docs/LICENSE-prose.md (CC BY-SA 4.0 note) | — | — | publish after owner confirms | ditto |
| docs/zh-CN-summary.md | 1 | — | publish | translation-only companion |

## Held privately (owner's local archive; NOT in this repository)

| artifact class | tier | recommendation | rationale |
|---|---|---|---|
| Harness skill instruction files (both tools, all versions incl. dated backups) | 2/3 boundary | owner decides per file | instruction text is spec-like but contains operational detail and the owner's private working idiom; dated backups are chronology evidence better proven by hash than by content |
| State-mutation helper, validator, miner, critic-channel, probe scripts | 3 | withhold by default | working implementation; publishing is a per-item owner decision |
| Runtime hooks (plan gate, stop gate, subagent logging; both tools) | 3 | withhold by default | security-adjacent runtime enforcement; publishing invites cargo-cult reuse without the gate semantics |
| Test suites (both tools) | 3 | withhold by default | encode implementation specifics |
| Rules ledger JSON + mining reports + preregistered-patterns file | 2/3 boundary | owner decides | the ledger schema is Tier 2 (spec'd in specs/rule-lifecycle.md); the live contents reveal operational history beyond the chronology's needs |
| Run archive (92 run folders, 8 project trees) | 3 | withhold; disclose in aggregate only | contains project content, paths, and research material; chronology cites it in aggregate and by framework-run slug only |
| Auditor agent definitions | 2/3 boundary | owner decides | short prompts; near-spec but verbatim operational text |
| Private evidence inventory (real-path citation map, raw agent outputs) | internal | never publish as-is | contains real usernames/paths by design; auditors may view under owner supervision |

## Standing rule

If any Tier 3 item is later approved for release, it enters as a NEW commit
after this package's initial publication, with its own scrub pass. Nothing in
the current staged tree changes when Tier 3 decisions are made.
