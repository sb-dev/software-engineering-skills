# Reliable Event Processing Pack — P4: Specialist Challenge and Gap Research

**Date:** 13 September 2026  
**P3 input commit:** `70d7d420e2520d48fd0a4626c267c1c73add253a`  
**Status:** P4 complete; operational profile and evaluation are P5 work.

## Questions, evidence roles and acceptance

Reviewed [P3's fourteen findings](2026-09-13-stage-12-reliable-event-processing-p3-extraction.md) and [EPK01–EPK08 coverage](2026-09-13-stage-12-reliable-event-processing-p2-corpus.md). The complete P4 requirement calls for independent specialist challenge, current authoritative semantics, separate disposition/standing, contrary cases and explicit gaps. The main challenges are whether broker delivery guarantees cover business effects, whether duplicate identity is sufficient, whether ordering survives recovery, and whether retry/dead-letter defaults preserve actual policy.

Seven primary sources were examined. RabbitMQ, Apache Kafka, AWS and SQLite provide different implementation/practice perspectives; multiple pages from one organisation are not independent votes. Current product documentation establishes scoped semantics. AWS's idempotency article supplies practitioner design experience; its backoff article supplies a described simulation, not measured proof about this pack or an arbitrary workload. No formal AMQP/SQL standard was directly examined or substituted for the actual versioned implementation contract.

## Source register

All sources retrieved 13 September 2026. Named sections are the actual examined scope; no entire-site or unexecuted source-code claim is made.

| ID / source | Examined observation | Applicability and limits |
|---|---|---|
| ES01 [RabbitMQ consumer acknowledgements and publisher confirms](https://www.rabbitmq.com/docs/confirms) | Publisher/consumer scope distinction; negative acknowledgement/requeue discussion; prefetch window. Confirmation of publication is separate from consumer processing, and immediate requeue can loop | Current RabbitMQ documentation; client/protocol/configuration details matter. No claim about an arbitrary business transaction or direct adoption of example code |
| ES02 [RabbitMQ queues](https://www.rabbitmq.com/docs/queues) | Message ordering and its exceptions: concurrent publishers, priorities and redelivery affect the observed sequence | Current implementation guidance, not a proof of business-level order or global freshness. Do not equate stable log positions with serial completion of application effects |
| ES03 [Apache Kafka 4.3 design](https://kafka.apache.org/43/design/design/) | Message Delivery Semantics and Using Transactions: offset/output sequencing and transaction scope; external destinations require cooperation beyond a Kafka-only transaction | Version-identified official design; no latest-release inference or installation claimed. Omitted production durability/configuration assumptions cannot be supplied by the phrase exactly once |
| ES04 [AWS: making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Client intent/identity, atomic token/effect recording, semantic repeat results, late requests and conflicting parameters | Practitioner mechanism/experience. Identity scope and lifetime are service contracts, not universal values; added complexity is not justified for every operation |
| ES05 [Amazon SQS dead-letter queues](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-dead-letter-queues.html) | Processing failures, redrive policy, ordering warning and retention distinctions | Current service guidance: a DLQ can change ordering and messages can expire. It is not a universal solution or permission to discard/replay business work |
| ES06 [AWS: exponential backoff and jitter](https://aws.amazon.com/blogs/architecture/exponential-backoff-and-jitter/) | Marc Brooker, 4 March 2015, update May 2023; read OCC simulation setup, backoff/jitter discussion and stated limitations. The described contention model compares work/completion under retry variants | Empirical simulation report with a particular workload/model; graphs and linked simulator were not independently rerun. No speedup figure or universally best jitter algorithm is adopted |
| ES07 [SQLite transactions](https://www.sqlite.org/lang_transaction.html) | Sections 2–3: single-writer/read-snapshot behaviour, busy commit and error-dependent rollback state, reassessed for consumer effect/identity storage | Current local-engine contract. Useful for the planned fixture; cannot establish broker/external atomicity or another database's concurrency |

The separate Builders' Library timeout/retry URL redirected to a page with no retrievable text in this session. It is **not** counted as examined; ES06 supplies the actually read retry analysis. No unavailable source is used to assert a method or runtime setting.

## Dispositions of all extracted findings

| Finding | Challenge / contrary condition | Disposition | Evidential standing | Qualified effect on production |
|---|---|---|---|---|
| EP01 test fidelity | ES01/03/07 expose different transport/storage boundaries; a real local database still does not model broker failover | Retain | Supported scoped distinction | Label model/local integration/production evidence separately and add only the missing relevant boundary |
| EP02 candidate evidence | Effect/ack logic and effective client configuration determine what a run actually tests | Retain | Supported project-contract obligation | Keep actual candidate/configuration/result identity; refresh affected evidence after repair |
| EP03 actual seam | Callback tests can bypass the real acknowledgement or carrier adapter; this is an implementation-specific risk | Qualify | Context-dependent method | Confirm actual entrypoint/bindings before trusting the fault probe; no mandatory architecture rewrite |
| EP04 effect observation | ES01 confirmation does not establish the business result; ES04 considers repeat-result meaning | Retain | Supported mechanism | Observe the accepted durable/external effect and acknowledgement boundary, not only a return code |
| EP05 quality conditions | ES06's single contention model cannot supply every application's delay/capacity target | Retain | Context-dependent method | Use actual workload, fault and owner constraints; no invented SLO or numeric benchmark target |
| EP06 capacity/retries | ES01 describes requeue loops; ES06 supports conditional spreading of retry contention, not a capacity cure | Adapt | Context-dependent method | Inspect retry ownership and bounded work/backpressure; do not layer an extra retry loop over a suitable existing policy blindly |
| EP07 state/exception paths | ES03's before/after-offset cases make crash placement decisive | Retain | Supported mechanism | Exercise meaningful before-effect, after-effect and before-ack transitions under the actual model |
| EP08 request meaning | ES04 rejects treating identical parameters as necessarily one caller intent and treats conflicting reuse explicitly | Adapt | Supported mechanism; contract-specific identity | Derive scoped identity and mismatch semantics from the actual operation; payload fingerprint alone is not business identity |
| EP09 policy boundary | ES05 shows poison handling changes ordering/retention; ES04 acknowledges different acceptable contracts | Retain | Supported boundary; project-dependent policy | Preserve approved best-effort/lossless/order/retention commitments and expose missing decisions |
| EP10 fault model | ES03 states scoped delivery/transaction assumptions; ES07 shows local storage state matters | Retain | Supported conditional guarantee | State tolerated faults and progress assumptions; no blanket never-lose/always-finish claim |
| EP11 transaction/effect boundary | ES03 external-destination limitation and ES07 storage semantics challenge a universal local-transaction recipe | Qualify | Supported mechanism; remedy context-dependent | Couple participating state where possible; use documented external identity/reconciliation or approved compensation elsewhere |
| EP12 unknown completion | ES04's lost-response/repeat semantics support stable identity; not every external API offers it | Retain | Supported mechanism | Preserve pending/unknown state and use the actual service's reconciliation path; absence of one remains an explicit gap |
| EP13 ordering | ES02 delivery exceptions and ES05 DLQ ordering warning contradict simplistic FIFO guarantees | Qualify | Supported scope distinction | Protect only the required entity/partition/business sequence; a global serialization rule needs separate justification |
| EP14 coordination state | ES03 offers existing supported transaction mechanisms; most ordinary consumers are not atomic-commit coordinators | Qualify | Context-dependent method | Preserve needed recovery identity/state but do not invent a consensus protocol or force two-phase commit |

## Added specialist guidance and rejected readings

| Item | Challenge and disposition | Standing | Behaviour / planned evaluation consequence |
|---|---|---|---|
| EP15 — Poison, replay and retention are one policy surface | ES05 makes ordering and expiry effects explicit. Add by adaptation; repair/replay must retain required identity and context | Supported service counterexample; handling is context-dependent | EPT15: malformed/permanent work follows actual policy, is not silently dropped or retried forever, and replay does not bypass deduplication/ordering obligations |
| EP16 — Retry control is conditional, not a correctness mechanism | ES06 supports jitter under its stated contention model and ES01 exposes immediate redelivery loops. Add by qualification | Context-dependent method, not universal performance proof | EPT16: inspect existing retry ownership, distinguish transient/permanent/unknown failure and bound work under supplied limits; jitter cannot fix a duplicate-effect invariant |
| Every producer confirm proves the consumer completed | Rejected using ES01's explicit separation | Unsupported general claim | Report which hop/operation was actually acknowledged |
| Kafka exactly-once means one arbitrary external side effect | Rejected using ES03's destination boundary | Disputed as a blanket claim | Name actual participants/consumer isolation/output cooperation; test the external failure window separately |
| An outbox or dedup table automatically solves every effect | Rejected as a sufficient condition; the actual boundary and recovery still need proof | Unsupported without additional mechanism | Allow these techniques when warranted, but inspect dispatch, result/identity and crash behaviour |
| Every consumer needs global ordering | Rejected by the distinction between business dependence and delivery scope | Context-dependent alternatives | Preserve parallelism for independent/commutative operations and enforce only accepted required order |
| A fixed retry count, permanent identity retention or mandatory DLQ | Rejected as universal policy | Unresolved until consuming context supplies needs | Use existing project policy or expose the precise missing decision; no arbitrary numeric default becomes a guarantee |

These are combined-source adaptations. Required correctness/evidence/authority obligations remain core; the pack adds a reusable analysis of identity, effect, acknowledgement, replay and progress. It does not ship vendor configuration copied from a documentation example or infer that a named pattern makes all qualities pass.

## Coverage resolution, contrary cases and limits

EPK01 now includes exact-repeat versus conflicting intent and service-specific identity lifetime. EPK02 has independently scoped publisher, consumer, Kafka transaction and external-effect boundaries. EPK03/07 require actual bindings and discriminating crash observations with model limits. EPK04 distinguishes required business order from delivery mechanics. EPK05/06 gain conditional retry/capacity and poison handling without inventing performance or loss policy. EPK08 includes supported event meaning, retention/replay and accurate recovery handoff.

A valid compensated multi-step workflow is not defective just because it lacks one global transaction. A telemetry task with explicit tolerated loss should not be silently converted into a costly lossless ledger. A real constraint forbidding retries must be preserved while its effect on accepted reliability is surfaced. These contrary cases keep soft defaults from overruling approved work.

Remaining consumer-specific evidence includes broker/client versions/configuration, business identity/ordering/retention, actual storage/adapter guarantees, workload/capacity and authorised replay. No real broker, carrier or production inventory service was executed. Simulation examples do not establish comparative agent quality; later P6/P7 must produce actual artifacts and disclose their bounded environment. No unresolved universal claim needs to become a hard rule for P5 to proceed.

## P4 conformance

Seven examined primary sources provide current implementation contracts, practitioner mechanisms and a bounded simulation study. All fourteen findings have separate disposition/standing; two added gaps have falsifiable criteria; contrary cases and inaccessible-source limits are explicit. All eight original coverage needs are addressed or bounded. Exit: **PASS**. Continue with P5's independent operational profile and predetermined showcase/reuse evaluation design.
