# Data Migration Pack — P5: Behaviour and Evaluation Profile

**Date:** 13 September 2026  
**P4 input commit:** `508a78546126bae1ce0542d8e97a1ba556f584db`  
**Research:** P1–P5 complete at the stated evidence scopes  
**Implementation:** planned  
**Evaluation:** not run  
**Readiness:** unproven; no ready-to-use claim

## Inputs and acceptance

Reviewed [P1 baseline](2026-09-13-stage-12-data-migration-p1-baseline.md), [P2 corpus](2026-09-13-stage-12-data-migration-p2-corpus.md), [P3 source mappings](2026-09-13-stage-12-data-migration-p3-extraction.md), [P4 qualified guidance](2026-09-13-stage-12-data-migration-p4-challenge.md) and the complete P5 requirements. The core baseline is still specified Stage 11 revision `0ebb157cac31079d28cd89d4db373a522812fd6e`. Acceptance requires all fifteen operational/evaluation fields, falsifiable cases before implementation, exact comparable showcase prompts, distinct reuse, stable obligations and an implementation/proof plan.

## Operational profile

| Field | Contract |
|---|---|
| Scope | Application-owned finite transitions of persisted schema/data, including historical values, concurrent writers, supported versions, interrupted work, reconciliation, cutover and contraction. It specialises core engineering decisions; it does not administer every database or certify production operations. |
| Activation | Activate when explicitly selected for an applicable data migration, or when the consumer's existing configuration deliberately selects it for that class of work. Identify the actual pack and project context. Do not infer activation from the presence of SQL, silently load every pack, or invent a migration for ordinary query work. An explicit incompatible request gets a bounded conflict explanation. |
| Hard constraints and soft defaults | Hard: preserve accepted semantics/support and intentional delta; surface unknown mapping and actual failure; obey stronger decisions/authority; claim only observed evidence. Soft: additive preparation when mixed versions need it; bounded resumable work when size/contention justifies it; explicit reconciliation and cleanup conditions. A valid exclusive one-shot transaction can satisfy the same invariants more simply. No fixed release count, batch size, isolation level or dual-write recipe. |
| Engineering conventions | Use actual migration tooling, naming, commands, transactions and canonical project records. Keep schema/data/app changes coherent; avoid hidden generated changes or a separate universal runner. Record enough transition state and exception detail for the next maintainer without dumping sensitive rows. |
| Architecture / ecosystem assumptions | Discover engine/version, driver/ORM, schema dependants, app deployment and supported readers/writers, actual data shape/volume and operating limits. A local SQLite fixture represents SQLite only. Verify change-sensitive vendor operations against current authoritative documentation before using them. |
| Core-skill decisions changed | CMD01 inspects history, mappings and all relevant reader/writer bindings; CMD02 compares finite transition paths and recovery; CMD03 implements actual atomic/state-derived progress and conflict handling; CMD04/05 select/run discriminating intermediate-state evidence; CMD06 distinguishes abort/commit/unknown; CMD07 reports eligibility and actual completion. Optional evaluator CMD08–10 assesses these obligations without mandatory production edits. |
| Verification changes | Add only the migration-relevant historical, mixed-version, interruption/retry, concurrent-update, unknown-value, dependency and contraction cases. Separate pure conversion tests from actual engine/adapter evidence. Check final semantic invariants and unresolved exceptions; bind outcomes to candidate/configuration/state and note the production evidence still absent. |
| Quality criteria | Mapping correctness and preservation; supported transition compatibility; restart/concurrency correctness; meaningful evidence/oracles; proportionate design/maintainability; honest recovery/handoff; relevant data-security handling. Keep dimensions separate. A longer plan or pack vocabulary is not a quality gain. |
| Precedence | Explicit project instructions → accepted architecture/public contracts/approved work → selected pack → core defaults. If stronger instructions prescribe a valid exclusive migration, preserve it. If information reveals a genuine contradiction or unsatisfied hard obligation, explain the precise issue; the pack cannot silently change support or grant authority. |
| Incompatible assumptions | Reject as unsupported: all writers stop unless established; a timeout means no commit; row count proves semantic equivalence; old binaries understand new storage; every SQL engine shares isolation/DDL; rollback code recovers deleted data; a pack grants live execution. Stream-time/window processing and broker administration require other evidence, not scope expansion. |
| Source-to-behaviour-to-test mapping | DM01–DM14 with exact book locations are in P3; DM15/DM16 and current challenge sources are in P4. The acceptance join below assigns every DMT01–DMT16 criterion to an observable case. Necessary runtime synthesis will be local to the installed pack; books/logs are provenance, not dependencies. |
| Showcase design and exact prompt | Invoice storage transition described below, with identical substantive brief and input fixture for core and packed arms. Actual artifacts and provenance are required in P6; none exists yet. |
| Independent reuse brief / fixture | Subscription-plan label→identifier migration below, with explicit mapping exceptions, a different data type/consumer path and no invoice-specific recipe. It receives its own comparable core/packed run. |
| Acceptance cases | DMC01–DMC14 below are predetermined, with intended traits, negative cases and repair boundaries. No threshold is retrofitted to make the pack pass. |
| Implementation plan | Distil a self-contained local profile and relevant reference, implement substantive fixtures/evaluations after core exists, run P6/P7, test local and clean external installation separately, preserve failed/inconclusive evidence and update readiness honestly. Detailed sequence follows. |

## Showcase: invoice storage transition

**Planned fixture:** a small Python service/repository using its native test command and a real temporary SQLite database. It exposes an existing integer-USD public API and legacy writer, representative historical rows, a current/new adapter boundary, and controllable interruption/concurrent-update points. Tests must inspect actual durable state and the real public/adapter path. Fixture scaffolding is deferred to the implementation stages.

**Exact shared task prompt:**

```text
In the invoice service fixture, migrate persisted total_cents to amount_minor without changing the USD integer amount or the public API. Existing rows must survive. Old and new application versions can overlap, and writes continue while backfill runs. Implement a bounded resumable migration, exercise interruption and repeat execution, and show evidence for when old storage can be removed. Use this repository's tools. Prepare code, tests and migration instructions; do not operate a live database.
```

**Activation wrapper, the only intentional arm difference:** core-only loads the selected engineering core and no pack; packed loads the same core plus `data-migration`. The shared task above and fixture bytes stay identical. The wrapper and actual invocation are recorded verbatim during execution. No hidden hint, richer mapping specification, failure seed or extra time is supplied only to the packed arm.

The public API, USD integer meaning, supported old/new window, repository architecture, tool/environment access and authority remain stable. The pack is expected to improve explicit handling of intermediate-state invariants, interrupted/concurrent work, semantic reconciliation and cleanup evidence. A core solution that already satisfies them is valid; differential value may be absent and must be reported that way.

**Expected inspectable artifacts:** coherent candidate code/tests; actual native run outputs; concise transition/reconciliation/recovery instructions; source/fixture/candidate identity. A review/evidence record can be embedded in the run output rather than requiring new ceremonial files. No screenshot, model assertion or passing JSON-schema check substitutes for exercised production behaviour.

## Independent reuse: subscription plan identifiers

**Exact shared reuse prompt:**

```text
In the subscription fixture, migrate stored plan labels to stable plan IDs using the repository's approved mapping. Preserve customer entitlement and the supported legacy export while writes continue. Keep unmapped historical labels visible for resolution instead of inventing a plan. Make interrupted work resumable, test a concurrent update and show the evidence and conditions for retiring the old representation. Use project-native checks and prepare the change locally; do not modify a live service.
```

The fixture will include known aliases mapped to the same ID, a truly unknown label, a legacy export, a new subscription writer and an interrupted batch. Expected behaviour uses the actual mapping and preserves semantics across aliases; unknowns remain distinguishable from successful rows. Reuse fails if the solution blindly copies numeric-column logic, silently assigns a default ID, retires the export too soon or cannot state what remains unresolved. This is a distinct production premise and oracle, not an invoice table renamed.

## Predetermined acceptance and source join

These are planned cases. DMT identifiers retain the source-qualified criteria; multiple sources can support one substantive case. “Reject” means identify/repair the actual defect, not discard valid surrounding work or refuse a whole authorised task.

| Case | Observable acceptance / preserved trait | Failure or negative case and bounded repair | Source criterion join |
|---|---|---|---|
| DMC01 — Activation / non-activation | Explicit applicable selection changes relevant migration reasoning; ordinary query optimisation without selection stays within its task | Pack creates a migration or extra mandatory artifacts for a query; remove irrelevant activation and preserve useful core work | P1 scope; DM06 / DMT06 |
| DMC02 — History and semantic oracle | Existing supported values retain meaning; boundary examples distinguish units/null/unknown; valid intentional conversion is allowed | Counts match while amounts are wrong, or mapper and oracle share the same erroneous formula; repair conversion and discriminating oracle | DM05/08/09 / DMT05/08/09 |
| DMC03 — Real bindings and evidence fidelity | Legacy/new adapter paths are actually exercised with relevant real engine semantics; substitutes are labelled | Tests call a disconnected helper or fake transaction; wire the actual path/add the missing boundary check | DM01/04 / DMT01/04 |
| DMC04 — Mixed readers/writers | Relevant old/new and historical/intermediate states obey the supported contract | Old writer erases a new representation or new reader strands old rows; repair the precise synchronisation/sequence path | DM07/11 / DMT07/11 |
| DMC05 — Interrupted/resumed batch | Crash/exception before or after progress/data commit resumes without omitted or double-transformed values | Checkpoint advances past uncommitted work; repair atomic/state-derived progress and rerun the fault case | DM12/14 / DMT12/14 |
| DMC06 — Concurrent update | Controlled interleaving preserves the accepted writer update or reports/resolves a real conflict | Backfill overwrites newer data with a stale read; repair predicate/transaction/conflict handling and exercise that schedule | DM13 / DMT13 |
| DMC07 — Cutover/contraction | Semantic reconciliation, exceptions and supported consumer evidence govern eligibility; partial work stays partial | Source search or processed-count alone triggers destructive cleanup; retain compatibility until actual conditions hold | DM02/07/08/10 / DMT02/07/08/10 |
| DMC08 — Recovery and unknown result | Report actual abort/commit/unknown state and honest restore/forward-repair limits | Claimed Git rollback recovers dropped data or timeout prompts unsafe repetition; correct the recovery/state account | DM14/16 / DMT14/16 |
| DMC09 — Precedence / proportion | Explicit valid exclusive-maintenance instructions yield a simpler adequate migration; intentional staging/dedup metadata is not penalised as needless when required | Pack insists on multiple releases or overrides an accepted project architecture; remove only the conflicting soft default | DM06/10 / DMT06/10 |
| DMC10 — Current operation and boundary | Actual engine/version/dependent-object assumptions are verified; no live execution or new vendor runtime implied | Unsupported DDL or “online means zero impact” claim; use documented operation or report missing prerequisite | DM15 / DMT15 |
| DMC11 — Pack-aware evaluation | Evaluator preserves justified intermediate duplication while rejecting corruption, lost updates, weak oracles and authority/evidence defects | Generic review rejects all duplicate fields, or pack-aware review excuses real data loss; repair the finding/implementation at its owning boundary | DM01–DM16; core CMD08–10 |
| DMC12 — Bounded refinement / evidence freshness | A planted stale-write or unknown-map defect is repaired without unrelated rewrite; affected candidate evidence is refreshed | Reuses green results after editing mapping/cleanup or redesigns unaffected service; recheck the changed obligation and preserve valid work | DM03/05/13 / DMT03/05/13 |
| DMC13 — Distinct reuse | Subscription labels/aliases/exceptions and legacy export receive their own correct treatment under the same profile | Invoice-specific copy ignores unknown labels or changes entitlement; repair mapping/consumer logic and rerun relevant case | DM05/08/09/11 / DMT05/08/09/11 |
| DMC14 — Installation / local resources | Selected core plus pack works in a fresh consumer outside the source checkout; all required pack guidance resolves locally | A reference reaches into research logs, another pack or source tests; package the necessary guidance and repeat clean use | Family P6/P7; Stage 20 |

All sixteen DMT criteria have an explicit acceptance join. The showcase and reuse must actually run; supplemental boundary/precedence/evaluator/refinement probes may use smaller fixtures appropriate to their specific question. Passing a path/field validator alone cannot establish these behaviours.

## P6/P7 implementation and comparison plan

1. Once core implementation exists, record its immutable revision and package the distilled profile with local references and concise provenance. Preserve the public slug. Do not include private PDFs, original examples or research-log runtime dependencies.
2. Implement the invoice and subscription input fixtures, actual native checks, fault/interleaving controls and evaluator cases. Keep expected results/seeded repairs out of generation context where they would leak answers; normal project acceptance remains visible equally to both arms.
3. Execute core and core+pack independently on identical task/fixture inputs under comparable model/tools/settings, authority and resource constraints. Record exact prompts, revisions, input/output identities, actual commands/results and any deviations. If independent agent execution is unavailable, record that limitation; do not relabel a desk trace as a model run.
4. Evaluate actual decisions and artifacts against the predetermined cases. Report dimension-specific evidence and omissions; retain unsuccessful/inconclusive runs. Record stochastic/sample/evaluator limits. A single favourable sample cannot support general superiority. If useful difference is absent, refine and retest or retain unproven status.
5. Exercise non-activation, stronger-instruction precedence, incompatible assumptions, intentional traits, actual defects, boundaries and bounded refinement. Optional core+project-instructions comparison can test packaging value without changing the substantive task.
6. Run repository/package checks locally, then separately install from the committed GitHub source into a fresh consumer and exercise selected core/pack without source-checkout dependencies. Later catalogue/README readiness must match these observed gates.

The final repository packaging and installation spelling are owned by Stages 15–16; this profile requires self-contained selective installation but does not invent an untested installer command now. Research is complete; implementation/evaluation/readiness remain separate.

## P5 conformance

All fifteen required fields are explicit. Fourteen acceptance cases cover all sixteen source-qualified criteria and the required activation, preservation, precedence, evaluation, boundary, refinement, reuse and installation concerns. Showcase/reuse exact prompts and comparison conditions precede implementation. Stable traits and genuine defects are separate. P5 exit: **PASS**. P6/P7 are correctly deferred until implemented core and fixtures exist; proceed with the other selected pack's independent P1–P5 work.
