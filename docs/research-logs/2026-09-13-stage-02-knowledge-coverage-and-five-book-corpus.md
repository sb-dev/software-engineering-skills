# Stage 2: Knowledge Coverage and Five-Book Corpus

**Project:** `software-engineering-skills`  
**Stage:** 2, Seed: Map Knowledge Coverage and Select Five Complementary Books  
**Status:** Complete for initial selection; direct corpus extraction and broader challenge remain unperformed  
**Version:** 1.0  
**Date:** 13 September 2026  
**Execution branch:** `feat/bootstrap-2`  
**Starting revision:** `17cbe59a818a29dd5977e69df486789245a8d0f1`  
**Corpus revision:** `SE-CORPUS-001`  
**Governing bootstrap:** [Software Engineering Skills bootstrap v1.1, Stage 2](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#9-stage-2--seed-map-knowledge-coverage-and-select-five-complementary-books)

## 1. Selection decision

Select these **exactly five distinct books** as the initial foundational corpus. Membership is settled for this revision; the usefulness and applicability of their individual claims must still be established through direct reading and challenge.

| ID | Selected book | Authors | Edition and publication year | Intended contribution to this project |
|---|---|---|---|---|
| B1 | [Software Engineering at Google][b1-home] | Titus Winters, Tom Manshreck and Hyrum Wright | Original edition, 2020 | Engineering changes over time: the connection between code, review, verification, dependencies and delivery. |
| B2 | [Working Effectively with Legacy Code][b2-catalogue] | Michael C. Feathers | First edition, published 2004; copyright 2005 | Entering and changing an existing system when understanding and test support are inadequate. |
| B3 | [Fundamentals of Software Architecture][b3-catalogue] | Mark Richards and Neal Ford | Second edition, 2025 | Making and communicating architectural choices under competing quality constraints. |
| B4 | [Effective Software Testing: A Developer's Guide][b4-catalogue] | Maurício Aniche | 2022 edition | Designing checks that can expose faults and assessing the adequacy and maintainability of tests. |
| B5 | [Designing Data-Intensive Applications][b5-catalogue] | Martin Kleppmann and Chris Riccomini | Second edition, 2026 | Reasoning about persistent state, compatibility, concurrent changes and distributed failure. |

The combination supports the charter's priority on brownfield change while retaining architectural, verification and state-related depth. It provides a broad engineering frame plus four more focused perspectives. It leaves significant gaps, recorded below. This is a justified initial selection from the examined candidates, not a measured optimum or a claim that five books cover software engineering completely.

Access is sufficient to finish **selection**, but not **extraction**. B1 has an official full-text source; B2 has directly accessible chapter excerpts; B3–B5 currently have bibliographic or descriptive material only. None has yet been meaningfully examined for its full intended contribution. Four access needs are recorded in section 8.

## 2. Inputs, authority and evidence boundary

### 2.1 Governing inputs

This record consumes the completed [Stage 1 domain charter](2026-09-12-stage-01-project-goal-and-domain-boundary.md), the domain bootstrap's Stage 2 requirements and the canonical [Domain Research Process][family-process] at `production-skills` revision `20979e0c68ac4b37433374df7fe10ceb2e7ee69a`.

The charter owns technical requirements and acceptance, architecture, construction, maintenance, diagnosis, verification, review and technical release readiness. Brownfield work is the primary proving ground; greenfield work remains included. The consuming repository supplies product intent, constraints, tools and authority. Specialist judgements and live-service ownership remain with the appropriate owners.

No book titles or files were supplied for this bootstrap in the available task instructions or persisted records at the starting revision. The initial supplied-book contribution is therefore **none across every coverage dimension**. All five places are empty slots that the process permits the agent to fill. No selection, source access or stage completion from the separate `feat/bootstrap` branch is inherited.

The user requested the next stage after Stage 1. This authorises Stage 2 execution and its commit on the established `feat/bootstrap-2` branch. It does not change corpus access, confer ownership of commercial books or establish later-stage completion.

### 2.2 Bounded reconnaissance

The charter supplies the responsibility map. Three official sources were used as limited checks that the map extends beyond writing code:

| Reconnaissance source | Directly examined material | Implication for source selection | Limit |
|---|---|---|---|
| [DORA: Continuous delivery][dora] | Capability page describing delivery and supporting practices. | Keep deployment readiness, test automation, configuration and operational feedback in the coverage map. | Does not establish which book combination is best or validate a future skill. |
| [Google: What to look for in a code review][google-review] | Reviewer guidance on design, functionality, complexity, tests and documentation. | Include review of system fit and verification quality, not just style. | One organisation's guidance; review policy remains repository-specific. |
| [NIST SP 800-218, SSDF v1.1][nist] | Official publication record and abstract, February 2022. | Treat security as part of the development lifecycle and retain a specialist research gap. | The full framework was not examined here; no claim that this is the latest revision or a compliance assessment. |

The Stage 1 IEEE SWEBOK access limitation remains recorded. No unavailable SWEBOK chapter findings are used in this selection.

Reconnaissance stopped when twenty responsibility dimensions could distinguish the marginal contributions of twelve serious book candidates. The stopping condition was a defensible comparison, not exhaustive literature coverage. Empirical validation, current standards analysis, detailed workflows and specialist practice research remain Stage 4 work.

### 2.3 What the evidence supports

Author and publisher pages establish bibliographic identity, advertised scope and, where available, chapter structure. The accessible book text sampled in this stage establishes access, not completion of reading. Candidate contributions and overlaps below are **selection hypotheses** to test in Stage 3; they are not extracted methods or accepted capabilities.

The mandated access label `secondary material only` means that only metadata, descriptions or contents are available for this record. Some of those pages are first-party bibliographic sources. The label distinguishes them from directly examined book content, rather than claiming they are third-party accounts.

## 3. Knowledge-coverage map

The map is derived from the charter, not divided into one topic per book. Every row needs enough depth to guide an engineering decision and judge its evidence; vocabulary recognition is insufficient. The final column identifies what the selected corpus cannot yet be relied upon to supply. Entries under books are **planned reading targets**, not verified coverage. Supplied-book coverage is none for every row.

| ID | Responsibility | Required decision depth | Planned corpus targets | Remaining need or boundary |
|---|---|---|---|---|
| K01 | Requirements and acceptance | Turn approved intent into observable examples, constraints and exclusions; identify ambiguity that changes the implementation. | B4 for testable obligations; B3 for quality constraints. | Structured elicitation, conflicting stakeholder needs and product/UX handoffs need wider research. |
| K02 | Design and architecture | Compare local and system-level alternatives, preserve system fit and explain quality, coupling and migration trade-offs. | B3; B5 for state-related choices. | Client, embedded and specialist architectures need contextual evidence. No mandated style follows from a book. |
| K03 | Construction and code quality | Produce coherent implementation using repository conventions; reason about interfaces, errors, dependencies and readability. | B1, B2 and B4. | Language semantics, type systems, resource ownership and framework idioms need current, ecosystem-specific sources. |
| K04 | Maintenance and evolution | Distinguish corrective, adaptive, preventive and improvement work; plan migration, deprecation and retirement without losing obligations. | B1, B2 and B5. | Platform upgrades, support policy and retirement authority are context-dependent. |
| K05 | Brownfield understanding | Build an evidence-backed model of relevant behaviour, dependencies and uncertainty before changing code. | B2; B1 for repository-scale context. | Runtime investigation, undocumented integrations and non-OO systems require additional examples and challenge. |
| K06 | Refactoring and technical debt | Establish what must remain invariant, justify scope and distinguish repair from speculative restructuring. | B2 and B3, with B1 for sustained change. | Detailed transformation catalogues and evidence for economic prioritisation remain supplementary research. |
| K07 | Testing and test quality | Derive useful cases and oracles, choose verification levels, assess omissions and maintain the checks themselves. | B4; B2 for weak test support; B1 for wider verification context. | Flakiness, nondeterminism, specialised assurance and empirical test-effectiveness claims require challenge. |
| K08 | Debugging and root-cause diagnosis | Reproduce or substantiate failure, discriminate hypotheses, trace causality and confirm a sufficient repair. | B2 and B4 as partial starting points; B5 for distributed failures. | No selected book is a general debugging foundation. Profiling, tracing and concurrency diagnosis need dedicated investigation. |
| K09 | Code review | Assess intent, design, correctness, compatibility and test quality; distinguish blocking defects from preferences. | B1; B3 and B4 for particular review questions. | Review effectiveness, independent judgement and AI-generated changes need evidence beyond one organisational model. |
| K10 | API and contract evolution | Identify consumers, state compatibility obligations and design transitions without silently changing public behaviour. | B1 and B5; B2 for existing interfaces. | Protocol-specific compatibility, SDK packaging and consumer-driven migration need current sources. |
| K11 | Data and schema evolution | Reason about invariants, transactions, schema transitions, backfills, recovery and irreversible effects. | B5. | Concrete database engines, data meaning, retention rules and production migration procedures remain specialist/contextual work. |
| K12 | Security engineering | Recognise security-relevant changes, preserve controls, verify bounded fixes and escalate unresolved specialist judgements. | B3 and B5 for constraints; B1 and B4 for lifecycle integration. | No dedicated security foundation is selected. Threat modelling, secure construction and supply-chain verification remain a high-priority gap. |
| K13 | Performance and concurrency | Define a relevant baseline, identify contention or resource costs and check correctness under concurrent execution. | B5; B3 for quality trade-offs. | Shared-memory models, async runtimes, profiling and benchmarking methods need dedicated material. |
| K14 | Reliability and resilience | Model partial failure, retries, recovery and degraded behaviour, then choose evidence appropriate to the failure mechanism. | B5 and B3. | Operational stability patterns, incident learning and reliability practices beyond data systems remain gaps. |
| K15 | Continuous delivery and release readiness | Relate a change to reproducible build, verification, migration and recovery evidence; execute release work within existing authority. | B1; B5 for state transitions. | Detailed deployment pipelines, rollback constraints and environment-specific mechanisms need current practice research. |
| K16 | Observability and operability | Establish what runtime evidence can confirm behaviour or discriminate failures, including limits and cost. | B5 and B3 as partial targets. | Telemetry design, actionable alerts, operational diagnosis and small-system practice need additional sources. Service operation is not transferred to this project. |
| K17 | Configuration and dependency management | Trace effective configuration and dependency impact; preserve reproducibility and compatible upgrades. | B1; B2 for dependency constraints. | Package ecosystems, CI privileges, provenance and secrets handling need current official guidance. |
| K18 | Engineering economics and change scope | Choose the cheapest adequate investigation and smallest coherent change; explain alternatives, uncertainty and maintenance cost. | B1, B2 and B3. | Cost-effectiveness claims, small-team constraints and evidence against unnecessary work require challenge. No invented scoring model. |
| K19 | Human review and commitment points | Use existing authorisations, expose material unresolved choices and recognise consequential external effects. | B1 and B3 for collaboration and decisions. | Agent permissions, organisational decision rights and irreversible actions are governed by the charter and task context, not book prescriptions. |
| K20 | Documentation and technical handoffs | Supply concise, traceable explanations of behaviour, decisions, verification and limitations to the receiving maintainer or specialist. | B1 and B3. | Handoff effectiveness and domain-specific receiving requirements need broader evidence; no compulsory document bureaucracy is implied. |

Across all dimensions, specialist assurance is a boundary rather than a claim of general competence. The corpus must be tested against services, libraries, CLIs and client applications, not only distributed services. AI capability and provider selection cannot redefine these responsibilities.

## 4. Candidate-book comparison

Twelve distinct works were assessed. The assessment favours complementary decision depth over reputation or number of topics mentioned. Publication dates distinguish durable concepts from details requiring current verification; newer publication alone is not a selection advantage.

### 4.1 Selected candidates

| Candidate and evidence | Relevance, expected depth and practical contribution | Credibility, perspective, currency and limits | Access examined and selection rationale |
|---|---|---|---|
| **B1 — Software Engineering at Google**. Official [publication page][b1-home] and [contents][b1-toc]. | A lifecycle frame spanning review, tests, documentation, builds, dependency management and large changes. Candidate input for connecting a local edit to sustained maintainability. | An explicit account of practice in a large engineering organisation. It must be qualified for smaller teams, different tooling and external consumers; institutional practice is not independent proof of effectiveness. | Official full HTML available; contents and the opening of chapter 1 sampled. Selected for connective breadth around the four focused books. |
| **B2 — Working Effectively with Legacy Code**. [Publisher record and contents][b2-catalogue]. | Its organisation around difficult change situations makes it a candidate for deciding where to begin when dependencies and tests obstruct safe progress. | A focused practitioner treatment, with older tooling and substantial OO context. Durable change constraints justify assessing it despite age; examples must not become universal language or architecture rules. | Two official chapter samples partly read; full intended coverage unavailable. Selected because weakly understood, weakly tested code is central to the charter. |
| **B3 — Fundamentals of Software Architecture, second edition**. [Author bibliography][b3-author] and [edition-specific publisher contents][b3-catalogue]. | Architecture characteristics, modularity, styles, decisions and risk offer a wider design frame than local code organisation alone. Candidate input for option comparisons and decision records. | Practitioner synthesis by two architecture authors. Breadth is useful, but style classifications and heuristics require contextual testing. The 2025 edition fixes the source version; it does not prove its advice superior. | Metadata, overview and contents read; no direct chapter text examined. Selected to preserve architecture as an owned responsibility alongside implementation. |
| **B4 — Effective Software Testing**. [Publisher record and description][b4-catalogue]. | Specification, boundary and structural testing, contracts and property-based testing suggest depth in selecting cases and judging what checks can miss. | An academic/practitioner perspective centred on developer testing. Java examples and advertised cross-language applicability require qualification; no promise of defect-free software is adopted. | Description read; the linked excerpt failed to load. Selected for test-design depth beyond the lifecycle and testability emphasis of B1/B2. |
| **B5 — Designing Data-Intensive Applications, second edition**. [Author edition announcement][b5-author] and [publisher contents][b5-catalogue]. | Data models, encoding evolution, replication, transactions and consistency provide focused material for reasoning about state and failure. | A specialist systems perspective, useful precisely where local code reasoning is insufficient. The 2026 revision requires its own reading; neither first-edition memory nor named technologies establish current behaviour. | Metadata, overview and second-edition contents read; no direct chapter text examined. Selected for data and distributed-systems depth otherwise thin in the combination. |

### 4.2 Alternatives not selected for the foundational five

“Not selected” concerns corpus membership only. These books remain eligible supplementary sources. Their methods have not been rejected without examination.

| Candidate and edition | Contribution and useful perspective | Credibility, currency and limitation | Access and reason for not selecting |
|---|---|---|---|
| **C6 — Refactoring**, Martin Fowler with Kent Beck, second edition, 2018. [Author record][c6]. | Concrete behaviour-preserving transformations would deepen K03/K06 and provide more local refactoring precision. | First-party explanation of a focused transformation catalogue. Durable refactoring ideas still need language and tool qualification; the catalogue is narrower than the charter. | Author overview read; linked sample not examined. B2 takes the place because establishing a safe change path with inadequate tests is the earlier brownfield problem. Loss: systematic transformation depth. |
| **C7 — The Pragmatic Programmer**, David Thomas and Andrew Hunt, 20th Anniversary Edition, second edition, 2019. [Publisher record and contents][c7]. | Broad individual craft, including requirements, debugging, contracts and tools; a useful contrast to B1's organisational setting. | Experienced practitioner guidance, with heuristic rather than universal authority. The updated edition remains subject to current tool and ecosystem checks. | Publisher description and contents read; direct book text not examined. Replacing a focused book would reduce depth; replacing B1 would weaken the chosen lifecycle frame. Loss: a stronger individual/small-team perspective and explicit debugging coverage. |
| **C8 — A Philosophy of Software Design**, John Ousterhout, second edition, 2021. [Author record][c8]. | A focused perspective on complexity, module design and interfaces; useful for challenging architectural and construction rules. | Author-developed design arguments, including explicit disagreement with other advice. That contrast is valuable, but argument strength must be assessed through reading and examples. | Author description and edition notes read; book excerpt not examined. B3 addresses a wider architectural responsibility. Loss: concentrated module-level design reasoning and a sharper counterpoint. |
| **C9 — Release It!**, Michael Nygard, second edition, 2018. [Publisher record and contents][c9]. | Production stability, failure patterns, configuration and release concerns would strengthen K14–K16. | Practitioner experience supplies operational perspective; examples and deployment mechanisms need current verification. It cannot by itself establish SRE ownership or service policy. | Publisher description and contents read; book text not examined. B5 wins the contested systems place for state, schema and consistency reasoning. Loss: greater operational stability and release-pattern depth. |
| **C10 — Secure by Design**, Dan Bergh Johnsson, Daniel Deogun and Daniel Sawano, 2019. [Publisher record][c10]. | Security through domain modelling, validation and design would deepen K03/K12 rather than treating security only as a final check. | Practitioner design perspective with Java/OO examples. Useful security depth, but not a complete secure-development lifecycle or specialist assurance basis. | Publisher description read; direct book content not examined. The five places prioritise broader change, architecture, testing and state foundations. Loss: dedicated secure-construction depth; security remains a high-priority gap. |
| **C11 — Continuous Delivery**, Jez Humble and David Farley, first edition, published 2010; copyright 2011. [Publisher record and contents][c11]. | Pipeline, configuration, acceptance, deployment and data-change concerns would deepen K15/K17 and release evidence. | Focused practitioner treatment of delivery. Durable process reasoning deserves examination, while the age makes current platform details a clear verification need. | Publisher contents read; linked chapter sample not examined. B1 gives the selected set a broader connection between code, review and sustained change. Loss: detailed delivery-method depth. |
| **C12 — Software Requirements**, Karl Wiegers and Joy Beatty, third edition, 2013. [Publisher record and contents][c12]. | Elicitation, specification, validation and requirements change would strengthen K01/K18/K19 and product-to-engineering handoffs. | A specialist requirements treatment with wider contexts than coding. Its methods need proportionate adaptation to the task and repository rather than default document production. | Publisher description and contents read; direct book text not examined. The charter consumes approved product intent and prioritises engineering change; this place would displace architecture, verification or state depth. Loss: systematic requirements practice. |

### 4.3 Combination-level reasoning

The selection is not five independent “best book” judgements. Each retained place has a marginal purpose relative to the other four:

| Contested place | Decision | Gain retained | Cost consciously accepted |
|---|---|---|---|
| B1 versus C7 or C11 | Keep the lifecycle frame. | A connective source for review, maintainability and engineering infrastructure around local work. | Less individual craft/debugging emphasis than C7 and less delivery specialisation than C11. |
| B2 versus C6 | Prioritise entry into constrained brownfield work. | Research directed at creating enough understanding and verification to make a change. | Less catalogue-level refactoring detail. |
| B3 versus C8 | Preserve system-level architecture depth. | A source for relating technical choices to quality constraints and communication. | Less concentrated module-design argument. |
| B4 versus relying on testing chapters in B1/B2 | Keep a dedicated test-design source. | The adequacy of selected checks receives its own investigation. | Some repeated testing context occupies scarce corpus capacity. |
| B5 versus C9 | Prioritise state and consistency. | A focused source for data obligations that cannot be inferred from ordinary code quality. | Operational stability and release depth remain incomplete. |
| C10 or C12 replacing a focused selected book | Retain the current combination for this revision. | The charter's architecture, verification and state responsibilities each retain a substantial candidate source. | Security and requirements need explicit supplementary investigation, not token mentions. |

These comparisons are research judgements based on examined scope evidence. Direct reading may show a contribution to be weaker than expected. Record that honestly and revise the corpus explicitly if needed; do not force every selected book to produce a skill.

## 5. Material overlap and perspective limits

All ten pairs in the selected set have been considered below. These are expected intersections and Stage 3 questions, not claims of agreement or contradiction between unread passages.

| Pair | Expected intersection | Why retain it; what direct reading must distinguish |
|---|---|---|
| B1 / B2 | Maintaining and changing existing software. | Repository-wide engineering practice versus local constraints on making a change. Determine when an incremental repair needs broader coordination. |
| B1 / B3 | Design, quality trade-offs and team decisions. | Sustained engineering context versus explicit architectural analysis. Check whether a proposed decision process is proportionate for small changes. |
| B1 / B4 | Testing. | Verification in an engineering system versus construction of effective checks. Merge repeated general advice only after examining its assumptions. |
| B1 / B5 | Long-lived systems, compatibility and scale. | Organisational/change context versus state and distributed semantics. Do not infer that Google-scale mechanisms are prerequisites for sound engineering. |
| B2 / B3 | Dependencies, boundaries and structural change. | Constraints of the current implementation versus alternative architecture. Investigate when restructuring is justified instead of assuming either local repair or redesign always wins. |
| B2 / B4 | Testability and regression protection. | Establishing a place to test versus deciding which evidence is adequate. Distinguish existing behaviour from intended acceptance. |
| B2 / B5 | Preserving behaviour across existing interfaces and state. | Code-level change constraints versus data-system obligations. Check where a local test harness cannot represent migration or concurrency risk. |
| B3 / B4 | Quality requirements and verification. | Architectural claims need evidence; testability can constrain design. Identify what a unit-level result cannot establish about the system. |
| B3 / B5 | System qualities and architectural choices. | Broad option framing versus a deeper state-oriented analysis. Keep the applicability boundary visible for systems with little distributed state. |
| B4 / B5 | Correctness and failure evidence. | General test design versus nondeterminism and distributed behaviour. Investigate suitable oracles and limits rather than treating passing tests as proof. |

Testing overlap is intentional: arranging verification, enabling it in difficult code and designing useful cases are different research needs. Architecture/state overlap is also useful when it exposes different levels of reasoning. Repetition of a slogan is neither additional coverage nor independent corroboration.

The set has perspective limitations. It is English-language, largely practitioner-led, and gives substantial attention to backend systems and OO examples. B4 adds a different teaching and research perspective, but the corpus as a whole is not an empirical evidence base. Small teams, client applications, accessibility, embedded systems and specialist assurance are underrepresented. No selected book establishes the reliability of AI coding agents or current provider capabilities.

Stage 3 should retain separate source locations for apparently shared ideas, identify differing prerequisites and record actual tensions only after reading. Stage 4 must seek counterexamples and independent evidence, including cases where the cost of a recommended practice exceeds its benefit.

## 6. Remaining domain gaps and disposition

These gaps do not remove charter responsibilities. They define work that later stages must address or explicitly bound. Proposed sources below are research leads, not already accepted findings.

| Gap | Affected dimensions | Required follow-up and completion evidence |
|---|---|---|
| Technical requirements and acceptance under conflicting or incomplete intent | K01, K18–K20 | Stage 4: examine specialist requirements practice, including C12 where useful. Establish how to distinguish an engineering clarification from a product decision, with task-sized acceptance examples. |
| Security engineering and software supply chain | K03, K12, K17 | Stage 4: directly examine then-current NIST secure-development guidance and applicable OWASP/official ecosystem material; consider C10. Record threat assumptions, bounded verification and specialist escalation. |
| General debugging, performance diagnosis and shared-memory concurrency | K08, K13 | Stage 4: investigate causal debugging and measurement methods; use primary runtime documentation for memory/concurrency semantics. Require evidence that discriminates causes and a justified repair scope. |
| Reliability beyond data systems, observability and technical release mechanics | K14–K16 | Stage 4: examine operational practice, C9/C11 where useful and current official deployment guidance. Separate software readiness evidence from authority to operate or launch a service. |
| Language, platform and configuration details | K03, K10, K13, K17 | Stage 4 establishes general obligations; later capability and pack research resolves ecosystem-specific mechanisms. Do not promote book examples into universal commands or defaults. |
| Client applications, accessibility and specialist systems | K01–K03, K07, K14 | Challenge the backend/OO bias with client, library and CLI cases. Explicitly bound embedded, real-time, safety-critical, ML and data-domain assurance; involve the appropriate specialist sources. |
| Maintenance economics, team constraints and review effectiveness | K04, K06, K09, K18, K20 | Stage 4: seek empirical findings and counterexamples to practitioner prescriptions. Assess proportionate effort, small-team applicability and whether review or documentation actually improves the intended outcome. |
| Verification effectiveness and limits | K07–K09, K14 | Stage 3 formulates claims from direct reading; Stage 4 challenges test adequacy, oracles, flaky/nondeterministic checks and false confidence. Later eval design must measure relevant failures, not merely count tests. |
| Agent behaviour, permissions and evidence integrity | K05, K07–K09, K19–K20 | Retain charter authority rules now. Use Stage 4 to identify professional obligations and Stage 8 for the current AI/tool landscape; later benchmarks must test agent-specific failure modes and truthful reporting. |

No numerical coverage score is assigned. A topic appearing in a contents page is not evidence that its practical depth is sufficient. Stage 3 must revisit this map using actual reading, and Stage 4 must revisit it independently of what the books happen to discuss.

## 7. Edition control and source identifiers

Bibliographic identity is fixed for `SE-CORPUS-001`. Print ISBNs are identifiers, not download locations or evidence of ownership.

| ID | Stable bibliographic identifier | Edition check |
|---|---|---|
| B1 | Official Abseil publication page and HTML edition. | The publication page identifies the March 2020 work and links the complete HTML contents. |
| B2 | ISBN `9780131177055`. | The publisher distinguishes September 2004 publication from 2005 copyright. This record uses the publication year. |
| B3 | Print ISBN `9781098155511`; O'Reilly catalogue identifier `9781098175504`. | The author bibliography and edition-specific catalogue both identify the second edition, 2025. |
| B4 | ISBN `9781633439931`. | The publisher identifies the March 2022 book. No unverified edition number is assigned. |
| B5 | Print ISBN `9781098119065`; O'Reilly catalogue identifier `9781098119058`. | The author's second-edition announcement and publisher catalogue establish the 2026 revision and both authors. |

An edition ambiguity was resolved during access checking: the general DDIA companion site's contents link led to the first-edition catalogue. The B5 record instead uses the verified second-edition catalogue linked here. Likewise, B3 uses its second-edition catalogue rather than treating the original companion site as evidence of revised contents. No first-edition findings are silently attributed to either selected second edition.

## 8. Source-access and reading register

All entries have **selected** origin, were checked on **13 September 2026**, and refer to the author/edition identities in sections 1 and 7. No user-supplied copy is registered. Only independently written research and public bibliographic references belong in this repository; book files and private access locations do not.

| ID | Access status | Public location and material actually examined | Intended contribution and reading limitation | Access action for Stage 3 |
|---|---|---|---|---|
| B1 | **full text available** | Official [landing page][b1-home], [complete contents][b1-toc] and the opening section of [chapter 1][b1-ch1]. The chapter was sampled to verify direct-text access. | Lifecycle and sustainable-change contribution described above. The remainder has not been read for this bootstrap; availability is not extraction evidence. | Use the official HTML and record the sections actually examined. No missing-copy request is currently needed. |
| B2 | **relevant excerpts available** | Publisher contents plus the first pages of official chapter 1 and chapter 4 samples: [Four Reasons to Change Software][b2-ch1] and [A Huge Sheet of Text][b2-ch4]. Later pages of these paginated samples were not examined. | Brownfield understanding, change constraints and verification support. The sampled openings do not establish the book's methods or enough context for the intended contribution. | Obtain an accessible first-edition copy, or coherent excerpts covering the intended contribution and its assumptions. The present samples alone are inadequate. |
| B3 | **secondary material only** | [Author bibliography][b3-author] and [second-edition publisher overview/contents][b3-catalogue]. No chapter body examined. | Architectural reasoning and decision trade-offs. Contents identify reading targets but cannot support extraction of arguments or methods. | Obtain accessible second-edition text or sufficiently contextual excerpts. |
| B4 | **secondary material only** | [Publisher description and metadata][b4-catalogue]. The linked reading sample returned an access error and was not read. | Test selection, adequacy and maintainability. Description-only evidence cannot establish the method or its limits. | Obtain accessible 2022 text or sufficiently contextual excerpts. Do not infer ownership from generic account controls on the publisher page. |
| B5 | **secondary material only** | [Second-edition announcement][b5-author] and [second-edition publisher overview/contents][b5-catalogue]. No chapter body examined. | Data evolution, concurrency and distributed failure. Neither earlier-edition familiarity nor catalogue text supplies direct evidence for this edition. | Obtain accessible second-edition text or sufficiently contextual excerpts. |

There is **one full-text source, one excerpt source and three metadata/description sources**. All five still require substantive Stage 3 reading. Four require additional accessible material for the scope intended here. A full copy is the simplest way to preserve context; the process also permits relevant excerpts when their scope and limitations genuinely support the intended contribution.

No purchase, private-account entitlement or successful full-text retrieval is claimed for B2–B5. Request suitable copies or access when starting extraction. Accessible B1 work can begin independently, but Stage 3 cannot be marked complete while any selected contribution is supported only by descriptions or inadequate excerpts. If access cannot be obtained, record a proposed corpus revision and its consequences instead of silently replacing a title or substituting summaries.

## 9. Supplied-book decisions and corpus revision

### 9.1 Decision log

There are no supplied books to retain, remove, replace or demote. The canonical process permits selection into empty slots without another approval. The decision reference for all entries is the user's request to start the next stage, the empty supplied-book inventory in section 2 and the Stage 2 selection rule.

| Decision | Book | Action and rationale | Approval status | Date |
|---|---|---|---|---|
| S2-01 | B1 | Add to empty slot for the lifecycle connection. | No separate approval required; no supplied book displaced. | 2026-09-13 |
| S2-02 | B2 | Add to empty slot for constrained brownfield work. | No separate approval required; no supplied book displaced. | 2026-09-13 |
| S2-03 | B3 | Add to empty slot for architectural reasoning. | No separate approval required; no supplied book displaced. | 2026-09-13 |
| S2-04 | B4 | Add to empty slot for test-design depth. | No separate approval required; no supplied book displaced. | 2026-09-13 |
| S2-05 | B5 | Add to empty slot for state and distributed behaviour. | No separate approval required; no supplied book displaced. | 2026-09-13 |

**Substitutions proposed:** none. **Substitutions applied:** none. **Pending required permissions:** none. Alternatives C6–C12 were researched candidates, not supplied corpus members; leaving them outside the foundational five does not demote a user-provided book.

### 9.2 Revision rule

`SE-CORPUS-001` is the initial selection revision, dated 13 September 2026, based on Stage 1 at the starting commit. It supersedes no earlier corpus on this branch. Its members are B1–B5 with the editions fixed above.

A later membership or edition change must receive a new corpus revision, preserve this decision history and identify affected reading, findings, challenge work and design artefacts. If a user supplies a book or a proposed change would remove a supplied book, apply the governing permission rule explicitly. Record expected gain, potential loss, alternatives and the actual decision; silence is not approval. Reading progress or a repaired access link alone does not silently change the corpus.

## 10. Stage 3 handoff

The next dependent stage is [Stage 3: Extract and Reconcile the Five-Book Corpus](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#10-stage-3--five-extract-and-reconcile-the-five-book-corpus). It must consume this record and the original charter, obtain the missing material and examine each book on its own terms before combining findings.

| ID | Initial reading focus, subject to the actual text | Question the extraction must answer |
|---|---|---|
| B1 | Time and trade-offs; review and documentation; testing; dependencies and large changes; delivery. | Which practices transfer to the consuming repository, with what prerequisites and justified effort? |
| B2 | Change and feedback; seams and dependency constraints; understanding existing code; regression confidence. | How can an agent establish a responsible path through a poorly understood system without expanding the change unnecessarily? |
| B3 | Architectural thinking, modularity and quality characteristics; choice of approach; decisions and risk. | What evidence and alternatives justify an architectural decision at the scale of the requested change? |
| B4 | Test derivation, coverage and contracts; testing levels; design for testing and test maintenance. | How should useful checks be chosen, and what failures or obligations do those checks leave unresolved? |
| B5 | Nonfunctional requirements; encoding/evolution; transactions; distributed failure and consistency. | Which state and failure obligations require stronger reasoning than a local passing test, and how should that affect a change? |

These are reading priorities, not assertions that the material has been extracted. Stage 3 must record actual chapter/section locations, reading coverage, assumptions, applicability, failure modes, repair strategies and disposition. Each material finding needs a traceable path to a provisional engineering capability, responsibility, workflow implication, evaluation criterion and possible benchmark case. A book may contribute less than anticipated.

Reconciliation must distinguish repeated advice from independent support, preserve context-dependent alternatives and expose unresolved contradictions. It should revisit K01–K20 and the gaps in section 6. Neither five books nor twenty dimensions determines the number of skills, commands, packs or examples. Stage 4 then challenges the resulting model through wider professional and empirical research; no accepted capability architecture is created by this selection record.

## 11. Exit review and completion evidence

| Required Stage 2 output or gate | Evidence in this record | Result |
|---|---|---|
| Knowledge-coverage map | Section 3: twenty charter-derived dimensions, required decision depth, planned targets and residual needs; zero supplied-book contribution recorded. | Complete for selection. |
| Candidate-book comparison | Section 4: twelve distinct works assessed for relevance, depth, practical contribution, perspective, credibility/limits, currency and access. | Complete. |
| Exactly five selected books | Section 1: B1–B5; section 7 fixes bibliographic identity. Editions are not counted as extra works. | Complete. |
| Selected and rejected rationale | Sections 4.1–4.3: individual assessments and marginal contribution trade-offs. | Complete. |
| Material-overlap analysis | Section 5: all ten selected pairs, useful overlap and common perspective limitations. | Complete as selection hypotheses. |
| Remaining domain gaps | Sections 3 and 6: uncovered depth and assigned later investigation or specialist boundary. | Complete for this revision. |
| Source-access register | Sections 7–8: origin, identity, location, exact access status, examined scope and four acquisition needs. | Complete; access is insufficient for completed extraction. |
| Supplied-book substitution decision log | Section 9: five additions, zero supplied removals, zero pending required permissions. | Complete. |
| Corpus revision identifier | `SE-CORPUS-001`, with date, baseline and revision rule. | Complete. |

Validation confirmed five selected identities, twenty coverage rows, twelve candidate assessments, ten distinct overlap pairs and five access entries using the prescribed states. Reference definitions and local document links resolve. The Stage 1 record and root README match their baseline Git blob hashes. Review against the governing Stage 2 requirements found all nine expected outputs present and no pending substitution decision.

The Stage 2 exit criteria are satisfied. This record and the research-log index are the stage deliverables. The charter and governing specification remain the inputs; no production scaffold, source-book files or later-stage completion claims are introduced. Selection completion does not imply that the corpus has been read, reconciled, empirically challenged or implemented.

[family-process]: https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/bootstrap/domain-research-process.md
[dora]: https://dora.dev/capabilities/continuous-delivery/
[google-review]: https://google.github.io/eng-practices/review/reviewer/looking-for.html
[nist]: https://csrc.nist.gov/pubs/sp/800/218/final
[b1-home]: https://abseil.io/resources/swe-book
[b1-toc]: https://abseil.io/resources/swe-book/html/toc.html
[b1-ch1]: https://abseil.io/resources/swe-book/html/ch01.html
[b2-catalogue]: https://www.informit.com/store/working-effectively-with-legacy-code-9780131177055
[b2-ch1]: https://www.informit.com/articles/article.aspx?p=359418
[b2-ch4]: https://www.informit.com/articles/article.aspx?p=359417
[b3-author]: https://www.developertoarchitect.com/books.html
[b3-catalogue]: https://www.oreilly.com/library/view/fundamentals-of-software/9781098175504/
[b4-catalogue]: https://www.manning.com/books/effective-software-testing
[b5-author]: https://martin.kleppmann.com/2026/03/24/designing-data-intensive-applications-2e.html
[b5-catalogue]: https://www.oreilly.com/library/view/designing-data-intensive-applications/9781098119058/
[c6]: https://martinfowler.com/books/refactoring.html
[c7]: https://pragprog.com/titles/tpp20/the-pragmatic-programmer-20th-anniversary-edition/
[c8]: https://web.stanford.edu/~ouster/cgi-bin/book.php
[c9]: https://pragprog.com/titles/mnee2/release-it-second-edition/
[c10]: https://www.manning.com/books/secure-by-design
[c11]: https://www.informit.com/store/continuous-delivery-reliable-software-releases-through-9780321601919
[c12]: https://www.microsoftpressstore.com/store/software-requirements-9780735679665
