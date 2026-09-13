# Stage 2: Knowledge Coverage and Five-Book Corpus

**Project:** `software-engineering-skills`  
**Stage:** 2, Seed: Map Knowledge Coverage and Select Five Complementary Books  
**Status:** Complete for revised selection; all five supplied books available; direct corpus extraction and broader challenge remain unperformed  
**Version:** 1.1  
**Date:** 13 September 2026  
**Execution branch:** `feat/bootstrap-2`  
**Starting revision (initial selection):** `17cbe59a818a29dd5977e69df486789245a8d0f1`  
**Revision baseline:** `f0a948b918fcac93fb371c964d555ab211867bb2`  
**Current corpus revision:** `SE-CORPUS-002`, superseding `SE-CORPUS-001`  
**Governing bootstrap:** [Software Engineering Skills bootstrap v1.1, Stage 2](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#9-stage-2--seed-map-knowledge-coverage-and-select-five-complementary-books)

## 1. Selection decision

Retain these **exactly five user-supplied books** as the foundational corpus. The user explicitly replaced *Effective Software Testing* with *Software Requirements Essentials*. The supplied DDIA is the first edition, so that actual edition is now the reading source. The original selection remains traceable in section 9 and the [initial Stage 2 commit][initial-selection]. Individual claims still require direct reading and challenge.

| ID | Selected book | Authors | Edition and publication year | Intended contribution to this project |
|---|---|---|---|---|
| B1 | [Software Engineering at Google][b1-home] | Titus Winters, Tom Manshreck and Hyrum Wright | Original edition, 2020 | Engineering changes over time: the connection between code, review, verification, dependencies and delivery. |
| B2 | [Working Effectively with Legacy Code][b2-catalogue] | Michael C. Feathers | First edition, published 2004; copyright 2005 | Entering and changing an existing system when understanding and test support are inadequate. |
| B3 | [Fundamentals of Software Architecture][b3-catalogue] | Mark Richards and Neal Ford | Second edition, 2025 | Making and communicating architectural choices under competing quality constraints. |
| B4 | [Software Requirements Essentials: Core Practices for Successful Business Analysis](#8-source-access-and-reading-register) | Karl Wiegers and Candase Hokanson | 2023 edition | Understanding the problem, clarifying requirements and acceptance, and managing decisions and change. |
| B5 | [Designing Data-Intensive Applications][b5-catalogue] | Martin Kleppmann | First edition, 2017 | Reasoning about persistent state, compatibility, concurrent changes and distributed failure. |

The combination connects requirements, architecture, implementation and maintenance with the engineering of stateful systems. Requirements now have a dedicated foundation. Verification remains an owned responsibility, with B1 and B2 as initial sources; specialised test-design depth becomes a more explicit supplementary research need. This follows the user's preference for a broader software-engineering foundation. It does not imply that five books cover the discipline completely.

All five supplied PDFs open and yield readable text at the inspected locations. Their status is **full text available**. The previous acquisition needs are resolved for `SE-CORPUS-002`; meaningful Stage 3 reading and extraction remain to be done. Section 8 distinguishes access checks from reading coverage.

## 2. Inputs, authority and evidence boundary

### 2.1 Governing inputs

This record consumes the completed [Stage 1 domain charter](2026-09-12-stage-01-project-goal-and-domain-boundary.md), the domain bootstrap's Stage 2 requirements and the canonical [Domain Research Process][family-process] at `production-skills` revision `20979e0c68ac4b37433374df7fe10ceb2e7ee69a`.

The charter owns technical requirements and acceptance, architecture, construction, maintenance, diagnosis, verification, review and technical release readiness. Brownfield work is the primary proving ground; greenfield work remains included. The consuming repository supplies product intent, constraints, tools and authority. Specialist judgements and live-service ownership remain with the appropriate owners.

At the initial selection revision, no book titles or files had been supplied. The agent filled all five empty places under the governing process. The user subsequently supplied five PDFs and explicitly replaced the testing book with the requirements book. All current members therefore have supplied origin and must be retained unless the user authorises a later removal, replacement or demotion. The planned contributions in section 3 now describe those supplied books. No selection, source access or stage completion from the separate `feat/bootstrap` branch is inherited.

The original next-stage request authorised Stage 2 and its commit on `feat/bootstrap-2`. The subsequent book submission authorises this selection/access revision, including the explicit requirements-book substitution. Registering supplied material does not establish later-stage completion or permission to redistribute the books.

### 2.2 Bounded reconnaissance

The charter supplies the responsibility map. Three official sources were used as limited checks that the map extends beyond writing code:

| Reconnaissance source | Directly examined material | Implication for source selection | Limit |
|---|---|---|---|
| [DORA: Continuous delivery][dora] | Capability page describing delivery and supporting practices. | Keep deployment readiness, test automation, configuration and operational feedback in the coverage map. | Does not establish which book combination is best or validate a future skill. |
| [Google: What to look for in a code review][google-review] | Reviewer guidance on design, functionality, complexity, tests and documentation. | Include review of system fit and verification quality, not just style. | One organisation's guidance; review policy remains repository-specific. |
| [NIST SP 800-218, SSDF v1.1][nist] | Official publication record and abstract, February 2022. | Treat security as part of the development lifecycle and retain a specialist research gap. | The full framework was not examined here; no claim that this is the latest revision or a compliance assessment. |

The Stage 1 IEEE SWEBOK access limitation remains recorded. No unavailable SWEBOK chapter findings are used in this selection.

Initial reconnaissance stopped when twenty responsibility dimensions could distinguish twelve serious book candidates. The supplied requirements book adds a thirteenth distinct work to the comparison. This revision checks its identity, contents and expected contribution without restarting the broader search. Empirical validation, current standards analysis, detailed workflows and specialist practice research remain Stage 4 work.

### 2.3 What the evidence supports

The original author/publisher evidence remains useful for candidate comparison. This revision directly checks the supplied PDFs' title/copyright pages and samples their text. B4's contents, foreword and author information were also examined to assess the replacement. Candidate contributions and overlaps below remain **selection hypotheses** to test in Stage 3; these access and scope checks do not complete extraction.

The mandated access label `secondary material only` means that only metadata, descriptions or contents are available for this record. Some of those pages are first-party bibliographic sources. The label distinguishes them from directly examined book content, rather than claiming they are third-party accounts.

## 3. Knowledge-coverage map

The map is derived from the charter, not divided into one topic per book. Every row needs enough depth to guide an engineering decision and judge its evidence; vocabulary recognition is insufficient. The final column identifies what the selected corpus cannot yet be relied upon to supply. Entries under books are **planned reading targets**, not verified coverage. All B1–B5 targets now refer to the supplied books in `SE-CORPUS-002`; no row implies completed extraction.

| ID | Responsibility | Required decision depth | Planned corpus targets | Remaining need or boundary |
|---|---|---|---|---|
| K01 | Requirements and acceptance | Turn approved intent into observable examples, constraints and exclusions; identify ambiguity that changes the implementation. | B4 for problem framing, elicitation, analysis, specification and validation; B3 for quality constraints. | Test the depth of B4's concise treatment and the boundary between engineering clarification and product/UX decisions. |
| K02 | Design and architecture | Compare local and system-level alternatives, preserve system fit and explain quality, coupling and migration trade-offs. | B3; B4 for quality requirements; B5 for state-related choices. | Client, embedded and specialist architectures need contextual evidence. No mandated style follows from a book. |
| K03 | Construction and code quality | Produce coherent implementation using repository conventions; reason about interfaces, errors, dependencies and readability. | B1 and B2; B4 for the obligations implementation must satisfy. | Language semantics, type systems, resource ownership and framework idioms need current, ecosystem-specific sources. |
| K04 | Maintenance and evolution | Distinguish corrective, adaptive, preventive and improvement work; plan migration, deprecation and retirement without losing obligations. | B1, B2 and B5; B4 for requirements change and impact. | Platform upgrades, support policy and retirement authority are context-dependent. |
| K05 | Brownfield understanding | Build an evidence-backed model of relevant behaviour, dependencies and uncertainty before changing code. | B2; B1 for repository-scale context. | Runtime investigation, undocumented integrations and non-OO systems require additional examples and challenge. |
| K06 | Refactoring and technical debt | Establish what must remain invariant, justify scope and distinguish repair from speculative restructuring. | B2 and B3, with B1 for sustained change. | Detailed transformation catalogues and evidence for economic prioritisation remain supplementary research. |
| K07 | Testing and test quality | Derive useful cases and oracles, choose verification levels, assess omissions and maintain the checks themselves. | B1 for verification practice; B2 for weak test support; B4 for requirements validation and acceptance. | Dedicated test-design depth, boundary/structural/property-based testing, flakiness and adequacy claims need supplementary research. |
| K08 | Debugging and root-cause diagnosis | Reproduce or substantiate failure, discriminate hypotheses, trace causality and confirm a sufficient repair. | B2 as a partial starting point; B5 for distributed failures. | No selected book is a general debugging foundation. Profiling, tracing and concurrency diagnosis need dedicated investigation. |
| K09 | Code review | Assess intent, design, correctness, compatibility and test quality; distinguish blocking defects from preferences. | B1; B3 for design questions; B4 for requirements review and acceptance alignment. | Requirements review does not replace code/test review. Review effectiveness and AI-generated changes need broader evidence. |
| K10 | API and contract evolution | Identify consumers, state compatibility obligations and design transitions without silently changing public behaviour. | B1 and B5; B2 for existing interfaces. | Protocol-specific compatibility, SDK packaging and consumer-driven migration need current sources. |
| K11 | Data and schema evolution | Reason about invariants, transactions, schema transitions, backfills, recovery and irreversible effects. | B5; B4 for data requirements and business rules. | Concrete database engines, data meaning, retention rules and production migration procedures remain specialist/contextual work. |
| K12 | Security engineering | Recognise security-relevant changes, preserve controls, verify bounded fixes and escalate unresolved specialist judgements. | B3 and B5 for constraints; B1 for lifecycle integration; B4 for quality requirements. | No dedicated security foundation is selected. Threat modelling, secure construction and supply-chain verification remain a high-priority gap. |
| K13 | Performance and concurrency | Define a relevant baseline, identify contention or resource costs and check correctness under concurrent execution. | B5; B3 for quality trade-offs. | Shared-memory models, async runtimes, profiling and benchmarking methods need dedicated material. |
| K14 | Reliability and resilience | Model partial failure, retries, recovery and degraded behaviour, then choose evidence appropriate to the failure mechanism. | B5 and B3. | Operational stability patterns, incident learning and reliability practices beyond data systems remain gaps. |
| K15 | Continuous delivery and release readiness | Relate a change to reproducible build, verification, migration and recovery evidence; execute release work within existing authority. | B1; B5 for state transitions. | Detailed deployment pipelines, rollback constraints and environment-specific mechanisms need current practice research. |
| K16 | Observability and operability | Establish what runtime evidence can confirm behaviour or discriminate failures, including limits and cost. | B5 and B3 as partial targets. | Telemetry design, actionable alerts, operational diagnosis and small-system practice need additional sources. Service operation is not transferred to this project. |
| K17 | Configuration and dependency management | Trace effective configuration and dependency impact; preserve reproducibility and compatible upgrades. | B1; B2 for dependency constraints. | Package ecosystems, CI privileges, provenance and secrets handling need current official guidance. |
| K18 | Engineering economics and change scope | Choose the cheapest adequate investigation and smallest coherent change; explain alternatives, uncertainty and maintenance cost. | B1, B2 and B3; B4 for problem boundaries, priorities and change impact. | Cost-effectiveness claims, small-team constraints and evidence against unnecessary work require challenge. No invented scoring model. |
| K19 | Human review and commitment points | Use existing authorisations, expose material unresolved choices and recognise consequential external effects. | B1 and B3 for collaboration; B4 for stakeholders, decision makers and requirements agreements. | Agent permissions, organisational decision rights and irreversible actions are governed by the charter and task context, not book prescriptions. |
| K20 | Documentation and technical handoffs | Supply concise, traceable explanations of behaviour, decisions, verification and limitations to the receiving maintainer or specialist. | B1 and B3; B4 for requirements representations, shared terminology and changes. | Handoff effectiveness and domain-specific receiving requirements need broader evidence; no compulsory document bureaucracy is implied. |

Across all dimensions, specialist assurance is a boundary rather than a claim of general competence. The corpus must be tested against services, libraries, CLIs and client applications, not only distributed services. AI capability and provider selection cannot redefine these responsibilities.

## 4. Candidate-book comparison

Thirteen distinct works have now been assessed: the original twelve plus the user-supplied requirements book. The replaced testing book remains in the alternative comparison as C13. B4 is a corpus-place identifier whose membership changed between revisions; its old identity is preserved in section 9. The assessment favours complementary decision depth over reputation or number of topics mentioned.

### 4.1 Selected candidates

| Candidate and evidence | Relevance, expected depth and practical contribution | Credibility, perspective, currency and limits | Access examined and selection rationale |
|---|---|---|---|
| **B1 — Software Engineering at Google**. Official [publication page][b1-home], [contents][b1-toc] and supplied PDF B1. | A lifecycle frame spanning review, tests, documentation, builds, dependency management and large changes. Candidate input for connecting a local edit to sustained maintainability. | An explicit account of practice in a large engineering organisation. It must be qualified for smaller teams, different tooling and external consumers; institutional practice is not independent proof of effectiveness. | Full PDF and official HTML available; identification and sampled text checked. Retained for connective breadth, including verification practice. |
| **B2 — Working Effectively with Legacy Code**. [Publisher record and contents][b2-catalogue] and supplied PDF B2. | Its organisation around difficult change situations makes it a candidate for deciding where to begin when dependencies and tests obstruct safe progress. | A focused practitioner treatment, with older tooling and substantial OO context. Durable change constraints justify assessing it despite age; examples must not become universal language or architecture rules. | Full supplied PDF now available; identification and sampled text checked. Retained because weakly understood, weakly tested code is central to the charter. |
| **B3 — Fundamentals of Software Architecture, second edition**. [Author bibliography][b3-author], [publisher contents][b3-catalogue] and supplied PDF B3. | Architecture characteristics, modularity, styles, decisions and risk offer a wider design frame than local code organisation alone. Candidate input for option comparisons and decision records. | Practitioner synthesis by two architecture authors. Breadth is useful, but style classifications and heuristics require contextual testing. The 2025 edition fixes the source version; it does not prove its advice superior. | Full supplied PDF now available; second-edition identity and sampled text checked. Retained to preserve architecture as an owned responsibility. |
| **B4 — Software Requirements Essentials**. Supplied PDF B4, title/copyright pages, contents, foreword and author information; see section 8. | Problem framing, elicitation, analysis, specification, validation and requirements change connect intent to implementation and acceptance. The contents also identify quality attributes, stakeholders and decision makers. | Practitioner synthesis by Wiegers and Hokanson, published 2023. The foreword describes deliberately concise treatment; deeper examples and method comparisons may require supplementary sources. Its business-analysis perspective strengthens the engineering handoff without transferring product authority. | Full supplied PDF available. Selected through the user's explicit substitution, filling a foundational requirements gap; systematic test-design depth moves to supplementary research. |
| **B5 — Designing Data-Intensive Applications, first edition**. Supplied PDF B5 and [first-edition catalogue][b5-catalogue]. | Persistent state, evolution, transactions and distributed failure remain the intended contribution; first-edition scope must be examined directly. | A specialist systems perspective where local code reasoning is insufficient. The supplied 2017 edition needs explicit current-practice challenge. No claims from the 2026 revision may be attributed to this text. | Full supplied first-edition PDF available; identity and sampled text checked. Retained as the user's supplied edition, preserving state-oriented depth. |

### 4.2 Alternatives not selected for the foundational five

“Not selected” concerns corpus membership only. These books remain eligible supplementary sources. Their methods have not been rejected without examination.

| Candidate and edition | Contribution and useful perspective | Credibility, currency and limitation | Access and reason for not selecting |
|---|---|---|---|
| **C6 — Refactoring**, Martin Fowler with Kent Beck, second edition, 2018. [Author record][c6]. | Concrete behaviour-preserving transformations would deepen K03/K06 and provide more local refactoring precision. | First-party explanation of a focused transformation catalogue. Durable refactoring ideas still need language and tool qualification; the catalogue is narrower than the charter. | Author overview read; linked sample not examined. B2 takes the place because establishing a safe change path with inadequate tests is the earlier brownfield problem. Loss: systematic transformation depth. |
| **C7 — The Pragmatic Programmer**, David Thomas and Andrew Hunt, 20th Anniversary Edition, second edition, 2019. [Publisher record and contents][c7]. | Broad individual craft, including requirements, debugging, contracts and tools; a useful contrast to B1's organisational setting. | Experienced practitioner guidance, with heuristic rather than universal authority. The updated edition remains subject to current tool and ecosystem checks. | Publisher description and contents read; direct book text not examined. Replacing a focused book would reduce depth; replacing B1 would weaken the chosen lifecycle frame. Loss: a stronger individual/small-team perspective and explicit debugging coverage. |
| **C8 — A Philosophy of Software Design**, John Ousterhout, second edition, 2021. [Author record][c8]. | A focused perspective on complexity, module design and interfaces; useful for challenging architectural and construction rules. | Author-developed design arguments, including explicit disagreement with other advice. That contrast is valuable, but argument strength must be assessed through reading and examples. | Author description and edition notes read; book excerpt not examined. B3 addresses a wider architectural responsibility. Loss: concentrated module-level design reasoning and a sharper counterpoint. |
| **C9 — Release It!**, Michael Nygard, second edition, 2018. [Publisher record and contents][c9]. | Production stability, failure patterns, configuration and release concerns would strengthen K14–K16. | Practitioner experience supplies operational perspective; examples and deployment mechanisms need current verification. It cannot by itself establish SRE ownership or service policy. | Publisher description and contents read; book text not examined. B5 wins the contested systems place for state, schema and consistency reasoning. Loss: greater operational stability and release-pattern depth. |
| **C10 — Secure by Design**, Dan Bergh Johnsson, Daniel Deogun and Daniel Sawano, 2019. [Publisher record][c10]. | Security through domain modelling, validation and design would deepen K03/K12 rather than treating security only as a final check. | Practitioner design perspective with Java/OO examples. Useful security depth, but not a complete secure-development lifecycle or specialist assurance basis. | Publisher description read; direct book content not examined. The current five places cover engineering change, architecture, requirements and state. Dedicated secure-construction depth remains a high-priority gap. |
| **C11 — Continuous Delivery**, Jez Humble and David Farley, first edition, published 2010; copyright 2011. [Publisher record and contents][c11]. | Pipeline, configuration, acceptance, deployment and data-change concerns would deepen K15/K17 and release evidence. | Focused practitioner treatment of delivery. Durable process reasoning deserves examination, while the age makes current platform details a clear verification need. | Publisher contents read; linked chapter sample not examined. B1 gives the selected set a broader connection between code, review and sustained change. Loss: detailed delivery-method depth. |
| **C12 — Software Requirements**, Karl Wiegers and Joy Beatty, third edition, 2013. [Publisher record and contents][c12]. | Elicitation, specification, validation and requirements change provide a wider requirements reference for K01/K18/K19. | A specialist treatment whose methods need proportionate adaptation rather than default document production. It is a different work from B4, with a different coauthor. | Publisher description and contents read; direct book text not examined. The user supplied B4 for the foundational requirements place. C12 remains a possible source for deeper techniques and examples beyond that concise treatment. |
| **C13 — Effective Software Testing**, Maurício Aniche, 2022. [Publisher record][c13]. Previously B4 in `SE-CORPUS-001`. | Specification, boundary and structural testing, contracts and property-based testing would add focused case-selection and adequacy depth to K07. | An academic/practitioner developer-testing perspective with Java examples; applicability still requires qualification. | Publisher description previously read; linked sample failed and no copy was supplied. Removed from foundational status by the user's explicit replacement. Remains a useful supplementary candidate; no extraction findings are discarded. |

### 4.3 Combination-level reasoning

The selection is not five independent “best book” judgements. Each retained place has a marginal purpose relative to the other four:

| Contested place | Decision | Gain retained | Cost consciously accepted |
|---|---|---|---|
| B1 versus C7 or C11 | Keep the lifecycle frame. | A connective source for review, maintainability and engineering infrastructure around local work. | Less individual craft/debugging emphasis than C7 and less delivery specialisation than C11. |
| B2 versus C6 | Prioritise entry into constrained brownfield work. | Research directed at creating enough understanding and verification to make a change. | Less catalogue-level refactoring detail. |
| B3 versus C8 | Preserve system-level architecture depth. | A source for relating technical choices to quality constraints and communication. | Less concentrated module-design argument. |
| B4 requirements versus C13 dedicated testing | Apply the user's replacement. | Problem definition, requirements, acceptance and change decisions receive dedicated foundational attention. | B1/B2 retain testing responsibilities, but specialised test-design depth needs supplementary research. |
| B5 versus C9 | Prioritise state and consistency. | A focused source for data obligations that cannot be inferred from ordinary code quality. | Operational stability and release depth remain incomplete. |
| C10 or C12 replacing a supplied book | Retain the supplied combination. | The five cover lifecycle practice, brownfield change, architecture, requirements and state. | Security remains a dedicated gap; C12 may deepen B4 without changing foundational membership. |

These comparisons are research judgements based on examined scope evidence. Direct reading may show a contribution to be weaker than expected. Record that honestly and revise the corpus explicitly if needed; do not force every selected book to produce a skill.

## 5. Material overlap and perspective limits

All ten pairs in the selected set have been considered below. These are expected intersections and Stage 3 questions, not claims of agreement or contradiction between unread passages.

| Pair | Expected intersection | Why retain it; what direct reading must distinguish |
|---|---|---|
| B1 / B2 | Maintaining and changing existing software. | Repository-wide engineering practice versus local constraints on making a change. Determine when an incremental repair needs broader coordination. |
| B1 / B3 | Design, quality trade-offs and team decisions. | Sustained engineering context versus explicit architectural analysis. Check whether a proposed decision process is proportionate for small changes. |
| B1 / B4 | Collaboration, documentation and change. | Engineering practice versus the requirements being agreed and maintained. Investigate how intent and acceptance stay connected to implementation evidence. |
| B1 / B5 | Long-lived systems, compatibility and scale. | Organisational/change context versus state and distributed semantics. Do not infer that Google-scale mechanisms are prerequisites for sound engineering. |
| B2 / B3 | Dependencies, boundaries and structural change. | Constraints of the current implementation versus alternative architecture. Investigate when restructuring is justified instead of assuming either local repair or redesign always wins. |
| B2 / B4 | Understanding and changing existing behaviour. | Existing behaviour may differ from approved requirements. Distinguish characterisation evidence, desired outcomes and authorised changes before deciding what to preserve. |
| B2 / B5 | Preserving behaviour across existing interfaces and state. | Code-level change constraints versus data-system obligations. Check where a local test harness cannot represent migration or concurrency risk. |
| B3 / B4 | Quality attributes, scope and decisions. | Eliciting constraints versus choosing an architecture to satisfy them. Preserve traceability without letting an architectural preference invent the requirement. |
| B3 / B5 | System qualities and architectural choices. | Broad option framing versus a deeper state-oriented analysis. Keep the applicability boundary visible for systems with little distributed state. |
| B4 / B5 | Data requirements, invariants and quality constraints. | Requirements define intended outcomes; system design must account for concurrency, compatibility and failure. Keep business meaning and technical guarantees distinct and connected. |

Requirements overlap is useful where it links intent, architecture, existing behaviour and data obligations. B1/B2 still overlap on testing, while B4 contributes requirements validation rather than a substitute for implementation test design. Repetition of a slogan is neither additional coverage nor independent corroboration.

The set has perspective limitations. It is English-language, largely practitioner-led, and gives substantial attention to backend systems and OO examples. B4 adds business-analysis and product-to-engineering perspectives, but the corpus as a whole is not an empirical evidence base. Small teams, client applications, accessibility, embedded systems and specialist assurance are underrepresented. No selected book establishes the reliability of AI coding agents or current provider capabilities.

Stage 3 should retain separate source locations for apparently shared ideas, identify differing prerequisites and record actual tensions only after reading. Stage 4 must seek counterexamples and independent evidence, including cases where the cost of a recommended practice exceeds its benefit.

## 6. Remaining domain gaps and disposition

These gaps do not remove charter responsibilities. They define work that later stages must address or explicitly bound. Proposed sources below are research leads, not already accepted findings.

| Gap | Affected dimensions | Required follow-up and completion evidence |
|---|---|---|
| Depth and applicability of requirements practice | K01, K18–K20 | Stage 3 now examines B4 directly. Stage 4 challenges its concise practices under conflicting intent and uses C12 where deeper examples are needed. Preserve the distinction between engineering clarification and a product decision. |
| Security engineering and software supply chain | K03, K12, K17 | Stage 4: directly examine then-current NIST secure-development guidance and applicable OWASP/official ecosystem material; consider C10. Record threat assumptions, bounded verification and specialist escalation. |
| General debugging, performance diagnosis and shared-memory concurrency | K08, K13 | Stage 4: investigate causal debugging and measurement methods; use primary runtime documentation for memory/concurrency semantics. Require evidence that discriminates causes and a justified repair scope. |
| Reliability beyond data systems, observability and technical release mechanics | K14–K16 | Stage 4: examine operational practice, C9/C11 where useful and current official deployment guidance. Separate software readiness evidence from authority to operate or launch a service. |
| Language, platform and configuration details | K03, K10, K13, K17 | Stage 4 establishes general obligations; later capability and pack research resolves ecosystem-specific mechanisms. Do not promote book examples into universal commands or defaults. |
| Client applications, accessibility and specialist systems | K01–K03, K07, K14 | Challenge the backend/OO bias with client, library and CLI cases. Explicitly bound embedded, real-time, safety-critical, ML and data-domain assurance; involve the appropriate specialist sources. |
| Maintenance economics, team constraints and review effectiveness | K04, K06, K09, K18, K20 | Stage 4: seek empirical findings and counterexamples to practitioner prescriptions. Assess proportionate effort, small-team applicability and whether review or documentation actually improves the intended outcome. |
| Dedicated test design, verification effectiveness and limits | K07–K09, K14 | Stage 3 examines B1/B2 testing and B4 acceptance/validation. Stage 4 must address boundary, structural and property-based techniques, adequacy, oracles and nondeterminism; consider C13 as a supplement. A requirements source does not close this test-design gap. |
| Currency of the supplied DDIA first edition | K10–K16 | Use the actual 2017 text for Stage 3. Stage 4 must verify change-sensitive database and distributed-system claims against current primary sources; later-edition material can supplement it only with its own access and citations. |
| Agent behaviour, permissions and evidence integrity | K05, K07–K09, K19–K20 | Retain charter authority rules now. Use Stage 4 to identify professional obligations and Stage 8 for the current AI/tool landscape; later benchmarks must test agent-specific failure modes and truthful reporting. |

No numerical coverage score is assigned. A topic appearing in a contents page is not evidence that its practical depth is sufficient. Stage 3 must revisit this map using actual reading, and Stage 4 must revisit it independently of what the books happen to discuss.

## 7. Edition control and source identifiers

Bibliographic identity is fixed for `SE-CORPUS-002` using the supplied books themselves. PDF page numbers below are one-based file positions, not printed-book pagination; these files have reflowed layouts. Source IDs identify the supplied copies internally without publishing attachment URLs, private storage locations or book files.

| ID | Bibliographic identifier | Evidence from supplied PDF |
|---|---|---|
| B1 | ISBN `9781492082798`; original edition, 2020. | Title page at PDF p. 2 names Winters, Manshreck and Wright; pp. 3–4 identify the first edition and ISBN. |
| B2 | ISBN `0131177052` / `9780131177055`; first edition, published 2004, copyright 2005. | PDF p. 4 names Feathers; pp. 5–6 give copyright, ISBN and first printing in September 2004. |
| B3 | Supplied edition ISBN `9781098175511`; second edition, 2025. | PDF p. 5 names Richards and Ford and the second edition; pp. 6–8 give copyright, March 2025 release and ISBN. |
| B4 | ISBN `9780138190286`; 2023 edition. | PDF p. 8 gives the full title and both authors, Karl Wiegers and Candase Hokanson; p. 10 gives copyright 2023 and ISBN. This is not C12, *Software Requirements*, by Wiegers and Joy Beatty. |
| B5 | ISBN `9781449373320`; first edition, 2017. | PDF p. 2 names Martin Kleppmann alone; pp. 3–4 identify the March 2017 first edition and ISBN. |

B5 changes from the agent-selected second edition (2026, Kleppmann and Riccomini) to the supplied first edition (2017, Kleppmann). The user's submission establishes the actual reading source; the edition difference is explicit in this revision and the decision log. The second-edition [announcement][b5-author] and [catalogue][b5-2e-catalogue] remain historical selection references, not evidence from the supplied text. B3's supplied copy confirms the originally selected second edition.

## 8. Source-access and reading register

All entries now have **user-provided** origin and were checked on **13 September 2026**. Each PDF opens without encryption restrictions and yields text in sampled front, middle and end locations. This supports full-text availability; it is not a page-by-page integrity review or completion of substantive reading. The supplied files were inspected without alteration.

| ID / internal source identifier | Access status | File size in pages and material actually examined | Intended contribution and reading limitation | Stage 3 access action |
|---|---|---|---|---|
| B1 / `SE-CORPUS-002/B1` | **full text available** | 981 PDF pages. Title/copyright pp. 2–4, foreword pp. 5–6 and text samples at pp. 328, 655 and 979. Earlier official HTML contents and opening chapter 1 access check remain recorded. | Lifecycle and sustainable change, including review and testing. Sampled text is not a systematic reading of these contributions. | No acquisition request. Use the supplied PDF or official [HTML contents][b1-toc], recording which source and locations support each finding. |
| B2 / `SE-CORPUS-002/B2` | **full text available** | 454 PDF pages. Identity pp. 4–6 and text samples at pp. 152, 303 and 452. Earlier first-page samples from official [chapter 1][b2-ch1] and [chapter 4][b2-ch4] remain historical reading evidence. | Brownfield understanding, change constraints and verification support. The earlier excerpt-only limitation is resolved; methods still need substantive examination. | No acquisition request. Read the supplied first edition and record actual sections and applicability. |
| B3 / `SE-CORPUS-002/B3` | **full text available** | 981 PDF pages. Identity pp. 5–8 and text samples at pp. 328, 655 and 979. Previously examined publisher contents remain selection evidence. | Architectural reasoning and decision trade-offs. Sampled passages establish readability, not acceptance of architectural claims. | No acquisition request. Read the supplied second edition; inspect diagrams directly when findings depend on them. |
| B4 / `SE-CORPUS-002/B4` | **full text available** | 258 PDF pages. Title p. 8, copyright p. 10, contents pp. 13–18, foreword pp. 19–20, author information pp. 23–24 and text samples at pp. 87, 173 and 256. | Requirements, acceptance and change decisions. The contents and foreword support selection scope; neither these nor isolated samples establish the practices in depth. | No acquisition request. Read the supplied 2023 book and assess where its concise treatment needs additional evidence or examples. |
| B5 / `SE-CORPUS-002/B5` | **full text available** | 906 PDF pages. Identity pp. 2–4 and text samples at pp. 303, 605 and 904. Earlier second-edition metadata is historical, not reading evidence for this copy. | Data evolution, concurrency and distributed failure. The available edition is 2017; specific claims still need reading and current-practice challenge. | No acquisition request. Read and cite the supplied first edition; do not reuse second-edition chapter numbering or attribute its newer material to this copy. |

There are now **five full-text sources and zero outstanding acquisition needs** for the current corpus. All five still require meaningful Stage 3 examination for their intended contributions. Earlier requests for four copies are satisfied by the supplied corpus, including the explicit B4 replacement and the recorded B5 edition change.

Only independently written synthesis and concise bibliographic/source-location references are published. Source PDFs, extensive extracts, private attachment identifiers and credentials are not part of this commit. If Stage 3 encounters a damaged or unreadable passage, record that specific limitation and resolve it then; no additional access barrier is assumed now.

## 9. Supplied-book decisions and corpus revision

### 9.1 Decision history

The original five additions below remain historical decisions for `SE-CORPUS-001`. The full original comparison is preserved in the [initial Stage 2 commit][initial-selection]. No book had been supplied at that point.

| Decision | Original book | Action and rationale | Original approval status | Date |
|---|---|---|---|---|
| S2-01 | B1: Software Engineering at Google, 2020 | Add to empty slot for the lifecycle connection. | No separate approval required; no supplied book displaced. | 2026-09-13 |
| S2-02 | B2: Working Effectively with Legacy Code, 2004 | Add to empty slot for constrained brownfield work. | No separate approval required; no supplied book displaced. | 2026-09-13 |
| S2-03 | B3: Fundamentals of Software Architecture, second edition, 2025 | Add to empty slot for architectural reasoning. | No separate approval required; no supplied book displaced. | 2026-09-13 |
| S2-04 | B4: Effective Software Testing, 2022 | Add to empty slot for test-design depth. | No separate approval required; no supplied book displaced. | 2026-09-13 |
| S2-05 | B5: Designing Data-Intensive Applications, second edition, 2026 | Add to empty slot for state and distributed behaviour. | No separate approval required; no supplied book displaced. | 2026-09-13 |

The user then supplied all five current books and stated that the requirements book replaces *Effective Software Testing* because it is more appropriate for the intended software-engineering foundation. That instruction is the decision reference for this revision; no confirmation of the same substitution is needed.

| Decision | Current book | Applied change | Authority / status | Date |
|---|---|---|---|---|
| S2-06 | B1 | Retain title and edition; register supplied full PDF. | User-provided book retained. | 2026-09-13 |
| S2-07 | B2 | Retain title and edition; replace excerpt-only access with supplied full PDF. | User-provided book retained. | 2026-09-13 |
| S2-08 | B3 | Retain second edition; replace descriptive-only access with supplied full PDF. | User-provided book retained. | 2026-09-13 |
| S2-09 | B4 | Replace Effective Software Testing with Software Requirements Essentials, Wiegers and Hokanson, 2023. | Explicit user substitution, applied. | 2026-09-13 |
| S2-10 | B5 | Retain the supplied first edition, Kleppmann, 2017, in place of the agent-selected second edition; register full PDF. | Actual supplied edition retained under the default retention rule; no supplied book removed. | 2026-09-13 |

### 9.2 Substitution rationale and consequences

| Required decision field | B4 replacement record |
|---|---|
| Book removed | Effective Software Testing: A Developer's Guide, Maurício Aniche, 2022; former B4, now supplementary candidate C13. |
| Replacement | Software Requirements Essentials: Core Practices for Successful Business Analysis, Karl Wiegers and Candase Hokanson, 2023. |
| Coverage / overlap problem | Requirements had no dedicated foundation in `SE-CORPUS-001`, while B1/B2 already supplied initial testing-related reading targets alongside the specialised testing book. |
| Supporting evidence | User's explicit preference; supplied B4 title/copyright pages, contents and foreword at the locations in section 8; the existing K01/K07 coverage comparison. |
| Expected gain | Dedicated investigation of problem framing, requirements development/management, acceptance and decision ownership across K01, K04, K18–K20. |
| Potential loss | Less dedicated implementation test-design depth in K07. Requirements validation is not equivalent to systematic test-case design. |
| Alternatives | Keep the original corpus and supplement requirements; or use C12 as the foundational requirements source. The user chose the supplied Essentials book, which is retained; C13 and C12 remain optional supplements. |
| Approval status | Explicitly authorised and applied on 2026-09-13. No unanswered request. |

B5's edition change preserves the work's intended contribution while making the source actually available for direct reading. It loses the presumed currency and additional scope of the 2026 edition; those cannot be claimed from the supplied 2017 text. The alternative was to continue requesting the second edition, but retaining the user's supplied edition resolves access without removing any supplied book. Stage 4 must verify change-sensitive claims against current primary evidence.

**Current supplied books retained:** five. **Title substitutions applied:** one, explicitly authorised. **Edition changes recorded:** one, to match a supplied copy. **Pending required permissions:** none. Alternatives C6–C13 are not supplied corpus members.

### 9.3 Revision and downstream impact

| Corpus revision | Basis | Status and impact |
|---|---|---|
| `SE-CORPUS-001` | Initial selection at the [Stage 2 commit][initial-selection], 13 September 2026. | Historical. Included Aniche's testing book and DDIA second edition; four access needs were open. |
| `SE-CORPUS-002` | User's five-book submission and explicit testing-to-requirements replacement, 13 September 2026. | Current. B4 membership and B5 edition updated; all five full texts available. Sections 1–8 and 10–11 describe this revision. |

The change affects the selection table, coverage map, candidate rationale, B4 overlap pairs, remaining gaps, access/edition register and Stage 3 reading plan. No Stage 3 extractions, Stage 4 findings, capability architecture, skills or evaluations existed on this branch at the revision baseline, so none require rework. Future findings must identify `SE-CORPUS-002` and the actual edition; B4 references without a corpus revision are ambiguous across this history.

A later membership or edition change must receive a new corpus revision, preserve these decisions and identify affected reading, research and design artefacts. All five current books are now user-provided: removing, replacing or demoting one requires explicit user authorisation. Reading progress or a repaired access link alone does not change corpus membership.

## 10. Stage 3 handoff

The next dependent stage is [Stage 3: Extract and Reconcile the Five-Book Corpus](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#10-stage-3--five-extract-and-reconcile-the-five-book-corpus). It must consume this revised record and the original charter, use the five available sources in `SE-CORPUS-002` and examine each book on its own terms before combining findings. Source access no longer blocks starting that work.

| ID | Initial reading focus, subject to the actual text | Question the extraction must answer |
|---|---|---|
| B1 | Time and trade-offs; review and documentation; testing; dependencies and large changes; delivery. | Which practices transfer to the consuming repository, with what prerequisites and justified effort? |
| B2 | Change and feedback; seams and dependency constraints; understanding existing code; regression confidence. | How can an agent establish a responsible path through a poorly understood system without expanding the change unnecessarily? |
| B3 | Architectural thinking, modularity and quality characteristics; choice of approach; decisions and risk. | What evidence and alternatives justify an architectural decision at the scale of the requested change? |
| B4 | Problem and solution boundaries; stakeholder needs; elicitation, analysis and specification; validation/acceptance; baselines and change. | How can an engineer clarify and preserve the intended outcome, expose the right decision and connect requirements to implementation evidence? |
| B5 | First-edition treatment of reliability, scalability and maintainability; encoding/evolution; transactions; distributed failure and consistency. | Which state and failure obligations require stronger reasoning than a local passing test, and which 2017 technology claims need current verification? |

These are reading priorities, not assertions that the material has been extracted. Stage 3 must record actual chapter/section locations, reading coverage, assumptions, applicability, failure modes, repair strategies and disposition. Each material finding needs a traceable path to a provisional engineering capability, responsibility, workflow implication, evaluation criterion and possible benchmark case. A book may contribute less than anticipated.

Reconciliation must distinguish repeated advice from independent support, preserve context-dependent alternatives and expose unresolved contradictions. It should revisit K01–K20 and the gaps in section 6. Neither five books nor twenty dimensions determines the number of skills, commands, packs or examples. Stage 4 then challenges the resulting model through wider professional and empirical research; no accepted capability architecture is created by this selection record.

## 11. Exit review and completion evidence

| Required Stage 2 output or gate | Evidence in this record | Result |
|---|---|---|
| Knowledge-coverage map | Section 3: twenty charter-derived dimensions, required decision depth, supplied-book targets and residual needs, updated for the requirements replacement. | Complete for revised selection. |
| Candidate-book comparison | Section 4: thirteen distinct works across the initial assessment and this revision, including the replaced testing book as an alternative. | Complete. |
| Exactly five selected books | Section 1: B1–B5; section 7 fixes bibliographic identity. Editions are not counted as extra works. | Complete. |
| Selected and rejected rationale | Sections 4.1–4.3: individual assessments and marginal contribution trade-offs. | Complete. |
| Material-overlap analysis | Section 5: all ten selected pairs, useful overlap and common perspective limitations. | Complete as selection hypotheses. |
| Remaining domain gaps | Sections 3 and 6: uncovered depth and assigned later investigation or specialist boundary. | Complete for this revision. |
| Source-access register | Sections 7–8: five supplied copies, verified identities, internal source IDs, exact access states and actual examined locations. | Complete; all five full texts available, substantive extraction pending. |
| Supplied-book substitution decision log | Section 9: original additions preserved; explicit B4 replacement and supplied B5 edition recorded; five supplied books retained and zero pending permissions. | Complete. |
| Corpus revision identifier | `SE-CORPUS-002`, with baseline, superseded revision and downstream impact. | Complete. |

Revision validation confirmed five selected identities, twenty coverage rows, thirteen candidate assessments, ten distinct overlap pairs and five full-text access entries. Review confirmed that current B4 references concern requirements, current B5 references identify the first edition, and superseded identities occur only as historical or alternative evidence. Reference definitions and local document links resolve. The commit is limited to this record and its index, preserving the Stage 1 record, bootstrap specification and root README. All nine expected outputs remain present, with no pending substitution decision.

The Stage 2 exit criteria are satisfied. This record and the research-log index are the stage deliverables. The charter and governing specification remain the inputs; no production scaffold, source-book files or later-stage completion claims are introduced. Selection completion does not imply that the corpus has been read, reconciled, empirically challenged or implemented.

[family-process]: https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/bootstrap/domain-research-process.md
[initial-selection]: https://github.com/sb-dev/software-engineering-skills/commit/f0a948b918fcac93fb371c964d555ab211867bb2
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
[b5-author]: https://martin.kleppmann.com/2026/03/24/designing-data-intensive-applications-2e.html
[b5-catalogue]: https://www.oreilly.com/library/view/designing-data-intensive-applications/9781491903063/
[b5-2e-catalogue]: https://www.oreilly.com/library/view/designing-data-intensive-applications/9781098119058/
[c6]: https://martinfowler.com/books/refactoring.html
[c7]: https://pragprog.com/titles/tpp20/the-pragmatic-programmer-20th-anniversary-edition/
[c8]: https://web.stanford.edu/~ouster/cgi-bin/book.php
[c9]: https://pragprog.com/titles/mnee2/release-it-second-edition/
[c10]: https://www.manning.com/books/secure-by-design
[c11]: https://www.informit.com/store/continuous-delivery-reliable-software-releases-through-9780321601919
[c12]: https://www.microsoftpressstore.com/store/software-requirements-9780735679665
[c13]: https://www.manning.com/books/effective-software-testing
