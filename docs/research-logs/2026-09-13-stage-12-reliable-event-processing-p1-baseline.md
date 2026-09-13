# Reliable Event Processing Pack — P1: Specialisation and Core Baseline

**Date:** 13 September 2026  
**Pack:** `reliable-event-processing`  
**Catalogue decision:** `b908644bba05382e2245bb287507d251c90f2951`  
**Branch input:** `f9bac9c052ad2f9634c3ba063bc47e09eec00775`  
**Status:** P1 complete; P2–P5 are separate dependent work.

## Inputs and acceptance

Reviewed the [catalogue's event-driven/reliability selection](2026-09-13-stage-12-pack-catalogue-curation.md), the [core command contracts](2026-09-13-stage-11-command-contracts.md) and the complete family/Stage 12 P1 requirement. The other pack's completed research does not establish this pack's applicability or source findings. Acceptance is a bounded repeatable outcome, nine explicit specialisation fields, constraints/defaults, a substantive core baseline and falsifiable evaluation questions.

## Specialisation brief

| Required field | Decision |
|---|---|
| Intended use and non-use | Use for application producers/consumers whose repeated, delayed, reordered or interrupted delivery can change durable business effects, acknowledgement or recovery. Do not activate merely because code is asynchronous. Exclude broker/cluster administration, stream event-time/window semantics, general consensus implementation, shared-memory safety certification and service-wide SLO ownership. |
| Reusable production need | Delivery, processing, durable effect and acknowledgement are separate events. A recurring engineering outcome is a consumer/effect path whose declared invariants survive its actual duplicate, crash, timeout and replay model and whose failures remain diagnosable/recoverable within policy. |
| Relevant core skills | Engineering CMD01 identifies producers/consumers/identity, CMD02 designs effect boundaries, CMD03 implements, CMD04/05 verify faults/interleavings, CMD06 diagnoses unknown outcomes, CMD07 hands off actual recovery state. Evaluator CMD08/09/10/12 can independently assess quality and compatibility without modifying production code. |
| Core revision / baseline status | Specified core at Stage 11 `0ebb157cac31079d28cd89d4db373a522812fd6e`; no implemented core comparison exists yet. P6/P7 must identify actual implemented revisions, prompts, tools and outputs. |
| Expected behavioural difference | Explicitly relate message/business identity, payload compatibility, effect transaction, acknowledgement and retry/reconciliation states. Choose deduplication, idempotent effects, ordering guards or compensation where justified. Test crash windows and progress/poison paths, not only successful processing. Observable output is grounded effect/recovery reasoning plus materially discriminating tests and bounded retry/visibility handling. |
| What must remain stable | Accepted business meaning, event/public contracts, tenant/trust boundaries, intentional consistency/loss policy, existing architecture/tools, supported versions, authority and truthful evidence. A pack cannot change business ordering, retention or availability requirements, claim exactly-once external effects from a broker label, or invent live replay permission. |
| Adjacent boundaries | Product/domain owners decide effect semantics and permitted compensation/loss; platform owners govern broker configuration, capacity, access and operations; security owners supply accepted policy. This pack owns application effect/delivery integration. Finite historical data transitions belong to data-migration when applicable; continuous processing is not itself a migration. |
| Why instructions or an existing pack are insufficient | Project facts must name broker/version, identity, business operation and policy. A reusable effect/ack/crash/replay analysis transfers across queues, jobs and serverless consumers. Inspected Kafka/Schema Registry candidates S26/S27 and Cassandra diagnostics S29 cover narrower products and mechanics; they do not establish a vendor-neutral end-to-end application effect contract. Reuse applicable tooling; P7 must still prove that packaging improves actual behaviour over substantive core work. |
| Provisional evaluation questions | Does the profile change a meaningful effect boundary or fault test? Can duplicate/concurrent delivery repeat a business effect? Does a lost response remain unknown until reconciled? Are mismatched payloads under one identity rejected appropriately? Can poison handling avoid infinite retry while preserving required evidence? Are ordering and deduplication lifetimes explicit without unnecessary global ordering? Does evaluation preserve a valid compensated design while rejecting hidden loss? |

## Constraints and conditional defaults

Hard constraints follow actual contracts: preserve declared effect/tenant invariants, keep evidence and external completion truthful, honour stronger decisions and authority, and make material unsupported guarantees explicit. No implementation can promise progress under every failure; state the relevant fault and recovery assumptions.

Provisional soft defaults to research: commit local effect and duplicate record atomically when one supported transaction can cover both; acknowledge only when the accepted processing boundary is satisfied; carry stable operation identity to a cooperative external API; distinguish permanent/malformed failures from retryable/unknown cases; bound retries/in-flight work according to real policy/capacity; retain enough redacted evidence to diagnose/reconcile. These are not mandates for an outbox, a global sequence, a fixed retry count, permanent deduplication storage or one broker vendor.

## Substantive baseline task

Both core-only and packed runs will receive identical task and fixture details:

> Repair the stock-reservation consumer in this repository. Delivery is at least once. Reserve stock once for each accepted tenant-scoped reservation request, preserve the public result for an exact repeat, and reject reuse of the same request identity with different contents. A process can stop before or after the database commit and before acknowledgement. Implement the bounded repair with project-native checks, exercise duplicate/concurrent delivery and crash/retry cases, and explain recovery for invalid messages. Do not operate a live broker or inventory service.

The fixture will contain actual consumer and durable storage bindings, a documented inventory invariant, repeat/mismatch cases, controllable crash/acknowledgement points and a broker-delivery model whose limitations are explicit. The raw task contains the real production need; the pack is not awarded value by giving core an intentionally weaker request. Correct core-only work may already solve it, and a null differential must remain visible.

The distinct reuse case will dispatch parcels through an external carrier API model with stable request identity and an injected lost response. Local database commit cannot include the carrier's effect. The task must preserve the approved externally visible outcome and accurately reconcile unknown completion. This changes the transaction boundary, exposing overfitting to a local atomic ledger recipe.

## Boundary and completion checks

The selected profile is narrower than “high-reliability services” and broader than one vendor client. It addresses recurring application effect semantics under the declared delivery/failure model. It does not configure a Kafka cluster, guarantee arbitrary stream-time computations, impose a particular schema format or claim an emulator validates a real broker. If a system intentionally accepts lossy telemetry under an approved contract, evaluate against that contract rather than silently imposing lossless business processing.

P1's nine required fields, hard/default distinction, specified baseline, practical reuse/existing-core comparison and evaluation questions are present. Exit: **PASS**. Next: independently select exactly five books for this event-effect specialisation and identify its missing specialist evidence.
