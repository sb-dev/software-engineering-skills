# Reliable Event Processing Pack — P5: Behaviour and Evaluation Profile

**Date:** 13 September 2026  
**P4 input commit:** `3c57e003aeb2aa1e912f3dd7ecf1b75e73300c19`  
**Research:** P1–P5 complete at the recorded scopes  
**Implementation:** planned  
**Evaluation:** not run  
**Readiness:** unproven

## Inputs and acceptance

Reviewed [P1 baseline](2026-09-13-stage-12-reliable-event-processing-p1-baseline.md), [P2 corpus](2026-09-13-stage-12-reliable-event-processing-p2-corpus.md), [P3 mappings](2026-09-13-stage-12-reliable-event-processing-p3-extraction.md), [P4 challenge](2026-09-13-stage-12-reliable-event-processing-p4-challenge.md) and the complete P5 requirements. Stage 11 `0ebb157cac31079d28cd89d4db373a522812fd6e` remains the specified core baseline; no executable comparison is claimed. Acceptance requires all fifteen operational/evaluation fields, predetermined falsifiable cases, exact comparable showcase and reuse prompts, stable traits, real defects and an implementation/proof plan.

## Operational profile

| Field | Contract |
|---|---|
| Scope | Continuing application event effects under declared duplicate, delay, reordering, crash, timeout and replay conditions. The profile covers effect/identity/acknowledgement integration and recovery; it is not broker administration, stream-window computation, consensus or shared-memory certification. |
| Activation | Explicit applicable selection or deliberate existing project selection for this class of work. Do not activate for every async function, add messaging to a synchronous task, or load the migration pack automatically. An incompatible requested use gets a bounded explanation and an appropriate core/specialist route. |
| Hard constraints and soft defaults | Hard: preserve accepted business/tenant/effect and event contracts; report actual evidence and unknown outcomes; obey stronger decisions and authority. Soft: atomic local effect/identity state where supported; stable request identity for cooperative external APIs; acknowledge at the accepted completion boundary; scoped ordering; bounded existing retry/in-flight policy; observable poison/recovery state. No universal outbox, global ordering, permanent retention, retry count or exactly-once promise. |
| Engineering conventions | Use actual worker/client/storage adapters and project-native tooling. Keep change scope coherent and retain significant effect/recovery rationale in an appropriate existing record. Redact unnecessary sensitive payloads; record useful identity/status without dumping event contents. |
| Architecture / ecosystem assumptions | Discover broker/client/version/configuration, durable storage boundary, identity/trust scope, accepted order/retention/loss model, downstream API semantics and operating workload. Verify vendor guarantees for actual versions. A local delivery model and SQLite store establish only their stated logical/storage behaviour. |
| Core-skill decisions changed | CMD01 traces producer→consumer→effect→ack and identity/meaning; CMD02 compares actual atomicity/reconciliation/compensation options; CMD03 implements the chosen bounded path; CMD04/05 exercise duplicate/crash/order/poison evidence; CMD06 preserves unknown outcomes and discriminates cause; CMD07 reports actual pending/recovery state. Optional evaluator independently assesses these without becoming a production mutator. |
| Verification changes | Add relevant exact-repeat/mismatch, tenant separation, concurrent duplicate, before/after-effect-before-ack, unknown remote result, required order and poison/retry cases. Observe actual durable/external results and acknowledgement, not only callback completion. Separate model, local integration and real-provider evidence. |
| Quality criteria | Accepted effect correctness and preservation; identity/trust scope; declared fault/recovery behaviour; required order/progress; meaningful tests and current evidence; proportionate structure/resource use; honest handoff. Evaluate dimensions separately. Correctness cannot be traded for an invented throughput gain. |
| Precedence | Explicit project instructions → accepted architecture/public contracts/approved work → selected pack → core defaults. Preserve an approved compensated or best-effort design when it satisfies its actual contract. Surface real contradictions without silently rewriting policy or requesting repeat approval for authorised repair. |
| Incompatible assumptions | Transport delivery identity equals business intent; publisher confirmation means consumer effect; broker exactly-once spans any external destination; timeout proves no effect; a dedup table by itself is atomic with the business write; FIFO implies every relevant application order; retries guarantee progress under permanent failure. Identify actual missing mechanisms/conditions. |
| Source-to-behaviour-to-test mapping | EP01–EP14 with exact book locations are in P3, EP15/16 and current challenge in P4. The acceptance join below covers EPT01–EPT16. Distilled runtime guidance will be local to the installed pack; logs/books are provenance only. |
| Showcase and exact prompt | Stock-reservation repair below uses a substantive shared task and identical input fixture for core and packed arms. Only activation/guidance differs. Actual artifacts/provenance are required after execution. |
| Independent reuse brief / fixture | Parcel dispatch below changes from a local atomic effect to a cooperative external carrier model with lost responses and documented status/identity. It tests transfer beyond the stock ledger. |
| Acceptance cases | EPC01–EPC15 below define meaningful positive, negative, preservation, precedence, evaluation, boundary and bounded-repair behaviour before implementation. |
| Implementation plan | Package concise local guidance/provenance after core exists; implement real inspectable fixtures/fault checks; execute P6/P7 under comparable recorded conditions; verify local and clean external use independently; catalogue readiness from observed evidence, retaining failures/inconclusive results. |

## Showcase: stock reservation consumer

**Planned fixture:** an existing small Python worker and SQLite-backed inventory store with tenant-scoped reservation requests, a stable public result and bounded delivery simulator. It contains the actual consumer binding, accepted stock invariant, controllable duplicate/concurrent delivery and crash/ack points. The simulator must expose its limits; it is not named or scored as a real Kafka/RabbitMQ deployment.

**Exact shared task prompt:**

```text
Repair the stock-reservation consumer in this repository. Delivery is at least once. Reserve stock once for each accepted tenant-scoped reservation request, preserve the public result for an exact repeat, and reject reuse of the same request identity with different contents. A process can stop before or after the database commit and before acknowledgement. Implement the bounded repair with project-native checks, exercise duplicate/concurrent delivery and crash/retry cases, and explain recovery for invalid messages. Do not operate a live broker or inventory service.
```

Core-only loads the engineering core without this pack. Packed loads the same core plus `reliable-event-processing`; that activation wrapper and actual invocation are recorded verbatim. The shared task, fixture bytes, accepted policy, accessible tools and resource constraints are otherwise identical. Neither arm receives a private answer key, richer requirements or extra hints unavailable to the other.

Expected inspectable work includes the actual candidate worker/store/tests, command outputs, bounded effect/ack/recovery explanation and evidence identity. A valid core-only solution can satisfy all obligations. The pack's hypothesis is more reliable coverage of identity/crash/replay decisions and discriminating tests, not a reward for naming a pattern or writing more prose. If both arms are equivalent, record that rather than manufacturing superiority.

## Independent reuse: parcel dispatch after a lost response

**Exact shared reuse prompt:**

```text
Repair the parcel-dispatch worker in this fixture. The carrier API is outside the local database transaction and may create a shipment before its response is lost. Use its documented request-identity and status contract to preserve one accepted dispatch outcome across retries and worker restart. Preserve tenant boundaries and existing public results. Exercise the lost-response and conflicting-request cases with the supplied carrier model, explain unresolved recovery states and run project-native checks. Do not contact a live carrier or broker.
```

The carrier model has its own durable effect store and documented identity/status behaviour; it can commit then drop a response. The worker cannot share its local SQLite transaction with that model. The fixture includes exact-repeat and conflicting payloads, a pending state, a restart and legitimate distinct requests with identical contents. Expected behaviour preserves the actual external identity and reconciles unknown outcomes. Copying the local stock ledger recipe without inspecting the external boundary is a failure of reuse. This is logical external-contract evidence, not certification of a real carrier.

## Predetermined acceptance and source join

The planned cases below cover all sixteen EPT criteria. Observed results must be recorded only after actual execution/inspection. A field-presence validator cannot establish these behaviours.

| Case | Observable acceptance / intentional trait | Negative or failure case and bounded repair | Source criterion join |
|---|---|---|---|
| EPC01 activation/non-use | Applicable explicit selection affects effect/recovery decisions; a plain async parsing task remains ordinary core work | Pack introduces a broker, ledger or migration into unrelated work; remove irrelevant scope | P1 scope; EP05/09 |
| EPC02 identity and tenant scope | Exact request repeat preserves the accepted result; conflicting reuse is rejected; tenants and legitimate distinct intents remain separate | Payload hash alone merges two valid requests or key omits tenant; repair identity/mismatch logic and tests | EP08/09 / EPT08/09 |
| EPC03 actual binding and observations | Actual consumer invokes the tested adapter; effect count/state and ack are observed | Helper-only pass hides unused repair or duplicate effect; fix binding/observation at the relevant boundary | EP01/03/04 / EPT01/03/04 |
| EPC04 local atomicity/concurrent duplicate | Accepted stock effect and identity/result survive concurrent repeats without decrementing twice | Dedup check and business write race or commit separately; repair the actual transactional/invariant boundary | EP10/11 / EPT10/11 |
| EPC05 crash windows | Before-effect, after-commit-before-ack and restart paths preserve accepted effect/result and delivery handling | Early ack loses work; lost ack duplicates committed work; repair the smallest state/ack path and rerun fault cases | EP07/11 / EPT07/11 |
| EPC06 unknown external result | Carrier lost response remains pending until supported identity/status resolves it; no fresh dispatch identity on blind retry | Local rollback is claimed to undo shipment; preserve identity/reconcile actual external status | EP12/14 / EPT12/14 |
| EPC07 poison/replay/retention | Invalid or permanent failure follows supplied policy and remains diagnosable; replay respects identity/order and actual lifetime | Infinite hot retry, silent drop or expired dedup replay creates harm; repair policy implementation without inventing business loss tolerance | EP09/15 / EPT09/15 |
| EPC08 ordering scope | Required per-entity sequence is preserved; independent/commutative work need not be globally serialized | FIFO label hides redelivery/stale-event overwrite; add the actual version/order rule | EP13 / EPT13 |
| EPC09 retry/capacity claims | Use inspected project/SDK retry policy and accepted workload limits; distinguish mitigation from correctness | Layered retries amplify work or jitter is claimed to fix duplicate effects; repair retry ownership and the separate invariant | EP05/06/16 / EPT05/06/16 |
| EPC10 stronger instructions / valid alternatives | Preserve an approved compensated workflow or explicit best-effort telemetry contract while assessing real defects | Pack forces a global transaction/lossless ledger or silently weakens an accepted stock invariant | EP05/09/11/14 / EPT05/09/11/14 |
| EPC11 guarantee and execution boundaries | Claims name actual participants, version and fault model; no live replay/broker/carrier action from a code-only task | Broker label used as external-effect proof or simulated evidence called production integration; narrow claim/add justified missing check | EP01/10/11 / EPT01/10/11 |
| EPC12 pack-aware evaluation | Review preserves justified dedup/recovery state and eventual completion traits while rejecting real duplicate/lost effects or weak tests | Generic cleanup removes needed identity state, or specialised review excuses a real invariant violation | EP04/10/11/14 / EPT04/10/11/14 |
| EPC13 bounded refinement / freshness | A planted wrong-identity or ack-order defect receives a targeted repair and affected re-verification | Rewrites unrelated architecture or reuses pre-edit green evidence; preserve valid work and refresh actual candidate results | EP02/03/08/11 / EPT02/03/08/11 |
| EPC14 independent reuse | Parcel worker honours separate carrier effect/status contract and survives lost response/restart | Assumes local commit covers carrier or conflates identical new requests with retries; repair external identity/recovery boundary | EP08/12/14 / EPT08/12/14 |
| EPC15 local and clean installation | Selected core+pack can run in a fresh consumer with local required guidance and disclosed tool prerequisites | Pack reads books/research logs/other pack/source-test paths; package necessary guidance and repeat external use | Family P6/P7; Stage 20 |

The two substantive briefs must run in both arms. Smaller supplemental probes can cover non-activation, precedence, evaluator behaviour, ordering/retention policy and targeted repair where those questions need a different bounded premise. Do not pretend the stock task exercises every conceivable messaging pattern.

## P6/P7 implementation and evidence plan

1. Identify implemented core revision before demonstration. Distil local pack guidance and provenance; retain the public slug and no dependency on other packs, source logs, original books or a new event runtime.
2. Implement stock and parcel input fixtures, native tests, meaningful fault/interleaving controls and protected evaluation criteria. Keep expected repair answers out of generation context while giving both arms equal normal project requirements.
3. Run independent core and packed production on identical inputs under comparable model/tools/settings, authority and resource constraints. Record exact task/activation prompts, input/output/revision identities, native commands/results, deviations and actual environmental limitations. A desk walkthrough is not a model production run.
4. Assess actual artifacts/decisions against EPC01–EPC15 with dimension-specific evidence. Record positive, failed and inconclusive results, regressions and evaluator/sample limits. Retain an unproven/deferred entry if useful specialised difference is absent; do not change the rubric simply to pass.
5. Exercise the distinct reuse, non-activation, precedence, incompatible assumptions, intentional traits, real defects, domain boundaries and bounded refinement. Optional core+project-instructions baseline can probe prompting burden without enriching only one arm's substantive need.
6. Run local repository/package checks, then separately install from the committed GitHub source into a fresh consumer outside the source checkout and exercise the selected pack. The catalogue and README may claim only the readiness this evidence supports.

Packaging/installation spelling remains owned by Stages 15–16 and must later be tested. No need for a provider-specific orchestration layer follows from comparison provenance. Existing tools perform execution; the pack refines engineering decisions.

## P5 conformance

All fifteen fields are specified; fifteen acceptance cases join all sixteen source criteria and the required boundary/activation/precedence/preservation/evaluation/refinement/reuse/install concerns. Exact showcase/reuse prompts, comparable conditions, stable traits and genuine defects precede implementation. Exit: **PASS**. P6/P7 remain deferred until implemented core. Stage 12 can now audit both packs, finalise the domain authoring contract and commit its overall completion record.
