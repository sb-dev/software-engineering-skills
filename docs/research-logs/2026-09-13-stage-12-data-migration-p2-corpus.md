# Data Migration Pack — P2: Five-Book Corpus

**Date:** 13 September 2026  
**Pack corpus:** `DM-CORPUS-001`  
**P1 input commit:** `79a95f1128ce7d312ac4994208479f26cbb3ab9f`  
**Status:** P2 selection complete; pack-specific reviewed extraction remains P3.

## Inputs and acceptance

Reviewed the [P1 specialisation and substantive baseline](2026-09-13-stage-12-data-migration-p1-baseline.md), the complete family P2 requirement, [core candidate/access/permission register](2026-09-13-stage-02-knowledge-coverage-and-five-book-corpus.md) and [direct-reading coverage](2026-09-13-stage-03-five-book-extraction-and-reconciliation.md#2-bibliography-and-reading-coverage). The five supplied PDFs remain available; their identities and examined scope are already recorded. This stage selects sources for the migration questions below rather than automatically inheriting a bibliography. Acceptance includes a coverage map, broader comparison, exactly five distinct justified works, access/reuse decisions, permission status and remaining specialist gaps.

## Migration-specific coverage map

| Need | Required decision depth | Selected contribution | Remaining challenge need |
|---|---|---|---|
| DMK01 data meaning and acceptance | Distinguish approved transformation, preservation, invalid/unknown values and acceptance oracle | B4 R04/R09/R10; B2 L05 contrasts observed with intended behaviour | Mapping exceptions, reconciliation completeness and applicable data-owner decisions |
| DMK02 supported readers/writers/history | Assess old/new code, stored records and intermediate states, not only final shape | B5 D03; B1 G01/G07 | Actual database/application schema caching, constraints and supported-client semantics |
| DMK03 entry into legacy code | Establish trustworthy observation points before changing persistence paths | B2 L02–L05; B1 G04/G05 | Real dependency fidelity and cases where mocks cannot expose locks/transactions |
| DMK04 rollout architecture and scope | Compare additive rollout, maintenance-window transaction and alternative storage without assuming a rewrite | B3 A01/A02/A05/A07; B1 G09 | Lock duration, deployment topology and demonstrated operational constraints |
| DMK05 concurrency and interrupted backfill | Reason about invariants, lost updates, resumability and unknown outcomes | B5 D05/D06/D07 | Current isolation/DDL contracts, checkpoint ownership and concrete idempotent batch behaviour |
| DMK06 validation and cutover | Choose meaningful record/invariant comparison and verify actual remaining consumers | B4 R09; B1 G07/G08; B3 A04 | Counts versus semantic checks, convergence under concurrent writes and evidence freshness |
| DMK07 contraction and recovery | Distinguish code rollback, database restore, forward repair and irrecoverable loss | B1 G07/G09; B5 D03/D05 | Current removal/deployment procedures and actual backup/restore limits, not promises |
| DMK08 maintainable handoff and proportionality | Preserve necessary rationale, exceptions, progress and receiving actions at useful depth | B1 G03; B3 A06; B4 R10 | Small migration counterexample to mandatory elaborate rollout documentation |

These needs are complementary. Transaction theory cannot decide the authorised mapping; characterisation cannot approve legacy errors; architectural discussion cannot establish vendor DDL safety; passing a backfill test cannot establish deployment completion.

## Broader candidate comparison

Bibliographic and access evidence for alternatives is the previously examined first-party material in Stage 2, with its exact reading limits. This comparison reuses those scope observations, not unread book methods. Direct pack findings will come only from the five accessible selected texts or adequate reviewed original extraction.

| Candidate | Contribution to this pack and overlap | Access / decision |
|---|---|---|
| B1 Software Engineering at Google | Finite deprecation/migration, consumer responsibility, candidate-specific evidence and documentation connect backfill to completion; complements B5's state mechanisms | Full supplied text and relevant direct extraction available. Select; qualify large-organisation rollout assumptions |
| B2 Working Effectively with Legacy Code | Getting a safe observation/change seam in an existing persistence path; distinguishes current behaviour from authorised meaning | Full supplied text and direct extraction available. Select; not a database migration manual or proof from mocks |
| B3 Fundamentals of Software Architecture, 2e | Compares transition alternatives and runtime coupling against actual quality constraints; prevents migration becoming an unjustified system rewrite | Full supplied text and direct extraction available. Select; no architecture-style ranking or universal metric threshold inherited |
| B4 Software Requirements Essentials | Data meaning, stakeholder decision rights, acceptance and controlled baseline changes supply the migration oracle | Full supplied text, all substantive chapters previously examined. Select; not a source of live-data authority or specialist assurance |
| B5 Designing Data-Intensive Applications, 1e | Encoding/evolution, transaction boundaries, anomalies and partial failure provide the deepest selected state-transition mechanism analysis | Full supplied first edition and relevant direct extraction available. Select; current vendor guarantees still need P4 |
| C6 Refactoring, Fowler with Beck, 2e, 2018 | More precise local behaviour-preserving transformations could help isolate persistence code; overlaps B2 but less directly targets weak feedback | Prior author overview only; no direct text examined. Supplementary candidate, not foundational replacement |
| C9 Release It!, Nygard, 2e, 2018 | Operational failure/release perspective could deepen interruption and recovery; overlaps B1/B5 while contributing different production experience | Prior publisher description/contents only. Supplementary operational gap candidate; no claims extracted |
| C11 Continuous Delivery, Humble/Farley, 2010 publication | Delivery/data-change detail is especially relevant to rollout and cutover; competes with B1's wider lifecycle and review link | Prior publisher contents only; linked book sample not examined. Strong supplement, but no supplied book is displaced and P4 must independently address rollout depth |
| C13 Effective Software Testing, Aniche, 2022 | Specification/boundary/property tests could deepen transformation and exception sensitivity; complements all five but overlaps initial B1/B2 feedback contribution | No supplied copy or adequate direct reading. The user's replacement remains honoured; optional supplement, never silently restored to foundational status |

Selection does not claim these five are the only or objectively best migration books. Each has a distinct assessed contribution and adequate source access; the retained combination respects the supplied corpus and permits specialist challenge beyond five. The cost is less migration-tool/operational depth than a dedicated delivery source and less systematic testing depth than C13. That cost is explicit in DMK03–DMK07 and must be addressed or bounded in P4, not hidden by broad book titles.

## Exactly five selected books, access and reuse decisions

All locations are **one-based PDF file pages** in the supplied edition, not printed pagination. Exact identities/ISBNs and complete examined ranges remain in the core register; the narrower ranges below identify relevant already-examined material for P3 review. Full PDFs were confirmed present again during this stage. Availability and prior direct examination are distinct from completion of pack-specific analysis.

| ID / work and edition | Origin and access | Reviewed evidence proposed for reuse | Pack-specific contribution and reuse decision |
|---|---|---|---|
| B1 — *Software Engineering at Google*, Titus Winters, Tom Manshreck, Hyrum Wright; original 2020 edition | User supplied; full text available | G03 PDF 311–318; G04/G05 385–394, 430–442; G07 515–519, 708–715, 755–763; G08/G09 768–779, 808–823; consult exact finding locations in P3 | Retain for migration completion, feedback fidelity and released-candidate evidence. Reuse only after checking original finding assumptions; do not require Google's CI or organisational scale |
| B2 — *Working Effectively with Legacy Code*, Michael C. Feathers; first edition, published 2004/copyright 2005 | User supplied; full text available | L02–L05; PDF 26–69, 198–219; exact finding scope reviewed in P3 | Retain for safely exposing existing persistence behaviour and distinguishing characterisation from approved mapping. Not evidence of database isolation or a mandate for OO restructuring |
| B3 — *Fundamentals of Software Architecture*, Mark Richards and Neal Ford; second edition, 2025 | User supplied; full text available | A01/A02/A04/A05/A06/A07; relevant subsets of PDF 40–44, 62–117, 159–194, 647–656, 698–721, 726–743 | Retain for option/scope/quality/recovery trade-offs. Reuse decision/risk methods conditionally, not style examples or uncalibrated numeric proxies |
| B4 — *Software Requirements Essentials: Core Practices for Successful Business Analysis*, Karl Wiegers and Candase Hokanson; 2023 | User supplied as the authorised requirements-book replacement; full text available | R04/R09/R10 within directly examined substantive chapters PDF 26–220; exact locations reviewed in P3 | Retain for data semantics, acceptance and support/cleanup decisions. Material contribution is the oracle and authority boundary, not generic project paperwork |
| B5 — *Designing Data-Intensive Applications*, Martin Kleppmann; first edition, 2017 | User supplied; full text available; no second-edition claims | D03 PDF 155–190; D05/D06 PDF 296–312, 321–337; D07 PDF 361–377, 380–411 | Retain for mixed-version history, transaction boundaries and interrupted/concurrent migration reasoning. Product examples are historical and require current authoritative challenge |

**Corpus count: five distinct works.** Shared sources do not multiply independent corroboration and do not create runtime dependencies. P3 must inspect original finding text, source locations, reading scope, edition, limits and migration applicability for every selected book; this selection table alone cannot satisfy it.

## Permissions, access limits and specialist gaps

The user supplied five core books and explicitly replaced the testing title with Requirements Essentials. This pack deliberately retains those five as inputs because each contributes above. No user-supplied title is removed, replaced or demoted, and no edition is silently upgraded. No additional pack-specific supplied titles exist in the visible task. Required substitution approvals pending: **none**. No new book access is claimed; alternatives remain unexamined supplements at their stated scope.

P4 must address current DDL/transaction and deployment behaviour, mixed-version schema caching, concurrent backfill reconciliation, lock/batch/cutover constraints, and recovery limits. Vendor commands and numerical budgets are not supplied by this corpus. Data sensitivity and actual restore authority remain project-specific. SQLite may support a runnable later fixture, but a local SQLite pass must not certify PostgreSQL, distributed databases or production load.

## P2 conformance

Eight migration-specific coverage needs, nine compared candidate works, five distinct selected books, per-book contribution/access/reuse records, explicit permission status and specialist gaps are present. Actual source access is available for all five; no bibliography is represented as completed specialised extraction. Exit: **PASS**. Continue with P3 after this record's individual commit and remote verification.
