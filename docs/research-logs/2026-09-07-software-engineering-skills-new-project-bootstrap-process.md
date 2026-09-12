# Software Engineering Skills — New Project Bootstrap Process

**Status:** Bootstrap specification  
**Version:** 1.1  
**Date:** 7 September 2026  
**Updated:** 12 September 2026

## 1. Purpose

This process defines how `software-engineering-skills` moves from a project idea to a **specified, scaffolded, benchmarked, installable open-source Agent Skills repository**.

The project must help AI agents perform real software engineering work rather than generate isolated code snippets.

The target production loop is provisionally:

```text
change intent / defect / requirement
→ inspect the existing system
→ identify contracts, constraints and affected behaviour
→ choose the smallest responsible change
→ design only as far as the uncertainty requires
→ implement
→ verify cheaply first
→ escalate verification according to risk
→ review quality and compatibility
→ diagnose failures
→ repair the smallest sufficient scope
→ produce release / handoff evidence
```

This is a hypothesis to validate through domain research, not a mandatory workflow imported from another Production Skills project.

The project is complete only when its skills can be installed into an unrelated software repository and used to perform realistic engineering changes while preserving existing behaviour and producing credible verification evidence.

---

## 2. Governing Sources

This bootstrap is governed by:

- `production-skills/docs/bootstrap/README.md`;
- `production-skills/docs/bootstrap/new-project-process.md`;
- `production-skills/docs/bootstrap/domain-research-process.md`;
- `production-skills/docs/bootstrap/extension-pack-process.md`;
- `production-skills/docs/bootstrap/shared-abstraction-process.md`;
- the current Production Skills family specifications;
- the current mature Video, Narrative and Music Production Skills repositories;
- the UI/UX Design Skills bootstrap as a depth reference only.

Initial external research anchors include:

- IEEE Computer Society, **SWEBOK Guide V4.0** — https://www.computer.org/education/bodies-of-knowledge/software-engineering
- DORA, **Continuous Delivery** — https://dora.dev/capabilities/continuous-delivery/
- NIST SP 800-218, **Secure Software Development Framework (SSDF) v1.1** — https://csrc.nist.gov/pubs/sp/800/218/final
- Google Engineering Practices, **Code Review** — https://google.github.io/eng-practices/review/

These are research anchors, not substitutes for the five-book corpus and not predetermined architectural authorities. They are particularly useful during bounded reconnaissance and the later challenge stage.

### Research foundation

The bootstrap follows **Seed → Five → Challenge**:

```text
domain boundary
→ bounded reconnaissance + knowledge-coverage map
→ select exactly five complementary foundational books
→ directly examine, extract and reconcile the five-book corpus
→ challenge claims and extend coverage through broader professional research
→ evidence-qualified software-engineering domain model
```

Books strengthen professional and empirical research; they do not replace it, define the skill count or limit the wider bibliography.

User-provided books remain in the foundational corpus unless the user explicitly approves their removal, demotion or replacement. Empty corpus slots may be filled without additional approval unless the user imposes a separate approval requirement.

Specification generation defines how the research will run. It does not count an unperformed bibliography, candidate list or proposed corpus as completed research.

---

## 3. Required Outputs

The bootstrap must produce:

1. a precise software-engineering domain boundary;
2. a software-engineering knowledge-coverage map;
3. an exactly five-book complementary foundational corpus with access and permission records;
4. direct per-book extraction, reconciliation and source-to-capability evidence;
5. broader professional research that challenges the corpus and fills gaps;
6. an evidence-qualified software-engineering domain model;
7. a software-change taxonomy and system-context model;
8. a domain-native workflow and artefact model;
9. a verification, risk and commitment strategy;
10. research into existing Agent Skills, engineering tools, CLIs, MCPs and provider capabilities;
11. an execution-layer decision and gap analysis;
12. a justified set of core Agent Skills;
13. decomposed commands where independent testing or reuse is valuable;
14. a first-class Software Engineering Extension Pack architecture;
15. an Extension Pack catalogue strategy based on complementary coverage;
16. explicit P1–P5 research and design stages for each selected Extension Pack;
17. a domain-native Extension Pack authoring capability;
18. five progressive example levels;
19. three complementary primary examples per level selected through capability coverage;
20. deterministic, behavioural and semantic evaluation;
21. benchmark and regression architecture;
22. six canonical specifications;
23. a public README following the proven Video Production Skills structure;
24. an open-source repository scaffold;
25. Agent Skills installation and selective-installation contracts;
26. local validation and a distinct clean external installation smoke test;
27. an implemented end-to-end core vertical;
28. implemented progressive examples and representative Extension Packs;
29. P6–P7 demonstration, differential evaluation and installation evidence for implemented packs;
30. optional Pactwright compatibility without runtime dependence;
31. maturity evidence and registry integration;
32. cross-domain abstraction candidates based only on repeated implementation evidence.

---

# 4. Domain Thesis to Validate

`software-engineering-skills` should own reusable engineering judgement about **how software changes are understood, designed, implemented, verified, reviewed and repaired**.

It should not become:

- a programming-language encyclopaedia;
- a package manager wrapper;
- a universal coding-agent runtime;
- a replacement for compilers, linters, test runners, profilers, scanners or build systems;
- a project-management workflow;
- a Pactwright lifecycle engine;
- a repository of project-specific architecture knowledge;
- a universal infrastructure or platform-operations system;
- a duplicate of strong existing specialist Agent Skills where composition is sufficient.

The project should direct deterministic and specialist tools rather than reimplement them.

A central hypothesis is:

> Software engineering production intelligence lies primarily in understanding the existing system, selecting the correct change scope, preserving contracts, choosing appropriate verification, diagnosing failures and improving the codebase without unnecessary change.

This thesis must be tested through the research and modelling stages before it becomes a core architecture rule.

---

# 5. Software-Native Governing Principles

Retain all Production Skills family principles and validate the following software-specific principles.

## Inspect before editing

A brownfield repository is not a blank canvas.

Before changing code, identify the relevant:

```text
architecture
modules
public interfaces
data contracts
runtime assumptions
tests
build system
configuration
observability
security constraints
existing conventions
```

Do not infer the system from filenames alone when executable or documentary evidence exists.

## Existing behaviour is a production asset

Passing behaviour, public contracts, accepted architecture decisions and operational assumptions must be preserved unless the change explicitly reopens them.

A successful implementation is not merely code that satisfies the new happy path.

## Smallest responsible change

Prefer the smallest coherent change that solves the actual problem and preserves unaffected behaviour.

Avoid speculative abstraction, unrelated cleanup and broad rewrites unless evidence shows that the local change would otherwise be unsafe or structurally wrong.

## Verification should escalate by cost and risk

A software-native cheap-first ladder may look like:

```text
repository inspection
→ syntax / formatting / static checks
→ compile / typecheck
→ focused unit tests
→ affected integration tests
→ broader regression tests
→ security / compatibility / performance checks when relevant
→ smoke / end-to-end validation
→ deployment or release evidence where required
```

The exact ladder remains project- and ecosystem-dependent.

Do not run the most expensive suite first when a cheaper check can expose the same defect.

## Tests are evidence, not decoration

Tests should demonstrate relevant behaviour and regressions rather than exist only to increase coverage metrics.

Evaluation must distinguish:

```text
test exists
```

from:

```text
test would fail for the defect it claims to protect against
```

## Correctness is not architecture quality

Keep separate evidence for:

```text
functional correctness
maintainability
simplicity
compatibility
security
performance
reliability
operability
test quality
```

A passing suite does not prove all of these dimensions.

## Root cause before repair

When a check fails, diagnose the owning layer before changing code.

Examples:

```text
wrong requirement interpretation → revise change intent
wrong interface contract         → revise contract/design
implementation bug               → revise implementation
incorrect test                    → revise test
integration mismatch             → revise boundary/configuration
performance regression           → profile and repair hotspot
security defect                  → repair threat/control failure
release/configuration failure    → repair delivery configuration
```

Do not regenerate or rewrite unaffected layers merely because a downstream check failed.

## Security is integrated, not a finishing pass

Security requirements, threat-sensitive design, dependency risk and vulnerability response should be considered at the relevant engineering stage rather than treated only as final scanning.

## Deployability is part of engineering quality where applicable

For software intended to be released or deployed, the project should preserve a deployable state and produce fast feedback on whether a change remains releasable.

The project must distinguish deployability from actually operating production systems.

## Research before architecture

The core skill architecture must follow the evidence-qualified software-engineering model. Do not use the selected books as a five-skill template, and do not let current coding-agent APIs define the discipline.

---

# 6. Bootstrap Flow

```text
PROJECT IDEA
    ↓
0. Confirm Bootstrap Workspace
    ↓
1. Define Project Goal and Domain Boundary
    ↓
2. Seed — Map Knowledge Coverage and Select Five Complementary Books
    ↓
3. Five — Extract and Reconcile the Five-Book Corpus
    ↓
4. Challenge — Broader Professional Software-Engineering Research
    ↓
5. Model Software Change Types, Contracts and System Context
    ↓
6. Map the Engineering Workflow and Artefacts
    ↓
7. Define Verification, Risk and Commitment Strategy
    ↓
8. Research Existing AI Skills, Tools and Providers
    ↓
9. Choose the Execution Layer
    ↓
10. Gap Analysis
    ↓
11. Design Core Skills and Commands
    ↓
12. Design Software Engineering Extension Packs
       ├─ Curate complementary catalogue coverage
       └─ For each selected pack: P1 → P2 → P3 → P4 → P5
    ↓
13. Design Five Progressive Example Levels
    ↓
14. Design Evals, Benchmarks and Regression Fixtures
    ↓
15. Generate Six Canonical Specifications
    ↓
16. Design the Public README
    ↓
17. Scaffold the Production Repository
    ↓
18. Implement the Core Vertical
    ↓
19. Implement Progressive Coverage and Extension Packs
       └─ For implemented packs: P6 → P7
    ↓
20. Validate Installation and Repository Integrity
    ↓
21. Optional Pactwright Integration
    ↓
22. Register and Promote Maturity
    ↓
23. Review Shared Abstraction Candidates
    ↓
MATURE SOFTWARE ENGINEERING SKILLS PROJECT
```

The repository already satisfies Stage 0 structurally. It currently exists as a minimal bootstrap workspace rather than a production scaffold.

## Stage execution contract

Every stage is a standalone task.

For each stage:

1. read the stage specification and required prior research logs;
2. perform the complete substantive work required by that stage;
3. persist detailed evidence and decisions under `docs/research-logs/`;
4. verify every exit criterion;
5. record blockers, unresolved evidence and required decisions explicitly;
6. commit the completed stage and its evidence;
7. only then begin a dependent stage.

Do not replace stage work with a summary. Do not merge stages merely to move faster. A bibliography is not evidence of book extraction. Silence is never approval for a required supplied-book substitution. Inadequate source access blocks extraction rather than justifying invented findings.

Existing adequate research may be reused after its persisted evidence, source coverage and applicability have been reviewed. Reuse should prevent unnecessary repetition, not weaken a stage gate.

---

# 7. Stage 0 — Confirm Bootstrap Workspace

## Purpose

Confirm that the minimal repository exists as the durable store for staged bootstrap research.

Target bootstrap shape:

```text
software-engineering-skills/
├── README.md
└── docs/
    └── research-logs/
        ├── README.md
        └── 2026-09-07-software-engineering-skills-new-project-bootstrap-process.md
```

Do not create production surfaces such as `skills/`, `examples/`, `benchmarks/`, `tests/`, Extension Pack directories or production CI merely because the repository exists.

## Exit criteria

The repository is writable, `docs/research-logs/` is the authoritative bootstrap record, and repository creation is not confused with `scaffolded` maturity.

---

# 8. Stage 1 — Define Project Goal and Domain Boundary

## Purpose

Define what software engineering production responsibility the repository owns before discussing individual skills or selecting foundational sources.

## Questions to resolve

```text
What software outcomes can the project produce?
What classes of software are in scope?
Does the domain include architecture as well as implementation?
Where does software engineering stop and product / UX / operations begin?
How are greenfield and brownfield work weighted?
What forms of maintenance are first-class?
What release responsibility is owned?
Which human approval points are important?
What quality dimensions define success?
What belongs in reusable engineering knowledge versus project-specific context?
```

Explicitly examine boundaries with:

```text
product management
UI/UX design
security engineering
platform engineering
DevOps / SRE
QA / testing specialists
data engineering
ML engineering
game development
deep research
technical writing
Pactwright lifecycle governance
```

## Inputs

- Production Skills family specifications;
- project-family research logs;
- the intended `software-engineering-skills` project idea;
- initial professional-practice anchors.

## Activities

- write a short domain charter;
- define owned outcomes and non-goals;
- identify intended users;
- identify cross-domain handoffs;
- identify important human decisions and irreversible/high-risk changes;
- define initial quality dimensions;
- separate reusable engineering practice from one repository's conventions.

## Expected outputs

```text
project mission
owned outcomes
non-goals
adjacent-domain map
intended-user definition
quality dimensions
approval / commitment candidates
open boundary questions
```

## Decisions made

A defensible initial boundary.

## Remains provisional

Exact workflow, core skill split, book corpus, pack dimensions and implementation tooling.

## Exit criteria

The project can explain in one page what it owns and why those responsibilities form a coherent reusable production discipline.

---

# 9. Stage 2 — Seed: Map Knowledge Coverage and Select Five Complementary Books

## Purpose

Establish the foundational software-engineering research corpus without mistaking popular books, supplied books or current AI capabilities for complete domain coverage.

Apply `production-skills/docs/bootstrap/domain-research-process.md` directly.

## Inputs

- completed Stage 1 domain charter;
- any user-provided book titles or files;
- existing persisted source-selection evidence;
- bounded authoritative reconnaissance sufficient to map the discipline.

## Bounded reconnaissance

Use strong professional and authoritative material only far enough to create a knowledge-coverage map and compare book contributions. Do not perform the full broader professional research of Stage 4 here.

The coverage map should test likely dimensions such as:

```text
requirements and acceptance
software design and architecture
construction and code quality
maintenance and evolution
brownfield understanding
refactoring and technical debt
testing and test quality
debugging and root-cause diagnosis
code review
API and contract evolution
data/schema evolution
security engineering
performance and concurrency
reliability and resilience
continuous delivery
observability and operability
configuration and dependency management
engineering economics and change scope
human review and commitment points
```

These are research dimensions, not mandatory book slots.

## Corpus selection

Select **exactly five distinct books** as the foundational corpus.

When zero to five books are supplied:

1. assess their combined contribution against the coverage map;
2. research a broader candidate pool rather than only enough books to fill empty slots;
3. retain supplied books by default;
4. fill empty slots with complementary sources;
5. choose the five-book combination for combined coverage, useful depth and contrasting perspective rather than individual popularity.

Assess candidates for:

```text
relevance to owned responsibilities
coverage and depth
practical contribution to engineering decisions
credibility and limitations
useful perspective or challenge
currency versus durable principles
source access
material overlap
remaining gaps
```

Useful overlap may provide depth or competing approaches. Do not invent overlap percentages or weighted authority scores without a defensible measurement method.

## Supplied-book permission rule

A user-provided book remains a corpus member unless the user explicitly authorises its removal, replacement or demotion.

Recommend substitution only when the expected improvement is material. Record:

```text
book proposed for removal
replacement
coverage / overlap problem
supporting evidence
expected gain
potential loss
alternatives
approval status
```

If approval is declined, retain the book and address remaining gaps through the other corpus slots and Stage 4 research. If approval is unanswered, selection is incomplete. If more than five books are supplied, propose the foundational five and request permission to exclude the others from foundational status.

## Source-access register

For every selected book record:

```text
title and author
edition / publication year
provided or selected origin
source identifier/location suitable for internal use
access status
intended contribution
material actually examined so far
reading limitations
```

Use access states:

```text
full text available
relevant excerpts available
secondary material only
unavailable
```

Selection and extraction are separate. Full-text availability does not mean a book has been examined.

## Expected outputs

```text
software-engineering knowledge-coverage map
candidate-book comparison
exactly five selected books
selected/rejected rationale
material-overlap analysis
remaining domain gaps
source-access register
supplied-book substitution decision log
corpus revision identifier
```

## Exit criteria

Exactly five complementary books are selected; all required substitution decisions are resolved; remaining gaps are explicit; and source-access needs are recorded. Missing access may remain an explicit acquisition need, but Stage 3 cannot complete until all five can be meaningfully examined for their intended contributions.

---

# 10. Stage 3 — Five: Extract and Reconcile the Five-Book Corpus

## Purpose

Directly examine the five selected books, extract traceable software-engineering knowledge and reconcile the corpus before broader research challenges it.

A title-level summary, model memory, publisher description, bibliography or secondary article is not completion evidence.

## Per-book extraction

For material findings record:

| Field | Required content |
|---|---|
| Source | Book, edition and identifiable chapter, section, page or other stable location actually examined |
| Problem and concept | Independently expressed principle, method or heuristic |
| Applicability | Context, assumptions, prerequisites and limitations |
| Production behaviour | Engineering decision, workflow step, artefact or responsibility affected |
| Evaluation | Metrics, evidence or evaluation criteria suggested |
| Failure and repair | Misuse, failure conditions and correction strategy |
| Relationships | Support, overlap, tension or contradiction with other sources |
| Disposition | Retain, merge, adapt, qualify, reject or research further |

Map useful findings as:

```text
source finding
→ provisional software-engineering capability
→ production responsibility
→ workflow / command implication
→ evaluation criterion
→ candidate benchmark case
```

Do not create one skill per book. A selected book may ultimately contribute little to the core; record that result rather than forcing it into the architecture.

## Reconciliation

Analyse:

```text
reinforcing findings
overlapping methods
competing assumptions
context-dependent alternatives
contradictions
important topics absent from the corpus
claims needing empirical or current-practice verification
```

Several books repeating a claim do not automatically provide independent corroboration.

## Publication boundary

Do not commit supplied books, private source locations, substantial copied text, reconstructed chapters or proprietary examples. Publish independently expressed synthesis and concise bibliographic/source-location references sufficient for traceability.

## Expected outputs

- per-book research findings;
- reading-coverage records;
- source-to-capability matrix;
- overlap/conflict analysis;
- provisional software-engineering capability model;
- claims/gaps requiring Stage 4 challenge.

## Exit criteria

All five books have been meaningfully examined for their intended contributions; material findings are traceable to actual examined locations; conflicts and limitations are explicit; and inadequate source access is not hidden by secondary summaries.

---

# 11. Stage 4 — Challenge: Broader Professional Software-Engineering Research

## Purpose

Challenge the book-derived model, fill gaps against the original domain boundary and model software engineering from durable professional practice rather than current coding-agent capabilities.

This stage incorporates the original professional-practice research responsibility, but now uses the five-book model as a hypothesis to test rather than as an architectural authority.

## Research questions

Answer both:

1. Which book-derived claims and methods are defensible, under what conditions, and with what limitations?
2. Which important software-engineering responsibilities, risks or perspectives are absent from the corpus?

## Research areas

Use SWEBOK V4 as a map and investigate current authoritative practice across at least:

```text
requirements and acceptance
software architecture and design
construction
code review
testing
maintenance and evolution
configuration management
engineering process
quality
security
CI / continuous delivery
observability and operability
performance
reliability
debugging and incident-driven repair
technical debt and refactoring
```

Do not assume every area belongs in the final core.

Use current authoritative and empirical sources where applicable, including relevant standards, primary research, official documentation and specialist practitioner material. The DORA, NIST SSDF and Google Engineering Practices anchors are candidate inputs here, not unquestioned rules.

## Study real workflows

Research how strong practitioners perform:

```text
small feature changes
bug fixes
refactors
API changes
database/schema changes
dependency upgrades
security fixes
performance repairs
concurrency repairs
legacy-system changes
cross-service changes
release preparation
```

For each, capture:

```text
inputs
working artefacts
uncertainties
cheap checks
commitment points
review points
expensive checks
failure modes
repair strategies
handoffs
quality criteria
```

Seek supporting and contrary evidence. Investigate failure conditions and counterexamples rather than confirming the corpus. Verify change-sensitive claims against current authoritative sources.

## Evidence qualification

Keep disposition separate from evidential standing. Distinguish:

```text
supported finding
qualified/context-dependent method
practical heuristic
disputed claim
unresolved question
rejected idea
```

An unresolved claim must not silently become an unconditional core rule.

## Expected outputs

- professional-practice research log;
- terminology and role/responsibility map;
- supporting and contrary evidence;
- book-claim dispositions;
- gap analysis against the Stage 1 boundary;
- software change lifecycle candidates;
- failure and repair taxonomy candidates;
- evidence-quality model;
- evidence-qualified software-engineering capability model.

## Exit criteria

Material book-derived findings have been assessed; important domain gaps are addressed or bounded; unresolved claims remain explicit; and the production model can be justified from software-engineering evidence without referring to a particular LLM, coding agent or book corpus alone.

---

# 12. Stage 5 — Model Software Change Types, Contracts and System Context

## Purpose

Introduce the domain-specific model that creative production projects do not need: software work usually changes a system with existing behavioural and technical contracts.

## Change taxonomy to research

At minimum investigate:

```text
new behaviour
bug repair
refactor without intended behaviour change
interface / API evolution
data / schema migration
dependency or platform upgrade
performance change
security change
reliability / resilience change
operability / observability change
decommissioning / removal
architecture migration
```

## Contract taxonomy to research

```text
user-visible behaviour
API contracts
schemas and persisted data
message / event contracts
CLI contracts
library contracts
configuration contracts
protocols
performance budgets
security properties
SLO / reliability assumptions
build / packaging contracts
backward compatibility
```

## System-context model

For a proposed change determine how the agent should discover:

```text
repository structure
build system
entry points
module boundaries
ownership boundaries
dependencies
call/data flow
existing tests
runtime configuration
public contracts
architecture decisions
observability
security-sensitive surfaces
release model
```

Avoid inventing a universal system graph until evidence proves one is necessary.

## Expected outputs

- change taxonomy;
- contract taxonomy;
- change-impact model;
- system-inspection checklist or command hypothesis;
- risk classification candidates.

## Exit criteria

The project can distinguish different software change classes and explain what must be preserved for each.

---

# 13. Stage 6 — Map the Engineering Workflow and Artefacts

## Purpose

Derive the smallest credible end-to-end engineering workflow from the evidence-qualified domain model.

## Candidate workflow

Research whether the core should resemble:

```text
understand change intent
→ inspect repository and current behaviour
→ identify affected contracts / risk
→ select smallest coherent approach
→ record design only when useful
→ implement
→ add or revise targeted tests
→ run cheapest meaningful validation
→ escalate validation according to risk
→ review diff and quality
→ diagnose failures
→ bounded correction
→ final verification
→ handoff / release evidence
```

Do not force every change through an architecture document or planning ceremony.

## Candidate artefacts

The codebase itself is the primary production artefact. Supporting artefacts may include:

```text
change brief / issue / specification
acceptance criteria
system inspection notes
impact analysis
design note or ADR
interface/schema definition
migration plan
implementation diff
tests and fixtures
benchmark fixture
verification evidence
review findings
release note / migration note
```

For each artefact identify:

```text
when it is justified
creator
source of truth
consumers
decisions preserved
change semantics
approval semantics
retention / disposal
```

Do not require files for transient reasoning that does not need to survive.

## Expected outputs

- domain workflow;
- artefact responsibilities;
- production state/decision semantics;
- handoff model;
- repair routes.

## Exit criteria

A small feature or defect repair can be traced end to end without inventing missing lifecycle semantics during implementation.

---

# 14. Stage 7 — Define Verification, Risk and Commitment Strategy

## Purpose

Translate the Production Skills cheap-first principle into software engineering.

## Verification ladder

Research a risk-sensitive ladder such as:

```text
static repository inspection
→ formatter / linter / syntax validation
→ compile / typecheck
→ focused tests
→ affected module tests
→ integration / contract tests
→ security or compatibility checks when relevant
→ performance / concurrency checks when relevant
→ broad regression suite
→ smoke / end-to-end validation
→ release/deployment verification where required
```

The project should decide **which evidence is necessary for the change**, not blindly run every available command.

## Commitment points

Research when explicit human approval or deliberate locking is appropriate, especially for:

```text
public API breaks
schema migrations
data-destructive operations
security model changes
architecture migrations
large dependency/platform upgrades
irreversible release operations
high-cost infrastructure consequences
```

## Risk model

Define factors such as:

```text
blast radius
reversibility
contract exposure
data impact
security impact
concurrency
runtime criticality
performance sensitivity
test coverage confidence
change novelty
cross-service coupling
```

Avoid one universal numeric risk score unless evidence shows it is useful.

## Expected outputs

- verification ladder;
- risk-to-verification policy;
- commitment/approval policy;
- stopping/escalation rules;
- rollback/reversibility considerations.

## Exit criteria

The project can explain why a one-line local fix and a schema migration should not receive identical verification or approval treatment.

---

# 15. Stage 8 — Research Existing AI Skills, Tools and Providers

## Purpose

Find reusable execution capability before designing native skills.

## Search categories

### General software engineering Agent Skills

Research skills for:

```text
software engineering
architecture
code review
systematic debugging
refactoring
TDD / testing
security review
performance engineering
API design
database design
CI/CD
Git / worktrees
requirements/spec-driven development
```

### Ecosystem skills

Research strong reusable skills for major ecosystems, for example:

```text
TypeScript / Node.js
Java / Spring Boot
Scala
Python
Go
Rust
React / React Native
Kubernetes
Kafka
SQL / PostgreSQL
MongoDB
Cassandra
```

These are research categories, not predetermined core packs.

### Deterministic tools

Research how the skills should discover and use repository-native:

```text
compiler / typechecker
formatter
linter
unit/integration/E2E test runner
build tool
coverage tool
static analyser
security scanner
dependency scanner
profiler
benchmark runner
mutation tester
container tooling
CI tooling
package manager
version control
```

### Coding agents and provider capabilities

Assess current provider capabilities for:

```text
repository inspection
code editing
shell execution
test execution
code search
GitHub interaction
browser interaction
long-context repository reasoning
parallel subagents
```

## Evaluation record

For each candidate record:

| Field | Meaning |
|---|---|
| Name | Skill/tool/provider |
| Source | Repository/provider |
| Licence | Reuse constraints |
| Maturity | Production confidence |
| Installation | Consumption model |
| Engineering role | Workflow responsibility |
| Deterministic/generative | Execution type |
| Provider coupling | Portability risk |
| Composability | Fit with project |
| Quality suitability | Engineering usefulness |
| Maintenance | Current state |
| Integration | USE / ADAPT / REFERENCE / REJECT |
| Gaps | Missing production behaviour |

## Expected outputs

- capability landscape;
- candidate dependency map;
- reuse decisions;
- gaps requiring project-owned intelligence.

## Exit criteria

The project can justify why each native capability is not better solved by composing an existing skill or deterministic tool.

---

# 16. Stage 9 — Choose the Execution Layer

## Purpose

Separate reusable software-engineering production intelligence from low-level execution.

## The project should own

Candidate ownership:

```text
how to inspect a system
how to classify a change
how to determine affected contracts
how to choose change scope
how much design is necessary
what verification is appropriate
how to diagnose a failure
how to preserve unaffected behaviour
how to review engineering quality
how to choose bounded repair
```

## Existing tools should own

```text
compilation
formatting
linting
test execution
coverage calculation
static analysis
security scanning
profiling
benchmark execution
Git operations
package installation
container execution
CI execution
```

unless a small deterministic helper is required to compose them consistently.

## Key decision

Determine how strongly the project should depend on repository-native commands rather than defining its own universal build/test abstraction.

Prefer discovering and invoking the repository's actual toolchain.

## Exit criteria

The architecture can replace an execution tool without redesigning the engineering workflow.

---

# 17. Stage 10 — Gap Analysis

## Purpose

Compare the required software-engineering workflow with available skills and tools.

## Classify

```text
covered
partially covered
missing
```

## Test especially for gaps in

```text
brownfield repository understanding
change-impact analysis
contract preservation
smallest-responsible-change behaviour
risk-sensitive verification selection
root-cause diagnosis
repair scope discipline
architecture-quality evaluation
test-quality evaluation
compatibility reasoning
security integration
performance/reliability reasoning
project-native tool discovery
external installability
```

## Over-engineering check

Flag capabilities that are attractive but not required to prove the core thesis, for example:

```text
universal dependency graph
universal AST framework
cross-language semantic index
custom CI engine
universal build/test runner
central provider registry
shared agent runtime
persistent software project graph
```

Move them to follow-up research unless the first vertical genuinely requires them.

## Expected outputs

- gap matrix;
- native-capability shortlist;
- reused-capability shortlist;
- deferred ideas;
- early over-engineering risks.

## Exit criteria

Every proposed native skill responsibility maps to an evidenced gap.

---

# 18. Stage 11 — Design Core Skills and Commands

## Purpose

Derive the smallest installable skill set capable of the complete engineering workflow.

Do not start from a fixed number of skills.

## Skill hypotheses to test

Possible responsibility clusters include:

```text
software-engineering      # inspect, design, implement, verify and hand off changes
software-evaluate         # review correctness, quality, risk and repair scope
software-extension-pack-creator
```

Alternative research may justify separate architecture, debugging, testing or review skills if they are independently useful and coherent when installed alone.

Do not split skills merely to mirror job titles.

## Candidate skill-local commands

Potential commands include:

```text
inspect-system
classify-change
assess-impact
identify-contracts
design-change
implement-change
add-or-update-tests
select-verification
run-verification
diagnose-failure
review-change
refactor
plan-migration
evaluate-test-quality
evaluate-compatibility
evaluate-security-risk
evaluate-performance-risk
prepare-handoff
```

Only retain commands that improve at least one of:

```text
isolated evaluation
reuse
composition
diagnosis
targeted repair
benchmark precision
```

## Command contract questions

For every command define:

```text
inputs
preconditions
repository evidence required
outputs
allowed mutations
forbidden mutations
failure states
verification responsibilities
interaction with approved decisions
```

## Exit criteria

The smallest skill set can cover the target workflow without turning commands into a universal lifecycle DSL.

---

# 19. Stage 12 — Design Software Engineering Extension Packs

## Purpose

Create first-class reusable specialisations that materially alter software-engineering behaviour without bloating the core.

Apply `production-skills/docs/bootstrap/extension-pack-process.md` at two levels:

1. curate complementary catalogue coverage;
2. run P1–P5 for every pack selected for evidence-qualified specification.

Catalogue size is not fixed by the five-book requirement.

## Catalogue curation

Research or generate a broader candidate pool and compare candidates through a combined capability-coverage matrix. Classify each need as:

```text
existing pack covers it → reuse
one-project detail → project instructions
broad domain responsibility → core-improvement candidate
reusable specialised behaviour → create/refine a pack
insufficient value/evidence → defer or reject
```

Assess practical reuse, distinct production behaviour, depth, evaluation feasibility, overlap with the core and neighbouring packs, and combined catalogue coverage.

### Pack dimensions to investigate

#### Language / runtime grammar

```text
TypeScript / Node.js
Java / JVM
Scala
Python
Go
Rust
```

#### Framework / ecosystem grammar

```text
Spring Boot
React
React Native
Play Framework
FastAPI
Kubernetes-native services
```

#### Architecture grammar

```text
HTTP API
event-driven systems
stream processing
CLI / developer tooling
libraries / SDKs
serverless
mobile applications
```

#### Engineering-risk specialisation

```text
secure-development
performance-critical
high-concurrency
data-migration
backward-compatible API evolution
high-reliability services
```

These are candidate dimensions. Research must determine which belong in Extension Packs, which should remain external specialist skills, which indicate a core gap and which are merely project-specific instructions.

## Per-pack P1–P5 research and design

Each selected pack must run the following as **distinct substantive stages with separate committed research evidence**.

### P1 — Define the specialisation and core baseline

Define:

```text
intended use and non-use
reusable production need
relevant core skills
core revision / baseline status
expected behavioural difference from core
what must remain stable
adjacent boundaries
why ordinary project instructions or an existing pack are insufficient
provisional evaluation questions
```

The baseline must represent the real production need rather than an artificially vague brief designed to make the pack look useful.

### P2 — Select five complementary foundational books

Select **exactly five justified books for the pack** using the same permission and access rules as Stage 2.

Books may reuse relevant examined evidence from the core corpus or another pack. There is no requirement for five new books. Reuse requires a pack-specific contribution assessment; a shared citation does not itself prove specialist applicability.

For supplied pack books, removal, replacement or demotion still requires explicit permission.

Produce:

```text
pack knowledge-coverage map
candidate comparison
five-book pack corpus
source-access register
source-reuse decisions
substitution approvals / pending decisions
remaining specialist gaps
```

### P3 — Extract and reconcile specialised knowledge

Meaningfully examine all five books for their pack-specific contribution, either directly or through adequate reviewed direct-source evidence whose applicability is verified.

Map:

```text
source finding + location
→ applicability to specialisation
→ change to a core-skill decision
→ observable workflow / artefact effect
→ evaluation criterion
→ failure / repair case
```

Do not automatically inherit the core bibliography or one pack's profile into another pack.

### P4 — Challenge claims and extend coverage

Use independent professional, empirical, standards, official and practitioner evidence to challenge the extracted specialist guidance and fill gaps.

Record separate:

```text
disposition: retain / merge / adapt / qualify / reject / investigate further
evidential standing: supported / context-dependent / heuristic / disputed / unresolved
```

Current, change-sensitive ecosystem practices must be verified against current authoritative sources.

### P5 — Specify behaviour and evaluation

Define operational pack behaviour:

```text
scope
activation
hard constraints and soft defaults
engineering conventions
architecture / ecosystem assumptions
core-skill decisions changed
verification changes
quality criteria
precedence
incompatible assumptions
source-to-behaviour-to-test mapping
showcase design + exact prompt
independent reuse brief/fixture
acceptance cases
implementation plan
```

Evaluation design must state what should change, what must remain stable, intentional traits to preserve and genuine defects still to reject.

## Precedence

Target common precedence:

```text
explicit project instructions
→ accepted architecture / public contracts / approved work
→ selected Software Engineering Extension Pack
→ core software-engineering defaults
```

A pack must not silently override repository conventions, accepted project architecture or stronger explicit instructions.

## Differential evaluation

Every implemented pack must ultimately prove:

```text
core
vs
core + pack
```

using the same substantive brief and comparable conditions. The comparison should detect meaningful engineering differences, not vocabulary changes.

## Pack authoring capability

The project should expose a domain-native authoring skill or equivalent workflow. Extend that capability as the process evolves rather than creating a competing generic pack-authoring runtime.

## Expected outputs

- catalogue candidate pool and coverage matrix;
- selected/deferred/rejected pack rationale;
- pack model and precedence rules;
- P1–P5 research logs for each selected pack;
- five-book corpus and evidence status per selected pack;
- source-to-behaviour-to-test mapping;
- planned showcase/evaluation design;
- domain-native pack-authoring contract.

## Exit criteria

The project can explain what makes a Software Engineering Extension Pack different from a framework prompt, project README or external specialist skill. Selected packs have evidence-qualified, testable production profiles; planned catalogue entries are not misrepresented as researched or ready. P6–P7 are deferred until the relevant core implementation exists.

---

# 20. Stage 13 — Design Five Progressive Example Levels

## Purpose

Demonstrate progressively broader software-engineering responsibility through real repository changes.

Do not select final examples by intuition alone.

## Level model to validate

### Level 1 — Bounded local change

One small change with narrow blast radius.

Capability themes:

```text
repository inspection
local implementation
focused tests
cheap verification
small diff
```

Candidate shapes:

```text
fix one defect
add one validation rule
refactor one local implementation without behaviour change
```

### Level 2 — Module or contract-aware change

A change spanning a coherent module or interface.

Capability themes:

```text
contract awareness
multi-file edits
compatibility
unit + integration evidence
```

Candidate shapes:

```text
add library/API behaviour
extend persistence behaviour
add a CLI command
```

### Level 3 — Complete feature across layers

A realistic feature crossing several layers while remaining one deployable product change.

Capability themes:

```text
architecture fit
cross-layer integration
schema/event/API behaviour
observability
broader test strategy
```

Candidate shapes:

```text
HTTP feature with persistence
asynchronous event-driven feature
mobile/web feature with backend contract
```

### Level 4 — Risky evolution / repair

A change where preservation, migration or diagnosis dominates.

Capability themes:

```text
root-cause analysis
migration
backward compatibility
performance/concurrency/security risk
bounded repair
```

Candidate shapes:

```text
schema migration without service breakage
performance regression diagnosis and repair
framework/dependency upgrade with compatibility constraints
```

### Level 5 — Full software-engineering thesis

A complex production change requiring research, architecture judgement, staged implementation, evaluation and handoff.

Capability themes:

```text
system-wide reasoning
multiple contracts
risk-sensitive verification
incremental/vertical implementation
release readiness
cross-domain handoff
```

Candidate shapes:

```text
modernise part of a legacy service without broad rewrite
implement a production feature from an accepted UX/product handoff
repair an incident class and convert it into permanent regression protection
```

## Example discovery process

For each level:

1. derive the capabilities the level must demonstrate;
2. research or generate a broader candidate pool, normally at least 8–12 credible candidates;
3. represent each candidate as a small reproducible repository or fixture where feasible;
4. map candidates against a capability-coverage matrix;
5. remove examples that test substantially the same engineering behaviour;
6. select the three examples whose **combined coverage** best demonstrates the level;
7. check the complete 15-example set against the full project capability map.

## Coverage matrix dimensions

Include at least:

```text
change type
core skills
commands
language/ecosystem diversity
repository shape
contracts affected
verification paths
failure modes
repair behaviour
preservation behaviour
quality dimensions
Extension Pack interaction
cross-domain handoff
benchmarkability
showcase clarity
```

Every primary example must contain the exact copyable generation prompt.

## Exit criteria

The planned 15 examples demonstrate substantially different engineering problems rather than 15 variants of CRUD feature generation.

---

# 21. Stage 14 — Design Evals, Benchmarks and Regression Fixtures

## Purpose

Define how software-engineering quality will be measured before large-scale implementation.

## Evaluation layers

Target the family model:

```text
deterministic repository validation
→ command conformance
→ skill orchestration
→ functional correctness
→ software-engineering quality
→ preservation / root-cause / repair
→ Extension Pack activation and fidelity
→ core-vs-pack differential behaviour
→ end-to-end engineering
→ installation smoke tests
```

## Deterministic evaluation

Candidate checks:

```text
build succeeds
typecheck succeeds
formatter/linter succeeds
required tests pass
fixture behaviour matches contract
no forbidden files changed
public API compatibility where measurable
schema compatibility where measurable
security scanner findings within fixture expectations
performance budget within fixture expectations
installation integrity
```

## Behavioural engineering evaluation

Test whether the agent:

```text
inspects before editing
changes the correct scope
preserves unaffected behaviour
adds meaningful regression evidence
uses repository-native tooling
stops when evidence disproves its approach
diagnoses before broad repair
avoids unrelated cleanup
respects accepted architecture and contracts
escalates verification according to risk
```

## Semantic engineering-quality evaluation

Keep distinct dimensions such as:

```text
correctness
simplicity
maintainability
architecture fit
readability
test quality
compatibility
security
performance
reliability
operability
scope discipline
```

Do not collapse them into one opaque score.

## Benchmark fixture design

Prefer reproducible repositories containing:

```text
known starting commit
explicit task or defect
hidden or independent behavioural checks
known contracts
allowed change surface where useful
expected risk concerns
reference failure modes
```

Do not require one golden implementation when several implementations are valid.

Use executable behaviour as an oracle where possible and semantic review for quality that cannot be reduced to deterministic checks.

## Regression loop

```text
escaped defect
→ diagnose owning layer
→ build smallest reproducible repository/fixture
→ add benchmark/eval
→ confirm failure on old behaviour
→ confirm protection on repaired behaviour
→ retain permanently
```

## Test-quality evaluation

Investigate techniques such as:

```text
mutation testing
fault seeding
negative test cases
contract break fixtures
assertion-quality review
```

when they improve confidence that generated tests actually protect behaviour.

## Extension Pack evaluation

Every implemented pack should test:

```text
activation
non-activation
specialised engineering behaviour
precedence
repository-convention preservation
pack-aware verification
core-vs-pack differential behaviour
negative/incompatible cases
independent reuse beyond the showcase
```

The P5 source-to-behaviour-to-test mapping should feed these cases directly.

## Exit criteria

The benchmark can detect incorrect code, poor engineering behaviour and meaningful regressions without pretending those are the same failure.

---

# 22. Stage 15 — Generate Six Canonical Specifications

Generate:

```text
docs/
├── 01-software-engineering-skills-system-spec.md
├── 02-software-engineering-skills-workflows-and-artifacts-spec.md
├── 03-software-engineering-skills-repository-and-contracts-spec.md
├── 04-testing-and-benchmark-spec.md
├── 05-software-engineering-extension-packs-spec.md
└── 06-software-engineering-extension-pack-catalogue.md
```

Generate these specifications from the persisted research logs rather than reconstructing bootstrap decisions from conversation memory.

## Spec 01 — System

Owns:

```text
mission
scope and boundaries
principles
system architecture
core skills
execution architecture
risk / verification policy
approval / commitment policy
build order
system acceptance
```

## Spec 02 — Workflows and Artefacts

Owns:

```text
change taxonomy
contract taxonomy
system inspection
engineering workflow
artefacts
decision semantics
change-impact model
verification flow
failure taxonomy
repair routes
handoffs
```

## Spec 03 — Repository and Contracts

Owns:

```text
repository structure
SKILL.md contracts
command contracts
self-containment
references/assets/scripts
tool discovery
installation
runtime dependencies
CI
technical acceptance
```

## Spec 04 — Testing and Benchmark

Owns:

```text
evaluation layers
fixture model
benchmark suites
quality dimensions
progressive-example coverage
regression policy
Extension Pack evaluation
installation tests
release gates
measured evidence
```

## Spec 05 — Software Engineering Extension Packs

Owns:

```text
pack model
specialisation dimensions
activation
precedence
core-skill integration
verification changes
pack-aware evaluation
pack packaging
pack authoring
source/evidence expectations
boundaries
```

## Spec 06 — Extension Pack Catalogue

Owns the actual curated entries, not merely a list of possible pack names.

For each pack record:

```text
identity
intended use and non-use
catalogue-selection rationale
complementary contribution
core baseline
expected behavioural difference
five-book corpus
contribution of each book
research-log references
source-access / reading limitations
unresolved questions
hard constraints / soft defaults / qualified methods
core-skill effects
source-to-behaviour-to-test mapping
showcase fixture and exact prompt
actual output status
independent reuse case
research status
implementation status
evaluation status
clean-installation status
readiness
limitations / compatibility / migration notes
```

Research, implementation, evaluation and readiness must be tracked independently. A listed entry, completed bibliography, directory or prompt does not imply a researched or ready-to-use pack.

## Exit criteria

Implementation can proceed without inventing core engineering architecture in code, and Specification 06 distinguishes planned catalogue coverage from evidence-backed readiness.

---

# 23. Stage 16 — Design the Public README

Follow the proven Video Production Skills public structure while remaining software-native.

Target sections:

```text
project positioning
what engineering work it can perform
change-scope / preservation / verification principles
installation
quick start using a strong Level 1 repository change
Learn by engineering
  Level 1 — 3 examples
  Level 2 — 3 examples
  Level 3 — 3 examples
  Level 4 — 3 examples
  Level 5 — 3 examples
project structure grows with the work
core skills
Software Engineering Extension Packs
execution layer
repository checks and benchmarks
documentation index
project boundary
contributing
licence
```

The README design may refer to planned examples, but the mature README must show actual repository changes and verification evidence rather than hypothetical capability claims.

Every implemented primary example should link to:

```text
starting repository/fixture
exact prompt
resulting change
verification result
explanation of engineering behaviour demonstrated
```

## Exit criteria

A developer can understand how the eventual product will be installed and used, and the README design has a clear path from bootstrap status to measured public claims.

---

# 24. Stage 17 — Scaffold the Production Repository

Create only structure justified by the specifications.

Candidate minimum:

```text
software-engineering-skills/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
├── docs/
│   └── research-logs/       # retained as the historical design record
├── skills/
├── examples/
├── benchmarks/
├── tests/
├── tools/                   # only if deterministic helpers are justified
└── .github/
```

Add Extension Pack surfaces only when they contain working or immediately useful specified content.

Do not create empty directories for symmetry with creative repositories.

## Exit criteria

A contributor can locate skills, examples, benchmarks and specifications with no speculative architecture in the scaffold. This is the first stage that should promote the repository to `scaffolded` maturity.

---

# 25. Stage 18 — Implement the Core Vertical

Implement the smallest subset of core skills and commands needed to complete one representative Level 1 change in an external fixture repository.

The vertical should prove at least:

```text
install skill
→ inspect existing repository
→ understand task and contracts
→ make bounded implementation
→ add/update meaningful test evidence
→ run repository-native verification
→ evaluate diff
→ correct only failed scope
→ finish with passing evidence
```

Prefer a brownfield fixture over a blank project.

Do not implement all candidate languages, packs or commands before this works.

## Exit criteria

Installed skills can complete one realistic software change end to end and the benchmark can distinguish success from a plausible but defective implementation.

---

# 26. Stage 19 — Implement Progressive Coverage and Extension Packs

Expand from the proven vertical.

Implement the selected 15 primary examples progressively rather than all at once.

Introduce representative Extension Packs only after the core works without them.

For every implemented pack, complete the remaining Extension Pack bootstrap stages.

## P6 — Implement and demonstrate

Use the domain's existing pack-authoring capability where available.

Implement a self-contained pack with concise relevant guidance and source provenance. Runtime behaviour must not depend on the original books, central research logs or another pack.

Create and run:

```text
realistic showcase fixture
exact copyable prompt
actual generated/changed artefacts
execution record
behavioural fixtures
local validation
```

A prompt or pack directory alone is not a demonstration.

## P7 — Evaluate, validate installation and catalogue

Compare:

```text
core-only
vs
core + pack
```

on the same substantive brief, constraints and comparable execution conditions. Record relevant core/pack revisions, prompts, model/tool versions, settings, resource limits and deviations.

Where useful, also compare against core plus ordinary project-specific instructions to determine whether packaging adds reusable depth, consistency or reduced prompting burden.

Test:

```text
activation and non-activation
intended specialised behaviour
precedence
preservation of repository conventions and approved work
pack-aware evaluation without hiding defects
negative/incompatible cases
the independent reuse brief/fixture
clean consumer-project installation and use
```

Preserve failed and inconclusive results. Do not infer general superiority from one favourable sample.

## Proof required for each implemented pack

```text
core works without pack
core + pack changes intended engineering behaviour
repository/project instructions outrank pack defaults
accepted architecture/contracts and approved work outrank pack defaults
pack-aware evaluation recognises valid specialisation without accepting real defects
showcase and independent reuse case both exercise the specialisation
pack authoring can create or revise the pack
clean external installation works
```

## Exit criteria

The project demonstrates broad engineering responsibility and specialisation rather than one polished fixture. Any pack described as ready has P6 implementation evidence, P7 differential evaluation and clean consumer installation evidence.

---

# 27. Stage 20 — Validate Installation and Repository Integrity

Validate local repository integrity and clean consumer installation as **separate gates inside the same stage**.

## Local/source-repository gate

Validate:

```text
repository contracts
deterministic checks
full installation
selective installation
skill self-containment
skill-local references
skill-local scripts
provider/tool prerequisites
README commands
benchmark/eval entry points
no undocumented repository-relative runtime dependencies
```

## Clean external consumer gate

Use a fresh consumer repository outside the source checkout.

Test:

```text
install from GitHub
install selected skills only
invoke the skill from the target coding agent
inspect a fixture repository
perform a bounded engineering command
run required deterministic tools
resolve skill-local references
produce expected benchmark evidence
exercise representative Extension Pack installation when advertised
```

The external smoke test should expose accidental assumptions about source-repository paths or developer-machine state.

## Exit criteria

Every advertised skill can be installed selectively into a clean consumer, discovered by the target coding agent and exercised without hidden source-checkout dependencies. Local validation and external installation results are reported separately.

---

# 28. Stage 21 — Optional Pactwright Integration

If useful, add:

```text
integrations/pactwright.yml
```

It may expose compatibility and capability bindings only.

It must not move into `software-engineering-skills`:

```text
Pactwright lifecycle stages
Project Graph semantics
Pactwright agents/prompts
project governance
project-specific Contract state
```

The skills must remain independently useful.

## Exit criteria

Pactwright can resolve the relevant software-engineering capabilities without being required by the repository.

---

# 29. Stage 22 — Register and Promote Maturity

Update the Production Skills registry as evidence advances:

```text
proposed
→ researching
→ specified
→ scaffolded
→ working
→ benchmarked
→ mature
```

Promotion is based on demonstrated behaviour, not repository existence or planned architecture.

For `mature`, require at least:

```text
core workflow works end to end
six spec responsibilities represented
public README accurately reflects implementation
5 × 3 primary examples represented
primary examples include exact prompts
domain benchmark operational
regression fixtures operational
Extension Pack architecture and curated catalogue represented
implemented packs have P1–P7 evidence, showcases and behavioural evals
pack-authoring capability exists
core remains useful without packs
clean consumer installation passes
quality claims are measured or explicitly marked unmeasured
```

---

# 30. Stage 23 — Review Shared Abstraction Candidates

Only after implementation and benchmark evidence exists, apply `shared-abstraction-process.md` and compare independently reproduced needs with other mature Production Skills domains.

For every candidate record:

```yaml
candidate: <name>
observed_in:
  - software-engineering-skills
  - <another independent production domain>
common_need: <domain-independent need>
domain_variations:
  software-engineering-skills: <software-specific form>
  other-domain: <other form>
evidence:
  - <implementation / benchmark evidence>
recommendation: <family principle | project contract | reject>
not_recommended:
  - <over-generalisation to avoid>
```

Potential candidates should remain hypotheses until repeated evidence exists.

Do not immediately extract:

```text
universal workflow engine
universal artefact graph
universal evaluator
universal pack interpreter
universal command runtime
```

Cross-project comparison during bootstrap generation may inform conformance and prevent known mistakes, but it must not be treated as evidence for a shared abstraction before the software-engineering implementation independently reproduces the need.

## Exit criteria

The project contributes reusable family evidence without weakening software-native terminology or creating a central software-production runtime.

---

# 31. Initial Research Questions for Later Stages

The following questions should be answered by the staged bootstrap rather than assumed now.

## Research foundation

- Which knowledge dimensions matter most when comparing the foundational book candidates?
- Which candidate books provide practical engineering decision models rather than broad programming advice?
- Where do durable classic texts require qualification against current delivery, security or ecosystem practice?
- Which important responsibilities are unlikely to be adequately represented by five books and must be deliberately covered in Stage 4?

## Scope

- Should architecture be a core skill responsibility or a separately installable skill?
- Should testing/debugging/review be independent skills or commands inside broader skills?
- How far should deployment and operability extend before responsibility hands to platform/SRE skills?
- Should infrastructure-as-code changes be first-class software changes or an adjacent domain?

## Tool composition

- Which current software-engineering Agent Skills already solve parts of the workflow well?
- Which capabilities should be composed from external skills rather than adapted locally?
- How should repository-native build and test commands be discovered safely?
- When should the project generate deterministic helper scripts versus invoke existing tools directly?

## Brownfield understanding

- What is the smallest reliable repository-inspection method?
- When is code search sufficient?
- When is architectural/data-flow reconstruction necessary?
- Can impact analysis remain ephemeral or does it need a durable artefact for risky changes?

## Verification

- How should risk determine the verification ladder?
- How can the benchmark test that generated tests genuinely catch defects?
- How should flaky tests and nondeterministic systems be handled?
- When are mutation testing and fault seeding worth their cost?

## Extension Packs

- Are language/runtime packs the strongest first specialisation dimension?
- Should framework knowledge live in packs or external provider/community skills?
- Can architecture packs compose safely with language packs without combinatorial complexity?
- Which quality specialisations materially change workflow enough to justify packs?
- Which specialist books can validly reuse core extraction evidence, and where is new direct examination needed?
- How should the catalogue distinguish planned, researched, implemented, evaluated and ready packs?

## Examples

- What open-source fixture projects are small enough to benchmark but realistic enough to expose engineering judgement?
- How can examples remain reproducible as dependencies age?
- How should multi-language coverage balance breadth against benchmark maintenance cost?

## Evaluation

- Which software-quality dimensions can be checked deterministically?
- Which require expert/LLM semantic evaluation?
- Which benchmark cases require hidden tests?
- How should several valid implementations be scored without a brittle golden patch?

---

# 32. Early Over-Engineering Risks

The bootstrap should explicitly resist the following until core behaviour proves the need:

```text
universal code intelligence graph
custom language server
custom compiler abstraction
cross-language AST normalisation
universal test runner
universal build system abstraction
universal dependency resolver
central model/provider router
persistent agent memory system
shared workflow engine
multi-agent organisation framework
one universal software quality score
pack-combination solver
central research database
shared Extension Pack runtime
```

These may become later research projects if repeated evidence demonstrates real leverage.

The first proof should remain simple:

```text
one installed engineering skill
+
one realistic brownfield repository
+
one bounded change
+
repository-native tools
+
credible tests/evaluation
```

---

# 33. Migration Note

This revision adopts the current Production Skills bootstrap research and Extension Pack processes before substantive software-engineering bootstrap execution has begun.

Therefore:

- Stage numbering is updated cleanly rather than preserved through compatibility aliases;
- the existing software-specific change, contract, workflow, verification, execution-layer, example and benchmark responsibilities are retained;
- the old broad professional-practice Stage 2 becomes the challenge-and-extension responsibility in Stage 4;
- Seed → Five → Challenge becomes the explicit research foundation;
- Extension Pack catalogue curation and P1–P5 are required before pack implementation;
- P6–P7 occur only after the relevant core implementation exists;
- the premature pre-scaffold cross-project abstraction-review stage is removed;
- shared abstraction review remains the final evidence-backed stage;
- local and clean external installation remain distinct gates within one installation/integrity stage.

This migration changes the bootstrap specification, not project maturity and not evidence status. No research stage is considered completed by this document update.

---

# 34. Success Criterion

A successful `software-engineering-skills` bootstrap is not a generic coding checklist with Production Skills terminology added, and it is not five books mechanically converted into five skills.

It should encode enough evidence-qualified software-specific knowledge, change semantics, contract preservation, verification strategy, repair behaviour, Extension Pack research, example discovery and benchmark architecture that later sessions can execute one standalone stage at a time without redesigning the project from scratch.

The resulting repository should eventually demonstrate this core behaviour:

```text
understand the system
→ change only what should change
→ preserve what should remain stable
→ prove the change with appropriate evidence
→ diagnose failures accurately
→ repair the smallest responsible scope
→ leave the software healthier or at least no worse than before
```

Do not scaffold `software-engineering-skills` while generating or updating this bootstrap specification. The bootstrap defines how the production repository will be researched, specified, created and proven.