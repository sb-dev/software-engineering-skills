# Stage 3: Five-Book Extraction and Reconciliation

**Project:** `software-engineering-skills`  
**Stage:** 3, Five: Extract and Reconcile the Five-Book Corpus  
**Status:** Complete for direct-source extraction and reconciliation; Stage 4 challenge remains unperformed  
**Date:** 13 September 2026  
**Branch:** `feat/bootstrap-2`  
**Execution baseline:** `7602c7e3ff38839b394bf220b7b0ff7902136e32`  
**Corpus:** `SE-CORPUS-002`, unchanged  
**Governing requirement:** [Bootstrap v1.1, Stage 3](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#10-stage-3--five-extract-and-reconcile-the-five-book-corpus)

## 1. Scope, inputs and acceptance checklist

This stage directly examines the five accepted books, extracts engineering methods with their limitations, and reconciles them into a provisional capability model. It does not establish that a method is empirically effective, that a named product still behaves as described, or that a proposed benchmark has passed.

The inputs are the [Stage 1 charter](2026-09-12-stage-01-project-goal-and-domain-boundary.md), revised [Stage 2 coverage and corpus record](2026-09-13-stage-02-knowledge-coverage-and-five-book-corpus.md), governing bootstrap, canonical [Domain Research Process](https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/bootstrap/domain-research-process.md), and [execution contract](2026-09-13-bootstrap-execution-contract.md). The repository baseline includes the contract after the contract's named starting revision, `21c608bade12791ce892ff7ab4d9d6bb083d5dee`. The complete governing Stage 3 and accepted prior records were read before extraction. The charter and corpus selection remain authoritative.

The acceptance checklist stated before work was:

- Use exactly the five supplied books in `SE-CORPUS-002`, with the accepted editions and no substitution or demotion.
- Meaningfully read each book for its intended contribution; record actual locations and omissions, not merely access or contents checks.
- Give every material finding all eight required fields: source, problem/concept, applicability, production behaviour, evaluation, failure/repair, relationships and disposition.
- Connect useful findings to capabilities, responsibilities, workflow implications, evaluation criteria and candidate cases.
- Reconcile reinforcement, overlap, competing assumptions, alternatives, contradictions, missing topics and claims needing challenge. Repetition is not independent corroboration.
- Persist all six required outputs in a research log, inspect their substance, record conformance, commit this stage alone and verify the remote commit.

There is no mandated number of findings, capabilities or executed benchmarks in Stage 3. The six outputs are sections 2–7 of this record: coverage, per-book findings, capability model, source mapping, reconciliation, and Stage 4 questions. Section 8 records the conformance review. All cases below are independently devised, synthetic **candidates**, not implemented fixtures or execution results. No production skill, command, framework or provider is selected here.

## 2. Bibliography and reading coverage

Locations use **one-based PDF file pages**, not printed-book pagination. The supplied files use different layouts and lengths. A source reference such as `B5, PDF 321–337` inherits the exact edition below; chapter/section descriptions aid navigation. Bibliographic identity was established in Stage 2 and retained here.

| ID | Book and authors | Accepted edition / ISBN | Intended contribution |
|---|---|---|---|
| B1 | *Software Engineering at Google*, Titus Winters, Tom Manshreck and Hyrum Wright | Original edition, 2020; `9781492082798` | Lifecycle connections between change, review, verification, dependencies and delivery. |
| B2 | *Working Effectively with Legacy Code*, Michael C. Feathers | First edition, published 2004, copyright 2005; `0131177052` / `9780131177055` | Understanding and safely changing existing code with inadequate feedback. |
| B3 | *Fundamentals of Software Architecture*, Mark Richards and Neal Ford | Second edition, 2025; `9781098175511` | Architectural alternatives, modularity, quality constraints, decisions and risk. |
| B4 | *Software Requirements Essentials: Core Practices for Successful Business Analysis*, Karl Wiegers and Candase Hokanson | 2023 edition; `9780138190286` | Problem framing, requirements development, acceptance and change management. |
| B5 | *Designing Data-Intensive Applications*, Martin Kleppmann | First edition, 2017; `9781449373320` | Persistent state, compatibility, concurrency and distributed failure. |

Full text remained available for all five. Text was extracted privately and read in bounded page sequences; extraction alone was not counted as examination. Truncated output was reread before being included in the confirmed ranges. Findings below were derived from the displayed book text, not publisher summaries, model recollection or unexamined references cited by a book. The coverage register excludes earlier access samples and contents browsing as substantive evidence.

| Book | Confirmed text examination: PDF pages | Contribution actually examined and resulting findings | Deliberate coverage limits |
|---|---|---|---|
| B1 | 19–53; 276–288; 294–302; 311–318; 385–394; 430–442; 515–519; 691–699; 708–715; 755–763; 768–779; 808–823 | Chapter 1's lifecycle reasoning; selected sections of chapters 9–10 on review/documentation, 12–13 on behavioural tests/doubles, 15 on deprecation, and 21–24 on dependencies, large changes, CI and delivery. Produces G01–G09, including mechanisms and institutional exceptions. | Not a cover-to-cover reading. Culture, leadership, productivity research, most build/static-analysis chapters and the larger-testing chapter were not examined. Google-specific practices are not universal requirements. |
| B2 | 26–69; 198–219; 231–245; 326–334 | Chapters 1–4 on change, feedback, sensing/separation and seams; selected chapters 12–13 on interception and characterisation; 16–17 on understanding/structure; 23 on avoiding unintended changes. Produces L01–L06 with testability prerequisites and limits. | The detailed dependency-breaking catalogue, non-OO chapter and most situation-specific refactorings were not read. No language-specific transformation or complete debugging method is claimed. |
| B3 | 40–44; 62–70; 75–117; 130–140; 159–194; 647–656; 698–721; 726–743 | Selected architectural thinking; modularity and characteristics; measurement/governance and quality scope; style selection, decision records and risk analysis. Produces A01–A07 with contextual choices and challenged examples. | Individual architecture-style chapters and most leadership, diagramming and component-design material were not examined. No comparative style ranking, metric formula or diagram geometry is adopted. |
| B4 | 26–220, continuously | All seven substantive chapters and all twenty practices: foundations, elicitation, analysis, specification, validation and management. Produces R01–R10 by combining related practices around engineering decisions. | Appendices, reference works and index were not examined as substantive sources. Concise practitioner treatment supplies methods, not empirical proof or specialist assurance. |
| B5 | 17–43; 155–190; 206–213; 217–224; 296–312; 321–337; 361–377; 380–411; 428–464; 466–474; 480–488 | Selected reliability/performance foundations, encoding/evolution, replication visibility/failover, transaction boundaries/anomalies, partial failures/clocks, consistency/order and coordination. Produces D01–D10, including concrete failure mechanisms. | Storage-engine/query-model and partitioning chapters, most replication variants, full isolation implementations, batch/stream chapters and future-systems chapter were not read. No complete consensus implementation, current product guarantee, shared-memory model or stream-processing method is claimed. |

The ranges contain 147, 90, 156, 195 and 217 PDF pages respectively. Those counts describe inspected text locations, **not a coverage score or proof of mastery**. Some pages contain figures; conclusions here rely on the accompanying text. Byte layouts, source-code examples, plotted values and figure-specific details were not independently executed or visually verified and are not production prescriptions.

The intended contributions are satisfied by examining the relevant methods, assumptions, failures and repairs, rather than by treating every book as a complete foundation for every charter responsibility. B1 supplies the lifecycle connection; B2 the entry into weakly tested code; B3 comparative architectural reasoning; B4 the full requirements practice sequence; B5 state and failure semantics. Section 6 identifies what this leaves insufficiently grounded. No book was removed, replaced or demoted; *Effective Software Testing* remains an unexamined supplementary candidate, as accepted in Stage 2.

## 3. Direct per-book findings

Each finding has all eight required fields. Production and evaluation statements are **project adaptations proposed from the examined material**; they are not claims that a production skill exists. Relationships refer to other findings in this record. Dispositions apply to the stated method, with narrower rejected readings identified explicitly. The complete capability/evaluation/case join is in sections 4–5.

### B1: Lifecycle engineering

#### G01 — Judge a change over its supported lifetime

- **Source:** B1, chapter 1, PDF 19–53, especially lifecycle, compatibility and trade-off discussions.
- **Problem and concept:** Local correctness can conceal future upgrade and consumer costs. Consider expected lifetime, change frequency, dependencies and who bears migration work.
- **Applicability:** Applies to scripts and small repositories as well as large systems; only supported obligations and plausible change pressures justify extra work.
- **Production behaviour:** State the change purpose, preservation obligations and relevant maintenance costs before choosing scope.
- **Evaluation:** E08/E18; the selected change addresses the authorised need and explains material lifetime costs without speculative redesign.
- **Failure and repair:** Treating undocumented use as nonexistent can break consumers. Inspect observable dependencies; Google's CI-based responsibility allocation is not permission to ignore uncovered regressions.
- **Relationships:** Reinforces L01 and R10; D03 makes lifetime costs concrete for stored data.
- **Disposition:** Adapt; reject organisation-specific blame policy as a general compatibility rule.

#### G02 — Review the engineering decision as well as the diff

- **Source:** B1, chapter 9, PDF 276–288 and 294–302.
- **Problem and concept:** Review must assess correctness, comprehensibility, design fit and maintainability; mechanical consistency and personal preference are different issues.
- **Applicability:** Use actual repository ownership and approval rules. A coherent change need not fit Google's illustrative line counts or response times.
- **Production behaviour:** Explain why/what, supply relevant evidence, resolve substantive findings and preserve new rationale with the change.
- **Evaluation:** E15; a planted contract defect is identified, while equivalent stylistic alternatives do not manufacture a blocker.
- **Failure and repair:** Ritual approval or endless perfection demands hide risk. Link feedback to an obligation; revisit an earlier decision when new evidence changes its premises.
- **Relationships:** R09 supplies acceptance alignment; A06 supplies durable decision context.
- **Disposition:** Adapt; no universal reviewer count, turnaround target or Google approval model.

#### G03 — Maintain documentation with the behaviour it explains

- **Source:** B1, chapter 10, PDF 311–318, documentation purpose and code-like maintenance.
- **Problem and concept:** Detached, ownerless explanations decay. Documentation needs an audience, canonical location and an update path tied to relevant changes.
- **Applicability:** Existing repository conventions may already provide this; additional documents must answer a receiving reader's question.
- **Production behaviour:** Update affected usage, contract or maintenance guidance alongside the change, with links to detailed evidence where useful.
- **Evaluation:** E17; a maintainer can locate the current behaviour, rationale and limitations without conflicting copies.
- **Failure and repair:** Producing more prose without resolving inconsistency increases uncertainty. Correct the canonical source and remove or redirect stale duplication.
- **Relationships:** Reinforces R08/R10 and A06, with different audiences and lifetimes.
- **Disposition:** Merge; no prescribed Google documentation tool or blanket wiki prohibition.

#### G04 — Test stable behaviour at a meaningful boundary

- **Source:** B1, chapter 12, PDF 385–394, unchanging tests, public APIs and behaviours.
- **Problem and concept:** Tests coupled to implementation structure obstruct refactoring. Assert outcomes at a stable boundary; an interaction is appropriate when that interaction is itself an obligation.
- **Applicability:** A meaningful boundary is not necessarily a class or a language-level public method. A test may also have an incorrect oracle.
- **Production behaviour:** Identify the behaviour protected, retain useful boundary checks and update expectations only for a justified contract correction/change.
- **Evaluation:** E07; equivalent restructuring passes and a relevant behavioural regression fails.
- **Failure and repair:** Literal refusal to change any bug-fix test would preserve a characterised defect. Separate observed behaviour from the desired oracle.
- **Relationships:** Tension with L05 resolves through R09's validation distinction; complements L04.
- **Disposition:** Qualify; reject the absolute reading that a bug fix can never require changing tests.

#### G05 — Choose doubles by the evidence they can supply

- **Source:** B1, chapter 13, PDF 430–442, real implementations and fakes.
- **Problem and concept:** Real dependencies increase realism; controlled substitutes can make important conditions cheap and reproducible. Neither choice proves every property.
- **Applicability:** Real implementations must be constructible and sufficiently reliable for the check. Fakes require explicit supported semantics and maintenance.
- **Production behaviour:** Select the dependency boundary, compare fake/real contracts where feasible, and reserve real-boundary checks for uncovered risks.
- **Evaluation:** E07; identify a fake that accepts invalid input or omits a production constraint; do not claim latency/durability from an in-memory substitute.
- **Failure and repair:** Mocking everything yields self-confirming tests. Restore the missing semantic boundary or narrow the evidence claim.
- **Relationships:** L03 supplies sensing/separation; D05/D07 expose dimensions ordinary doubles omit.
- **Disposition:** Merge and qualify; terminology and realism depend on the test purpose.

#### G06 — Treat dependencies as continuing compatibility commitments

- **Source:** B1, chapter 21, PDF 691–699 and 708–715.
- **Problem and concept:** Adopting a dependency imports upgrade, support and transitive-consumer obligations. Version labels help communicate intent but cannot establish actual compatibility.
- **Applicability:** Repository resolution policy, external consumers and supported versions constrain the choice; Google's internal upgrade model is contextual.
- **Production behaviour:** Record relevant consumers, effective versions, support responsibility and upgrade evidence; inspect fork costs when considering divergence.
- **Evaluation:** E14; reproduce the selected dependency set and detect a behavioural break despite a nominally compatible version increment.
- **Failure and repair:** Blind newest/minimum-version selection or overriding resolver constraints can invalidate the build. Use actual policy and consumer checks.
- **Relationships:** G01 supplies lifetime costs; D03 supplies bidirectional compatibility; G08 binds evidence to the candidate.
- **Disposition:** Adapt; no universal live-at-head, unpinned or minimal-version policy.

#### G07 — Give migrations and deprecations a verifiable end

- **Source:** B1, chapter 15, PDF 515–519; chapter 22, PDF 755–763.
- **Problem and concept:** A partly completed transition leaves permanent coordination cost. Discover consumers, divide work into coherent steps, and define how completion and new-use prevention will be established.
- **Applicability:** Large changes need coordination; small changes may use the same reasoning without a migration programme. Dynamic/external uses may evade static searches.
- **Production behaviour:** Specify supported intermediate states, migration ownership, consumer checks, cleanup and a defensible retirement condition.
- **Evaluation:** E16; old consumers retain their promised path and completion evidence covers the known usage boundary.
- **Failure and repair:** Mass edits or green tests alone do not prove retirement safety. Inspect missing consumers; retain the transition until obligations are discharged.
- **Relationships:** D03 constrains data transitions; L01 constrains preservation; R10 records decisions.
- **Disposition:** Adapt; reject book-specific bypassing of flaky checks or project gates as general authority.

#### G08 — Attach verification to the exact release candidate

- **Source:** B1, chapter 23, PDF 768–779.
- **Problem and concept:** A green result for another revision, dependency set or configuration is not evidence for the candidate being delivered.
- **Applicability:** Verification scope depends on risk and environment; pipeline success never proves all system qualities.
- **Production behaviour:** Record revision, effective configuration, dependencies, artefact identity, environment and relevant results; preserve evidence through promotion.
- **Evaluation:** E14/E16; detect that a rebuilt or cherry-picked candidate differs from the verified one and identify what needs rechecking.
- **Failure and repair:** Reporting the last green build as current success conceals a gap. Bind the result to its actual inputs and obtain missing candidate evidence.
- **Relationships:** G06 supplies dependency identity; G09 separates candidate readiness from rollout; R10 identifies the intended baseline.
- **Disposition:** Retain with scope qualification; not a mandate to build a new pipeline here.

#### G09 — Separate technical readiness, deployment and feature exposure

- **Source:** B1, chapter 24, PDF 808–823.
- **Problem and concept:** Shipping binaries, exposing functionality and recovering from failure are distinct transitions. Smaller steps can improve control when intermediate states are supported.
- **Applicability:** Client update delays, configuration, flags and persistent state constrain sequencing. Existing release authority governs execution.
- **Production behaviour:** Establish mixed-version behaviour, exposure controls, observability and a viable recovery path before an authorised release action.
- **Evaluation:** E16; a flag-off or old-binary rollback is not accepted as recovery when changed data remains incompatible.
- **Failure and repair:** Treating frequent release or a microservice rewrite as inherently safer ignores transition cost. Compare the actual failure and recovery mechanisms.
- **Relationships:** D03/D05 constrain rollback; A01 and L01 challenge generic rewrite advice.
- **Disposition:** Qualify; frequency, rewrite-return and causal safety claims go to Q02/Q03.

### B2: Changing weakly understood systems

#### L01 — Define the intended delta and preservation envelope

- **Source:** B2, chapter 1, PDF 26–32.
- **Problem and concept:** A change usually alters a small set of obligations while preserving others. Feature addition, repair, restructuring and resource improvement have different intended deltas.
- **Applicability:** Existing behaviour matters, but defects targeted by authorised work are not invariants. Fewest edited lines need not be the smallest coherent repair.
- **Production behaviour:** Identify desired changes, protected behaviours and affected boundaries before selecting the edit.
- **Evaluation:** E08/E18; repair the target while demonstrating preservation of relevant adjacent behaviour and justifying necessary scope.
- **Failure and repair:** Treating an additive edit as harmless misses indirect effects; freezing every legacy behaviour prevents repair. Trace effects and classify the oracle.
- **Relationships:** G01 adds lifecycle consequences; R01 supplies purpose; L05 distinguishes observed and intended behaviour.
- **Disposition:** Retain and merge into change-scope reasoning.

#### L02 — Establish feedback before expanding a risky change

- **Source:** B2, chapter 2, PDF 33–44.
- **Problem and concept:** When tests require code changes, demanding full coverage before any edit creates a deadlock. A conservative testability cut can enable local feedback before the substantive change.
- **Applicability:** Especially useful in poorly tested code; fast local checks complement broader checks. No universal duration threshold or test for every low-impact edit follows.
- **Production behaviour:** Find a test point, minimise the initial dependency cut, establish a useful baseline, then change/refactor under feedback.
- **Evaluation:** E06; the initial cut preserves the relevant contract and the resulting check detects the target regression.
- **Failure and repair:** Large cleanup mixed into the unprotected cut defeats the method. Separate goals and narrow the first change.
- **Relationships:** L03 supplies the seam mechanism; G05 qualifies isolation; L06 qualifies compiler evidence.
- **Disposition:** Adapt to available tools, language and change risk.

#### L03 — Locate the actual seam and enabling point

- **Source:** B2, chapters 3–4, PDF 45–69.
- **Problem and concept:** Observing an effect and controlling a dependency are different needs. A seam requires a real binding point where behaviour can be substituted without editing each caller.
- **Applicability:** Object, preprocessing and linking seams have different mechanics. A test substitute cannot establish the real adapter or hardware contract.
- **Production behaviour:** Explain production/test bindings, choose the least invasive useful seam and identify which real-boundary evidence is still needed.
- **Evaluation:** E06/E07; demonstrate that the intended binding is exercised and that a substitute's success is not reported as integration proof.
- **Failure and repair:** Imagined injection or wrong binding leaves production paths untested. Inspect actual construction/linking and repair the enabling point.
- **Relationships:** G05 adds fake fidelity; A02 distinguishes dependency control from architectural improvement.
- **Disposition:** Adapt; language-specific syntax and contemporary tools require separate verification.

#### L04 — Select observation points from the effects of this change

- **Source:** B2, chapter 12, PDF 198–208, interception and pinch-point reasoning.
- **Problem and concept:** A convenient test point may miss relevant effects. Trace propagation to observable boundaries; a shared interception point is useful only if it covers the necessary effects.
- **Applicability:** Some changes need several points. Static structure alone cannot expose all runtime/data effects, and distant checks may be expensive or ambiguous.
- **Production behaviour:** Build a bounded effect trace, justify observation points and mark unknown consumers or unobserved paths.
- **Evaluation:** E02/E09; a multi-effect change cannot be declared covered because one local result passes.
- **Failure and repair:** Choosing one public method by habit misses side effects. Add an appropriate boundary check or narrow the change/evidence claim.
- **Relationships:** A02 broadens coupling; D07 adds remote uncertainty; G04 qualifies advice to replace all higher-level checks.
- **Disposition:** Retain with boundary-dependent qualification.

#### L05 — Use characterisation as evidence of reality, not approval

- **Source:** B2, chapter 13, PDF 209–219.
- **Problem and concept:** Recording current outputs can establish a baseline when specifications are weak, but that baseline can contain defects.
- **Applicability:** Choose inputs that expose changed paths and conversions. A passing path count does not establish a sensitive oracle or valid expected behaviour.
- **Production behaviour:** Label observed behaviour, desired behaviour and unresolved intent separately; preserve unaffected obligations while correcting the authorised defect.
- **Evaluation:** E06; the target defect is exposed, the expected correction is justified, and adjacent characterisation remains useful.
- **Failure and repair:** Golden-master acceptance can fossilise a bug; weak values can mask a conversion failure. Revalidate the oracle and use discriminating inputs.
- **Relationships:** R09 supplies validation; G04's absolute unchanged-test heuristic needs this distinction.
- **Disposition:** Retain; qualify blanket per-method test prescriptions.

#### L06 — Treat understanding aids and compiler feedback as bounded evidence

- **Source:** B2, chapters 16–17, PDF 231–245; chapter 23, PDF 326–334.
- **Problem and concept:** Notes, sketches and isolated exploratory refactoring can clarify structure. Single-purpose edits and compiler feedback reduce some mistakes without proving behaviour preservation.
- **Applicability:** Validate hypotheses against the original system; inheritance fallback, dynamic users and environmental changes can escape compiler checks.
- **Production behaviour:** Separate exploratory work from the intended patch, trace a focused architecture explanation, and verify each material preservation claim.
- **Evaluation:** E02/E08; reject a compiling edit that changes dispatch or hides a known exception to the model.
- **Failure and repair:** Merging exploratory cleanup or assuming unchanged code cannot fail confuses evidence. Restore isolation and investigate runtime/input/configuration causes.
- **Relationships:** G01's time lens and D01's correlated faults contradict a literal code-only cause rule; A02 supplies structural context.
- **Disposition:** Adapt; reject unchanged-code infallibility and universal pairing requirements.

### B3: Architectural reasoning

#### A01 — Compare alternatives against the actual constraints

- **Source:** B3, chapter 2, PDF 40–44 and 62–70; chapter 19, PDF 647–656.
- **Problem and concept:** Architectural importance follows consequences and change cost, not job title. Compare alternatives using domain needs, data, environment, team capability and operating constraints.
- **Applicability:** Include retaining or locally improving the existing design. A style label cannot decide suitability, and alternatives violating hard invariants are invalid.
- **Production behaviour:** Explain feasible options, their benefits/costs, assumptions and why the chosen scope addresses the requirement.
- **Evaluation:** E04; a preferred technology loses when it violates an explicit constraint, even if it fits a generic style chart.
- **Failure and repair:** Declaring all answers equally valid hides contradictions. Separate hard constraints, negotiable preferences and uncertain premises.
- **Relationships:** R05 supplies qualities; D09 supplies semantic constraints; G09's generic rewrite advice needs contextual challenge.
- **Disposition:** Adapt; reject literal absence of right/wrong answers and unverified topic-versus-queue generalisations.

#### A02 — Examine semantic and runtime coupling, not only imports

- **Source:** B3, chapter 3, PDF 75–108.
- **Problem and concept:** Module boundaries organise responsibilities; physical separation alone does not create independence. Dependencies can involve meanings, order, timing, values and shared state as well as calls.
- **Applicability:** Structural measures can reveal questions but do not establish cohesion or correctness. Granularity trades local clarity against coordination cost.
- **Production behaviour:** Identify the relevant forms of coupling and keep unnecessary implementation dependence local when making a bounded structural change.
- **Evaluation:** E05; detect shared-data or temporal dependence hidden behind separate services, and explain the effect of a proposed boundary.
- **Failure and repair:** Optimising a coupling score can worsen the design. Trace actual responsibilities and change propagation before restructuring.
- **Relationships:** L04 supplies effect tracing; A05 scopes qualities; D03/D09 expose cross-version and ordering coupling.
- **Disposition:** Qualify; no formula threshold, mandatory taxonomy or universal component graph.

#### A03 — Derive architectural qualities from needs and conditions

- **Source:** B3, chapters 4–5, PDF 109–117 and 130–140.
- **Problem and concept:** Important qualities may be implicit, composite or differently named. Translate domain concerns into explicit, testable constraints that influence structure.
- **Applicability:** An inferred requirement is a hypothesis until validated; architects do not gain authority to invent product objectives or numerical targets.
- **Production behaviour:** Connect each significant architectural choice to the relevant quality, operating condition and acceptance evidence.
- **Evaluation:** E03/E04; distinguish throughput, latency, recovery and integrity instead of declaring the system generically fast or available.
- **Failure and repair:** Treating a quality as an isolated backlog item can miss system-wide consequences. Trace its scope and clarify the actual target.
- **Relationships:** R05 supplies elicitation; D01/D02 supply failure and workload mechanisms.
- **Disposition:** Merge; retain local vocabulary rather than imposing the book's terminology preference.

#### A04 — Make architecture checks answer a specific quality question

- **Source:** B3, chapter 6, PDF 159–184.
- **Problem and concept:** A fitness function is useful because of the invariant it assesses, not because it creates a new class of tooling. Measurements need conditions and interpretation.
- **Applicability:** Existing tests, dependency checks or runtime measurements may suffice. Coverage and complexity numbers are proxies, not semantic quality or test adequacy.
- **Production behaviour:** Define the property, observation method, threshold rationale where applicable and response to violation.
- **Evaluation:** E05/E13; detect a relevant boundary violation or performance regression while refusing to certify quality from assertion presence alone.
- **Failure and repair:** Arbitrary thresholds and averages conceal failures or invite gaming. Inspect distributions, semantics and the validity of the measure.
- **Relationships:** G08 binds checks to inputs; G04 supplies behavioural sensitivity; D02 supplies workload conditions.
- **Disposition:** Adapt; do not adopt illustrative complexity limits or unverified AI-based testing claims.

#### A05 — Scope quality claims across actual dependencies

- **Source:** B3, chapter 7, PDF 185–194.
- **Problem and concept:** Deployment units, synchronous calls, shared data and asynchronous flows constrain which qualities can vary independently.
- **Applicability:** The book's architecture-quantum model is a diagnostic lens, not a mandatory artefact. Component-level guarantees coexist with end-to-end obligations.
- **Production behaviour:** Follow runtime/data dependencies when defining failure, scaling and deployment boundaries; account for queues and downstream capacity.
- **Evaluation:** E04/E13; reject a service-isolation claim that ignores a shared database or sustained backlog growth.
- **Failure and repair:** Asynchrony may absorb a burst without fixing a persistent capacity deficit. Analyse demand, service rate, backlog and failure propagation.
- **Relationships:** A02 supplies coupling; D02 supplies load analysis; D07 supplies partial-failure limits.
- **Disposition:** Qualify; service count or a framework label does not establish independence.

#### A06 — Preserve decision rationale and supersession

- **Source:** B3, chapter 21, PDF 698–721.
- **Problem and concept:** A decision record should explain context, choice, consequences and status so later changes can distinguish a deliberate trade-off from an accident.
- **Applicability:** Reuse existing records and the actual decision authority. Storage must suit the readers; neither central storage nor proximity to code is universally sufficient.
- **Production behaviour:** Record significant alternatives, assumptions, verification needs and superseding decisions, linking the canonical record to the change.
- **Evaluation:** E17; a later maintainer can determine whether changed assumptions invalidate the decision and which version is authoritative.
- **Failure and repair:** Template completion or approval labels can hide unsupported guarantees. Check premises and preserve the history of corrections.
- **Relationships:** G03/R08 supply maintained knowledge; R02 supplies authority; D09 challenges the FIFO example's scope.
- **Disposition:** Adapt; reject illustrative security exceptions or approval thresholds as project authorisation.

#### A07 — Assess risk with explicit evidence and uncertainty

- **Source:** B3, chapter 22, PDF 726–743.
- **Problem and concept:** Compare risks by affected quality, plausible impact, likelihood rationale, mitigation cost and ownership. Different perspectives can reveal missing assumptions.
- **Applicability:** Ordinal ratings are discussion aids; their sums/products are not measured probabilities. Unknown technology is uncertainty, not automatically maximum measured risk.
- **Production behaviour:** Record the failure mechanism and evidence, compare proportionate mitigations, and identify what investigation could change the choice.
- **Evaluation:** E05/E18; a high-impact uncertain case remains visible despite a low aggregate score or group consensus.
- **Failure and repair:** Ranking by arithmetic or assuming clustered infrastructure is safe hides common dependencies. Inspect the mechanism and correlated failures.
- **Relationships:** D01 supplies fault models; R07 supplies priority context; G02 provides review questions.
- **Disposition:** Qualify; no universal risk score, mandatory workshop or extra reviewer requirement.

### B4: Requirements and change decisions

#### R01 — Separate the problem, proposed solution and desired outcome

- **Source:** B4, chapter 1, PDF 26–40; chapter 2, practices 1–2, PDF 42–57.
- **Problem and concept:** A requested solution may obscure the underlying need. Distinguish the problem, desired business outcome and software behaviour that could contribute to it.
- **Applicability:** Existing approved intent is an input; clarifying technical implications does not authorise changing product strategy. Outcome proxies may be confounded.
- **Production behaviour:** State the bounded problem, accepted objective, assumptions and observable technical acceptance before comparing implementations.
- **Evaluation:** E01/E18; tests establish software behaviour without claiming that a business outcome has thereby occurred.
- **Failure and repair:** Treating a suggested rewrite as the requirement inflates scope. Expose the technical alternative and route any actual product decision to its owner.
- **Relationships:** L01 constrains the delta; A01 compares solutions; G01 adds lifetime cost.
- **Disposition:** Adapt; causal questioning is a heuristic, not proof that a root cause has been found.

#### R02 — Distinguish system boundaries, stakeholders and decision rights

- **Source:** B4, chapter 2, practices 3–5, PDF 57–80.
- **Problem and concept:** System context differs from project scope. Consumers, operators and other affected parties may not be the immediate requester; consultation differs from authority.
- **Applicability:** Include nonhuman clients and manual/file/data flows where relevant. One person can hold several roles; existing authorisation remains valid.
- **Production behaviour:** Identify affected boundaries, responsible owners, unresolved decisions and the lowest appropriate existing decision authority.
- **Evaluation:** E01/E02; detect a downstream consumer and distinguish a permitted implementation choice from a new business-policy decision.
- **Failure and repair:** Treating an available stakeholder proxy as authorised can yield false agreement. Verify the relevant responsibility without inventing a universal approval ceremony.
- **Relationships:** L04 traces effects; A06 records decisions; G02 uses repository review ownership.
- **Disposition:** Adapt; the book does not authorise contacting people or expanding task scope.

#### R03 — Elicit behaviour through goals, events and states

- **Source:** B4, chapter 3, practices 6–7, PDF 83–100.
- **Problem and concept:** User goals reveal normal and alternative paths, while event/state reasoning exposes background work, timeouts and missing transitions.
- **Applicability:** Use cases, stories, event tables and state models are alternatives or complements; choose representations that answer a real uncertainty.
- **Production behaviour:** Specify relevant preconditions, triggering events, responses and exception paths, including concurrent or temporal interactions needing clarification.
- **Evaluation:** E03; acceptance includes the relevant exception/background behaviour, not only a successful screen interaction.
- **Failure and repair:** A diagram may omit actions and a table may hide connectivity. Compare representations and resolve missing or inconsistent transitions.
- **Relationships:** D07 introduces delayed/duplicate effects; R09 checks intended behaviour; A05 locates cross-boundary consequences.
- **Disposition:** Retain with proportional representation choices; no compulsory story or modelling template.

#### R04 — Trace data meaning and obligations across producers and consumers

- **Source:** B4, chapter 3, practice 8, PDF 100–110.
- **Problem and concept:** Data requirements include origin, use, relationships, allowed values and lifecycle operations, not only a physical schema.
- **Applicability:** Conceptual meaning and ownership precede storage choices. Domain specialists retain authority over business meaning and policy.
- **Production behaviour:** Identify relevant entities, transformations, constraints and missing producer/consumer operations; carry these obligations into interface and migration design.
- **Evaluation:** E03/E10; a newly required field is checked against existing records and old producers rather than accepted from a new-schema test alone.
- **Failure and repair:** An entity diagram alone can hide cardinality or conversion rules. Add the necessary dictionary/contract detail and check affected flows.
- **Relationships:** D03 supplies compatibility mechanics; D06 supplies concurrent invariants; R08 supplies rule ownership.
- **Disposition:** Merge; no automatic database, rules engine or universal data model.

#### R05 — Make qualities measurable without inventing targets

- **Source:** B4, chapter 3, practice 9, PDF 110–117.
- **Problem and concept:** Terms such as reliable or usable permit incompatible interpretations. Elicit the conditions and evidence that make the required quality assessable.
- **Applicability:** Targets must be necessary, realistic and grounded in the consuming context. Quality trade-offs require appropriate owners and specialist contributions.
- **Production behaviour:** Connect a quality constraint to workload/environment, observable result and acceptance criterion before it drives structural decisions.
- **Evaluation:** E03/E13; identify the missing workload or latency bound instead of fabricating a percentile target.
- **Failure and repair:** Copying illustrative coverage or performance numbers manufactures requirements. Mark an unknown, investigate or obtain the needed decision.
- **Relationships:** A03/A04 translate qualities into decisions/checks; D02 provides measurement mechanisms.
- **Disposition:** Merge; system-wide qualities remain obligations beyond an individual backlog item.

#### R06 — Compare requirements individually and as a connected set

- **Source:** B4, chapter 4, practices 10–11, PDF 119–140.
- **Problem and concept:** A clear individual statement can still conflict with another or leave a necessary behaviour absent. Compare origins, rules, dependencies and alternative representations.
- **Applicability:** Trace only useful relationships; a draft model is a hypothesis. Inferred convenience features are not automatic requirements.
- **Production behaviour:** Identify ambiguity, omissions, duplicate/conflicting obligations and implementation suggestions masquerading as constraints; connect acceptance to its source.
- **Evaluation:** E03/E15; expose a cross-model contradiction and resolve which assumption is wrong before implementation.
- **Failure and repair:** Fabricated numerical goals used to prompt discussion can be mistaken for approved targets. Label hypotheses and preserve actual decision status.
- **Relationships:** R09 validates the result; A01 prevents architecture preference from inventing intent; L05 supplies contrary observed evidence.
- **Disposition:** Adapt; reject invented targets as accepted facts and arbitrary cognitive limits as design rules.

#### R07 — Use prototypes and priorities to answer bounded questions

- **Source:** B4, chapter 4, practices 12–13, PDF 140–157.
- **Problem and concept:** A prototype can reduce a specific uncertainty; priority needs importance, urgency, dependency and cost context rather than unqualified ranking.
- **Applicability:** Technical exploration stays within engineering scope; UX intent and product priority remain with their owners. Compare items at useful granularity.
- **Production behaviour:** Name the question, select fidelity and a stopping condition; distinguish disposable exploration from code deliberately taken toward production quality.
- **Evaluation:** E01/E18; stop once the question is answered and do not use a polished interface as proof of integration or performance.
- **Failure and repair:** Prototype momentum or weighted scores can substitute for evidence. Reassess the unresolved question and production obligations explicitly.
- **Relationships:** L06 isolates exploration; A07 handles uncertainty; G01 exposes continuing cost.
- **Disposition:** Adapt; no default prototype, prioritisation formula or transfer of product authority.

#### R08 — Keep requirements, rules and terminology canonically usable

- **Source:** B4, chapter 5, practices 14–17, PDF 158–187.
- **Problem and concept:** Usable requirements need retrievable identity and context; business rules may outlive an application, and similar words may have distinct domain meanings.
- **Applicability:** Use the minimum metadata needed for change and traceability. Rule ownership and version matter; storage tools do not perform elicitation or reconciliation.
- **Production behaviour:** Maintain canonical requirements, link derived behaviour to applicable rules, and clarify terms where different interpretations affect implementation.
- **Evaluation:** E03/E17; identify which policy version a test implements and preserve meaningful distinctions between similar terms.
- **Failure and repair:** Multiple inconsistent copies or an unowned rule obscure authority. Resolve the canonical source and trace the affected behaviour/tests.
- **Relationships:** G03 and A06 maintain explanations; D06 enforces application invariants; R10 manages versions.
- **Disposition:** Merge; no mandatory document count, wording convention, enterprise glossary or rules engine.

#### R09 — Validate the intended requirement as well as verifying implementation

- **Source:** B4, chapter 6, practice 18, PDF 188–200.
- **Problem and concept:** Implementation conformance cannot prove that the specified behaviour meets the actual need. Review examples, models and prospective tests to expose misunderstandings.
- **Applicability:** Stakeholder/domain judgement and engineering verification have different responsibilities. Sign-off alone is not validation, and test partitions need justified equivalence.
- **Production behaviour:** Compare requirement and test interpretations, investigate disagreements, and establish an appropriate oracle for normal, boundary and failure cases.
- **Evaluation:** E03/E07/E15; question both a failing implementation and a potentially wrong test, using the accepted need to discriminate.
- **Failure and repair:** Two agreeing representations may repeat the same error. Seek discriminating examples or domain evidence rather than counting agreement.
- **Relationships:** L05 distinguishes characterisation; G04 protects stable obligations; R06 detects set-level inconsistency.
- **Disposition:** Retain; numerical rework and early-detection effectiveness claims require Q02/Q04 challenge.

#### R10 — Manage a baseline as versioned agreement, not a freeze

- **Source:** B4, chapter 7, practices 19–20, PDF 201–220.
- **Problem and concept:** Requirements change over a product's life. Preserve origin, status, impact, decision and the baseline to which each change applies.
- **Applicability:** Concurrent releases may have different baselines; the process should match impact and existing authority. Preauthorised changes need no repeated permission.
- **Production behaviour:** Trace the proposed technical change across requirements, code, data and tests; record the decision and update the appropriate canonical baseline.
- **Evaluation:** E17/E18; distinguish approved intent, observed implementation and pending change without rewriting history.
- **Failure and repair:** Updating the baseline to match reality can conceal an unauthorised deviation. Preserve the discrepancy and obtain any genuinely needed decision.
- **Relationships:** G07/G08 track transitions and evidence; L01 constrains preservation; R02 locates authority.
- **Disposition:** Adapt; reject page 208's proceed-without-approval advice as a source of new authority.

### B5: State, concurrency and distributed failure

#### D01 — Define correctness against an explicit fault model

- **Source:** B5, chapter 1, PDF 17–28 and 39–43; chapter 8, PDF 397–411.
- **Problem and concept:** Component faults and service failures differ. Correlated software/input failures can defeat redundant hardware; safety properties and eventual progress need different assumptions.
- **Applicability:** An algorithm's proof is conditional on its model, including timing, crashes and storage durability. Ordinary crash tolerance is not security or Byzantine-fault assurance.
- **Production behaviour:** State protected invariants, tolerated faults, progress conditions, observability and the recovery/handoff when assumptions fail.
- **Evaluation:** E09/E12; distinguish a recoverable outage from an invariant violation and expose an unmodelled shared dependency.
- **Failure and repair:** Declaring replication sufficient ignores common failures or lost durable state. Reassess assumptions and test the relevant mechanism in an authorised environment.
- **Relationships:** A07 supplies risk comparison; L06 rejects code-only diagnosis; G09 connects recovery to readiness.
- **Disposition:** Retain with model limits; no authority for live fault injection or specialist assurance.

#### D02 — Measure performance under a stated workload

- **Source:** B5, chapter 1, PDF 28–43, load parameters and performance description.
- **Problem and concept:** Performance depends on request mix, size, fan-out, resources and queueing. Means can hide slow users; client-observed response and service time answer different questions.
- **Applicability:** Choose distributions and conditions relevant to the requirement. A load generator that waits for each response may hide accumulating demand.
- **Production behaviour:** Establish the workload and baseline, measure relevant distributions/resource costs, and compare like conditions before claiming improvement.
- **Evaluation:** E13; detect a tail regression hidden by a better mean and reject averaging percentiles across incompatible samples.
- **Failure and repair:** Unspecified load or synthetic throughput alone overstates scalability. Correct the measurement design and report its limits.
- **Relationships:** R05 supplies targets; A04 interprets measurements; A05 exposes downstream bottlenecks.
- **Disposition:** Retain; no fixed percentile target or speculative scale redesign.

#### D03 — Check compatibility in both directions and through stored history

- **Source:** B5, chapter 4, PDF 155–190, encoding evolution and dataflow.
- **Problem and concept:** Readers, writers, stored records and queued messages can outlive one another. A successful new-to-new exchange does not establish transition compatibility.
- **Applicability:** Exact wire/schema resolution rules matter; unknown-field preservation, defaults, numeric conversion and identifier reuse vary by format and operation.
- **Production behaviour:** Map supported reader/writer versions, historical data and read-modify-write paths; define deployment and recovery sequences with their compatibility obligations.
- **Evaluation:** E10/E16; an old writer cannot silently erase newly introduced data, and a newly required field cannot strand supported old records.
- **Failure and repair:** Assuming all clients upgrade first or that a reverted binary reverses data changes breaks transitions. Add the missing compatibility path or revise sequencing.
- **Relationships:** R04 defines meaning; G06 covers dependency promises; G07/G09 govern transition completion.
- **Disposition:** Retain; verify concrete formats/APIs and do not import newer-edition claims.

#### D04 — Specify visibility and failover guarantees explicitly

- **Source:** B5, chapter 5, PDF 206–213 and 217–224.
- **Problem and concept:** Acknowledgement policy trades durability and availability; lag can violate read-own-writes, monotonic reads or causal-prefix expectations in different ways.
- **Applicability:** Guarantees depend on replication, routing, failover and client context. Eventual convergence does not supply a user-visible time bound.
- **Production behaviour:** State acknowledged-write obligations and needed read visibility, then assess lag, leadership change and cross-device behaviour against them.
- **Evaluation:** E10/E12; detect a disappearing acknowledged update or a stale read after an observed newer value under the claimed contract.
- **Failure and repair:** Fixed sleeps, sticky routing or leader labels can fail during outages. Use a mechanism that enforces the required visibility, or disclose a weaker authorised contract.
- **Relationships:** R03 describes observable behaviour; D09 distinguishes consistency models; G09 handles release implications.
- **Disposition:** Qualify by mechanism and fault model; product defaults require Q07 verification.

#### D05 — Identify the transaction boundary and unknown outcomes

- **Source:** B5, chapter 7, PDF 296–312, ACID meanings, operation scope and retries.
- **Problem and concept:** Atomic abort concerns participating writes; isolation and application invariants are separate. A timeout after commit differs from a known abort.
- **Applicability:** External messages or effects may lie outside the transaction. Durability depends on the documented acknowledgement and failure model.
- **Production behaviour:** State participating objects/effects, failure outcomes and retry semantics; distinguish transient aborts from permanent errors and uncertain success.
- **Evaluation:** E11; retrying an uncertain operation cannot silently duplicate an externally visible effect or imply that it was rolled back.
- **Failure and repair:** Treating ACID as a universal guarantee or blindly retrying overload amplifies harm. Inspect the exact boundary and design bounded, appropriate recovery.
- **Relationships:** D07 supplies lost-response cases; D06 supplies invariant races; R08 supplies the rule being protected.
- **Disposition:** Retain; no generic retry count or assumption about current database/ORM defaults.

#### D06 — Choose isolation from the invariant and interleaving

- **Source:** B5, chapter 7, PDF 321–337, lost updates, write skew, phantoms and serial execution.
- **Problem and concept:** Two transactions can each pass a local check yet jointly violate a predicate. Protecting the same row differs from protecting a condition spanning rows or absence.
- **Applicability:** Atomic updates, locks, compare-and-set, constraints and serializable transactions have different scopes/costs. Check actual engine semantics and handle rejected operations.
- **Production behaviour:** State the invariant, construct a violating interleaving and select a supported enforcement mechanism with necessary retry/error handling.
- **Evaluation:** E11; expose write skew on different rows and a race where locking returned rows does not lock an absent record.
- **Failure and repair:** A successful transaction or ignored compare-and-set result is insufficient. Enforce the relevant predicate within a valid boundary.
- **Relationships:** R04/R08 define obligations; D09 separates serializability from real-time ordering; G05 limits fake evidence.
- **Disposition:** Retain with exact semantic qualification; no claim that serializability fixes external effects.

#### D07 — Diagnose partial failure without inventing certainty

- **Source:** B5, chapter 4, PDF 183–190; chapter 8, PDF 361–377.
- **Problem and concept:** Remote calls can lose requests or responses, pause, queue or partially succeed. A timeout cannot identify which happened, and a transport acknowledgement is not application success.
- **Applicability:** Detection delay and false failure suspicion trade off; retries can duplicate work or increase overload. Distributed calls are not ordinary local calls.
- **Production behaviour:** Enumerate plausible outcomes, seek discriminating observations, and define retry, cancellation, deduplication or recovery obligations for the actual operation.
- **Evaluation:** E09/E12; retain unknown status after a lost response, avoid duplicate effects and explain the evidence required to resolve the outcome.
- **Failure and repair:** Declaring timeout equivalent to failure invites unsafe repetition. Preserve uncertainty and reconcile using application-level identity/status where supported.
- **Relationships:** L04 locates observations; D05 constrains retries; A05 exposes cross-service dependencies.
- **Disposition:** Retain; mechanisms and live operational actions require their own context and authority.

#### D08 — Treat clocks and leases as assumptions requiring enforcement

- **Source:** B5, chapter 8, PDF 380–402, clocks, process pauses and fencing.
- **Problem and concept:** Wall-clock order can differ from causality; a process can resume after its lease expires. Client belief in ownership does not exclude stale writes.
- **Applicability:** Local monotonic duration measurement is not cross-machine ordering. Fencing requires a suitable increasing token and enforcement by the protected resource; it is not protection against malicious token forgery.
- **Production behaviour:** Identify time assumptions and reject stale-owner effects at the relevant resource boundary when correctness depends on exclusive ownership.
- **Evaluation:** E12; pause the old owner, admit a newer fenced operation, then reject the stale operation after resumption.
- **Failure and repair:** Checking lease time only in the client leaves a pause window. Establish enforceable resource semantics or avoid claiming exclusion.
- **Relationships:** D01 supplies model limits; D09 supplies ordering distinctions; A07 assesses consequence.
- **Disposition:** Retain; runtime clocks and coordination APIs need current verification.

#### D09 — Distinguish transaction, real-time and causal ordering

- **Source:** B5, chapter 9, PDF 428–464, linearizability, its costs and ordering guarantees.
- **Problem and concept:** Serializability orders transactions; linearizability adds an object's real-time operation constraint; causal order and total delivery order answer different questions. Sortable timestamps alone do not finalise a distributed decision.
- **Applicability:** Specify object/key/partition scope and cross-channel dependencies. Overlapping execution can still implement linearizable semantics; the abstraction does not ban physical concurrency.
- **Production behaviour:** Name the required guarantee, read path and order scope, and evaluate operation histories or message/state races against it.
- **Evaluation:** E11; ordered delivery alone cannot prove fresh reads or global order across partitions.
- **Failure and repair:** Generic strong-consistency, FIFO or CAP labels conceal missing guarantees. Check the exact model and mechanism rather than assuming them.
- **Relationships:** A06's FIFO example needs qualification; D04 exposes read visibility; D06 distinguishes transaction invariants.
- **Disposition:** Qualify; theoretical/product performance generalisations and implementation claims enter Q07/Q08.

#### D10 — Account for coordination state and progress conditions

- **Source:** B5, chapter 9, PDF 466–474 and 480–488, atomic commit and fault-tolerant consensus.
- **Problem and concept:** Prepared participants can become uncertain after coordinator failure. Consensus mechanisms add agreement/recovery rules, but progress depends on their fault, communication and quorum assumptions.
- **Applicability:** Atomic commit, transaction isolation and consensus are distinct. A timeout alone does not solve asynchronous impossibility, and a majority slogan does not specify a correct protocol.
- **Production behaviour:** Identify durable coordinator state, in-doubt recovery, membership/leadership assumptions and the required availability trade-off; use verified mechanisms rather than inventing a protocol.
- **Evaluation:** E11/E12/E16; a prepared participant cannot unilaterally abort merely because its coordinator timed out; recovery preserves the recorded decision.
- **Failure and repair:** Calling a coordinator stateless or dropping its log can make recovery impossible. Preserve required state and test the documented recovery path.
- **Relationships:** D01 separates safety/progress; G09 requires viable recovery; A01 compares coordination costs.
- **Disposition:** Qualify; current implementations, topology limits and performance claims require Q07/Q08.

## 4. Provisional capability model and evaluation candidates

These eighteen capabilities organise decisions across books. They are **research hypotheses**, not eighteen skills or a command catalogue. Later stages must challenge, merge, divide or reject them using professional evidence and actual workflows. The workflow column states an implication for future behaviour; it does not prescribe a runtime, permanent graph, universal document or command name.

The engineering role acts within the consuming repository's authority. Product owners retain value and business-policy decisions; UX retains interaction intent; security, data/ML and other specialists retain their assurance and domain judgements. Platform/SRE retains live-service ownership, and QA retains independent assembled-system assessment. The engineer supplies the relevant technical evidence and executes already authorised engineering work. These handoffs apply even when one person holds multiple roles. Security, accessibility and other material constraints remain cross-cutting obligations despite incomplete corpus depth.

| Capability | Production responsibility | Workflow / future command implication | Evidence boundary |
|---|---|---|---|
| C01 — Frame intent and authority | Translate accepted need into bounded technical acceptance; expose actual unresolved decisions. | Read existing intent and authority → distinguish problem/solution/outcome → clarify only decisions that affect the work. | Does not decide product strategy or manufacture approval. |
| C02 — Reconstruct relevant system context | Understand affected behaviour, consumers, dependencies and uncertainty. | Inspect existing evidence → trace relevant effects → select observation points → update the bounded model. | A sketch or static search is not proof of all runtime uses. |
| C03 — Specify assessable obligations | Express behaviour, state, data, rules and qualities sufficiently for implementation and acceptance. | Compare requirements, examples and models → resolve material inconsistency → connect each obligation to evidence. | Domain semantics and numerical targets need valid sources. |
| C04 — Compare architectural alternatives | Select a feasible design that satisfies constraints with defensible trade-offs. | Include the current design/local repair → compare alternatives → state assumptions and consequences. | No default style or context-free ranking. |
| C05 — Assess structure and architectural risk | Detect coupling and quality risks, then choose proportionate mitigation/checks. | Trace structural and runtime dependencies → identify failure mechanism → compare mitigation and verification cost. | Metrics and ratings are evidence aids, not semantic verdicts. |
| C06 — Establish feedback in weakly tested code | Create enough trustworthy baseline evidence to make the intended change. | Find an actual seam/observation point → make a conservative cut → characterise/classify behaviour → verify test sensitivity. | Applies when feedback is inadequate; not every edit needs a new test harness. |
| C07 — Choose useful oracles and verification boundaries | Establish relevant correctness evidence and disclose what a check cannot show. | Select cases and boundary → assess oracle and substitute fidelity → add broader checks for uncovered material risks. | Coverage counts and fake success do not certify production behaviour. |
| C08 — Make a coherent change while preserving obligations | Implement the authorised delta with proportionate scope and controlled restructuring. | Identify preservation envelope → separate exploration/structural edits from behaviour change → check the resulting obligations. | Language/tool correctness requires additional ecosystem evidence. |
| C09 — Discriminate failure hypotheses | Determine a defensible cause and sufficient repair from observations. | Reproduce or substantiate failure → enumerate plausible outcomes → seek discriminating evidence → confirm repair and residual uncertainty. | Corpus grounding is partial and strongest for effect tracing/distributed uncertainty; general debugging remains Q05. |
| C10 — Evolve contracts and persistent state | Preserve supported consumers and data across transitions. | Map versions and data paths → check reader/writer/visibility obligations → sequence migration/recovery → verify the supported combinations. | Semantic data ownership and engine-specific mechanisms remain external inputs. |
| C11 — Protect concurrent invariants | Choose valid transactional, ordering and coordination semantics for the required rule. | State invariant/scope → construct violating interleaving → select enforcement → assess retry and external-effect boundaries. | Does not author a consensus protocol or claim general shared-memory expertise. |
| C12 — Design and verify failure/recovery behaviour | Preserve invariants and define progress/degradation under a stated fault model. | Identify uncertain outcomes and stale actors → choose enforceable recovery behaviour → check fault cases in an authorised environment. | General service operability needs Q06; live experiments require actual authority. |
| C13 — Evaluate performance under relevant conditions | Assess whether a change meets workload/resource and response requirements. | Establish baseline/workload → measure relevant distributions → investigate bottleneck → compare controlled evidence. | Detailed profiling, runtime memory models and benchmark validity need further research. |
| C14 — Control dependency and configuration evidence | Preserve compatible, reproducible effective inputs. | Inspect resolution/configuration → identify consumers and versions → validate upgrade → bind results to exact inputs. | Security/provenance and ecosystem rules need current sources. |
| C15 — Review engineering substance | Assess scope, correctness, design, compatibility, test quality and explanations under repository rules. | Review intent plus diff/evidence → classify defects versus preferences → resolve material feedback → record remaining limits. | Review cannot replace execution evidence or specialist assurance. |
| C16 — Establish migration and release readiness | Demonstrate coherent transitions, candidate identity and viable recovery; execute within existing authority. | Check supported intermediate states → bind candidate evidence → assess rollout/exposure/recovery → verify transition completion. | Readiness does not imply a release happened or confer deployment rights. |
| C17 — Maintain decisions and handoff knowledge | Keep canonical behaviour, rationale, baseline and limitations usable by the next maintainer/owner. | Update affected records → preserve decision/supersession history → provide evidence links and unresolved receiving needs. | Document count is not quality; use existing artefacts when adequate. |
| C18 — Choose proportionate investigation and change scope | Compare adequate options using need, dependencies, risk, uncertainty and continuing cost. | Identify the next decision → choose the cheapest sufficient investigation/change → stop or revisit when evidence warrants. | Product priority is an input; no fabricated universal economic/risk score. |

### Evaluation criteria and candidate cases

`E##` and `BC##` share the number of their capability. Each case describes an independently devised test of judgement for later benchmark design. **None was executed**, and no threshold or fixture implementation is accepted here. Passing one would not establish the whole capability. Later evaluation must also test minimal adequate responses and unnecessary-work failures.

| Criterion | Candidate case and discriminating expected behaviour |
|---|---|
| E01 — Intent, authority and acceptance are distinguished. | **BC01: Export request.** An approved CSV export is presented alongside an optional product redesign. Proceed with authorised technical choices, identify a genuinely missing retention-policy decision, and do not claim that export tests establish adoption or business value. |
| E02 — The bounded model includes relevant effects and honest unknowns. | **BC02: CLI option change.** A parser feeds both console output and a scheduled file consumer. Locate both paths and observation points; a static sketch that omits the scheduled consumer fails. Avoid mapping unrelated subsystems. |
| E03 — Requirements and oracles are mutually consistent and grounded. | **BC03: Background import.** A state table, field dictionary and acceptance examples disagree about an optional field after a retry. Identify the conflict and its owner/source; include relevant event/error behaviour without inventing a quality target. |
| E04 — The selected alternative satisfies actual constraints. | **BC04: Offline settings editor.** Compare a local repair, modular restructuring and a remote service under an offline requirement. Reject infeasible alternatives and justify remaining trade-offs; service popularity or a style score cannot decide. |
| E05 — Structural/risk claims follow a mechanism rather than a score. | **BC05: Shared configuration store.** Two deployable services share a schema and fail together. Expose the coupling and common failure despite favourable import metrics; select a bounded check or mitigation with stated uncertainty. |
| E06 — Testability work creates a sensitive, correctly interpreted baseline. | **BC06: Legacy formatter.** A hardwired clock obstructs a regression check and an existing output is defective. Identify the real enabling point, make a conservative seam, label the defect, and retain adjacent formatting behaviour. A compiling but differently bound seam fails. |
| E07 — Tests detect relevant failures without unnecessary implementation coupling. | **BC07: File adapter.** A fake accepts paths the real adapter rejects. Find the fidelity gap, use appropriate shared/real-boundary evidence, and preserve a stable behavioural check through an equivalent refactor. Do not infer persistence guarantees from the fake. |
| E08 — The patch is a sufficient, coherent authorised delta. | **BC08: Subcommand repair.** A default-dispatch defect coexists with tempting unrelated cleanup. Preserve supported dispatch/output contracts, fix the cause and justify any structural change. A compiling inherited fallback or broad rewrite is not sufficient evidence. |
| E09 — The diagnosis discriminates causes and preserves unresolved outcomes. | **BC09: Uncertain job submission.** The submit response is lost after possible acceptance. Distinguish rejected, accepted and unknown outcomes using available application evidence; do not equate a timeout with failure or repeat an irreversible effect blindly. |
| E10 — Compatibility covers supported versions and historical data. | **BC10: Settings schema evolution.** A new optional attribute must survive old-client read/modify/write and delayed replication. Check old/new readers/writers and the stated read visibility. New-to-new success and a fixed delay are insufficient. |
| E11 — Enforcement protects the invariant under a violating interleaving. | **BC11: Concurrent resource assignment.** Two transactions inspect a shared predicate and update different rows; another variant loses a response after an external action. Show the invariant failure and appropriate semantic boundary. FIFO delivery alone cannot prove unique assignment or fresh reads. |
| E12 — Recovery enforces safety and states progress assumptions. | **BC12: Expired worker lease.** Pause an old worker, allow a newer fenced write, then resume the old worker. Require resource-side stale-write rejection; separately assess coordinator loss without pretending all nodes can progress through a partition. |
| E13 — A performance claim is tied to valid comparative evidence. | **BC13: Document preview load.** Mean response improves while tail latency and queued demand worsen. Interpret request mix, concurrency, resources and measurement method; do not average percentiles or assert an unspecified SLA. |
| E14 — Effective inputs and compatibility match the reported result. | **BC14: Dependency update.** A nominally compatible release changes behaviour and a CI configuration selects another transitive version. Identify the mismatch, preserve the repository's resolution policy and obtain evidence for the actual candidate. |
| E15 — Review catches material engineering defects and avoids invented gates. | **BC15: Review bundle.** A plausible patch has a mismatched acceptance oracle and unhandled consumer; a separate comment requests equivalent stylistic rewording. Distinguish the substantive defects from preference and use the actual project review rules. |
| E16 — Release/retirement evidence covers identity, transitions and recovery. | **BC16: Mixed-version rollout.** A verified artefact is rebuilt, an old client remains active, and a schema change survives binary rollback. Detect each evidence gap, preserve required coordinator/data state, and define a viable completion/recovery condition before authorised execution. |
| E17 — The next maintainer can identify authoritative behaviour and rationale. | **BC17: Superseded decision.** Code, requirements and an old ADR disagree after a change. Preserve intended/observed/pending distinctions and supersession history, update the canonical record, and provide a concise receiving handoff without duplicating everything. |
| E18 — Effort and scope are justified by the next material decision. | **BC18: Small maintenance task.** A bounded compatibility fix has a tempting architecture workshop and elaborate prototype. Choose the least costly adequate evidence, account for real dependency risk, and stop when acceptance is established. Unexamined assumptions and invented economic scores both fail. |

## 5. Source-to-capability matrix

This is a relational mapping, not a list of topic associations. For each row, the capability supplies the **production responsibility and workflow implication** in section 4; the matching `E##` supplies the evaluation criterion and `BC##` the candidate case. Thus every listed path is complete:

`finding + examined source → C## responsibility → C## workflow → E## criterion → BC## case`.

All 42 material findings have at least one path. Multiple paths indicate different implications of the same finding, not extra independent evidence. Rejected absolute readings are evaluated through the retained qualified behaviour; none is quietly promoted to a rule.

| Finding | Capability → evaluation → candidate case | Specific implication carried forward |
|---|---|---|
| G01 | C08 → E08 → BC08; C18 → E18 → BC18 | Preserve obligations and account for supported lifetime cost. |
| G02 | C15 → E15 → BC15 | Review material engineering concerns using actual ownership/gates. |
| G03 | C17 → E17 → BC17 | Keep canonical explanations usable and current. |
| G04 | C07 → E07 → BC07 | Preserve stable behavioural checks; revalidate a defective oracle. |
| G05 | C07 → E07 → BC07 | Match dependency fidelity to the property being claimed. |
| G06 | C14 → E14 → BC14 | Check effective dependency and consumer compatibility. |
| G07 | C16 → E16 → BC16 | Verify intermediate states, consumers and transition completion. |
| G08 | C14 → E14 → BC14; C16 → E16 → BC16 | Tie evidence to exact effective inputs and the delivered candidate. |
| G09 | C16 → E16 → BC16 | Distinguish readiness, exposure and viable recovery. |
| L01 | C08 → E08 → BC08; C18 → E18 → BC18 | State the authorised delta and preservation envelope. |
| L02 | C06 → E06 → BC06 | Make a conservative initial cut before expanding change. |
| L03 | C06 → E06 → BC06; C07 → E07 → BC07 | Verify the seam binding and disclose substitute limits. |
| L04 | C02 → E02 → BC02; C09 → E09 → BC09 | Select observations from relevant effect paths. |
| L05 | C06 → E06 → BC06 | Distinguish observed baseline, desired behaviour and unknown intent. |
| L06 | C02 → E02 → BC02; C08 → E08 → BC08 | Validate understanding hypotheses and do not confuse compilation with preservation. |
| A01 | C04 → E04 → BC04 | Compare feasible alternatives against actual constraints. |
| A02 | C05 → E05 → BC05 | Inspect semantic/runtime coupling beyond import counts. |
| A03 | C03 → E03 → BC03; C04 → E04 → BC04 | Ground architectural qualities in validated conditions. |
| A04 | C05 → E05 → BC05; C13 → E13 → BC13 | Define meaningful quality checks and interpret measurements. |
| A05 | C04 → E04 → BC04; C13 → E13 → BC13 | Trace quality scope and bottlenecks through real dependencies. |
| A06 | C17 → E17 → BC17 | Preserve rationale, assumptions and supersession. |
| A07 | C05 → E05 → BC05; C18 → E18 → BC18 | Compare risk mechanisms and mitigation effort without false precision. |
| R01 | C01 → E01 → BC01; C18 → E18 → BC18 | Separate need, proposed solution and business outcome. |
| R02 | C01 → E01 → BC01; C02 → E02 → BC02 | Identify affected parties, system boundary and actual decision authority. |
| R03 | C03 → E03 → BC03 | Specify goal/event/state and exception behaviour. |
| R04 | C03 → E03 → BC03; C10 → E10 → BC10 | Connect data meaning and constraints to producer/consumer evolution. |
| R05 | C03 → E03 → BC03; C13 → E13 → BC13 | Require grounded quality targets and operating conditions. |
| R06 | C03 → E03 → BC03; C15 → E15 → BC15 | Detect conflicts, omissions and unsupported inferred requirements. |
| R07 | C01 → E01 → BC01; C18 → E18 → BC18 | Bound prototype questions and technical prioritisation inputs. |
| R08 | C03 → E03 → BC03; C17 → E17 → BC17 | Trace behaviour to canonical rules and scoped terminology. |
| R09 | C03 → E03 → BC03; C07 → E07 → BC07; C15 → E15 → BC15 | Validate need and oracle as well as implementation conformance. |
| R10 | C17 → E17 → BC17; C18 → E18 → BC18 | Preserve versioned agreement, impact and actual authorisation. |
| D01 | C09 → E09 → BC09; C12 → E12 → BC12 | State fault assumptions, safety, progress and recovery limits. |
| D02 | C13 → E13 → BC13 | Compare performance under an explicit workload and valid measurement. |
| D03 | C10 → E10 → BC10; C16 → E16 → BC16 | Check mixed versions, stored history and recovery compatibility. |
| D04 | C10 → E10 → BC10; C12 → E12 → BC12 | State read visibility and acknowledged-write obligations under failover. |
| D05 | C11 → E11 → BC11 | Locate transaction/external-effect boundaries and uncertain outcomes. |
| D06 | C11 → E11 → BC11 | Construct invariant-violating interleavings and choose valid enforcement. |
| D07 | C09 → E09 → BC09; C12 → E12 → BC12 | Diagnose uncertain remote effects and avoid unsafe repetition. |
| D08 | C12 → E12 → BC12 | Enforce stale-owner exclusion at the protected resource. |
| D09 | C11 → E11 → BC11 | Distinguish order scope, recency, causality and transaction isolation. |
| D10 | C11 → E11 → BC11; C12 → E12 → BC12; C16 → E16 → BC16 | Preserve coordination state and valid recovery/progress conditions. |

## 6. Corpus reconciliation and remaining coverage

### 6.1 Reinforcement and overlap across all ten book pairs

The corpus repeatedly supports making obligations explicit, tracing effects, obtaining useful feedback and retaining decision context. These are convergent practitioner arguments with some formal systems reasoning in B5. Shared vocabulary or agreement does **not** constitute independent empirical corroboration. A book's cited study/proof was not independently examined merely because its discussion was read.

| Pair | Actual overlap and complementary depth | Tension, context distinction and resulting decision |
|---|---|---|
| B1 / B2 | G01/G07 and L01/L04 connect consumer preservation to local effect tracing; G04/G05 and L02/L03 connect test boundaries to feasible feedback. | Google-scale coordinated change presumes infrastructure that weakly tested code lacks. Start with the actual feedback gap; escalate coordination only for affected obligations. G04's absolute unchanged-test reading conflicts with L05's defective baseline. Use BC06/BC08 to distinguish preservation from defect repair. |
| B1 / B3 | G01/G02 and A01/A06 connect lifecycle trade-offs, review and recorded architectural rationale. | Generic rewrite/microservice return claims in G09 cannot decide A01's contextual comparison. Reuse prior decisions unless premises change, and do not prescribe architecture ceremony for a local repair. BC04/BC18 test the distinction. |
| B1 / B4 | G03/G08 and R08/R10 require maintained intent and evidence tied to a version; G02 and R09 complement review with acceptance validation. | Google approval mechanisms are organisational policies; R02 addresses who actually holds a decision. Requirements agreement does not prove implementation, and CI success does not prove business outcome. Merge canonical knowledge, keep different evidence claims separate in BC01/BC15/BC17. |
| B1 / B5 | G06–G09 describe compatibility and delivery responsibilities; D03–D05 explain mixed versions, stored history and uncertain commit outcomes. | Shipping faster or reverting binaries cannot erase persistent-state obligations. Retain incremental delivery only when intermediate states and recovery are valid. Use BC10/BC16; do not assume Google's scale or infrastructure. |
| B2 / B3 | L04/L06 and A02 connect effects, structural understanding and dependency boundaries. | A useful seam is not necessarily a desirable final architecture; an ideal design is not a safe initial cut. Separate enabling feedback from justified structural improvement. BC05/BC06/BC08 reject both permanent test-driven distortion and unprotected redesign. |
| B2 / B4 | L01/L05 and R01/R09 distinguish observed behaviour, intended acceptance and authorised change. | Characterisation answers what occurs, requirements validation what should occur. Neither automatically overrides the other: preserve valid obligations, correct the approved defect, and expose unresolved intent. R07 prototypes and L06 scratch work also share a hypothesis boundary, with different audiences. BC03/BC06/BC18 test these decisions. |
| B2 / B5 | L03/L04 and D03/D07 explain why local feedback must be connected to external effects and data paths. | A fast isolated check cannot establish distributed durability, causal order or compatibility with historical data. A literal unchanged-code-cannot-fail rule conflicts with D01/D07's environment and partial failures. Add evidence for the relevant boundary, not indiscriminately more tests. BC07/BC09/BC10 exercise the limit. |
| B3 / B4 | A03/A06 and R05/R08 connect quality requirements, architectural choices and decision records. | The terminology differs, but no charter vocabulary change is needed. Architect-inferred qualities remain hypotheses until grounded; numeric model placeholders cannot become accepted targets. R02's actual authority governs the decision. BC03/BC04/BC17 assess traceability without duplicate bureaucracy. |
| B3 / B5 | A05/A07 and D01/D02 connect quality scope, shared dependencies, load and failure mechanisms. | Architecture examples invoking FIFO, topic/queue properties or generic clustering need narrower semantics than labels provide. D09/D10 distinguish partition/order/read/progress guarantees. Do not adopt a technology recommendation from a style chart or ADR example. BC05/BC11/BC12 supply challenge directions. |
| B4 / B5 | R03/R04/R08 define behaviour/data rules; D03–D10 explain evolution, concurrent invariant violations and uncertain outcomes. | A business rule is not enforced by documenting it or naming an ACID database. Conversely, choosing a technical mechanism cannot silently weaken the rule or change data meaning. Connect the approved obligation to exact semantic enforcement in BC03/BC10/BC11. |

### 6.2 Explicit conflict dispositions and context alternatives

| Issue | Examined evidence | Resolution for the provisional model |
|---|---|---|
| Unchanged tests versus correcting a recorded defect | G04, B1 PDF 385–394; L05, B2 PDF 209–219; R09 | **Reject the absolute rule.** Preserve tests for stable valid obligations; revise a defective oracle with evidence of intended behaviour and retain adjacent regression protection. |
| Source edits as the only cause of failure | L06, B2 PDF 326; G01; D01/D07 | **Reject the closed-world reading.** Unchanged code can encounter changed inputs, dependencies, configuration or faults. A compiler result is one bounded observation. |
| Class-isolated tests versus durable boundary evidence | L02/L04 and G04/G05 | **Context-dependent alternative.** Local checks aid feedback/localisation; broader checks protect other obligations. Keep a check when its evidence is material, rather than replacing it solely to fit class boundaries. |
| Generic rewrite/delivery claims versus migration constraints | G09, especially B1 PDF 812; A01; L01; D03 | **Qualify and research further.** Compare the current system, change economics and supported intermediate states. Faster delivery and microservices are not independent proof of lower risk or better return. |
| No right/wrong architecture versus hard invariants | A01; R05; D06/D09 | **Reject the literal universal claim.** Several feasible alternatives may exist, but violating an accepted invariant makes an alternative unsuitable. |
| Numerical architecture/risk proxies versus semantic obligations | A02/A04/A07; G04; R05 | **Qualify.** Counts, ordinal scores and thresholds can guide investigation. They cannot substitute for correctness, adequacy, probability estimates or grounded acceptance. |
| FIFO or replicated storage labels versus precise guarantees | A06, B3 PDF 714; D04/D09/D10 | **Research further before product rules.** Distinguish enqueue/delivery/processing order, key/partition scope, duplicate effects, read freshness and failure behaviour. B5's conditional models expose questions; they are not a current broker audit. |
| Draft model or recorded reality versus approved requirement | R06, B4 PDF 138; R10, PDF 208–209; L05 | **Reject fabricated authority.** Label hypotheses and observed deviations, retain their history, and use existing authorisation. Never turn a deliberately invented target or unapproved deviation into an accepted baseline. |
| Central versus code-adjacent records | G03; A06; R08 | **Context-dependent alternative.** Choose an accessible canonical source with version/status links. Do not copy records merely to satisfy both storage preferences. |
| Large-team review/change policies versus consuming-repository authority | G02/G07; A06/A07; R02/R10; L06 | **Adapt.** Existing owner, gate and execution policies govern. Neither a book's bypass example nor its mandatory pairing/workshop advice grants authority or mandates extra people. |
| Formal algorithm versus deployed implementation | D01/D08–D10 | **Qualify.** State safety and progress assumptions and verify the actual implementation/configuration. Clock resolution, replication count or a named consensus algorithm does not prove the full application contract. |

These resolutions restrict source advice to the accepted charter; none requires rewriting Stage 1 or Stage 2. “Reject” concerns the stated overgeneralisation, not rejection or demotion of its source book. Alternative methods remain available when their prerequisites and costs fit the task.

### 6.3 Revisit every Stage 2 knowledge dimension

“Substantial foundation” means the examined corpus supplies actionable reasoning for that dimension; it does not mean complete professional coverage or empirical validation. “Partial” means important owned decisions still lack sufficient depth. All dimensions still undergo Stage 4 challenge.

| Dimension | Direct foundation from this stage | Remaining depth / Stage 4 question |
|---|---|---|
| K01 — Requirements and acceptance | **Substantial:** R01–R10, A03; C01/C03 | Validate proportionate use, conflicting intent and specialist inputs; Q04/Q10/Q11. |
| K02 — Design and architecture | **Substantial:** A01–A07, D09/D10; C04/C05 | Challenge style assumptions, risk metrics and non-backend contexts; Q03/Q08/Q09/Q11. |
| K03 — Construction and code quality | **Partial:** G02/G04, L01–L03/L06; C06–C08/C15 | Language semantics, errors/resources, typing and secure construction remain ungrounded in detail; Q01/Q05/Q11. |
| K04 — Maintenance and evolution | **Substantial:** G01/G06–G09, L01, R10, D03; C08/C10/C16/C18 | Actual support/retirement economics and platform migration practice; Q02/Q03/Q07/Q10. |
| K05 — Brownfield understanding | **Substantial for bounded change:** L03–L06, R02; C02/C06 | Dynamic integrations, non-OO examples and general investigation methods; Q05/Q11. |
| K06 — Refactoring and technical debt | **Partial:** L01/L02/L06, A02; C05/C08/C18 | Detailed transformations and economic evidence beyond practitioner heuristics; Q03/Q09/Q10/Q11. |
| K07 — Testing and test quality | **Substantial starting methods, incomplete test design:** G04/G05, L02–L05, R09; C06/C07 | Boundary/structural/property-based adequacy, oracle limits and nondeterminism; Q04. The requirements-book substitution does not close this gap. |
| K08 — Debugging and root cause | **Partial:** L04/L06, D01/D07; C09 | General causal debugging, reproduction, tracing and profiling methods; Q05. |
| K09 — Code review | **Substantial practitioner foundation:** G02, R06/R09, A07; C15 | Effectiveness, small-team constraints and review of misleading evidence; Q02/Q04/Q10/Q12. |
| K10 — API and contract evolution | **Substantial:** G06/G07, R04, D03/D04; C10/C14 | Current protocol/SDK semantics and external consumer practices; Q07/Q11. |
| K11 — Data and schema evolution | **Substantial semantic foundation:** R04/R08, D03–D06/D09/D10; C10/C11 | Concrete migration/backfill/recovery mechanics and semantic ownership; Q06/Q07/Q08. |
| K12 — Security engineering | **Insufficient dedicated depth:** requirements/fault boundaries in R05/A03/D01 only | Retain the charter responsibility and specialist handoff; threat modelling, secure construction and supply-chain evidence are high-priority Q01 work. |
| K13 — Performance and concurrency | **Substantial for data-system reasoning; partial overall:** A04/A05, D02/D06/D08–D10; C11/C13 | Profiling, shared-memory/async semantics and measurement validity; Q05/Q07/Q08/Q09. |
| K14 — Reliability and resilience | **Substantial for distributed data; partial overall:** A05/A07, D01/D04/D07–D10; C12 | General service failure handling, degradation and incident learning; Q06/Q07. |
| K15 — Delivery and release readiness | **Substantial conceptual foundation:** G07–G09, D03/D10; C16 | Concrete deployment/recovery mechanisms and independent effectiveness evidence; Q02/Q06/Q07. |
| K16 — Observability and operability | **Partial:** D01/D02/D07, A04/A05; C09/C12/C13 | Telemetry selection, cost, diagnostic value, alerts and operator handoff; Q05/Q06. |
| K17 — Configuration and dependencies | **Partial:** G06/G08; C14 | Effective configuration, package resolution, provenance, CI privilege and secrets guidance; Q01/Q07/Q11. |
| K18 — Economics and scope | **Substantial reasoning, limited empirical support:** G01, L01, A01/A07, R01/R07/R10; C18 | Benefits versus maintenance/process cost, including small tasks; Q02/Q03/Q09/Q10. |
| K19 — Human review and commitment | **Substantial role distinctions:** G02, A06/A07, R02/R10; C01/C15/C17 | Actual authority comes from the charter/task/repository; truthful automated evidence and consequential actions need Q12, then Stage 8 landscape research. |
| K20 — Documentation and handoffs | **Substantial practitioner foundation:** G03, A06, R08/R10; C17 | Receiving-owner needs, effectiveness and economical maintenance; Q06/Q10/Q11/Q12. |

The coverage also has a context bias: English-language practitioner accounts, large backend systems, distributed data and substantial OO examples. Client/offline software, accessibility, embedded/real-time systems, games, data/ML semantics and specialist assurance are underrepresented. Their charter boundaries remain in force. Mentioning a quality or an example in a book does not establish competence in that domain.

## 7. Claims and gaps for Stage 4 challenge

These are **open research questions**, not completed broader research, current technical recommendations or Stage 3 blockers. No missing source access remains for this stage. Stage 4 must read primary professional/technical material, seek counterexamples and distinguish empirical support, contextual judgement and unresolved uncertainty. Suggested evidence below describes what would resolve a question; it does not claim that evidence has already been obtained.

Priorities order the research within Stage 4: **high** affects correctness, authority or a major uncovered responsibility; **medium** affects effectiveness, cost or scope calibration. Both groups must be assessed or explicitly bounded to satisfy Stage 4, rather than silently dropping medium-priority questions.

| Question / priority | Claim or gap, with traceable origin | Consequence for the model | Evidence needed to resolve or bound it |
|---|---|---|---|
| **Q01 — Secure construction and supply chain / high** | K12 remains weak. A03's security classification, A06's exception example and D01's non-Byzantine assumptions do not supply security assurance. | C03–C08/C14/C15 must integrate security-relevant obligations without pretending to replace specialists. | Direct then-current secure-development and application-security guidance; primary ecosystem guidance on trust boundaries, dependencies, secrets and CI privilege; concrete threat-to-control-to-check examples. Distinguish development evidence from certification. |
| **Q02 — Effectiveness of early feedback, review and frequent delivery / medium** | G01/G02/G09 and R09 contain practitioner/causal benefit claims; B1 PDF 808–823 and B4 PDF 188–200 do not establish a universal effect size. | Do not promise that process presence, release frequency or an approval causes quality. | Original empirical studies or datasets/methods, with population, confounding, effect limits and contrary findings; examine which mechanism helps a small change and what it costs. |
| **Q03 — Rewrite, architecture change and migration economics / medium** | G09, especially B1 PDF 812, suggests favourable microservice/rewrite returns; A01 and L01 require context and preservation. | C04/C08/C18 must include current-design/local-repair alternatives and transition costs. | Primary migration/postmortem accounts with baseline, migration effort, consumer/data obligations and outcome evidence, including unsuccessful or unnecessary rewrites. No style-popularity proxy. |
| **Q04 — Test design, oracle quality and adequacy / high** | G04/G05, L02–L05 and R09 supply useful methods but leave dedicated test-design depth incomplete after the accepted corpus replacement. | C06/C07/C15 need criteria for omitted cases, misleading green results, nondeterminism and test maintenance. | Primary testing research and maintained tool documentation for boundary/structural/property-based methods, mutation sensitivity and flaky-test diagnosis; inspect method assumptions, false confidence and cost. A supplemental book requires its own direct-source evidence. |
| **Q05 — General debugging, profiling and shared-memory concurrency / high** | L04/L06 and D07 address effects and remote uncertainty, not a complete general diagnosis method; D02 does not establish runtime memory semantics. | C09/C13 and parts of C08/C11 remain provisionally grounded. | Primary debugging/performance methodology and actual runtime/language memory/async documentation; examples where observations discriminate competing causes and confirm a sufficient repair. Verify measurement bias, reproduction limits and resource behaviour. |
| **Q06 — Operability and release/recovery beyond data systems / high** | G08/G09 and D01/D07/D10 identify readiness and failure obligations; K14–K16 still lack general operational mechanisms. | C09/C12/C16/C17 need realistic telemetry, degraded behaviour, recovery and receiving-owner evidence. | Primary operational guidance and incident reports; official deployment/rollback/configuration mechanisms; examples of failed recovery, irreversible data changes and non-server delivery. Separate software evidence from live-service authority. |
| **Q07 — Currency of products and runtime mechanisms / high** | B5 is the supplied **2017 first edition**: D03–D10 mention formats, isolation, replication, coordination and historical system defaults. G06 also discusses particular dependency strategies. | Preserve conceptual questions but do not turn old examples into current commands, defaults or guarantees. | Exact current/versioned primary docs and release histories for any product chosen in later examples: supported isolation/constraints, wire/schema resolution, retry/acknowledgement, read paths, durability/failover, membership and dependency resolution. Verify the consuming configuration; no silent substitution of DDIA editions. |
| **Q08 — Ordering, coordination and performance claims / high** | A01's topic/queue examples, A06's FIFO example (B3 PDF 714), and D09/D10's consistency, quorum and impossibility discussions need precise scope. B5 PDF 446–452/466/482–487 includes broad theoretical/performance language. | C04/C11/C12 must distinguish message processing from delivery, transaction scope from real-time reads, and safety from progress. | Read original definitions/proofs with their models and primary implementation contracts. Check partition/key scope, retries, read barriers, membership and failure assumptions. Timeouts alone do not establish progress; physical concurrency is not forbidden by a linearizable abstraction. Product performance needs measured conditions. |
| **Q09 — Architecture metrics and risk validity / medium** | A02/A04/A07 use structural metrics, fitness checks and ordinal risk tools; illustrative thresholds and aggregation lack universal validity. | C05/C13/C18 must not certify semantics, test quality or probability from proxy scores. | Original metric studies and practical counterexamples, with construct validity, calibration, costs and gaming risks. Compare a proposed measure to the actual invariant and useful decision; retain uncertainty when data is absent. |
| **Q10 — Proportionate requirements, documentation and team process / medium** | R01–R10, G02/G03 and A06/A07 offer practices spanning organisational settings; B4 is deliberately concise. | C01/C03/C15/C17/C18 must work for solo/small maintenance tasks as well as multi-owner work. | Primary practice accounts or studies comparing representations and review/decision methods, including failed requirements, obsolete records and process overhead. Test whether existing artefacts suffice and what evidence a receiving maintainer needs. |
| **Q11 — Ecosystem, client and specialist contexts / high** | K03/K05/K10/K13/K17 and the context-bias review reveal unexamined language/client/accessibility and specialist obligations. | Challenge the backend/OO emphasis while retaining bounded handoffs; do not grow unsupported universal rules. | Primary language/framework/platform and accessibility guidance for representative library, CLI, service and offline/client workflows. Bound embedded/real-time, games, data/ML and other specialist assurance with explicit responsibility and evidence handoffs. Later pack research supplies deeper specialisation. |
| **Q12 — Authority and evidence integrity in automated engineering / high** | R02/R10 reject invented authority; G08 distinguishes tested from delivered inputs; G02 distinguishes review from proof. None of the five books establishes reliable agent behaviour. | All capabilities must preserve real authorisation and report observations, limitations and execution truthfully. | Professional change/review/release obligations and concrete cases of misreported, stale or incomplete evidence. Stage 4 establishes responsibilities; Stage 8 investigates current tools/providers. Later evaluation must test false success, concealed uncertainty and unauthorised consequential action. |

For each question, Stage 4 should preserve the originating finding and report: examined primary source/version/location; supported, qualified or contradicted claim; applicability; changed production implication; and evaluation consequence. Unresolved evidence must stay explicit. Existing Stage 2 supplementary candidates remain leads only; no findings from their unread texts are imported here.

The capability model is therefore grounded in direct book examination but **not yet justified independently of the corpus**. That is the next stage's gate. No benchmark, installation, skill implementation, pack readiness or final bootstrap completion is claimed.

## 8. Conformance review and stage handoff

The original bootstrap Stage 3 was reread after the outputs were written. The review checked the actual record against every extraction field, mapping step, reconciliation category, publication restriction and exit criterion. This was a substantive self-review, supplemented by structural checks; it is not independent empirical validation.

The semantic review checked, in particular, that G04/L05/R09 do not freeze a defective oracle; G05/L03 do not treat doubles as integration proof; G07/G09/D03 retain mixed-version and data-recovery obligations; D05/D06 distinguish transaction scope from invariant enforcement; D08 requires resource enforcement; D09/D10 do not reduce ordering or progress to labels; and R02/R10 preserve actual authority. Those distinctions carry through the capability mapping, candidate cases and Stage 4 questions. The coverage review checks each book against its accepted intended contribution and keeps unexamined depth visible in all twenty K-dimensions.

Programmatic inspection found 42 unique findings (B1: 9; B2: 6; B3: 7; B4: 10; B5: 10), all eight fields in each, 42 corresponding mapping rows, 18 distinct capability/criterion/candidate definitions, all ten distinct book pairs, twenty coverage dimensions and twelve challenge questions. Every finding's cited PDF range is contained in the confirmed examination register. Local relative links and Markdown table structure were checked. The accepted Stage 1/Stage 2, repository README and execution-contract file contents still match their baseline Git blob identities. These checks establish record integrity; they cannot mechanically establish that a book method is effective.

| Requirement | Evidence | Verification | Result |
|---|---|---|---|
| Consume governing requirements and accepted prior inputs | Section 1; baseline and linked Stage 1/Stage 2/contract records | Complete Stage 3 reread; prior records consumed; accepted file identities preserved. | PASS |
| Retain exactly five supplied books with accepted editions and permissions | Section 2 bibliography, `SE-CORPUS-002` | B1–B5 and ISBN/edition identities match revised Stage 2; zero removals, substitutions or demotions. | PASS |
| Meaningfully examine all five for their intended contributions | Section 2 ranges and contribution/limitation assessments; G01–D10 | Direct text examination supplies actual methods, prerequisites, failure mechanisms and repairs in each intended area; access/contents checks are excluded as substitutes. | PASS |
| Record truthful reading coverage and source access limits | Section 2 | Confirmed displayed ranges, repaired truncations, explicit unexamined sections and text/figure limits; no outstanding acquisition need. | PASS |
| Give each material finding all eight required fields | Section 3, 42 findings | Field presence checked for every finding; substance reviewed for source, context, behaviour, evaluation, repair, relationships and disposition. | PASS |
| Trace material findings to actually examined stable locations | Edition register plus each Source field | All 42 citation sets checked against confirmed PDF ranges; chapter/section descriptions and exact editions identify the source. | PASS |
| Complete the source-to-capability-to-evaluation path | Sections 4–5 | All 42 findings map through defined responsibility/workflow rows to defined criteria and candidate cases; no missing IDs or inconsistent joins. | PASS |
| Produce a provisional engineering model without one skill per book | Section 4; cross-book mapping in section 5 | Eighteen decision-oriented hypotheses integrate sources; final skills/commands and implementation remain undesigned. | PASS |
| Reconcile reinforcement, overlap, assumptions, alternatives and contradictions | Sections 6.1–6.2 | All ten book pairs assessed; concrete conflict dispositions and context-dependent alternatives recorded; repeated claims are not treated as independent corroboration. | PASS |
| Identify absent topics and empirical/current-practice questions | Sections 6.3–7 | All twenty accepted coverage dimensions revisited; twelve traceable questions state consequence and required evidence, including security, testing and DDIA currency. | PASS |
| Persist all six expected outputs | Sections 2, 3, 5, 6, 4 and 7 respectively | Reading coverage; per-book findings; source matrix; reconciliation; provisional model; Stage 4 claims/gaps are substantively present in this research log. | PASS |
| Respect the publication boundary | Entire stage change set | Independent synthesis and new synthetic cases only; no supplied PDFs, extracts, private paths/attachment identifiers, copied code examples or reconstructed chapters included. | PASS |
| Preserve charter boundaries and accepted work | Sections 1, 4, 6.2 and 7; baseline file checks | Source advice is qualified to existing authority and specialist handoffs; no change to accepted Stage 1/Stage 2 is needed. | PASS |
| Report execution and research status truthfully | Sections 1, 4 and 7; progress index | Candidate cases explicitly unexecuted; no production code/test/benchmark/install success claimed; Stage 4 and subsequent work remain unperformed. | PASS |
| Meet the Stage 3 exit criteria | Combined evidence above | Five intended contributions meaningfully examined, traceable findings, explicit conflicts/limitations, and no hidden source-access gap. No Stage 3 question requires user input. | PASS |

All mandatory **pre-commit content requirements pass**. The stage change set consists only of this log and the research-log index. The commit gate must use the existing branch ancestry, preserve all other tree entries, and verify the remote branch, commit parent/tree and the exact two intended file contents after updating `feat/bootstrap-2`. The enclosing Git commit identifies the published version; its SHA is reported only after that remote verification succeeds.

**Next stage:** Stage 4, Challenge: Broader Professional Software-Engineering Research. Consume the governing Stage 4 requirements, accepted Stage 1/Stage 2 records and this complete Stage 3 record, especially sections 5–7. The twelve questions are inputs to that research, not replacements for its full specification. This execution stops at the verified Stage 3 boundary under the execution contract's large-work rule. **Remaining Stage 3 blockers: none.**
