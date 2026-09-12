# Stage 2 — Knowledge Coverage and Five-Book Corpus

**Project:** `software-engineering-skills`  
**Bootstrap stage:** 2 — Seed: Map Knowledge Coverage and Select Five Complementary Books  
**Status:** Complete  
**Date:** 12 September 2026  
**Corpus revision:** `software-engineering-corpus-r1`

## 1. Stage purpose

This stage establishes the foundational five-book research corpus for `software-engineering-skills`.

It does **not** extract the books, validate their claims, design skills, or treat five books as a complete model of software engineering. Its job is narrower:

```text
Stage 1 domain boundary
→ bounded authoritative reconnaissance
→ knowledge-coverage map
→ broader candidate-book comparison
→ exactly five complementary foundational books
→ explicit overlap and gaps
→ source-access register
→ Stage 3 acquisition requirements
```

The governing rule is **Seed → Five → Challenge**. The five books are a research foundation, not an architectural authority.

## 2. Inputs reviewed

### 2.1 Project evidence

- [`2026-09-07-software-engineering-skills-new-project-bootstrap-process.md`](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md)
- [`2026-09-12-stage-01-project-goal-and-domain-boundary.md`](2026-09-12-stage-01-project-goal-and-domain-boundary.md)
- [`production-skills/docs/bootstrap/domain-research-process.md`](https://github.com/sb-dev/production-skills/blob/main/docs/bootstrap/domain-research-process.md)
- [`production-skills/docs/specs/01-production-skills-family-system.md`](https://github.com/sb-dev/production-skills/blob/main/docs/specs/01-production-skills-family-system.md)
- [`production-skills/docs/specs/02-production-skills-project-contract.md`](https://github.com/sb-dev/production-skills/blob/main/docs/specs/02-production-skills-project-contract.md)

Stage 1 establishes a **brownfield-first, greenfield-capable** discipline that owns reusable engineering judgement from system understanding through releasable evidence. The corpus therefore needs to serve software change, not only new-system design or programming technique.

### 2.2 User-provided books

No software-engineering books or source files were supplied for this stage.

Therefore:

- there are no protected supplied-book slots;
- no substitution permission is required;
- all five corpus slots may be selected on complementary coverage;
- later corpus changes still require a new explicit corpus revision and impact review.

## 3. Bounded authoritative reconnaissance

This reconnaissance is intentionally limited to mapping the discipline well enough to compare book contributions. It is not the broader professional challenge research required by Stage 4.

### 3.1 SWEBOK Guide V4.0

The IEEE Computer Society SWEBOK V4 topic map treats software requirements, architecture, design, construction, testing, engineering operations, maintenance, configuration management, engineering management and software quality as distinct but connected knowledge areas.

Source:

- [SWEBOK Guide V4.0 Topics](https://www.computer.org/education/bodies-of-knowledge/software-engineering/topics)

Important implications for corpus selection:

- requirements and acceptance cannot be inferred from coding practice alone;
- architecture and detailed design require explicit trade-off reasoning;
- testing is broader than test execution;
- maintenance includes program comprehension, impact analysis and evolution;
- release/deployment, rollback, data migration, troubleshooting and telemetry sit in the software-engineering landscape even when production operations are owned elsewhere;
- configuration and change control matter to safe evolution;
- software quality is multidimensional.

### 3.2 DORA continuous delivery

DORA defines continuous delivery as keeping software in a state where changes can be released quickly, safely and sustainably on demand. Its current capability guidance links this to test automation, continuous integration, version control, continuous testing, deployment automation, fast feedback and deployability.

Source:

- [DORA — Continuous delivery](https://dora.dev/capabilities/continuous-delivery/)

Implication: the corpus needs meaningful coverage of **releasability and fast feedback**, not only code construction.

### 3.3 NIST Secure Software Development Framework

NIST SP 800-218 v1.1 remains the current final SSDF publication at this stage; SP 800-218 Rev. 1 / SSDF 1.2 is still an initial public draft. The SSDF requires secure practices to be integrated with software development rather than appended only at the end.

Sources:

- [NIST SP 800-218, SSDF v1.1](https://csrc.nist.gov/pubs/sp/800/218/final)
- [NIST SSDF project](https://csrc.nist.gov/projects/ssdf)

Implication: general engineering must recognise security-sensitive change, dependency/supply-chain risk and vulnerability response, but the five-book corpus does not need to become a specialist security curriculum. Missing depth can be challenged with current primary sources in Stage 4.

### 3.4 Google Engineering Practices

Google's code-review guidance evaluates design, functionality, complexity, tests, naming, comments, documentation and whole-system context, and explicitly warns against speculative over-engineering.

Source:

- [Google Engineering Practices — What to look for in a code review](https://google.github.io/eng-practices/review/reviewer/looking-for.html)

Implication: code correctness alone is insufficient. The corpus should support reviewability, simplicity, test quality, code health and contextual fit.

### 3.5 ISO/IEC 25010:2023

ISO/IEC 25010:2023 defines a product-quality model intended to support specification, measurement and evaluation of software quality across the lifecycle.

Source:

- [ISO/IEC 25010:2023 product quality model](https://www.iso.org/standard/78176.html)

Implication: quality must remain a set of explicit dimensions. The corpus should not be selected around one opaque quality score or one methodology.

## 4. Knowledge-coverage map

The following map is derived from the Stage 1 boundary plus the bounded reconnaissance above. `High`, `medium` and `supporting` describe **needed foundational depth**, not numerical scores.

| Knowledge dimension | Needed depth | Why it matters to this project | Desired foundational contribution |
| --- | --- | --- | --- |
| Requirements and acceptance | High | Engineering must turn change intent into testable conditions without inventing product policy | requirement quality, elicitation/clarification, validation, non-functional requirements, change management |
| System/repository understanding | High | Brownfield-first agents must understand existing code before editing | program comprehension, context discovery, dependency understanding, safe investigation |
| Software architecture | High | Architecture is in scope when structure or qualities must change | quality attributes, boundaries, patterns/styles, trade-offs, architectural significance, decisions |
| Detailed design and complexity | High | Local design quality determines maintainability and change safety | modularity, coupling/cohesion, complexity control, design proportional to need |
| Construction and code quality | High | The system must produce maintainable implementation rather than snippets | code health, implementation discipline, reviewability, defensive construction |
| Maintenance and evolution | High | Corrective, adaptive, additive, perfective and emergency work are first-class | change impact, evolution, deprecation, compatibility, sustainable maintenance |
| Brownfield change safety | High | Existing behaviour and contracts are production assets | characterization/feedback, seams, dependency breaking, incremental safe change |
| Refactoring and technical debt | High | Agents must improve structure without speculative rewrites | behaviour-preserving change, scope discipline, evidence for cleanup |
| Testing and test quality | High | Tests must detect relevant defects, not merely exist | test strategy, testability, focused regression, test effectiveness, test maintenance |
| Debugging and root-cause diagnosis | High | Repair must target the owning layer rather than regenerate unrelated work | reproducibility, hypothesis-driven diagnosis, failure isolation, smallest sufficient repair |
| Code review | High | Change quality requires independent/contextual examination | design/functionality/complexity/tests/context review |
| API and contract evolution | High | External behaviour must remain compatible unless explicitly changed | versioning, deprecation, compatibility, migration, consumer impact |
| Data/schema evolution | High | Persistent changes can be destructive or difficult to reverse | migration safety, compatibility, invariants, rollback/recovery |
| Security engineering integration | Medium–high | General engineering owns secure implementation and escalation, not specialist assurance | secure-by-default development, dependency risk, trust-boundary awareness, vulnerability response |
| Performance and concurrency | Medium–high | Performance/concurrency regressions may be material and difficult to test casually | measurement, resource budgets, concurrency hazards, evidence-led optimisation |
| Reliability and resilience | High for runtime software | Stage 1 includes failure behaviour and graceful recovery | failure modes, timeouts, retries, isolation, back pressure, recovery, production-oriented design |
| Continuous integration and delivery | High | Releasability and fast feedback are owned outcomes | build/test automation, deployability, release path, feedback loops |
| Observability and operability | Medium–high | Changed runtime behaviour must be diagnosable | logs/metrics/traces/diagnostics as uncertainty-reduction tools, not instrumentation for its own sake |
| Configuration/dependency management | High | Dependencies and configuration are part of the executable system | version control, dependency evolution, deterministic/reproducible builds, configuration safety |
| Engineering economics and change scope | High | The project must choose the smallest responsible change | trade-offs, cost of change, blast radius, sequencing, avoiding speculative work |
| Human review and commitment | Medium–high | Breaking/destructive/high-consequence changes require authority | decision records, escalation, explicit irreversible commitments |
| Releasability and handoff evidence | High | Software Engineering owns credible release readiness, not merely local success | build/package integrity, smoke evidence, migration notes, release constraints, technical handoff |

No single book is expected to cover this map. The five-book corpus should create **complementary lenses** and leave the remaining gaps visible for Stage 4.

## 5. Candidate pool

Selection considered a broader pool than the five available slots. Publisher/author descriptions and tables of contents were used only for selection; they do not count as Stage 3 extraction.

| Candidate | Distinct contribution | Main limitation for this corpus | Decision |
| --- | --- | --- | --- |
| **Software Requirements, 3rd ed.** — Karl Wiegers & Joy Beatty (2013) | End-to-end requirements development/management; validation; non-functional, data and change requirements; enhancement/replacement projects | Older examples and process framing need challenge against current product/delivery practice | **Selected** |
| **Fundamentals of Software Architecture, 2nd ed.** — Mark Richards & Neal Ford (2025) | Architecture characteristics, modularity, styles, trade-offs, ADRs, risk, architecture/implementation intersection | Practitioner-oriented rather than a formal architecture standard; not a construction/testing book | **Selected** |
| **Working Effectively with Legacy Code** — Michael Feathers (2004) | Brownfield program change, feedback, seams, dependency breaking, test harnesses, safe work in hard-to-change code | Examples and language/tool assumptions are old; architectural/runtime concerns are limited | **Selected** |
| **Software Engineering at Google** — Titus Winters, Tom Manshreck & Hyrum Wright (2020) | Engineering over time and scale; trade-offs/costs; testing, code review, deprecation, dependencies, large changes, CI/CD and tooling | Google scale/culture is not universal; organisation-specific practices need qualification | **Selected** |
| **Release It! Second Edition** — Michael Nygard (2018) | Production-oriented reliability, failure modes, stability patterns/antipatterns, deployment/versioning, systemic failures | Runtime/distributed emphasis; some cloud/DevOps details require current verification | **Selected** |
| **Refactoring, 2nd ed.** — Martin Fowler (2018) | Precise behaviour-preserving code transformation and refactoring catalogue | Strong but narrower; substantial overlap with the brownfield/change-safety slot occupied by Feathers | Rejected from foundational five; strong supplementary candidate |
| **A Philosophy of Software Design, 2nd ed.** — John Ousterhout (2021) | Complexity, module depth, information hiding and deliberate design; useful contrast to common “clean code” doctrine | Narrower than the architecture + engineering-practice combination already selected | Rejected from foundational five; useful Stage 4/design challenge source |
| **Code Complete, 2nd ed.** — Steve McConnell (2004) | Broad construction, defensive programming, debugging, quality and practical coding discipline | Large overlap with construction/review/change concerns; examples and technology context are old | Rejected from foundational five; possible debugging/construction supplement |
| **Modern Software Engineering** — David Farley (2021) | Empiricism, experimentation, feedback, incremental progress and managing complexity | Broad philosophy overlaps heavily with Google engineering and later DORA evidence; less unique domain-edge coverage | Rejected from foundational five; useful challenge source |
| **Continuous Delivery** — Jez Humble & David Farley (2010) | Deployment pipeline, build/test/deploy automation, configuration/data migration and low-risk delivery | Important but delivery-specific; overlaps Google + Release It; tooling details require substantial current challenge | Rejected from foundational five; Stage 4/delivery supplement |
| **Accelerate** — Nicole Forsgren, Jez Humble & Gene Kim (2018) | Empirical evidence linking delivery capabilities and outcomes | Organisation/team-performance emphasis exceeds this project's default boundary; current DORA research is a stronger Stage 4 authority | Rejected from foundational five; evidence source rather than core craft source |
| **Effective Software Testing** — Maurício Aniche (2022) | Developer-focused test design from requirements/code through unit, integration and system levels | Narrower testing focus; Google + Feathers provide foundational testing/change context | Rejected from foundational five; likely Stage 4/testing supplement |
| **Software Architecture in Practice, 4th ed.** — Len Bass, Paul Clements & Rick Kazman (2021) | Rigorous quality-attribute-driven architecture design, analysis and evolution | Strong alternative, but only one architecture slot is justified; the selected Richards/Ford edition is newer and more directly bridges architecture, implementation, ADRs and practitioner trade-offs | Rejected from foundational five; strong architecture challenge/reference |
| **Designing Data-Intensive Applications, 2nd ed.** — Martin Kleppmann & Chris Riccomini (2026) | Current data/distributed-system architecture, reliability, consistency, encoding/evolution and trade-offs | Excellent but too specialised to consume one of five general-core slots | Rejected from foundational five; likely distributed/data Extension Pack or later specialist source |
| **The Pragmatic Programmer, 20th Anniversary Edition** — David Thomas & Andrew Hunt (2019) | Broad programmer judgement and durable craft heuristics | Very broad and heuristic; less unique coverage than the five selected responsibilities | Rejected from foundational five; supplementary craft source |

## 6. Selected foundational corpus

The selected corpus contains exactly five distinct books.

### Book 1 — Software Requirements, 3rd Edition

**Authors:** Karl Wiegers and Joy Beatty  
**Published:** 2013  
**Publisher:** Microsoft Press  
**Selection source:** [Microsoft Press](https://www.microsoftpressstore.com/store/software-requirements-9780735679627)

**Primary role in corpus:** change intent, requirements quality, acceptance, requirements validation and requirements evolution.

Why selected:

- Stage 1 allows Software Engineering to clarify engineering acceptance but forbids silently inventing product policy;
- the book explicitly covers requirements development and management, non-functional requirements, data requirements, validation, change, traceability and enhancement/replacement projects;
- it adds upstream discipline that none of the other four books covers deeply;
- it prevents the corpus from starting at architecture or code after important ambiguity has already been lost.

Expected challenge:

- distinguish reusable engineering clarification from Product Management ownership;
- challenge older process assumptions against current iterative/product practice;
- verify current requirements/acceptance practices through Stage 4 evidence.

### Book 2 — Fundamentals of Software Architecture, 2nd Edition

**Authors:** Mark Richards and Neal Ford  
**Published:** March 2025  
**Publisher:** O'Reilly Media  
**Selection source:** [O'Reilly](https://www.oreilly.com/library/view/fundamentals-of-software/9781098175504/)

**Primary role in corpus:** architecture characteristics, modularity, architectural styles, trade-off analysis, architectural decisions, risk and the boundary between architecture and implementation.

Why selected:

- Stage 1 explicitly includes architecture but requires architecture depth to be proportional to uncertainty and consequence;
- the second edition covers strategic versus tactical decisions, modularity, coupling/cohesion, architecture characteristics, risk, ADRs, architectural styles and architecture/implementation intersections;
- it provides a practical vocabulary for identifying when a local code change is insufficient and a structural decision is actually required;
- the 2025 edition reduces the need to compensate for outdated architectural examples during initial extraction.

Expected challenge:

- architecture patterns must not become default prescriptions;
- practitioner heuristics require comparison with quality-attribute and empirical architecture research;
- team/leadership material outside the project's boundary must not be promoted into core engineering behaviour automatically.

### Book 3 — Working Effectively with Legacy Code

**Author:** Michael Feathers  
**Published:** September 2004  
**Publisher:** Pearson  
**Selection sources:** [Pearson](https://www.pearson.com/en-gb/subject-catalog/p/working-effectively-with-legacy-code/P200000008984/9780131177055), [O'Reilly catalogue](https://www.oreilly.com/library/view/working-effectively-with/0131177052/)

**Primary role in corpus:** brownfield understanding, feedback, dependency breaking, testability and safe change in code that is difficult to modify.

Why selected:

- the project is explicitly brownfield-first;
- its chapter structure directly addresses unfamiliar or poorly structured code, deciding what to test, adding features safely, dependency problems and verifying that a change has not broken behaviour;
- its seam and feedback concepts provide concrete production mechanics rather than only abstract maintainability advice;
- it fills a different role from architecture: how to create safe change capacity when the existing code does not already support clean modification.

Expected challenge:

- examples are more than two decades old and must be separated from durable principles;
- heavy unit-test/seam tactics should be challenged against modern language, static-analysis, integration-testing and runtime-observability capabilities;
- “legacy” must not become synonymous with “bad” or justify unnecessary rewrites.

### Book 4 — Software Engineering at Google

**Authors:** Titus Winters, Tom Manshreck and Hyrum Wright  
**Published:** 2020  
**Publisher:** O'Reilly Media  
**Selection sources:** [Google Research](https://research.google/pubs/software-engineering-at-google/), [freely available HTML edition](https://abseil.io/resources/swe-book)

**Primary role in corpus:** sustainable engineering over time and scale, engineering trade-offs, code review, testing, deprecation, dependency management, large changes, static analysis, CI/CD and tooling.

Why selected:

- it explicitly distinguishes programming from software engineering by considering time, change, scale and trade-offs;
- it covers many connective practices between individual code changes and a sustainable codebase;
- it adds code-review and large-change perspectives not represented deeply by the other selected books;
- it provides the broadest cross-cutting engineering lens in the corpus while the other four books supply sharper responsibility-specific depth;
- the complete HTML text is legally available, so Stage 3 can examine it directly and traceably.

Expected challenge:

- Google-specific scale, monorepo, tooling and culture assumptions must not be universalised;
- organisation design and cultural material must be kept separate from reusable change-engineering behaviour when outside the Stage 1 boundary;
- claims should be compared with broader empirical evidence and smaller-team contexts.

### Book 5 — Release It! Second Edition

**Author:** Michael T. Nygard  
**Published:** January 2018  
**Publisher:** The Pragmatic Bookshelf  
**Selection source:** [Pragmatic Bookshelf](https://books.pragprog.com/titles/mnee2/release-it-second-edition/)

**Primary role in corpus:** failure-aware design, reliability/resilience, production-readiness, integration failure, deployment/versioning and systemic operational failure modes.

Why selected:

- Stage 1 owns credible releasability and software-level reliability without taking over SRE operations;
- the book explicitly covers stability antipatterns, stability patterns, integration points, production design, security concerns, deployment, version handling, load testing and systemic problems;
- it adds runtime failure reasoning that is largely absent from the requirements, brownfield-change and Google-process books;
- it gives the corpus a concrete counterweight to code-centric quality: software that is locally correct may still fail badly under real runtime conditions.

Expected challenge:

- distributed/cloud practice has evolved since 2018;
- security coverage is not sufficient for specialist security engineering;
- production-operation advice must be separated from the project's boundary of application engineering and releasability.

## 7. Why these five work together

The five-book set is designed as a chain of complementary engineering questions rather than five overlapping “best practices” books.

```text
Software Requirements
→ What does the change actually need to achieve and how can it be validated?

Fundamentals of Software Architecture
→ Which structural qualities and trade-offs matter, and is this change architecturally significant?

Working Effectively with Legacy Code
→ How can the existing system be made safe enough to understand, test and change?

Software Engineering at Google
→ How should change remain sustainable over time through review, testing, dependencies, tooling and engineering discipline?

Release It!
→ Will the changed software remain resilient, diagnosable and releasable under real runtime failure conditions?
```

This ordering is explanatory only. Stage 3 must not force the final workflow to mirror the books.

## 8. Coverage contribution matrix

Legend:

- **Primary** — a major intended corpus contribution;
- **Supporting** — meaningful material expected, but not the main reason for selection;
- **Limited** — some relevant material may exist but should not be relied upon for foundational depth;
- **Gap** — deliberately requires Stage 4 or supplementary research.

| Dimension | Requirements | Architecture | Legacy Code | SWE at Google | Release It! | Corpus result |
| --- | --- | --- | --- | --- | --- | --- |
| Requirements and acceptance | **Primary** | Supporting | Limited | Limited | Limited | Strong foundation |
| System/repository understanding | Limited | Supporting | **Primary** | **Primary** | Supporting | Strong foundation |
| Architecture and trade-offs | Supporting | **Primary** | Limited | Supporting | **Primary** | Strong foundation, useful competing lenses |
| Detailed design/complexity | Limited | **Primary** | Supporting | **Primary** | Supporting | Strong foundation |
| Construction/code quality | Limited | Supporting | Supporting | **Primary** | Limited | Moderate; Stage 4 should challenge with construction evidence |
| Maintenance/evolution | Supporting | Supporting | **Primary** | **Primary** | Supporting | Strong foundation |
| Brownfield change safety | Supporting | Supporting | **Primary** | Supporting | Limited | Strong foundation |
| Refactoring/technical debt | Limited | Supporting | **Primary** | Supporting | Limited | Moderate–strong; Fowler remains supplementary candidate |
| Testing/test quality | Supporting | Limited | **Primary** | **Primary** | Supporting | Strong general foundation; specialist depth still needed |
| Debugging/root cause | Limited | Limited | Supporting | Supporting | **Primary** | Moderate; explicit Stage 4 gap |
| Code review | Limited | Supporting | Limited | **Primary** | Limited | Strong single-source foundation; must be challenged |
| API/contract evolution | Supporting | Supporting | Supporting | **Primary** | Supporting | Moderate; explicit Stage 4 gap |
| Data/schema evolution | **Primary** for requirements | Supporting | Limited | Limited | Supporting | Partial; explicit Stage 4 gap |
| Security integration | Supporting | Supporting | Limited | Supporting | Supporting | Partial; Stage 4 must use current security authorities |
| Performance/concurrency | Supporting | **Primary** at architectural level | Limited | Supporting | **Primary** in runtime context | Moderate–strong, but specialist depth absent |
| Reliability/resilience | Supporting | **Primary** at architecture level | Limited | Supporting | **Primary** | Strong foundation |
| CI/CD | Limited | Supporting | Limited | **Primary** | **Primary** | Strong foundation; current DORA challenge required |
| Observability/operability | Limited | Supporting | Limited | Supporting | **Primary** | Moderate; explicit Stage 4 gap |
| Configuration/dependencies | Limited | Supporting | **Primary** for dependency breaking | **Primary** | Supporting | Strong foundation |
| Engineering economics/change scope | Supporting | **Primary** trade-offs | **Primary** local safety | **Primary** time/scale/cost | Supporting | Strong foundation |
| Human review/commitment | Supporting | Supporting | Limited | **Primary** review | Supporting | Moderate; project authority model still later-stage work |
| Releasability/handoff evidence | Limited | Supporting | Limited | **Primary** | **Primary** | Strong foundation |

## 9. Material overlap analysis

Overlap is retained only where it creates useful depth or contrasting viewpoints.

### 9.1 Software Engineering at Google ↔ Working Effectively with Legacy Code

Overlap:

- testing;
- dependency management;
- change safety;
- code health.

Why both remain:

- Feathers operates at the local brownfield-change problem: how to create feedback and isolate hard-to-change code;
- Google operates at codebase/system scale: how engineering practices remain sustainable over time and across large changes;
- the tension between local test seams and organisation-scale tooling is useful research material rather than duplication.

### 9.2 Fundamentals of Software Architecture ↔ Release It!

Overlap:

- distributed systems;
- architecture characteristics;
- reliability;
- deployment/runtime concerns.

Why both remain:

- Richards/Ford frames architecture as explicit trade-offs, characteristics, styles, risk and decisions;
- Nygard frames architecture from concrete production failure, stability and recovery;
- Stage 3 should test where architecture abstractions predict the failure modes described by Nygard and where they do not.

### 9.3 Software Requirements ↔ Fundamentals of Software Architecture

Overlap:

- non-functional/quality concerns;
- prioritisation and business/technical drivers.

Why both remain:

- requirements work identifies and validates the needed qualities and constraints;
- architecture work decides how system structure addresses architecturally significant qualities;
- this is a producer/consumer relationship, not redundant coverage.

### 9.4 Software Engineering at Google ↔ Release It!

Overlap:

- CI/CD;
- change processes;
- production readiness;
- testing.

Why both remain:

- Google focuses on engineering processes, tools and change sustainability;
- Nygard focuses on failure behaviour and production architecture;
- together they prevent delivery automation from being mistaken for runtime resilience.

### 9.5 Software Engineering at Google ↔ Fundamentals of Software Architecture

Overlap:

- design trade-offs;
- scale;
- dependency and structure concerns.

Why both remain:

- Google is deliberately broad and process/tool-oriented;
- Richards/Ford provides architecture-specific vocabulary, risk analysis and decision mechanisms that the Google book does not attempt to provide comprehensively.

## 10. Why prominent alternatives were not selected

### Refactoring, 2nd Edition

It is highly relevant and remains a strong supplementary source. It was not selected because `Working Effectively with Legacy Code` better matches the project's distinctive brownfield-first boundary: understanding, isolating and safely changing systems that are not already testable. Refactoring can challenge and deepen the safe-transformation model later without consuming one of the five foundational slots.

### A Philosophy of Software Design, 2nd Edition

It offers valuable, sometimes contrarian design guidance on complexity and module design. However, the selected architecture book plus Google and Feathers already provide three different design/change lenses. Ousterhout is more valuable as a Stage 4 challenge source precisely because its disagreements with other design schools can be investigated rather than silently elevated to foundational doctrine.

### Code Complete, 2nd Edition

Its breadth in construction and debugging is useful, but it is from 2004 and overlaps heavily with Google, Feathers and later professional-practice research. Debugging remains a known gap, so selected sections or the book may still be used during Stage 4 if direct examination can resolve that gap.

### Modern Software Engineering

Its feedback, empiricism and incrementalism fit the project well, but its broad thesis overlaps the cross-cutting role already occupied by `Software Engineering at Google`, while requirements and production failure would otherwise be underrepresented.

### Continuous Delivery

It is a foundational delivery work, but one of only five slots should not duplicate coverage already available across Google's CI/CD chapters and Nygard's deployment/versioning material. Current DORA capabilities provide a natural Stage 4 mechanism to challenge older delivery practices.

### Effective Software Testing

It is a strong modern testing candidate, but testing is already materially represented by Feathers and Google. A specialist testing source is better used during Stage 4 to challenge test effectiveness and fill gaps without removing requirements, architecture or production reliability from the five-book foundation.

### Software Architecture in Practice, 4th Edition

It is a particularly strong alternative to `Fundamentals of Software Architecture`. Only one general architecture slot is justified. Richards/Ford 2nd edition was selected because it is newer, explicitly includes ADRs, architecture risk, architecture/implementation intersections and current architecture styles in a highly practitioner-oriented form. Bass/Clements/Kazman should remain a high-priority architecture challenge/reference source.

### Designing Data-Intensive Applications, 2nd Edition

The 2026 second edition is highly current and directly relevant to distributed/data-heavy systems, including consistency, reliability and encoding/evolution. It is nevertheless a specialist systems book. Selecting it in the core five would overfit the corpus toward distributed data systems and away from general software engineering. It is a likely later Extension Pack or specialist research source.

## 11. Remaining domain gaps after selection

Selection is not complete coverage. The following gaps are deliberately carried forward.

### 11.1 Security engineering depth

The corpus contains security-adjacent material but no dedicated secure-development book. Stage 4 must use current authoritative security material, especially the final NIST SSDF and suitable OWASP/secure-design evidence, to determine what belongs in general engineering versus specialist escalation.

### 11.2 Debugging and root-cause diagnosis

Feathers and Nygard contribute diagnosis context, and Google contributes failure-isolation/tooling material, but the corpus does not provide a complete evidence-based debugging model across local, integration and production failures.

### 11.3 API, event and schema evolution

Compatibility appears across several books, but the corpus lacks a dedicated source for API versioning, event evolution and zero/low-downtime schema migration. This is important to the Stage 1 contract and must be challenged directly.

### 11.4 Observability

`Release It!` provides production transparency/diagnostic concerns, but modern logs/metrics/traces, observability-driven development and cost/proportionality need current verification.

### 11.5 Performance and concurrency

Architecture and production books address performance characteristics and failure modes, but the corpus lacks a systematic modern source for profiling, concurrency correctness and performance experimentation across software classes.

### 11.6 Test effectiveness beyond test presence

Feathers and Google provide substantial test guidance, but Stage 1 explicitly requires evidence that tests can detect the claimed regression. Stage 4 should investigate mutation testing, test selection/adequacy and empirical test-effectiveness evidence.

### 11.7 Configuration, dependency and software supply-chain security

Google covers dependencies and build/tooling at scale, but current lockfile/SBOM/provenance/supply-chain practices require current authoritative research rather than book-only conclusions.

### 11.8 High-assurance and specialist domains

The five books are not sufficient authority for safety-critical, hard real-time, cryptographic, embedded, regulated or other high-assurance engineering. Those contexts remain specialist until later evidence justifies a core rule or Extension Pack.

### 11.9 AI-generated software changes

The corpus predates or only lightly touches current agentic coding practice. Stage 4 must investigate whether AI-generated changes require materially different review/evaluation behaviour or whether existing engineering controls remain sufficient when correctly applied.

### 11.10 Engineering economics and change sizing

Google and the architecture book provide trade-off/cost framing, but Stage 4 should investigate practical evidence for batch size, review size, technical-debt economics and when a broader refactor is justified.

## 12. Source-access register

The access state records what is available **now**, not what has been read. Stage 3 requires meaningful direct examination of all five books for their intended contributions.

| Book | Edition/year | Origin | Public/internal source identifier | Access status | Intended contribution | Material actually examined in Stage 2 | Reading limitation / Stage 3 need |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Software Requirements | 3rd / 2013 | Selected | Microsoft Press product page, ISBN 978-0-7356-7962-7 | **secondary material only** | requirements, acceptance, validation, change/traceability, non-functional/data requirements | publisher description and detailed table of contents only | Obtain full text or sufficiently broad lawful excerpts before Stage 3 can complete this book |
| Fundamentals of Software Architecture | 2nd / 2025 | Selected | O'Reilly, ISBN 9781098175504 | **relevant excerpts available** | architecture characteristics, modularity, trade-offs, risk, ADRs, architecture/implementation boundary | publisher overview/TOC and Chapter 2 preview used for selection | Current preview is not sufficient for corpus-wide Stage 3 extraction; full text or broader lawful access needed |
| Working Effectively with Legacy Code | 1st / 2004 | Selected | Pearson ISBN 9780131177055; O'Reilly catalogue | **relevant excerpts available** | brownfield comprehension, feedback, seams, dependency breaking, safe change/testing | publisher TOC, official sample material and introduction preview used for selection | Excerpts establish fit but not complete intended contribution; full text or sufficiently broad lawful access needed |
| Software Engineering at Google | 2020 | Selected | Google/Abseil free HTML edition; O'Reilly 2020 | **full text available** | engineering over time/scale, review, testing, dependencies, deprecation, large changes, CI/CD, tooling | publisher/Google description and TOC used for selection; full text availability verified | Stage 3 must still perform direct traceable reading; availability is not extraction |
| Release It! Second Edition | 2018 | Selected | Pragmatic Bookshelf ISBN 9781680502398 | **relevant excerpts available** | failure modes, stability, resilience, production design, deployment/versioning, systemic diagnosis | publisher TOC/overview plus official extracts such as Stability Antipatterns and security excerpt used for selection | Several extracts are available, but full intended contribution requires full text or sufficiently broad lawful excerpts for Stage 3 |

### Access conclusion

Stage 2 may complete because access needs are explicitly recorded.

**Stage 3 is currently blocked from completion for four books unless lawful source access is expanded.** `Software Engineering at Google` is the only selected book with verified complete public text available at this stage.

No inaccessible book has been treated as already examined.

## 13. Supplied-book substitution decision log

| Decision | Status |
| --- | --- |
| User-provided books supplied | None |
| Protected supplied-book members | None |
| Substitution proposed | No |
| Permission required | No |
| Pending selection decision | None |

The corpus therefore satisfies the five-book selection rule without requiring an interruption for approval.

## 14. Corpus revision record

**Revision:** `software-engineering-corpus-r1`  
**Effective date:** 12 September 2026

Selected members:

1. Karl Wiegers & Joy Beatty — *Software Requirements, 3rd Edition* (2013)
2. Mark Richards & Neal Ford — *Fundamentals of Software Architecture, 2nd Edition* (2025)
3. Michael Feathers — *Working Effectively with Legacy Code* (2004)
4. Titus Winters, Tom Manshreck & Hyrum Wright — *Software Engineering at Google* (2020)
5. Michael T. Nygard — *Release It! Second Edition* (2018)

Any later replacement must:

1. create a new corpus revision;
2. explain the coverage gain and loss;
3. preserve the current rationale and rejected alternatives;
4. identify any Stage 3/4 extraction or design work invalidated by the change;
5. follow the supplied-book permission rule if user-provided material is introduced later.

## 15. Stage 3 reading priorities

Once access is available, Stage 3 should not simply read each book cover-to-cover without a research plan. The intended extraction emphasis is:

### Software Requirements

Prioritise:

- requirement quality and classification;
- elicitation/clarification applicable to engineering;
- non-functional requirements;
- data requirements;
- validation and acceptance;
- enhancement/replacement work;
- requirements change, traceability and risk.

### Fundamentals of Software Architecture

Prioritise:

- architecture versus design;
- architectural characteristics;
- modularity/coupling/cohesion;
- identifying architecturally significant change;
- trade-off analysis;
- style selection and risks rather than style memorisation;
- ADRs;
- risk analysis;
- architecture/implementation and architecture/data intersections.

### Working Effectively with Legacy Code

Prioritise:

- mechanics of change;
- feedback and characterization safety;
- sensing/separation and seams;
- deciding what to test around a change;
- dependency breaking;
- understanding unfamiliar/unstructured code;
- adding features without broad rewrites;
- evidence that behaviour was not broken.

### Software Engineering at Google

Prioritise:

- time/change/scale and trade-off framing;
- code review;
- testing strategy and test maintainability;
- deprecation;
- dependency management;
- static analysis;
- large-scale change;
- continuous integration/delivery;
- build philosophy and sustainable tooling;
- explicit Google-specific assumptions that should not generalise.

### Release It!

Prioritise:

- stability and failure propagation;
- stability antipatterns and patterns;
- integration points;
- production visibility/transparency;
- deployment and version handling;
- systemic failures and postmortem reasoning;
- load/stress and resilience evidence;
- boundary between application engineering and production operations.

## 16. Decisions made

Stage 2 establishes the following decisions:

1. the foundational corpus contains exactly five books;
2. the corpus is intentionally complementary rather than five general overviews;
3. requirements/acceptance receives one dedicated slot because the engineering workflow must clarify change intent before implementation;
4. architecture receives one dedicated slot because architecture is explicitly inside the Stage 1 domain boundary;
5. brownfield safe change receives one dedicated slot because the project is brownfield-first;
6. sustainable codebase/process/tool practice receives one broad cross-cutting slot;
7. production reliability/releasability receives one dedicated slot so code-centric correctness is not mistaken for production quality;
8. testing is covered across Feathers and Google rather than consuming a sixth unavailable slot;
9. specialist security, observability, API/schema evolution, debugging depth, supply chain and AI-generated-change evidence remain explicit Stage 4 responsibilities;
10. no selected book determines a future skill name or skill count;
11. no book claim is accepted merely because the book is in the corpus;
12. corpus selection is complete even though Stage 3 source acquisition remains incomplete.

## 17. Remains provisional

This stage deliberately does **not** decide:

- which claims from the books are correct or transferable;
- the final software-engineering capability model;
- the exact workflow or artefacts;
- the software-change taxonomy;
- final verification/risk/approval policy;
- skill count or names;
- command decomposition;
- Extension Packs;
- implementation providers or tooling;
- benchmark cases or thresholds.

Those require direct extraction and broader challenge research.

## 18. Stage 2 exit-criteria verification

| Required output / gate | Evidence in this log | Status |
| --- | --- | --- |
| Software-engineering knowledge-coverage map | Section 4 | Complete |
| Bounded authoritative reconnaissance | Section 3 | Complete |
| Broader candidate-book comparison | Section 5 | Complete |
| Exactly five selected books | Sections 6 and 14 | Complete — exactly five |
| Selected/rejected rationale | Sections 5, 6 and 10 | Complete |
| Material-overlap analysis | Section 9 | Complete |
| Remaining domain gaps | Section 11 | Complete |
| Source-access register | Section 12 | Complete |
| Supplied-book substitution decision log | Section 13 | Complete; no supplied books |
| Corpus revision identifier | `software-engineering-corpus-r1` | Complete |
| Required permission decisions resolved | No substitutions required | Complete |
| Stage 3 access needs explicit | Section 12 | Complete |

### Exit decision

**Stage 2 passes.**

Exactly five complementary foundational books are selected, no supplied-book permission decision is pending, overlap and residual gaps are explicit, and source-access needs are recorded.

The next stage may begin only as **Stage 3 — Five: Extract and Reconcile the Five-Book Corpus**. Stage 3 must not claim completion until all five selected books have been meaningfully and directly examined for their intended contributions. Current source access is insufficient for four of the five books, so that limitation must be resolved rather than replaced with title-level summaries or model memory.
