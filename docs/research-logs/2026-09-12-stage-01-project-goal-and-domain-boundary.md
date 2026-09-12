# Stage 1 — Project Goal and Domain Boundary

**Project:** `software-engineering-skills`  
**Bootstrap stage:** 1 — Define Project Goal and Domain Boundary  
**Status:** Complete  
**Date:** 12 September 2026

## 1. Stage purpose

This stage defines what `software-engineering-skills` owns before foundational-book selection, broader professional research, AI/tool research, workflow design or skill decomposition begins.

The project is a Production Skills repository for reusable expertise that helps an agent make **safe, maintainable and evidence-backed software changes in an existing or new software system**.

The core boundary is:

> `software-engineering-skills` owns reusable engineering judgement for understanding software systems, choosing responsible change scope, making architecture and implementation decisions, preserving contracts and existing behaviour, verifying changes according to risk, diagnosing failures, and carrying work to releasable evidence.

It does not own product strategy, interaction design, specialist security assurance, shared platform operations, integrated-product QA, model research, game-design semantics, technical-writing production or Pactwright lifecycle governance.

The project is **brownfield-first and greenfield-capable**. Existing systems make engineering judgement observable because changes must respect code, interfaces, data, tests, runtime assumptions and operational constraints that already exist. Greenfield work remains in scope, but it must establish equivalent contracts and quality constraints rather than treating an empty repository as permission for unconstrained generation.

## 2. Canonical inputs reviewed

This charter is grounded in the current repository bootstrap and Production Skills family contracts:

- [`2026-09-07-software-engineering-skills-new-project-bootstrap-process.md`](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md)
- [`production-skills/docs/specs/01-production-skills-family-system.md`](https://github.com/sb-dev/production-skills/blob/main/docs/specs/01-production-skills-family-system.md)
- [`production-skills/docs/specs/02-production-skills-project-contract.md`](https://github.com/sb-dev/production-skills/blob/main/docs/specs/02-production-skills-project-contract.md)
- [`production-skills/docs/specs/04-cross-domain-orchestration-and-integration.md`](https://github.com/sb-dev/production-skills/blob/main/docs/specs/04-cross-domain-orchestration-and-integration.md)
- [`production-skills/docs/research-logs/2026-09-07-production-skills-and-extension-packs-project-family-brief.md`](https://github.com/sb-dev/production-skills/blob/main/docs/research-logs/2026-09-07-production-skills-and-extension-packs-project-family-brief.md)

Bounded professional-practice anchors were also checked only far enough to test the initial boundary:

- IEEE Computer Society, [SWEBOK Guide V4.0 topics](https://www.computer.org/education/bodies-of-knowledge/software-engineering/topics)
- DORA, [Continuous delivery](https://dora.dev/capabilities/continuous-delivery/)
- NIST, [Secure Software Development Framework](https://csrc.nist.gov/projects/ssdf)
- Google, [Engineering Practices — Code Review](https://google.github.io/eng-practices/review/)
- ISO, [ISO/IEC 25010:2023 product quality model](https://www.iso.org/standard/78176.html)

This is not Stage 2 source selection or Stage 4 challenge research. No foundational corpus is selected here and no later skill architecture is implied by these anchors.

## 3. Bounded professional-practice observations

The reconnaissance supports a broad but coherent engineering boundary.

### 3.1 Software engineering is larger than coding

SWEBOK V4 treats requirements, architecture, design, construction, testing, maintenance, quality and engineering operations as related software-engineering knowledge areas. That makes an implementation-only repository too narrow.

The project should therefore cover the judgement that connects an intended change to architecture, code, verification, maintenance and release evidence rather than treating generated source code as the end product.

### 3.2 Maintenance is a primary engineering mode

SWEBOK V4 explicitly treats software maintenance as a major knowledge area and recognises corrective, preventive, adaptive, additive and perfective maintenance, with emergency maintenance as a further category.

This supports a brownfield-first posture. Defect repair, dependency/runtime adaptation, controlled feature addition, maintainability improvement and emergency correction are first-class production work rather than secondary examples after greenfield generation.

### 3.3 Deployability is an engineering quality without implying continuous production operation

DORA defines continuous delivery around keeping software in a state where changes can be released quickly, safely and on demand. It distinguishes continuous delivery from continuous deployment.

The project should therefore own **releasability and deployment-readiness evidence** where applicable, while leaving actual production operation, organisation-wide deployment platforms and SRE ownership outside the default boundary.

### 3.4 Security must enter the engineering loop early

NIST SSDF organises secure development around preparing, protecting, producing well-secured software and responding to vulnerabilities. Security is therefore not adequately represented by a final scanner invocation.

The core engineering discipline must include security-sensitive requirements, design and implementation decisions, dependency/supply-chain awareness and vulnerability repair. Specialist security engineering still owns deeper assurance where threat or regulatory risk requires it.

### 3.5 Code quality is multidimensional

Google's engineering practices ask reviewers to consider design, functionality, complexity, tests, naming, comments, style and documentation, with the broader goal of improving code health over time.

Passing tests alone must not be treated as sufficient proof of engineering quality.

### 3.6 Quality requires explicit dimensions rather than one score

ISO/IEC 25010:2023 provides a product-quality model intended to support requirements, design objectives, testing objectives, acceptance criteria and quality evaluation across the product lifecycle.

The project should use explicit quality dimensions and context-specific evidence rather than inventing a universal software quality score.

## 4. One-page domain charter

### Mission

Make professional software-engineering judgement installable for AI agents so they can change software responsibly rather than merely emit code.

### The project owns

```text
change understanding
→ repository/system inspection
→ requirements and contract clarification
→ impact and risk analysis
→ architecture/design at the necessary depth
→ smallest responsible change selection
→ implementation and refactoring
→ change-specific tests and verification
→ security/reliability/performance checks when relevant
→ code review and compatibility review
→ root-cause diagnosis
→ targeted repair
→ releasability / handoff evidence
```

### The project does not own

```text
product strategy and prioritisation
interaction or visual design
specialist security assurance programmes
shared cloud/platform engineering
production SRE operations
independent integrated-product QA ownership
analytics/data-platform production
model training and ML-science quality
video-game design semantics
open-ended research production
editorial / documentation-product production
Pactwright lifecycle governance
one consuming project's architecture knowledge
```

### Default operating posture

- inspect before editing;
- prefer evidence from the actual system over assumptions;
- make the smallest coherent change that solves the problem;
- preserve existing behaviour and public contracts unless change is authorised;
- make architecture proportional to uncertainty and consequence;
- verify cheaply first, then escalate according to risk;
- treat tests as evidence only when they can detect the claimed regression;
- integrate security, reliability and deployability concerns at the relevant stage;
- diagnose the owning layer before repairing a failure;
- preserve accepted work outside the failing layer;
- surface decisions that are destructive, irreversible, externally breaking or materially expensive;
- keep reusable engineering expertise separate from repository-specific facts.

### Boundary test

A reusable capability belongs here when it answers a question such as:

> Given an intended software change and the evidence available in this system, what is the safest, smallest and most maintainable engineering action, and what evidence is sufficient to accept it?

If the capability instead decides what product to build, what interaction users should have, how a shared platform should be operated, or how a consuming project should be governed, it belongs elsewhere.

## 5. Intended users

Primary users are people or agents responsible for changing software systems, including:

- software engineers working in existing codebases;
- senior engineers and technical leads making local architecture and compatibility decisions;
- maintainers of libraries, services, applications and developer tooling;
- AI coding agents that require disciplined repository inspection, change scoping and verification;
- small teams that need professional engineering behaviour without a large specialist organisation;
- multidisciplinary projects that need a reusable implementation-engineering capability alongside other Production Skills families;
- consuming-project orchestrators that need software-engineering execution while retaining project governance themselves.

The repository should remain useful to less experienced engineers, but it should encode professional production behaviour rather than tutorial sequences or language-learning curricula.

## 6. Software classes in scope

The core should be technology-agnostic but system-aware. Its reusable judgement should apply across common software forms including:

- backend services and APIs;
- web applications and frontend implementation;
- mobile and desktop applications;
- libraries, SDKs and reusable packages;
- command-line tools and developer tooling;
- integration and event-driven systems;
- data-persistence and schema-backed application components;
- batch and background processing;
- build, packaging and repository automation owned by the application or library;
- distributed software where general architecture, contracts, reliability and performance are engineering concerns.

This does **not** mean the core can claim specialist adequacy for every software context.

The following contexts should initially consume the core discipline plus specialised evidence, Extension Packs or adjacent expertise:

- safety-critical and high-assurance systems;
- hard real-time and embedded systems;
- operating-system/kernel and low-level systems programming;
- cryptographic implementation;
- high-performance scientific/HPC systems;
- large-scale data platforms;
- ML training systems and model-development pipelines;
- game-specific runtime and gameplay systems;
- highly regulated software where formal certification or specialist assurance is required.

The general engineering loop may still apply, but domain-specific rules must not be invented by the core.

## 7. Greenfield and brownfield weighting

The project is **brownfield-first, not brownfield-only**.

Brownfield work should be the primary proving ground because it forces the agent to demonstrate:

```text
program comprehension
impact analysis
contract preservation
change isolation
regression reasoning
migration safety
convention discovery
existing-test interpretation
root-cause diagnosis
compatibility judgement
```

Greenfield work remains important for:

- establishing clean contracts;
- making architecture decisions before inertia forms;
- choosing interfaces and data models;
- establishing testability and observability;
- creating a maintainable initial vertical.

However, greenfield generation must not become a blank-slate architecture exercise. Even a new system has external requirements, platform constraints, dependencies, future maintenance needs and consuming-project conventions.

No numerical brownfield/greenfield ratio is fixed at this stage. Later examples and benchmarks should prove both, with stronger coverage of change to existing systems.

## 8. Architecture responsibility

Architecture is inside the software-engineering boundary when it concerns the structure and qualities of software being changed.

The project owns reusable judgement about:

- system/module boundaries;
- dependency direction;
- public and internal interfaces;
- data ownership and persistence boundaries;
- synchronous/asynchronous interaction choices;
- failure and concurrency boundaries;
- compatibility and evolution strategy;
- deployment-relevant software topology;
- quality-attribute trade-offs;
- architectural impact of a proposed change;
- whether a local change is sufficient or a structural change is required;
- recording material architecture decisions and rationale.

The project should **design only as far as the uncertainty and consequence require**.

It must not turn every code change into a system redesign, nor own enterprise architecture, organisation design, portfolio architecture or product roadmap decisions.

A key architecture question is therefore:

```text
Can the required behaviour be added safely inside existing contracts?
YES → prefer the local coherent change.
NO  → identify the smallest architectural boundary that must change.
```

## 9. Owned software outcomes

A mature `software-engineering-skills` installation should be able to help produce or direct the following outcomes:

1. understand an unfamiliar repository well enough to identify the relevant architecture, conventions, contracts, tests and execution path before editing;
2. turn a defect, requirement or change intent into explicit engineering acceptance conditions;
3. identify affected components, interfaces, data, tests, configuration and operational assumptions;
4. distinguish local implementation work from changes requiring architecture or contract decisions;
5. choose the smallest responsible change and reject unrelated cleanup unless it is necessary for correctness or maintainability;
6. implement new behaviour while preserving unaffected behaviour;
7. evolve APIs, schemas, events and configuration with explicit compatibility and migration reasoning;
8. refactor without silently changing behaviour when behaviour preservation is the goal;
9. repair defects from reproducible evidence and root-cause analysis rather than symptom-driven rewriting;
10. design and maintain tests that demonstrate the behaviour or regression they claim to protect;
11. select verification that is proportional to the change and escalate from cheap checks to expensive checks according to risk;
12. review design, complexity, maintainability, security, performance, reliability and compatibility separately from functional correctness;
13. improve or preserve deployability and produce release-readiness evidence where the software is releasable/deployable;
14. produce enough change rationale, migration information and handoff evidence for another engineer or agent to understand what changed and why;
15. stop and request authority when a change would intentionally break an external contract, destroy data, weaken a material control or cross another high-consequence boundary.

## 10. First-class maintenance work

Maintenance is not a fallback mode. The project should treat the following as first-class software-engineering work.

### Corrective

Repair defects and regressions from reproducible evidence, with regression protection where practical.

### Preventive

Reduce credible future failure or maintenance risk when evidence justifies the work, without using prevention as a licence for speculative cleanup.

### Adaptive

Change software because an environment, dependency, protocol, platform, regulation or external system has changed.

### Additive

Add new capability to an existing system while respecting current contracts and architecture.

### Perfective

Improve performance, maintainability, usability of developer-facing surfaces or other software qualities without disguising an unrelated feature change.

### Emergency

Restore acceptable behaviour under urgent conditions using the smallest safe intervention, followed by explicit debt, follow-up and regression evidence when normal engineering depth had to be deferred.

Additional recurring maintenance concerns include:

- dependency upgrades;
- deprecations;
- data/schema migrations;
- API and event evolution;
- security vulnerability response;
- performance regressions;
- reliability defects;
- configuration changes;
- test-suite repair;
- technical-debt reduction with an evidenced payoff;
- documentation changes required to keep software contracts usable.

## 11. Release responsibility

Software Engineering owns getting a change to **credible releasability**, not automatically operating production.

Owned responsibilities may include:

- version and compatibility impact;
- build/package integrity;
- automated verification status;
- migration requirements;
- rollout and rollback constraints that arise from the software change;
- release notes or changelog information needed to explain technical impact;
- smoke-test requirements;
- configuration compatibility;
- dependency and artefact integrity;
- evidence that the software remains deployable or distributable through its intended path.

Actual release/deployment execution may be performed by Software Engineering when the consuming project explicitly delegates that operation and the execution is within authorised policy.

The default boundary excludes ownership of:

- organisation-wide deployment platforms;
- cloud/cluster lifecycle management;
- production on-call operations;
- SLO policy and service-management governance;
- incident command;
- change-management governance imposed by an organisation;
- app-store, certification or regulatory approval processes owned elsewhere.

This distinction deliberately aligns with continuous delivery rather than assuming continuous deployment.

## 12. Adjacent-domain boundary map

Cross-domain work should use explicit handoffs rather than duplication.

| Adjacent discipline | Adjacent discipline owns | Software Engineering owns | Typical handoff back / escalation |
| --- | --- | --- | --- |
| Product management | problem selection, product outcomes, priority, roadmap, commercial/product trade-offs | feasibility evidence, engineering constraints, implementation acceptance conditions, technical impact | requirement ambiguity, cost/risk evidence, incompatible product assumptions |
| UI/UX design | user research, interaction model, information architecture, visual/interaction design, experience-level accessibility decisions | faithful implementation, frontend architecture, state/data integration, performance, implementation-level accessibility conformance | technical constraints, behaviour mismatches, implementation evidence affecting design |
| Security engineering | specialist threat analysis, security architecture/assurance, penetration/red-team work, policy and high-assurance controls | secure implementation, threat-aware engineering, dependency/supply-chain hygiene, change-level security tests, vulnerability repair | high-risk threat decisions, cryptographic/security architecture, unresolved control failure |
| Platform engineering | shared developer platform, infrastructure products, environment/cluster/cloud platform architecture | application-owned build/config/deployment integration, runtime requirements, software packaging, app-level infrastructure contracts | shared-platform capability gap, platform policy change, environment-level failure |
| DevOps / SRE | production reliability programme, SLO/SLI governance, incident response/command, production operations, shared deployment practice | observability hooks, graceful failure behaviour, release readiness, software-level reliability fixes, runbook inputs | production incident evidence, capacity/SLO conflict, operational policy decision |
| QA / testing specialists | independent system/integration/exploratory validation and broader product-quality assurance | developer-owned test strategy for the change, testability, unit/component/integration regression evidence, failure diagnosis and repair | independent acceptance failure, cross-system defect, exploratory evidence needing engineering correction |
| Data engineering | data pipelines/platforms, warehouse/lake architecture, analytical data quality/lineage | application persistence, transactional schemas, application migrations, data contracts consumed/produced by the software | pipeline/analytics ownership, large-scale data-platform concerns, domain data-quality policy |
| ML engineering | model lifecycle, training/evaluation, feature/model quality, drift/model monitoring | software around model integration, APIs, serving/application architecture, reliability/security/performance of software components | model-quality or training-data problem, model-specific evaluation, ML lifecycle change |
| Game development | gameplay intent, rules, game systems, player-facing runtime semantics and gameplay acceptance | general implementation architecture, maintainability, software performance, infrastructure, generic networking/persistence/tooling | gameplay-rule ambiguity, game-feel/tuning issue, game-design acceptance decision |
| Deep research | systematic evidence discovery, source evaluation and research synthesis | engineering interpretation and implementation decisions based on accepted evidence | unresolved external evidence question, technology landscape research beyond bounded engineering investigation |
| Technical writing | documentation information architecture, editorial quality, audience communication, publication | code/API documentation accuracy, ADR/change rationale, developer-facing technical notes required for correct use and maintenance | documentation-product rewrite, audience/editorial strategy, publication workflow |
| Pactwright lifecycle governance | Contracts, lifecycle authority, Project Graph, evidence governance, delivery orchestration and project-level approvals | software-engineering execution and engineering evidence for assigned responsibilities | lifecycle decision, scope/authority conflict, Contract change, project-governance decision |

The boundary is intentionally compositional. A software engineer may perform adjacent work in a small team, but that does not make the adjacent discipline part of the reusable Software Engineering Skills domain.

## 13. Quality dimensions

Software quality must remain multidimensional. Evidence for one dimension must not silently stand in for another.

### 13.1 Functional correctness

- required behaviour works;
- invalid behaviour is prevented or handled;
- relevant edge cases are covered;
- the implementation matches explicit acceptance conditions.

### 13.2 Compatibility and contract integrity

- public APIs, events, schemas, protocols and configuration remain compatible unless an authorised break is intentional;
- migrations and deprecations are explicit;
- downstream consumers are considered where evidence exists.

### 13.3 Maintainability and changeability

- the change fits the local architecture and conventions;
- complexity is proportionate to the problem;
- future engineers can understand and modify the code;
- abstractions have demonstrated purpose rather than speculative value.

### 13.4 Simplicity and scope discipline

- the solution is no broader than necessary;
- unrelated cleanup is separated;
- duplicate or unnecessary machinery is avoided;
- the change can be reviewed and reasoned about at an appropriate size.

### 13.5 Testability and verification quality

- relevant behaviour is observable and testable;
- tests can fail for the defect or regression they claim to protect;
- verification covers the changed risk rather than only increasing counts;
- expensive checks are used when cheaper evidence is insufficient.

### 13.6 Security

- trust boundaries, validation, authorisation, dependency and secret-handling concerns are addressed where relevant;
- new vulnerabilities are not knowingly introduced;
- security-sensitive changes receive stronger review and evidence.

### 13.7 Reliability and resilience

- failure modes are understood;
- retries/timeouts/idempotency/recovery are appropriate when relevant;
- partial failure does not silently corrupt state;
- regression risk to availability or correctness is considered.

### 13.8 Performance and resource efficiency

- material latency, throughput, memory, storage, CPU and concurrency constraints are preserved or intentionally changed;
- optimisation follows evidence rather than guesswork;
- representative measurements are used for performance claims.

### 13.9 Data integrity and migration safety

- persistent-state changes preserve required invariants;
- migration direction, compatibility and rollback/recovery are considered;
- destructive transformations are explicit and authorised.

### 13.10 Deployability and releasability

- the change can pass the intended build/package/release path;
- required configuration and migrations are known;
- release-impact evidence is available;
- software is not called ready merely because it runs locally.

### 13.11 Observability and operability

- changed runtime behaviour can be diagnosed at the level appropriate to the system;
- logs, metrics, traces or diagnostics are added when they materially reduce operational uncertainty;
- observability work remains proportionate rather than automatic instrumentation sprawl.

### 13.12 Documentation and rationale integrity

- public or developer-facing contracts affected by the change are updated;
- material architecture and compatibility decisions retain enough rationale for later maintenance;
- documentation does not claim behaviour that the software does not provide.

No universal numeric quality score is defined at this stage.

## 14. Human approval and commitment candidates

Stage 7 will define the full verification, risk and commitment strategy. Stage 1 identifies the change classes that should normally require explicit authority or a pre-authorised policy before execution.

### 14.1 External contract break

Require explicit authority before intentionally breaking a public API, event schema, protocol, stored-data contract, supported configuration or compatibility promise.

### 14.2 Destructive or hard-to-reverse data change

Require explicit authority for irreversible deletion, lossy migration or transformations where rollback/recovery is materially uncertain.

### 14.3 Security-control or trust-boundary change

Escalate material changes to authentication, authorisation, cryptography, secret handling, tenant isolation, sandboxing or other high-consequence controls.

### 14.4 Material architecture commitment

Escalate choices with substantial switching cost, broad blast radius or long-term ecosystem lock-in when local evidence cannot establish a clearly safe default.

### 14.5 Production release or rollout outside standing policy

A deployment may be automated under an explicit pre-authorised delivery policy. Deployment outside that authority, or a rollout carrying unusual risk, requires approval from the owning project/operations authority.

### 14.6 Intentional quality compromise

Require explicit acceptance before shipping with known failing tests, waived security findings, unresolved compatibility breaks, reduced resilience or other material quality debt.

### 14.7 Broad change beyond the requested scope

If the smallest responsible solution expands into a rewrite, multi-system migration or large refactor, surface the evidence and obtain authority rather than silently increasing scope.

### 14.8 Requirement ambiguity with externally visible consequences

Software Engineering may clarify and propose interpretations, but it must not invent product policy when plausible interpretations create materially different user or business behaviour.

These are commitment candidates, not a universal mandatory approval workflow. Mature projects may encode pre-authorised policies that allow safe automation inside known bounds.

## 15. Reusable engineering knowledge versus project-specific context

The core project must teach agents how to discover and use project context without absorbing one project's facts into reusable skills.

### Reusable knowledge belongs in `software-engineering-skills`

Examples:

- how to inspect an unfamiliar repository;
- how to identify architectural boundaries and contracts;
- how to perform impact analysis;
- how to distinguish local change from architectural change;
- how to preserve compatibility;
- how to choose focused versus broad verification;
- how to design regression tests;
- how to diagnose failures and isolate root cause;
- how to refactor safely;
- how to evolve APIs and schemas;
- how to reason about concurrency, performance, reliability and security risks;
- how to review a change for code health;
- how to produce release-readiness evidence.

### Project-specific knowledge stays with the consuming project

Examples:

- exact repository architecture and module map;
- domain/business rules;
- naming conventions and local style;
- supported language/framework versions;
- exact build/test/lint commands;
- service topology and ownership;
- environment names and deployment targets;
- production SLOs and alert thresholds;
- database schemas and migration history;
- API consumers and compatibility promises;
- accepted architecture decisions;
- dependency policies;
- release calendars;
- credentials and secret locations;
- known incidents and project-specific workarounds.

A Production Skill may read and apply these facts during execution. It must not generalise them into reusable doctrine without independent evidence.

## 16. Non-goals

`software-engineering-skills` is not intended to become:

- a programming-language tutorial collection;
- a framework encyclopaedia;
- a repository of copy-paste code recipes without engineering context;
- a universal coding-agent runtime;
- a replacement for compilers, typecheckers, linters, test runners, profilers, scanners or build systems;
- a package-manager abstraction layer;
- an enterprise architecture method;
- a product-management or requirements-prioritisation system;
- a UI/UX design repository;
- a specialist cybersecurity assurance product;
- a cloud/platform operations framework;
- an SRE operating model;
- an independent QA organisation encoded as skills;
- a data-engineering or ML-engineering replacement;
- a game-design/game-development repository;
- a research-production system;
- a technical-writing production repository;
- a Pactwright lifecycle engine;
- a store of consuming-project architecture knowledge;
- a licence for agents to perform destructive or externally breaking changes without authority.

It should direct deterministic and specialist tools rather than reproduce them.

## 17. Open boundary questions

The initial boundary is sufficient to proceed, but the following questions remain intentionally open for later evidence:

1. Which software contexts deserve core treatment versus Extension Packs once the five-book corpus and broader research expose real coverage gaps?
2. How far should core requirements engineering go before a handoff to Product Management or consuming-project specification authority becomes mandatory?
3. Which architecture decisions are common enough to encode as reusable commands versus remaining part of a broader engineering skill?
4. How should specialist security review be triggered from change risk without turning the core into a security-engineering substitute?
5. Where should application-owned infrastructure-as-code sit when a change spans software and platform concerns?
6. How should independent QA evidence interact with developer-owned verification in the later evaluation architecture?
7. What minimum release-readiness evidence is portable across libraries, services, mobile apps, desktop apps and other software classes?
8. Which high-assurance domains require explicit exclusion from generic automation unless a specialised pack is active?
9. How should AI-generated changes be reviewed differently, if at all, once empirical evidence is collected?
10. What forms of technical-debt work can be justified reliably enough to avoid speculative refactoring?

These questions belong to subsequent research. None blocks the Stage 1 boundary.

## 18. Decisions made

Stage 1 establishes the following initial decisions:

1. `software-engineering-skills` owns reusable engineering judgement from system understanding through releasable evidence.
2. The domain includes architecture as well as implementation, but architecture depth must be proportional to uncertainty and consequence.
3. The project is brownfield-first and greenfield-capable.
4. Maintenance is first-class, including corrective, preventive, adaptive, additive, perfective and emergency work.
5. Existing behaviour and contracts are production assets to preserve unless a change explicitly reopens them.
6. Release readiness is in scope; shared production operations and SRE ownership are not in scope by default.
7. Security, reliability, performance and deployability are integrated engineering concerns, with specialist handoffs where their depth exceeds general software engineering.
8. Change-level testing and verification are core Software Engineering responsibilities; independent integrated-product QA remains adjacent.
9. Product, UX, platform, data, ML, game-development, deep-research, technical-writing and Pactwright responsibilities remain distinct even when one person or agent performs multiple roles.
10. The project must keep reusable engineering practice separate from consuming-project facts and conventions.
11. High-consequence, destructive, externally breaking or materially scope-expanding changes require explicit authority or a pre-authorised policy.
12. Software quality will be represented by separate evidence dimensions, not one opaque score.

## 19. Remains provisional

This stage deliberately does **not** decide:

- the five-book foundational corpus;
- final knowledge-coverage dimensions;
- the exact software-change taxonomy;
- the final workflow and artefact model;
- verification ladder details;
- risk scoring or approval mechanics;
- the core skill count or skill names;
- command decomposition;
- language/framework/tool choices;
- AI coding providers or execution adapters;
- Extension Pack catalogue;
- progressive example levels;
- benchmark fixtures or evaluation thresholds;
- repository production scaffold.

Those decisions require later evidence and must not be inferred from this charter.

## 20. Stage 1 exit-criteria verification

The bootstrap requires the project to explain what it owns and why the responsibilities form a coherent reusable production discipline.

| Required output | Evidence in this log | Status |
| --- | --- | --- |
| Project mission | Sections 1, 4 and 18 | Complete |
| Owned outcomes | Sections 4, 8, 9, 10 and 11 | Complete |
| Non-goals | Sections 4 and 16 | Complete |
| Adjacent-domain map | Section 12 | Complete |
| Intended-user definition | Section 5 | Complete |
| Quality dimensions | Section 13 | Complete |
| Approval / commitment candidates | Section 14 | Complete |
| Reusable vs project-specific boundary | Section 15 | Complete |
| Open boundary questions | Section 17 | Complete |
| Greenfield/brownfield weighting | Section 7 | Complete |
| Architecture boundary | Section 8 | Complete |
| Release boundary | Section 11 | Complete |
| First-class maintenance forms | Section 10 | Complete |

**Stage 1 result:** complete. The project has a defensible initial domain boundary and can proceed to Stage 2 — Seed: map knowledge coverage and select exactly five complementary foundational books.

## 21. Handoff to Stage 2

Stage 2 should treat this boundary as its coverage frame rather than choosing books first and retrofitting the domain around them.

The knowledge-coverage map should at minimum test whether candidate sources collectively address:

```text
requirements / acceptance interpretation
architecture and design
construction and code quality
program comprehension / brownfield change
maintenance and evolution
refactoring and technical debt
testing and test quality
debugging and root-cause diagnosis
code review
API / schema / contract evolution
security-aware engineering
performance and concurrency
reliability and resilience
configuration and dependency management
continuous integration and releasability
observability / operability
engineering economics and change scope
human review / commitment boundaries
```

These are coverage questions, not book slots and not predetermined future skills.
