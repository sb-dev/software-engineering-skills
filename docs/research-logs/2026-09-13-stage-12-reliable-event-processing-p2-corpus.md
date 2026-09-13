# Reliable Event Processing Pack — P2: Five-Book Corpus

**Date:** 13 September 2026  
**Corpus:** `REP-CORPUS-001`  
**P1 input commit:** `e9913279ccb3c7f4068bba56004142c72346b35e`  
**Status:** P2 selection complete; event-specific extraction remains P3.

## Inputs and acceptance

The [P1 effect/acknowledgement baseline](2026-09-13-stage-12-reliable-event-processing-p1-baseline.md), complete family P2 requirement, [core source/access/permission comparison](2026-09-13-stage-02-knowledge-coverage-and-five-book-corpus.md) and [direct-reading coverage](2026-09-13-stage-03-five-book-extraction-and-reconciliation.md#2-bibliography-and-reading-coverage) were reviewed. This pack independently selects its five contributions. The migration pack's corpus membership neither forces nor proves this selection. Acceptance covers a specialist map, broader candidates, exactly five works, access/reuse, supplied-book authority and residual gaps.

## Event-effect knowledge map

| Need | Required depth | Selected contribution | Specialist gap to challenge |
|---|---|---|---|
| EPK01 effect and identity semantics | Define the business operation, scope of identity, exact-repeat versus conflicting intent and allowed compensation | B4 R03/R04; B5 D05 | Concrete idempotency-key mismatch, lifetime and external-service contract |
| EPK02 delivery/effect/ack boundary | Distinguish receipt, application work, durable result and acknowledgement under the actual fault model | B5 D01/D05/D07; B3 A05 | Current broker acknowledgement/confirm/transaction guarantees and their limits |
| EPK03 preservation in existing consumers | Locate actual adapter/worker binding and observe the business effect without unnecessary rewrite | B2 L03/L04; B1 G05 | Faithful fault injection, real adapter evidence versus simulation |
| EPK04 concurrent duplicates and ordering | Protect business invariants across concurrent deliveries and relevant ordering scope | B5 D09/D10, with D05; B4 R04 | Broker partition/order/redelivery semantics and actual database concurrency |
| EPK05 retry, poison and progress | Separate unknown/transient/permanent outcomes; avoid unbounded retry, lost work and overload | B5 D01/D07/D10; B3 A03/A05 | Retry/capacity policy, dead-letter/replay obligations and service-specific liveness |
| EPK06 qualified quality and workload | Evaluate correctness, recovery, delay/resources and maintained structure without inventing SLOs | B3 A03/A05; B4 R05 | Current native measurements and actual workload/fault assumptions |
| EPK07 evidence/oracle fidelity | Make a fault test expose the mechanism; identify candidate, environment and actual result | B1 G05/G08; B2 L04; B4 R03 | Loss-of-reply, commit/ack crash windows and equivalent versus misleading substitutes |
| EPK08 contract evolution and handoff | Preserve supported event/consumer meaning, recovery state and owner decisions | B4 R04/R05; B1 G08; B5 D07 | Schema compatibility versus semantic effects, retention, operational replay authority |

The pack excludes stream-time/window and consensus implementation depth. Its selected DDIA evidence need not pretend those unexamined chapters were read. Current broker/client semantics and operational policies require broader research even though the books support the underlying failure reasoning.

## Broader candidates and combined choice

Alternative identity/scope evidence is the previously examined first-party publisher/author material in Stage 2. Only that scope is reused; no methods from an unread alternative are extracted here.

| Candidate | Specific contribution / contested role | Access and decision |
|---|---|---|
| B1 Software Engineering at Google, 2020 | Fidelity of doubles and candidate-specific evidence connect fault tests to actual consumer code; complements systems reasoning with verification practice | Full supplied text and direct relevant extraction. Select; no universal test pyramid or Google CI/runtime requirement |
| B2 Working Effectively with Legacy Code, first edition | Actual worker/adapter seams and effect observation let a bounded consumer repair enter weakly tested code | Full supplied text and direct relevant extraction. Select; not a broker or distributed transaction manual |
| B3 Fundamentals of Software Architecture, second edition | Runtime coupling, quality scope and constraints prevent assuming asynchronous boundaries create operational independence | Full supplied text and direct relevant extraction. Select; no mandatory event-driven architecture or numerical risk score |
| B4 Software Requirements Essentials, 2023 | Events, states, data meaning and measurable qualities establish the business effect/oracle, identity and owner-supplied trade-offs | Full supplied text; substantive chapters previously examined. Select; no invention of product ordering, retention or accepted loss |
| B5 Designing Data-Intensive Applications, first edition | Fault models, transaction/effect scope, partial failure, ordering and coordination supply the deepest selected mechanism analysis | Full supplied text and direct relevant extraction. Select; no current Kafka guarantee or unexamined stream-window method attributed to it |
| C9 Release It!, Nygard, second edition, 2018 | Strong prospective operational stability/retry/failure-pattern complement; competes with B5's deeper state/coordination role | Publisher contents/description only previously examined. Supplementary candidate; missing operational depth must be addressed in P4 |
| C10 Secure by Design, Johnsson/Deogun/Sawano, 2019 | Domain modelling/validation could deepen tenant-scoped identity and untrusted event controls | Publisher description only; direct content unexamined. Supplementary specialist candidate; do not demote a supplied foundation or claim its methods read |
| C11 Continuous Delivery, Humble/Farley, 2010 publication | Deployment/configuration and acceptance pipeline detail could deepen consumer rollout and recovery evidence | Publisher contents only; book sample not examined. Supplementary; B1 retains the broader lifecycle/test link |
| C13 Effective Software Testing, Aniche, 2022 | Specification/boundary/property methods could deepen duplicate/interleaving/oracle sensitivity | No supplied copy or adequate direct reading. User's requirements replacement remains honoured; not silently restored as foundational |
| C7 The Pragmatic Programmer, Thomas/Hunt, second edition, 2019 | Smaller-team debugging and contracts offer useful contrast to B1's institutional perspective | Publisher contents/description only; direct text unexamined. Supplementary; narrower selected contributions have priority |

The combination is justified by five distinct decisions: what an event means (B4), where effects actually occur in legacy code (B2), which distributed outcomes are possible (B5), how boundaries/quality constraints shape design (B3), and what the verification actually establishes (B1). The same five titles as the core/migration corpus are retained after this different contribution assessment. Shared sources do not add independent corroboration. Missing broker, operational and specialist testing depth stays explicit rather than being filled by a title's reputation.

## Exactly five books and access/reuse register

One-based PDF file pages refer to the exact supplied editions. Full PDFs remain available; identities and complete direct-reading ranges are in the core register. The targets below name already examined evidence to review in P3, not completed event-specific extraction.

| ID / full bibliographic identity | Origin / access | Reuse target and pack-specific decision | Limits |
|---|---|---|---|
| B1 *Software Engineering at Google*, Titus Winters, Tom Manshreck, Hyrum Wright; original edition, 2020, ISBN 9781492082798 | User supplied; full text available | G05 ch13 PDF 430–442 and G08 ch23 768–779. Reassess substitute fidelity for crash/ack boundaries and exact consumer evidence | No quantitative effectiveness inference, universal organisational method or guarantee from green CI |
| B2 *Working Effectively with Legacy Code*, Michael C. Feathers; first edition published 2004/copyright 2005, ISBN 9780131177055 | User supplied; full text available | L03 ch3–4 PDF 45–69; L04's effect/observation analysis at its exact original locations. Reassess real consumer binding and observation of durable/external effects | Older OO mechanics are not an instruction to redesign consumers or proof of current library semantics |
| B3 *Fundamentals of Software Architecture*, Mark Richards and Neal Ford; second edition, 2025, ISBN 9781098175511 | User supplied; full text available | A03 quality conditions and A05 ch7 PDF 185–194. Reassess backlog, downstream capacity and accepted recovery/workload constraints | Architectural lens is contextual; asynchronous messaging does not establish independent capacity or a universal style choice |
| B4 *Software Requirements Essentials: Core Practices for Successful Business Analysis*, Karl Wiegers and Candase Hokanson; 2023, ISBN 9780138190286 | User supplied under explicit requirements-book replacement; full text available | R03/R04/R05 within fully examined PDF 26–220; exact original locations checked in P3. Reassess event/state meaning, identity, data obligations and owner-defined quality | Concise practitioner methods, not formal distributed protocol verification or policy authority |
| B5 *Designing Data-Intensive Applications*, Martin Kleppmann; first edition, 2017, ISBN 9781449373320 | User supplied; full text available | D01, D05, D07, D09 and D10: examined fault/transaction/ordering/coordination sections, exact scopes reviewed in P3 | Batch/stream chapters were not previously read; no stream processor completeness or current vendor/second-edition claim |

**Five distinct foundational works selected; no extra edition counted as a work.** P3 will inspect the original extracted findings and explicit source limitations and record the specialised decision/evidence join. It may use adequate reviewed direct evidence; it may not inherit the migration pack's production rules simply because source titles match.

## Permissions and residual gaps

All five supplied books are retained as relevant foundational inputs; no supplied work is removed, replaced or demoted. The user's explicit replacement of the testing book with Requirements Essentials remains in force. There are no additional visible supplied pack titles and no pending required substitution decisions. No inaccessible alternative is claimed as examined or required to complete extraction.

P4 must verify acknowledgement versus publisher confirmation, retry/deduplication scope and retention, partition/order semantics, external effect reconciliation, poison/replay handling and actual database transaction boundaries. Security-sensitive identity and logs need the consuming project's trust model. A controlled local delivery model can demonstrate a logical failure mechanism, but cannot establish real Kafka/RabbitMQ availability, throughput or provider guarantees.

## P2 conformance

Eight specialist needs, ten compared works, five distinct selected contributions, explicit identities/access/reuse/limitations and zero pending substitutions satisfy P2. Source access is adequate for planned reviewed extraction; specialist production claims remain unproved. Exit: **PASS**. Continue with P3 after committing and remotely verifying this independent selection record.
