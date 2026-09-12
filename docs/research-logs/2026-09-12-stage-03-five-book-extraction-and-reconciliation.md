# Stage 3 — Five-Book Extraction and Reconciliation

**Project:** `software-engineering-skills`  
**Bootstrap stage:** 3 — Five: Extract and Reconcile the Five-Book Corpus  
**Status:** Complete, with qualified `Release It!` source coverage  
**Date:** 12 September 2026  
**Corpus revision:** `software-engineering-corpus-r2`

## 1. Stage purpose

This stage directly examines the five-source software-engineering corpus, extracts traceable production knowledge, reconciles overlaps and tensions, and produces a provisional capability model for later challenge research.

It does **not** design the final skills, commands, workflow, Extension Packs or benchmark architecture.

The governing flow is:

```text
selected corpus
→ direct examination
→ per-source findings
→ source-to-capability mapping
→ overlap / tension / limitation analysis
→ provisional software-engineering capability model
→ Stage 4 challenge backlog
```

The books are evidence sources, not architectural authorities. Repeated advice is not accepted merely because several authors agree with it.

---

## 2. Corpus revision from Stage 2

Stage 2 selected `software-engineering-corpus-r1`, which contained **Software Requirements, 3rd Edition** by Karl Wiegers and Joy Beatty.

The user subsequently supplied a different requirements book as part of the five-source Stage 3 corpus:

- **Software Requirements Essentials: Core Practices for Successful Business Analysis** — Karl Wiegers and Candase Hokanson, 2023.

The supplied set is treated as explicit authorisation to replace the Stage 2 requirements title rather than silently substituting it.

### Revision record

| Field | Decision |
| --- | --- |
| Previous corpus | `software-engineering-corpus-r1` |
| New corpus | `software-engineering-corpus-r2` |
| Removed foundational source | *Software Requirements, 3rd Edition* — Wiegers & Beatty |
| Added foundational source | *Software Requirements Essentials* — Wiegers & Hokanson, 2023 |
| Reason | This is the exact requirements source supplied for Stage 3 extraction |
| Expected gain | Newer, concise treatment; explicitly iterative/agile-aware; strong focus on the twenty core practices |
| Expected loss | Less depth and fewer extended examples than the larger 2013 requirements text |
| Mitigation | Preserve the loss as a Stage 4 research gap rather than pretending the shorter source is exhaustive |
| Permission status | Resolved by the user's explicit source handoff |

The other four Stage 2 selections remain unchanged.

---

## 3. Source-access and reading-coverage register

Private source files are not committed to the repository. The entries below record only enough bibliographic and reading-scope information to make the research traceable.

| Source | Access state | Material actually examined | Intended contribution | Limitation |
| --- | --- | --- | --- | --- |
| Karl Wiegers & Candase Hokanson, *Software Requirements Essentials* (2023) | Full text available | Contents; chapters 1–7; targeted examination of problem framing, boundaries, stakeholder authority, quality attributes, modelling, prototypes, validation, baselines and change control | Requirements clarification, acceptance, boundaries, authority, change impact | Intentionally condensed; not a complete requirements-engineering reference |
| Mark Richards & Neal Ford, *Fundamentals of Software Architecture*, 2nd ed. (2025) | Full text available | Preface; chapters 1–8; targeted examination across architecture styles, trade-offs, fitness functions, ADRs, distributed-system fallacies and architecture intersections | Architecture significance, quality attributes, trade-offs, modularity, architecture evolution | Practitioner synthesis; style ratings and heuristics require external challenge |
| Michael Feathers, *Working Effectively with Legacy Code* (2004/2005) | Full text available | Parts I–III; targeted examination of chapters 1–4, 6–13, 16–17, 20–25 and dependency-breaking techniques | Brownfield understanding, safe change, seams, testing, dependency breaking, incremental repair | Examples and some testing terminology reflect a 2004 tool/language environment |
| Titus Winters, Tom Manshreck & Hyrum Wright, *Software Engineering at Google* (2020) | Full text available | Thesis; code review; testing; deprecation; version control; build/static analysis; dependency management; large-scale changes; CI/CD | Sustainable engineering over time, review, testing, dependency evolution, automation and delivery | Google scale, tooling and organisational assumptions are not universal |
| Michael T. Nygard, *Release It!*, 2nd ed. (2018) | Relevant excerpts available | User-supplied expanded concept map; official publisher table of contents and official excerpts covering living in production and stability antipatterns; current professional sources used to extend retry, overload and observability detail | Production reliability, failure containment, deployment/version coexistence, operability | Not a full-text extraction. Findings beyond directly available excerpts are explicitly qualified and triangulated rather than represented as direct reading |

### `Release It!` web-extension sources

The supplied `Release It!` material is an expanded summary rather than the complete book. It was extended using current, public sources while keeping the book-derived and web-derived evidence distinguishable.

Primary structure / direct-book support:

- Pragmatic Bookshelf — *Release It! Second Edition*: https://books.pragprog.com/titles/mnee2/release-it-second-edition/

Current operational triangulation:

- Google SRE — *Production Services Best Practices*: https://sre.google/sre-book/service-best-practices/
- Google SRE — *Addressing Cascading Failures*: https://sre.google/sre-book/addressing-cascading-failures/
- AWS Architecture Blog — *Exponential Backoff and Jitter*: https://aws.amazon.com/blogs/architecture/exponential-backoff-and-jitter/
- AWS Builders' Library collection and resilience guidance: https://aws.amazon.com/builders-library/
- OpenTelemetry — *Signals*: https://opentelemetry.io/docs/concepts/signals/

These web sources extend or update the operational detail; they do not convert the summary into a claim of full-book access. Broader validation remains Stage 4 work.

---

# 4. Per-book extraction

## 4.1 Software Requirements Essentials

### REQ-1 — Understand the problem before committing to a solution

**Source:** Chapter 2, Practice #1; Chapter 1 framing.  
**Problem and concept:** Teams can implement a requested solution correctly while solving the wrong problem. Requirements work should expose the underlying problem, intended outcomes and assumptions before technical commitment.  
**Applicability:** Especially valuable when a request arrives already phrased as a solution. Software Engineering may clarify the engineering problem and acceptance target but must not silently take ownership of product strategy.  
**Production behaviour:** Ask what problem and outcome justify the requested change; separate stated solution from underlying need; surface unresolved policy choices to the owning authority.  
**Evaluation:** The change intent can be connected to explicit outcomes, constraints and acceptance conditions.  
**Failure and repair:** If implementation begins from an untested solution assumption, return to problem/outcome clarification rather than polishing the wrong implementation.  
**Relationships:** Reinforces Google’s evidence-driven trade-off framing and Feathers’ focus on identifying the actual change point before editing.  
**Disposition:** **Retain provisionally.** Core candidate for change-intent clarification.

### REQ-2 — Bound the solution and identify affected systems

**Source:** Chapter 2, Practice #3; context diagrams and ecosystem maps.  
**Problem and concept:** A change can expand accidentally because the solution boundary and neighbouring systems are unclear.  
**Applicability:** Greenfield and brownfield work involving interfaces, integrations, shared data or multiple components.  
**Production behaviour:** Define what is in/out; map immediate external entities and wider system interactions; identify the minimal change that can satisfy the objective; record potentially affected owners and data flows.  
**Evaluation:** Requested functionality fits a defined boundary and likely upstream/downstream impacts are visible.  
**Failure and repair:** If new dependencies or out-of-scope responsibilities appear during implementation, update the impact map and seek a scope decision rather than silently absorbing them.  
**Relationships:** Strongly complements Feathers’ effect reasoning and architecture-level component boundaries.  
**Disposition:** **Retain provisionally.** Candidate input to impact analysis.

### REQ-3 — Make quality attributes measurable and testable

**Source:** Chapter 3, Practice #9.  
**Problem and concept:** Vague statements such as “fast”, “secure” or “reliable” cannot guide design or acceptance.  
**Applicability:** Any change where non-functional behaviour matters.  
**Production behaviour:** Convert relevant quality expectations into precise, necessary, measurable, verifiable and realistic conditions; distinguish local feature criteria from cross-cutting architectural characteristics.  
**Evaluation:** Applicable quality expectations have an observable condition or fit criterion instead of an adjective.  
**Failure and repair:** If a quality problem is discovered late, determine whether the missing requirement should have driven architecture/design earlier and add the corresponding regression/fitness evidence.  
**Relationships:** Direct bridge to Richards/Ford architecture characteristics and fitness functions.  
**Disposition:** **Retain provisionally.** Do not promote example thresholds from the book as universal targets.

### REQ-4 — Validate requirements before implementation evidence becomes expensive

**Source:** Chapter 6, Practice #18.  
**Problem and concept:** Ambiguous or incomplete requirements can be exposed by review, conceptual tests and acceptance criteria before implementation is finished.  
**Applicability:** Particularly useful for externally visible behaviour, edge cases and cross-team requirements.  
**Production behaviour:** Review requirements; derive acceptance conditions; involve testing perspectives early; trace material acceptance cases to the requirement they protect.  
**Evaluation:** A requirement is complete enough that a tester and implementer converge on the same expected behaviour.  
**Failure and repair:** If tests expose competing interpretations, fix the requirement/acceptance contract before changing implementation blindly.  
**Relationships:** Supports the bootstrap principle that tests are evidence, not decoration; feeds Feathers/Google verification behaviour.  
**Disposition:** **Retain provisionally.** Acceptance style remains project-dependent.

### REQ-5 — Make decision authority explicit

**Source:** Chapter 2, Practices #4–#5.  
**Problem and concept:** Broad-impact decisions fail or stall when the affected stakeholders and actual decision authority are unclear.  
**Applicability:** Breaking contracts, scope changes, conflicting stakeholder needs, high-impact quality or migration decisions.  
**Production behaviour:** Identify who supplies evidence, who is affected, who can decide and which decision rule applies; communicate rationale to affected parties.  
**Evaluation:** A consequential decision has a named authority and understood input path.  
**Failure and repair:** If implementation is blocked by contradictory direction, escalate to the empowered decision maker rather than selecting product policy autonomously.  
**Relationships:** Aligns with architecture decision rationale and Google’s explicit approval/escalation for broad changes.  
**Disposition:** **Retain provisionally.** Organisational governance details stay outside the reusable core.

### REQ-6 — Baselines are change references, not freezes

**Source:** Chapter 7, Practices #19–#20.  
**Problem and concept:** Teams need a shared statement of current intended behaviour, while still accepting that requirements will change.  
**Applicability:** Iterative delivery, releases, maintenance and multi-team work.  
**Production behaviour:** Record the agreed baseline; assess a proposed change for impact; route it to the right decision authority; update the baseline and related artefacts after approval; record rejection rationale when useful.  
**Evaluation:** The implemented/released scope can be reconciled with an explicit current agreement and approved changes.  
**Failure and repair:** If work drifts through informal unrecorded changes, reconstruct the intended baseline and run unresolved changes through an appropriate decision path.  
**Relationships:** Compatible with continuous delivery when the baseline is lightweight and frequently updated; does not imply waterfall freezing.  
**Disposition:** **Retain with qualification.** Exact change-control ceremony must scale to risk and team size.

### REQ-7 — Choose prototype fidelity according to the uncertainty

**Source:** Chapter 4, Practice #12.  
**Problem and concept:** Prototypes are tools for learning, but polished prototypes can be mistaken for production-ready systems.  
**Applicability:** Requirement ambiguity, interaction uncertainty, feasibility questions and technical spikes.  
**Production behaviour:** State what the prototype is meant to learn; use the cheapest adequate fidelity; decide in advance whether it is throwaway or evolutionary; if it may become production, build it to the corresponding quality bar.  
**Evaluation:** The prototype answers its target question without accidentally becoming an unreviewed production commitment.  
**Failure and repair:** If a throwaway prototype begins accumulating production expectations, stop and either rebuild deliberately or reclassify it with explicit technical-debt and quality work.  
**Relationships:** Tension with Richards/Ford’s advice to make architectural PoCs production-quality is resolved by prototype intent.  
**Disposition:** **Retain provisionally.** Strong family fit with cheapest-adequate representation.

---

## 4.2 Fundamentals of Software Architecture, 2nd Edition

### ARC-1 — Architecture decisions are distinguished by consequence, not title

**Source:** Chapter 2, architecture-versus-design spectrum.  
**Problem and concept:** Architecture and detailed design are not separated by a clean boundary. Decisions become more architectural as strategic horizon, change cost and trade-off significance increase.  
**Applicability:** Changes that might cross module/service/data/deployment boundaries or materially alter quality attributes.  
**Production behaviour:** Classify the decision by consequence and reversibility; avoid escalating ordinary local design into architecture work.  
**Evaluation:** The depth of design evidence is proportional to switching cost, blast radius and quality impact.  
**Failure and repair:** If a local patch cannot preserve required characteristics/contracts, reopen the smallest structural boundary necessary.  
**Relationships:** Supports Stage 1’s “design only as far as uncertainty requires” rule.  
**Disposition:** **Retain provisionally.** Exact architecture thresholds remain contextual.

### ARC-2 — Architecture combines structure, characteristics, components and decisions

**Source:** Chapter 1.  
**Problem and concept:** Architecture is more than a topology diagram; required qualities, logical components, style and constraining decisions interact.  
**Applicability:** Architecture analysis for new or evolving systems.  
**Production behaviour:** When architecture is material, identify relevant quality characteristics, logical responsibilities, topology/style and constraints/rationale rather than choosing a pattern by name.  
**Evaluation:** Architecture evidence explains both the structure and what qualities it is meant to preserve.  
**Failure and repair:** If implementation follows the nominal style while violating required qualities, treat this as architecture non-conformance rather than “style correctness”.  
**Relationships:** Requirements quality attributes supply input; fitness functions later enforce characteristics.  
**Disposition:** **Retain provisionally.** Useful architecture-analysis frame.

### ARC-3 — Every architecture choice is a contextual trade-off

**Source:** Chapters 1–2; laws of software architecture.  
**Problem and concept:** Architecture choices rarely have context-free best answers; rationale matters more than merely recording a chosen technology.  
**Applicability:** Architecture styles, communication models, persistence, distribution, integration and platform choices.  
**Production behaviour:** Identify competing qualities and constraints, compare options in the actual environment, retain the “why”, and revisit as context changes.  
**Evaluation:** A material choice exposes its expected gains, costs, assumptions and rejected alternative rather than asserting a pattern as best practice.  
**Failure and repair:** If later evidence invalidates an assumption, revise the decision rather than defending historical consistency.  
**Relationships:** Strongly reinforces Google’s cost/trade-off reasoning.  
**Disposition:** **Retain provisionally.** Stage 4 should test specific heuristics, not the existence of trade-offs itself.

### ARC-4 — Modularity is an evolvability control surface

**Source:** Chapter 3.  
**Problem and concept:** Logical grouping, cohesion, coupling, connascence and granularity determine how easily responsibilities can change independently.  
**Applicability:** Module/service boundaries, monolith decomposition, codebase structural health.  
**Production behaviour:** Inspect coupling and responsibility boundaries before introducing new dependencies; prefer boundaries that localise change rather than maximising the number of components.  
**Evaluation:** A proposed structure reduces unnecessary cross-boundary knowledge and allows relevant change to remain local.  
**Failure and repair:** If decomposition increases coordination/coupling, reconsider granularity or merge responsibilities.  
**Relationships:** Feathers’ dependency-breaking work provides a code-level mechanism; Google’s large-scale changes expose the cost of bad dependency structure.  
**Disposition:** **Retain provisionally.** Metrics are diagnostic evidence, not universal quality scores.

### ARC-5 — Select topology from characteristics and problem shape

**Source:** Architecture-style chapters and Part II synthesis.  
**Problem and concept:** Monolithic/distributed, data-location and communication choices should follow required characteristics and domain coupling rather than fashion.  
**Applicability:** Structural architecture selection and evolution.  
**Production behaviour:** Ask whether one or several characteristic sets are required; decide where data ownership belongs; choose communication based on actual latency, coupling, consistency and reliability needs.  
**Evaluation:** Chosen topology has an explicit fit to the problem and quality requirements.  
**Failure and repair:** If a distributed design creates more semantic coupling, latency or operational burden than it resolves, move toward a simpler topology or redefine boundaries.  
**Relationships:** Reinforced by `Release It!` integration-failure concerns.  
**Disposition:** **Retain with qualification.** The authors’ recommendation to default to synchronous communication where possible is a heuristic for Stage 4 challenge, not a core rule.

### ARC-6 — Protect important architecture with executable evidence

**Source:** Chapters on architectural characteristics, fitness functions and governance.  
**Problem and concept:** Architecture degrades when decisions exist only as documentation.  
**Applicability:** Characteristics or constraints that must survive continuous change.  
**Production behaviour:** Express enforceable architecture expectations as fitness evidence where practical: tests, metrics, static rules, monitors or controlled failure experiments. Use ADRs for consequential rationale that cannot be fully encoded.  
**Evaluation:** Material architecture constraints can be checked repeatedly and violations are visible.  
**Failure and repair:** If a characteristic drifts, locate the implementation or engineering-practice source and repair that layer rather than redesigning the system blindly.  
**Relationships:** Strong match with Google CI/static analysis and `Release It!` fault testing.  
**Disposition:** **Retain provisionally.** Fitness function mechanics remain implementation-specific.

### ARC-7 — Architecture must evolve because unknown unknowns appear

**Source:** Chapter 26 intersections; evolutionary-architecture discussion.  
**Problem and concept:** Long-lived systems encounter changes that could not be fully planned up front.  
**Applicability:** Long-lived products and infrastructure.  
**Production behaviour:** Prefer architecture that can be evaluated and changed incrementally; use migration patterns and feedback rather than one irreversible redesign where evidence is incomplete.  
**Evaluation:** Structural change has a staged path, measurable intermediate state and rollback/repair strategy.  
**Failure and repair:** If big-bang migration risk grows, reduce batch size and introduce an incremental coexistence path.  
**Relationships:** Matches Google sustainability and Release It mixed-version deployment.  
**Disposition:** **Retain provisionally.** Specific migration patterns need Stage 4 evidence.

### ARC-8 — Architecture intersects implementation, data, infrastructure and operations

**Source:** Chapter 26.  
**Problem and concept:** A nominally correct architecture can fail because data topology, deployment placement, infrastructure or engineering practice contradicts its intended characteristics.  
**Applicability:** Distributed systems and systems with significant operational requirements.  
**Production behaviour:** Check whether persistence, infrastructure placement, deployment and team/engineering practices preserve the architecture characteristics being claimed.  
**Evaluation:** The implementation/runtime topology supports, rather than negates, the architectural rationale.  
**Failure and repair:** When a quality characteristic fails, inspect these intersections before replacing the top-level style.  
**Relationships:** Direct bridge to Release It operational reality and Google delivery practices.  
**Disposition:** **Retain provisionally.** Helps prevent architecture from becoming diagram-only work.

---

## 4.3 Working Effectively with Legacy Code

### LEG-1 — Most software change is a preservation problem

**Source:** Chapter 1, “Changing Software” and “Risky Change”.  
**Problem and concept:** Feature additions, bug fixes, refactoring and optimisation usually alter a small subset of behaviour while requiring much more existing behaviour to remain intact.  
**Applicability:** Brownfield changes of nearly every type.  
**Production behaviour:** Identify what must change, what must remain invariant and how both facts will be demonstrated before editing.  
**Evaluation:** Evidence covers both intended new behaviour and relevant preserved behaviour.  
**Failure and repair:** If the changed area is poorly understood, reduce scope, increase characterisation/inspection, or create a safer feedback point before proceeding.  
**Relationships:** Strongly reinforced by Hyrum’s Law in *Software Engineering at Google*.  
**Disposition:** **Retain provisionally.** Central brownfield principle.

### LEG-2 — Feedback changes the economics of safe change

**Source:** Chapter 2, “Working with Feedback”.  
**Problem and concept:** Careful editing without fast feedback leaves risk hidden; local tests can constrain behaviour and expose mistakes quickly.  
**Applicability:** Change to code where automated feedback can be made sufficiently representative.  
**Production behaviour:** Establish the cheapest relevant feedback loop before invasive editing; run it after small steps.  
**Evaluation:** A defect caused by the current step can be localised quickly enough to guide repair.  
**Failure and repair:** If feedback is slow or broad, add narrower test points or split the change; retain higher-level coverage for integration evidence.  
**Relationships:** Reinforces Google shift-left and CI principles.  
**Disposition:** **Retain provisionally.** Do not equate a unit test with complete verification.

### LEG-3 — Use the legacy-code change algorithm as a safe-change heuristic

**Source:** Chapter 2, “The Legacy Code Change Algorithm”.  
**Problem and concept:** Difficult-to-test code needs a disciplined route from intended change to protected edit.  
**Production behaviour:** Identify change points → find useful test points → break only the dependencies needed for feedback → write tests → make the change and refactor.  
**Evaluation:** The new behaviour is tested and the touched area becomes easier to verify than before.  
**Failure and repair:** If enabling tests becomes a large redesign, seek a smaller interception point or a bounded sprout/wrap technique.  
**Relationships:** Requirements boundary mapping can improve change-point selection; architecture analysis may show that the local point is structurally wrong.  
**Disposition:** **Retain as a context-dependent heuristic**, not the universal project workflow.

### LEG-4 — Seams create controllable test boundaries

**Source:** Chapters 3–4, sensing, separation and the seam model.  
**Problem and concept:** Dependencies block observation or isolated execution. A seam permits behaviour to be substituted without editing the call site; an enabling point selects the alternate behaviour.  
**Applicability:** Existing code whose dependencies are slow, unavailable, destructive or otherwise difficult under test.  
**Production behaviour:** Break the minimum dependency needed either to sense effects or separate the unit from an unsuitable collaborator.  
**Evaluation:** The target behaviour can be exercised and observed with less unrelated infrastructure.  
**Failure and repair:** If dependency-breaking makes production design worse, keep the incision minimal and heal it after adequate test cover exists.  
**Relationships:** Tension with Google’s preference for real implementations is contextual rather than contradictory: seams are justified when the real dependency prevents useful feedback.  
**Disposition:** **Retain with qualification.** Prefer realism when it remains fast, deterministic and safe.

### LEG-5 — Trace effects to choose the smallest useful test boundary

**Source:** Chapters 11–12, effect reasoning, interception points and pinch points.  
**Problem and concept:** Testing only the edited method can miss propagated effects; testing the whole system can be unnecessarily expensive and hard to diagnose.  
**Applicability:** Changes spanning several collaborators or unclear dependency graphs.  
**Production behaviour:** Trace effects outward from change points; select an interception point that observes the important effect with manageable setup; use pinch points when one boundary covers a useful cluster.  
**Evaluation:** Tests fail for relevant behavioural impact while remaining local enough to diagnose.  
**Failure and repair:** If a chosen boundary is too brittle or too broad, move the interception point inward/outward based on actual failure evidence.  
**Relationships:** Complements Requirements ecosystem mapping and Google’s mixed testing portfolio.  
**Disposition:** **Retain provisionally.** Strong candidate for brownfield impact analysis.

### LEG-6 — Characterisation tests record observed behaviour before risky change

**Source:** Chapter 13.  
**Problem and concept:** Existing software may have undocumented or surprising behaviour that must be understood before modification.  
**Applicability:** Legacy paths without trustworthy executable specifications.  
**Production behaviour:** Capture relevant observed behaviour around the intended change, especially at effect boundaries, before refactoring or altering functionality.  
**Evaluation:** The test protects behaviour that is relevant to the change and would detect unintended drift.  
**Failure and repair:** Do not blindly preserve an observed defect; separate “current behaviour” from “desired contract” and obtain an explicit decision where they differ.  
**Relationships:** Hyrum’s Law strengthens the warning that undocumented observable behaviour may still have consumers.  
**Disposition:** **Retain provisionally.** Characterisation is evidence, not proof that behaviour is correct.

### LEG-7 — When time is constrained, isolate new behaviour rather than contaminating old code

**Source:** Chapters 6–8, Sprout Method/Class and Wrap Method/Class.  
**Problem and concept:** Sometimes existing code cannot be brought fully under test within the available change window.  
**Applicability:** Urgent bounded changes in hard-to-test systems.  
**Production behaviour:** Put new logic in a separately testable unit and connect it through the smallest call-site change; acknowledge the untested integration risk.  
**Evaluation:** New behaviour has direct tests and the integration point is as small/reviewable as possible.  
**Failure and repair:** Follow up by bringing the call path under cover when risk warrants it; do not treat isolated new-code tests as full end-to-end evidence.  
**Relationships:** Fits Stage 1 emergency-maintenance boundary and Google small-change discipline.  
**Disposition:** **Retain as fallback heuristic.** Not a substitute for adequate system verification.

### LEG-8 — Understanding tools can be disposable

**Source:** Chapter 16 and later change-safety guidance: sketching, listing markup, scratch refactoring, single-goal editing, preserving signatures and leaning on the compiler.  
**Problem and concept:** Engineers sometimes need temporary transformations or annotations to reveal structure without committing those experiments.  
**Applicability:** Unfamiliar, tangled code.  
**Production behaviour:** Use disposable scratch refactors, sketches and compiler/static feedback to learn; revert exploratory edits; then make the deliberate production change in small single-purpose steps.  
**Evaluation:** Understanding improves without accidental exploratory code entering the final patch.  
**Failure and repair:** If an exploratory refactor begins to carry unrelated cleanup into the change, revert and separate it.  
**Relationships:** Matches the family rule of cheapest adequate representation.  
**Disposition:** **Retain provisionally.** Highly relevant to AI-agent repository inspection.

---

## 4.4 Software Engineering at Google

### GOOG-1 — Software engineering is programming under time, scale and change

**Source:** Chapter 1, “What Is Software Engineering?”.  
**Problem and concept:** Code that only works now is different from software that must remain useful while dependencies, requirements and maintainers change.  
**Applicability:** Any software with a non-trivial maintenance life.  
**Production behaviour:** Consider expected lifetime, future change and repeated maintenance cost when choosing how much engineering investment is justified.  
**Evaluation:** The system can respond to likely valuable changes without disproportionate effort.  
**Failure and repair:** When an infrequent maintenance task becomes painfully large, reduce future batch size and build repeatable capability rather than assuming stagnation is cheaper.  
**Relationships:** Reinforces Feathers incremental improvement and architecture evolvability.  
**Disposition:** **Retain provisionally.** Central definition of sustainable engineering.

### GOOG-2 — Effective contracts include observable behaviour

**Source:** Chapter 1, Hyrum’s Law.  
**Problem and concept:** With enough consumers, behaviours not promised in the formal API can still become dependencies.  
**Applicability:** Public APIs, libraries, services, events, schemas and long-lived internal interfaces.  
**Production behaviour:** Inspect actual consumers and observed behaviour before claiming a change is compatible; distinguish documented contract from effective contract.  
**Evaluation:** Compatibility analysis considers both explicit promises and evidence of real usage.  
**Failure and repair:** When unavoidable breakage is discovered, use migration/deprecation mechanisms instead of assuming documentation absolves the provider.  
**Relationships:** Deepens Feathers characterisation testing and Release It version coexistence.  
**Disposition:** **Retain with qualification.** Stage 4 must examine limits and current API-evolution practice.

### GOOG-3 — Engineering decisions should expose cost and trade-offs

**Source:** Chapter 1, “Trade-offs and Costs”.  
**Problem and concept:** Engineering cost includes developer time, compute/resources, transaction cost, opportunity cost and less measurable effects.  
**Applicability:** Architecture, refactoring, automation, performance and dependency choices.  
**Production behaviour:** State the decision inputs, measurable costs where available, assumptions and hard-to-measure factors; revisit when evidence changes.  
**Evaluation:** A material decision can explain why it is preferable under current constraints rather than relying on “best practice”.  
**Failure and repair:** When new data invalidates the decision, reopen it without treating revision as failure.  
**Relationships:** Strongly reinforces Richards/Ford architecture trade-offs and Requirements prioritisation.  
**Disposition:** **Retain provisionally.** Avoid fake precision where measurements are not defensible.

### GOOG-4 — Keep changes small enough to review, diagnose and roll back

**Source:** Code review chapter; rollback and large-scale-change discussion.  
**Problem and concept:** Large mixed-purpose patches make correctness, review and rollback harder.  
**Applicability:** Routine implementation, refactors and generated changes.  
**Production behaviour:** Prefer atomic, single-purpose changes with clear descriptions; separate unrelated cleanup; preserve a coherent larger design through linked increments where needed.  
**Evaluation:** Reviewer can understand what changed and why; failure can be associated with a bounded change; rollback does not remove unrelated work.  
**Failure and repair:** Split an oversized change unless doing so would create an incoherent/unsafe intermediate state.  
**Relationships:** Reinforces Feathers single-goal editing and Stage 1 smallest-responsible-change rule.  
**Disposition:** **Retain with qualification.** Google’s approximate 200-line guideline is local, not a universal threshold.

### GOOG-5 — Testing needs complementary scopes and should avoid implementation over-specification

**Source:** Testing Overview, Unit Testing, Test Doubles and Larger Testing chapters.  
**Problem and concept:** Small tests offer speed/localisation but deliberately remove real-world complexity; larger tests catch integration, load and emergent behaviour but cost more and are harder to own. Interaction-heavy tests can become brittle.  
**Applicability:** Test strategy for non-trivial systems.  
**Production behaviour:** Choose the cheapest test that can expose the relevant risk; test public/state behaviour where possible; prefer real collaborators when fast and deterministic; add larger tests for integration/load/emergence where small tests cannot provide the evidence.  
**Evaluation:** Each test layer has a defined failure class and useful diagnostic signal.  
**Failure and repair:** Remove brittle assertions on implementation details; move tests to a more behavioural boundary or use a more realistic collaborator where practical.  
**Relationships:** Qualifies Feathers’ use of fakes/seams and supports the bootstrap cheap-first verification ladder.  
**Disposition:** **Retain provisionally.** Exact test mix remains system-specific.

### GOOG-6 — Dependency management is evolution of a network, not package installation

**Source:** Dependency Management chapter.  
**Problem and concept:** The hard problem is maintaining a graph of direct and transitive dependencies as versions and requirements change over time.  
**Applicability:** Long-lived applications, libraries, build systems and supply chains.  
**Production behaviour:** Inspect transitive dependencies and version constraints; prefer supported upgrade paths; consider future update/compatibility cost when introducing a dependency.  
**Evaluation:** Dependency changes can be tested/released without leaving incompatible or abandoned combinations.  
**Failure and repair:** Resolve conflicting requirements through supported version convergence, isolation or redesign rather than pinning indefinitely without recognising the maintenance debt.  
**Relationships:** Extends Stage 1 adaptive maintenance; architecture coupling influences dependency cost.  
**Disposition:** **Retain provisionally.** Stage 4 must add current supply-chain/security practice.

### GOOG-7 — Deprecation and large migration need explicit ownership and scalable automation

**Source:** Deprecation and Large-Scale Changes chapters.  
**Problem and concept:** Advising consumers to migrate does not make a migration complete; repeated manual migration effort scales poorly.  
**Applicability:** API replacement, platform/framework upgrades, organisation-wide refactors and large repositories.  
**Production behaviour:** Name an owner; design a migration path with the successor; make warnings actionable/relevant; automate mechanical transforms; authorise broad changes; shard/review/test them; clean up obsolete paths.  
**Evaluation:** Usage of the old surface declines measurably and migration can complete without every consumer rediscovering the same work.  
**Failure and repair:** If migration stalls, identify missing ownership, tooling or compatibility path rather than only increasing warnings.  
**Relationships:** Reinforces Requirements change authority and Release It version coexistence.  
**Disposition:** **Retain provisionally.** Large-scale mechanics may be Extension Pack/tool-dependent later.

### GOOG-8 — CI/CD is continuous evidence of releasability

**Source:** Continuous Integration and Continuous Delivery chapters.  
**Problem and concept:** A passing local change is insufficient evidence that a release candidate remains deployable with its configuration and dependencies.  
**Applicability:** Software delivered through repeatable build/release paths.  
**Production behaviour:** Keep code/configuration under controlled review; continuously build/test; assemble release candidates; promote the same artefacts through representative environments; use staged rollout/feature controls where appropriate; preserve rollback/culprit finding.  
**Evaluation:** At a known point, the code compiles, relevant tests pass, the release candidate is traceable and a release could be made through the supported path.  
**Failure and repair:** If late environments reveal version/configuration skew, fix the promotion/reproducibility mechanism rather than adding one-off release steps.  
**Relationships:** Reinforces Release It deployment/versioning and Stage 1 release-readiness boundary.  
**Disposition:** **Retain provisionally.** Continuous deployment itself is not mandatory.

---

## 4.5 Release It!, 2nd Edition — qualified extraction plus web extension

The supplied source is an expanded concept map, not the complete book. Findings below therefore distinguish the book structure and supplied synthesis from current web extension. The official Pragmatic Bookshelf contents confirm the twelve stability antipatterns and twelve stability patterns represented in the supplied map.

### REL-1 — Feature-complete is not production-ready

**Source basis:** Official introduction excerpt; supplied expanded map, Part I framing.  
**Problem and concept:** Passing functional tests does not demonstrate that a system will survive long-running production conditions, partial failure, hostile input, resource limits or unexpected interactions.  
**Applicability:** Deployed runtime software.  
**Production behaviour:** Review a change/system through operational questions: failure behaviour, resource limits, deployment, dependency health, recovery and diagnostic visibility.  
**Evaluation:** Release evidence covers relevant failure and runtime behaviour rather than only happy-path correctness.  
**Failure and repair:** When a production failure class was never exercised, add the cheapest reproducible fault/test harness capable of protecting it.  
**Relationships:** Complements Google larger testing and architecture characteristics.  
**Disposition:** **Retain provisionally.** Direct source support is adequate for this principle.

### REL-2 — Failures become outages through propagation

**Source basis:** Official Stability Antipatterns excerpt plus supplied map.  
**Problem and concept:** Integration points, blocked resources, chain reactions, cascading failures, synchronized load spikes, capacity mismatch and slow responses can turn a local defect into systemic failure.  
**Applicability:** Services and applications with external dependencies, pools, queues or shared resources.  
**Production behaviour:** Identify propagation paths and bounded resources; assume remote calls can be slow or fail; inspect whether retries, pools, queues or automation amplify the fault.  
**Evaluation:** A dependency failure remains bounded enough that unrelated capacity/functional areas continue operating where intended.  
**Failure and repair:** Repair propagation and amplification, not only the original fault: isolate resources, reduce load, cap queues/retries and restore healthy feedback.  
**Relationships:** Reinforced by Google SRE cascading-failure guidance and Richards/Ford distributed-computing fallacies.  
**Disposition:** **Retain provisionally.** Strong cross-source support.

### REL-3 — Stability patterns are coordinated controls, not a checklist

**Source basis:** Supplied map and official publisher structure; current AWS/Google SRE extension.  
**Problem and concept:** Timeouts, circuit breakers, bulkheads, fail-fast behaviour, decoupling, load shedding and back pressure address different failure-propagation mechanisms.  
**Applicability:** Distributed and dependency-heavy runtime paths.  
**Production behaviour:** Select controls based on the actual failure mode. For retries, current AWS/Google practice strengthens the book-era guidance: bound retries, back off exponentially, add jitter, avoid retrying non-idempotent or multiple stack layers blindly, and test overload behaviour.  
**Evaluation:** Fault injection/load tests demonstrate that the selected control reduces amplification under the targeted failure.  
**Failure and repair:** If a resilience mechanism creates a retry storm, queue debt or hidden overload, tune/remove it and restore explicit limits.  
**Relationships:** Google SRE and AWS currently preserve the same core failure-amplification model.  
**Disposition:** **Retain with current-practice extension.** Exact retry/circuit thresholds are system-specific.

### REL-4 — Steady-state operation and transparency must be designed

**Source basis:** Supplied map, Part II; official structure.  
**Problem and concept:** Logs, sessions, caches, temporary resources and configuration accumulate or drift; systems need mechanisms to expose state and run without continuous manual cleanup.  
**Applicability:** Long-running services/applications.  
**Production behaviour:** Bound accumulating resources; automate safe cleanup; separate configuration from code where appropriate; expose diagnostics needed to understand current state.  
**Evaluation:** Soak/steady-state evidence shows resource behaviour remains bounded and operators/engineers can explain current runtime state.  
**Failure and repair:** If recurring manual cleanup is needed, model the accumulation source and automate a bounded lifecycle rather than normalising toil.  
**Relationships:** Google CI/deprecation automation and current observability practice support the same maintainability objective.  
**Disposition:** **Retain provisionally.** Detailed operability ownership remains Stage 4 boundary work.

### REL-5 — Test dependency failure, not only success

**Source basis:** Supplied stability pattern “Test Harnesses”; chaos-engineering section; current Google/AWS resilience practice.  
**Problem and concept:** Normal integration tests underrepresent hangs, malformed responses, latency, overload and partial failure.  
**Applicability:** Material external/internal dependencies.  
**Production behaviour:** Use controlled misbehaving dependencies or fault injection to exercise failure assumptions, starting with bounded blast radius and cheap environments.  
**Evaluation:** The test demonstrates expected degraded/failure behaviour, not merely successful integration.  
**Failure and repair:** If the test itself has an unsafe blast radius, reduce scope/environment before expanding fidelity.  
**Relationships:** Architecture fitness functions can encode recurring failure experiments; Google larger tests fill gaps left by isolated unit tests.  
**Disposition:** **Retain provisionally.** Production chaos is not a default first verification step.

### REL-6 — Deployment and versioning are part of design

**Source basis:** Supplied map, Part III; reconciled with *Software Engineering at Google* CD/compatibility material.  
**Problem and concept:** Zero-downtime or low-risk rollout requires coexistence between versions; schema/API changes that require coordinated replacement increase release risk.  
**Applicability:** Services, persistent data and externally consumed interfaces.  
**Production behaviour:** Design for phased rollout and mixed versions; prefer compatibility windows; separate additive migration from destructive removal; make rollback/recovery constraints explicit.  
**Evaluation:** Old/new versions and schema/API states can coexist for the intended rollout window and the supported rollback path is known.  
**Failure and repair:** If deployment requires all components to switch atomically, introduce a compatibility/migration stage or explicitly accept the risk.  
**Relationships:** Strongly reinforced by Google deprecation/CD and Hyrum’s Law.  
**Disposition:** **Retain provisionally.** Stage 4 must research current API/schema migration practice and challenge Postel-style assumptions.

### REL-7 — Automation can amplify failures, so destructive control needs resistance

**Source basis:** Supplied antipattern “Force Multiplier” and pattern “Governor”.  
**Problem and concept:** Fast automation acting on bad signals can produce damage faster than humans can intervene.  
**Applicability:** Autoscaling, fleet management, automated shutdown/deletion/blocking and control planes.  
**Production behaviour:** Apply rate limits, staged actions, confirmation/authority boundaries or other resistance in the dangerous direction; make reversal easier than escalation.  
**Evaluation:** A faulty signal cannot trigger unbounded destructive action before detection/intervention.  
**Failure and repair:** If automation compounds the incident, disable/bound the control loop and restore a known safe operating state before fixing the trigger.  
**Relationships:** Fits Stage 1 approval candidates for destructive/high-consequence changes.  
**Disposition:** **Retain provisionally.** Valuable beyond operations because AI agents can also become force multipliers.

### REL-8 — Observability is diagnostic evidence, not decorative telemetry

**Source basis:** Supplied transparency/observability material, extended with current OpenTelemetry signal model.  
**Problem and concept:** Distributed/emergent behaviour cannot be diagnosed reliably from uptime alone.  
**Applicability:** Runtime paths where internal state/failure propagation cannot be inferred locally.  
**Production behaviour:** Add only the telemetry needed to answer material operational questions and correlate behaviour across relevant boundaries. Current OpenTelemetry practice recognises traces, metrics and logs, with profiling now an additional supported/emerging signal; signal choice remains problem-driven.  
**Evaluation:** A representative failure can be localised from available evidence without speculative logging changes after the fact.  
**Failure and repair:** If telemetry volume exists without useful diagnosis, remove low-value noise and instrument the missing decision boundary instead.  
**Relationships:** Complements root-cause diagnosis, architecture fitness functions and Google production testing.  
**Disposition:** **Retain with qualification.** Stage 4 must define the Software Engineering versus SRE/operations boundary.

---

# 5. Reconciliation across the corpus

## 5.1 Reinforcing findings

### Change is the primary production unit

All five sources converge on change rather than code generation as the meaningful unit of engineering:

```text
requirements change
→ system impact
→ architecture/design consequence
→ bounded implementation
→ verification
→ compatibility/release consequence
→ future maintainability
```

The convergence is useful because the sources reach it from different directions:

- Requirements Essentials — changing needs, baselines and impact;
- Feathers — behavioural preservation during code change;
- Richards/Ford — architecture must adapt as context changes;
- Google — sustainability is capability to change over time;
- Nygard — production systems must survive faults, rollout and evolution.

**Provisional conclusion:** core Software Engineering Skills should be organised around responsible software change, not around language/framework taxonomies.

### Existing behaviour is evidence, but not automatically the desired contract

Feathers’ characterisation tests and Hyrum’s Law strongly reinforce each other: observed behaviour may matter even when not documented.

Requirements Essentials adds an important constraint: expected behaviour still needs an authorised acceptance target.

**Provisional rule:** discover both formal and effective contracts; preserve unaffected behaviour by default; do not preserve an actual defect merely because it is observable.

### Cheap feedback should precede expensive evidence

Requirements reviews/prototypes, Feathers local tests, architecture PoCs/fitness functions, Google presubmit/CI and Release It fault harnesses form a coherent cost ladder.

**Provisional rule:** use the cheapest evidence capable of resolving the current uncertainty, then escalate according to residual risk.

### Architecture should be proportional to consequence

Requirements quality attributes identify the needed qualities; Richards/Ford determine when structural decisions are significant; Google adds cost/lifetime; Feathers warns against broad rewrites when local safe change is sufficient.

**Provisional rule:** perform architecture work when the change crosses a consequential structural/quality boundary, not because architecture documentation exists as a stage.

### Verification is a portfolio

No source supports treating one testing layer as sufficient:

- local tests improve feedback and localisation;
- characterisation protects existing behaviour;
- larger/integration tests expose emergent interactions;
- fitness functions protect architectural characteristics;
- fault/load tests expose resilience failures;
- release-candidate and production probes verify deployment reality.

**Provisional rule:** verification selection should follow failure class and risk, not a fixed universal test pyramid.

### Releasability belongs inside engineering quality

Google and Nygard are especially aligned: configuration, mixed versions, compatibility, release candidates, rollout and failure behaviour must be designed rather than added after implementation.

**Provisional rule:** “done” for releasable software includes credible evidence that the change can travel through the supported release path; it does not require Software Engineering to own production operations.

---

## 5.2 Important tensions and their provisional resolution

| Tension | Sources | Provisional resolution |
| --- | --- | --- |
| Test doubles/seams versus realism | Feathers vs Google testing | Use seams/doubles when real collaborators prevent fast, deterministic or safe feedback; otherwise prefer behavioural/state tests with real implementations. |
| Cheap prototype versus production-quality PoC | Requirements Essentials vs Richards/Ford | Decide prototype fate first. Throwaway learning artefacts optimise for question/fidelity and are discarded; PoCs likely to survive or become reference implementations need production-quality discipline. |
| Requirements baseline versus continuous change | Requirements Essentials vs Google CI/CD | A baseline is the current agreed change target, not a freeze. Keep it lightweight and update through explicit decisions. |
| Local safe change versus architecture evolution | Feathers vs Richards/Ford | Prefer local coherent change unless evidence shows required characteristics/contracts cannot be preserved without structural change. |
| Explicit API contract versus observed behaviour | Requirements/architecture vs Hyrum’s Law | Treat formal contract as authority for intended behaviour but inspect actual consumers before compatibility claims. |
| Fast small tests versus realistic failure evidence | Feathers/Google unit testing vs Google larger tests/Release It | Run fast local checks first, then add the smallest higher-fidelity test that covers residual integration/runtime risk. |
| Automation versus human control | Google large-scale automation vs Release It Force Multiplier/Governor | Automate repeatable work, but add stronger boundaries to destructive/high-blast-radius actions and preserve escalation/rollback. |

---

## 5.3 Claims that must remain qualified

1. **“Legacy code is code without tests.”** Useful operating heuristic from Feathers, not a universal definition.
2. **Feathers’ strict 2004 unit-test boundary.** Fast/localising feedback is durable; categorical exclusions such as file/network use need current empirical challenge.
3. **Google’s approximate small-change size guidance.** Evidence for small atomic changes is useful; the specific line-count heuristic is organisation-specific.
4. **Google organisational practices.** Valuable proof at very large scale, not automatic defaults for small teams.
5. **Architecture-style star ratings.** Comparison aids, not universal quantitative scores.
6. **“Default synchronous, asynchronous only when necessary.”** Richards/Ford heuristic requires contextual challenge; it must not become a blanket rule.
7. **Release It operational implementation details.** Core failure-containment principles appear durable, but tooling/platform assumptions from 2018 must be checked against current practice.
8. **Postel-style liberal input acceptance.** The supplied Release It summary presents it in versioning; modern security and protocol-evolution evidence must challenge when permissiveness creates ambiguity or attack surface.
9. **Requirements Essentials completeness.** The book explicitly condenses a much larger field; its selection does not eliminate the need for broader requirements research.
10. **Any example quality threshold.** Example response times, coverage targets or other numbers in the books are illustrations, not project defaults.

---

# 6. Source-to-capability matrix

The following are **provisional capabilities**, not skill names.

| Capability | Primary source support | Production responsibility | Possible workflow/command implication | Evaluation / benchmark direction |
| --- | --- | --- | --- | --- |
| C1. Clarify change intent and acceptance | Requirements Essentials; Google | Convert request/defect into explicit engineering target without inventing product policy | Clarify problem, boundaries, quality and acceptance | Ambiguous request resolved into testable target; unresolved policy escalated |
| C2. Discover system context and effective contracts | Requirements Essentials; Feathers; Google | Understand repository/system before editing | Inspect architecture, dependencies, consumers, tests and runtime assumptions | Correctly identifies affected contracts and hidden observable behaviour |
| C3. Analyse impact, risk and blast radius | Requirements Essentials; Feathers; Architecture | Determine what can change and what must remain stable | Effect tracing, ecosystem/context mapping, dependency/quality impact | Change affects intended area while preserving unaffected behaviour |
| C4. Decide local design versus architecture change | Architecture; Google; Feathers | Avoid both patching through broken boundaries and unnecessary redesign | Classify consequence/trade-offs; record rationale when structural | Chooses smallest coherent structural scope; rejects pattern-by-fashion |
| C5. Establish a safe feedback boundary | Feathers; Google testing | Make risky brownfield code verifiable | Characterise, choose interception point, introduce seam if justified | Feedback detects relevant regression with useful localisation |
| C6. Implement and refactor incrementally | Feathers; Google code review | Produce small coherent changes that preserve behaviour | Single-goal edits, sprout/wrap fallback, small atomic patching | Patch is reviewable, reversible and free of unrelated change |
| C7. Select layered verification | All five | Match checks to failure/risk | Cheap checks first, then integration/load/fault/release evidence | Each layer covers a named residual risk; test actually detects claimed failure |
| C8. Review code and architecture health | Google; Architecture | Separate correctness from maintainability/architecture quality | Code review, complexity/consistency, architecture compliance | Reviewer can explain correctness, readability, compatibility and characteristic impact separately |
| C9. Evolve APIs, schemas, dependencies and configuration | Requirements; Google; Release It | Preserve compatibility while enabling change | Consumer analysis, deprecation, migration, version coexistence | Mixed versions/consumers handled; migration and rollback evidence exists |
| C10. Design failure containment and resilience | Release It; Architecture; Google larger testing | Prevent local runtime faults from becoming systemic outages | Identify integration points, apply timeout/isolation/backpressure/load shedding as justified | Fault injection/overload shows bounded degradation rather than cascade |
| C11. Produce diagnostic evidence and isolate failure | Release It; Feathers; Google | Find owning layer before repair | Trace effects, observability, reproduction, hypothesis isolation | Representative defect can be reproduced/localised without broad rewrite |
| C12. Preserve releasability | Google CI/CD; Release It; Architecture | Keep software capable of safe release/distribution | Build/package/config validation, RC promotion, smoke/staged rollout constraints | Same artefact/config path remains deployable; rollback/migration constraints known |
| C13. Govern consequential commitments | Requirements; Architecture; Google; Release It governor | Escalate destructive/breaking/high-blast-radius choices | Identify decision owner, record rationale, bound automation | No unauthorised contract/data/security break; decision evidence is traceable |
| C14. Maintain, migrate and deprecate sustainably | Google; Feathers; Architecture | Reduce future change cost without speculative cleanup | Explicit owner, automation, incremental migration, cleanup | Old path usage declines; future change becomes cheaper or better evidenced |

---

# 7. Provisional evidence-to-behaviour model

The corpus currently supports the following hypothesis:

```text
change intent / defect / requirement
→ clarify problem, boundaries and acceptance
→ inspect the real system and effective contracts
→ identify change points, effects and quality risks
→ decide whether the change is local or architectural
→ establish the cheapest adequate feedback boundary
→ implement the smallest coherent change
→ verify locally and cheaply
→ escalate verification according to residual risk
→ review correctness, compatibility and code/architecture health
→ test runtime/release behaviour where relevant
→ diagnose failures at the owning layer
→ repair the smallest sufficient scope
→ preserve releasability and migration evidence
```

This is still a research hypothesis. Stage 4 must challenge it against professional practice and subjects the corpus covers weakly.

The model deliberately keeps separate:

```text
intent / acceptance
system understanding
architecture decision
implementation
verification
runtime resilience
release readiness
human commitment
```

A failure in one layer should not automatically cause regeneration of all others.

---

# 8. Candidate benchmark cases derived from the corpus

These are benchmark **candidates**, not final benchmark design.

## B1 — Brownfield defect in untested dependency-heavy code

Expected evidence:

- identify the true change point and affected behaviour;
- establish characterisation/feedback at a useful interception point;
- introduce only the minimum seam/dependency break required;
- fix the defect with a focused regression;
- preserve unrelated behaviour.

Tests C2, C3, C5, C6, C7 and C11.

## B2 — Backward-compatible API evolution with hidden consumers

Expected evidence:

- distinguish documented and observed contracts;
- inspect consumers;
- design deprecation/migration path;
- preserve coexistence window;
- avoid accidental broad breakage.

Tests C2, C3, C9, C13 and C14.

## B3 — Persistent schema change during rolling deployment

Expected evidence:

- identify mixed-version period;
- stage additive/migration/removal work;
- preserve data integrity and rollback/recovery constraints;
- verify release path.

Tests C3, C9, C12 and C13.

## B4 — Dependency slowdown causing retry amplification

Expected evidence:

- identify the integration point and propagation path;
- diagnose blocked resources/retry amplification;
- choose bounded timeout/retry/backoff/isolation/load-shedding behaviour as appropriate;
- verify with controlled fault/load evidence.

Tests C7, C10 and C11.

## B5 — Quality-attribute requirement forces an architectural decision

Expected evidence:

- translate the quality requirement into measurable characteristic;
- determine that local implementation is insufficient;
- compare architecture alternatives and trade-offs;
- retain decision rationale;
- create a fitness check protecting the selected characteristic.

Tests C1, C4, C7 and C8.

## B6 — Large dependency/runtime upgrade

Expected evidence:

- map direct/transitive impact;
- break migration into reviewable increments;
- use automation for mechanical work;
- preserve compatibility and CI evidence;
- clean up obsolete paths.

Tests C3, C6, C9, C12 and C14.

## B7 — Ambiguous high-consequence change request

Expected evidence:

- expose conflicting interpretations;
- identify decision authority;
- avoid implementation until the externally visible policy is resolved;
- encode the decision as acceptance evidence.

Tests C1 and C13.

## B8 — Prototype at risk of becoming production

Expected evidence:

- state the uncertainty the prototype answers;
- classify it as throwaway or evolutionary;
- prevent low-fidelity exploratory code from silently becoming release code;
- either discard or raise engineering quality deliberately.

Tests C1, C4, C6 and C12.

---

# 9. Stage 4 challenge backlog

The corpus is complementary but incomplete. Stage 4 must not merely confirm it.

## Highest-priority gaps

### Security engineering integration

The corpus discusses security unevenly and often only as a quality attribute or introductory operational concern.

Research current primary guidance for:

- secure development lifecycle;
- threat modelling trigger points;
- authentication/authorisation and trust-boundary change;
- dependency/supply-chain risk;
- vulnerability response;
- secrets handling;
- when specialist security review becomes mandatory.

NIST SSDF and current OWASP material should be primary anchors.

### Debugging and root-cause diagnosis

Feathers provides effect reasoning and Google discusses troubleshooting, but the five sources do not provide a sufficiently complete modern debugging discipline.

Research:

- reproducibility and minimisation;
- hypothesis-driven debugging;
- binary search / bisection;
- concurrency and distributed tracing;
- causal versus correlated signals;
- incident-derived repair evidence.

### API / event / schema evolution

The corpus strongly establishes the need but only partially covers modern methods.

Research:

- semantic compatibility;
- additive versus breaking change;
- consumer-driven evidence;
- event/schema evolution;
- online database migration;
- version negotiation;
- deprecation and removal;
- the limitations of Postel-style permissiveness.

### Observability and operability

`Release It!` and current OpenTelemetry material establish the need, but core versus SRE ownership remains unclear.

Research:

- logs, metrics, traces and profiles;
- high-cardinality diagnostics;
- correlation and exemplars;
- instrumentation cost;
- actionable telemetry;
- Software Engineering/SRE handoff.

### Performance and concurrency

The architecture and production sources contain relevant material but do not provide a complete general method.

Research:

- measurement before optimisation;
- representative workload design;
- latency distributions and tail behaviour;
- memory/resource profiling;
- concurrency hazards and race detection;
- capacity versus efficiency;
- performance regression evidence.

## Additional claims to challenge

1. When are characterisation tests the right preservation tool versus higher-level contract tests?
2. How should modern testing literature qualify Feathers’ fast-isolated unit-test framing?
3. What empirical evidence supports small batch/change size and what is merely organisational convention?
4. Which architecture fitness-function practices have durable evidence beyond practitioner examples?
5. When is synchronous-first communication a good heuristic, and when does it create tight runtime coupling?
6. Which resilience patterns still hold across serverless, managed messaging and modern service meshes?
7. What current evidence exists for safe retry placement, idempotency and retry budgets?
8. How should dependency-management guidance incorporate SBOMs, provenance, signatures and current supply-chain controls?
9. How should AI-generated or agent-generated changes alter review, provenance or evaluation, if at all?
10. Where exactly does requirements clarification stop and Product Management authority begin in small versus large teams?
11. What release-readiness evidence differs between libraries, services, web, desktop and mobile software?
12. Which high-assurance domains require formal methods or specialist packs rather than generic automation?

---

# 10. What this stage does not conclude

Stage 3 does **not** establish:

- final skill names or count;
- final command decomposition;
- a mandatory lifecycle;
- a universal risk score;
- one architecture style or language stack;
- universal testing ratios;
- universal code-review size limits;
- mandatory continuous deployment;
- a default microservices architecture;
- a fixed observability stack;
- a fixed set of resilience thresholds;
- final Extension Packs;
- benchmark thresholds;
- AI provider or coding-agent choices.

The extracted capabilities remain provisional until Stage 4 challenge research qualifies them.

---

# 11. Stage 3 exit-criteria verification

| Exit criterion | Evidence | Status |
| --- | --- | --- |
| Five corpus members identified | `software-engineering-corpus-r2` records exactly five sources | PASS |
| Supplied-source substitution resolved | Requirements title replacement explicitly recorded | PASS |
| Per-book findings are based on examined material | Four full texts examined directly; Release It basis explicitly separates summary, official excerpts and web extension | PASS |
| Material findings are traceable | Each extraction records chapter/section or stable source basis | PASS |
| Production implications recorded | Every extraction includes behaviour/evaluation/failure disposition | PASS |
| Source-to-capability matrix exists | Section 6 | PASS |
| Reinforcing, overlapping and competing ideas reconciled | Section 5 | PASS |
| Limitations and context are explicit | Sections 3, 5.2 and 5.3 | PASS |
| Missing subjects and claims needing challenge are explicit | Section 9 | PASS |
| No book is converted mechanically into a skill | Capability model remains provisional and cross-source | PASS |
| Private/copyright source material is not published | Only independent synthesis and bibliographic/source locations are committed | PASS |

## Completion decision

Stage 3 is complete for the purposes of the bootstrap gate.

The `Release It!` evidence is intentionally marked **qualified** rather than pretending the full book was directly examined. Its intended contribution—production stability, failure containment and release/version behaviour—is supported by the supplied expanded map, official publisher material and current independent operational sources. Claims that depend on unexamined detail remain qualified and are carried into Stage 4 rather than silently promoted.

Stage 4 may now challenge the provisional capability model through broader professional software-engineering research.
