# Software Engineering Skills — New Project Bootstrap Process

**Status:** Bootstrap specification  
**Date:** 7 September 2026

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
- `production-skills/docs/bootstrap/shared-abstraction-process.md`;
- the current Production Skills family specifications;
- the current mature Video, Narrative and Music Production Skills repositories;
- the UI/UX Design Skills bootstrap as a depth reference only.

Initial external research anchors include:

- IEEE Computer Society, **SWEBOK Guide V4.0** — https://www.computer.org/education/bodies-of-knowledge/software-engineering
- DORA, **Continuous Delivery** — https://dora.dev/capabilities/continuous-delivery/
- NIST SP 800-218, **Secure Software Development Framework (SSDF) v1.1** — https://csrc.nist.gov/pubs/sp/800/218/final
- Google Engineering Practices, **Code Review** — https://google.github.io/eng-practices/review/

These sources inform the research agenda. They do not predetermine the final skill architecture.

---

## 3. Required Outputs

The bootstrap must produce:

1. a precise software-engineering domain boundary;
2. research into real professional software-engineering practice;
3. a software-change taxonomy and system-context model;
4. a domain-native workflow and artefact model;
5. a verification, risk and commitment strategy;
6. research into existing Agent Skills, engineering tools, CLIs, MCPs and provider capabilities;
7. an execution-layer decision and gap analysis;
8. a justified set of core Agent Skills;
9. decomposed commands where independent testing or reuse is valuable;
10. a first-class Software Engineering Extension Pack architecture;
11. an initial Extension Pack catalogue strategy;
12. a domain-native Extension Pack authoring capability;
13. five progressive example levels;
14. three complementary primary examples per level selected through capability coverage;
15. deterministic, behavioural and semantic evaluation;
16. benchmark and regression architecture;
17. six canonical specifications;
18. a public README following the proven Video Production Skills structure;
19. an open-source repository scaffold;
20. Agent Skills installation and selective-installation contracts;
21. local validation and clean external installation smoke tests;
22. an implemented end-to-end core vertical;
23. implemented progressive examples and representative Extension Packs;
24. optional Pactwright compatibility without runtime dependence;
25. maturity evidence and registry integration;
26. cross-domain abstraction candidates based only on repeated evidence.

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

This thesis must be tested during Stages 1–8.

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

---

# 6. Bootstrap Flow

```text
PROJECT IDEA
    ↓
1. Define Project Goal and Domain Boundary
    ↓
2. Research Professional Software Engineering Practice
    ↓
3. Model Software Change Types, Contracts and System Context
    ↓
4. Map the Engineering Workflow and Artefacts
    ↓
5. Define Verification, Risk and Commitment Strategy
    ↓
6. Research Existing AI Skills, Tools and Providers
    ↓
7. Choose the Execution Layer
    ↓
8. Gap Analysis
    ↓
9. Design Core Skills and Commands
    ↓
10. Design Software Engineering Extension Packs
    ↓
11. Design Five Progressive Example Levels
    ↓
12. Design Evals, Benchmarks and Regression Fixtures
    ↓
13. Generate Six Canonical Specifications
    ↓
14. Design the Public README
    ↓
15. Cross-Project Review
    ↓
16. Scaffold the Repository
    ↓
17. Implement the Core Vertical
    ↓
18. Implement Progressive Coverage and Extension Packs
    ↓
19. Configure and Validate Skill Installation
    ↓
20. Clean External Installation Smoke Test
    ↓
21. Optional Pactwright Integration
    ↓
22. Register and Promote Maturity
    ↓
23. Review Shared Abstraction Candidates
    ↓
MATURE SOFTWARE ENGINEERING SKILLS PROJECT
```

Stages may be refined as domain research exposes missing responsibilities, but later sessions should not collapse major decisions merely to reduce stage count.

---

# 7. Stage 1 — Define Project Goal and Domain Boundary

## Purpose

Define what software engineering production responsibility the repository owns before discussing individual skills.

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
- initial professional-practice sources.

## Activities

- write a short domain charter;
- define owned outcomes and non-goals;
- identify intended users;
- identify cross-domain handoffs;
- identify important human decisions and irreversible/high-risk changes;
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

Exact core skill split, pack dimensions and implementation tooling.

## Exit criteria

The project can explain in one page what it owns and why those responsibilities form a coherent reusable production discipline.

---

# 8. Stage 2 — Research Professional Software Engineering Practice

## Purpose

Model software engineering from durable professional practice rather than current coding-agent capabilities.

## Research areas

Use SWEBOK V4 as a map, then investigate modern practice across at least:

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

## Expected outputs

- professional-practice research notes;
- terminology map;
- role/responsibility map;
- software change lifecycle candidates;
- failure and repair taxonomy candidates;
- evidence-quality model.

## Decisions made

Which practices are durable enough to encode as reusable software-engineering production intelligence.

## Remains provisional

Repository workflow and exact skill boundaries.

## Exit criteria

The production model can be justified from professional practice without referring to a particular LLM or coding agent.

---

# 9. Stage 3 — Model Software Change Types, Contracts and System Context

## Purpose

Introduce the domain-specific model that UI/UX or creative production projects do not need: software work almost always changes a system with existing behavioural and technical contracts.

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

# 10. Stage 4 — Map the Engineering Workflow and Artefacts

## Purpose

Derive the smallest credible end-to-end engineering workflow.

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

# 11. Stage 5 — Define Verification, Risk and Commitment Strategy

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

# 12. Stage 6 — Research Existing AI Skills, Tools and Providers

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

# 13. Stage 7 — Choose the Execution Layer

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

# 14. Stage 8 — Gap Analysis

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

# 15. Stage 9 — Design Core Skills and Commands

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

# 16. Stage 10 — Design Software Engineering Extension Packs

## Purpose

Create first-class reusable specialisations that materially alter software-engineering behaviour without bloating the core.

## Pack dimensions to investigate

### Language / runtime grammar

Examples to research:

```text
TypeScript / Node.js
Java / JVM
Scala
Python
Go
Rust
```

### Framework / ecosystem grammar

Examples:

```text
Spring Boot
React
React Native
Play Framework
FastAPI
Kubernetes-native services
```

### Architecture grammar

Examples:

```text
HTTP API
event-driven systems
stream processing
CLI / developer tooling
libraries / SDKs
serverless
mobile applications
```

### Engineering-risk specialisation

Examples:

```text
secure-development
performance-critical
high-concurrency
data-migration
backward-compatible API evolution
high-reliability services
```

These are candidate dimensions. Research must determine which belong in Extension Packs, which should remain external specialist skills, and which are merely project-specific instructions.

## Pack contract

A valid pack should define:

```text
scope
activation conditions
engineering conventions
architecture or ecosystem assumptions
core-skill behaviour changed
verification changes
quality criteria
references
incompatible assumptions
example prompt
showcase repository/fixture
benchmark cases
```

## Precedence

Target common precedence:

```text
explicit project instructions
→ accepted architecture / public contracts
→ selected Software Engineering Extension Pack
→ core software-engineering defaults
```

A pack must not silently override repository conventions or accepted project architecture.

## Differential evaluation

Every implemented pack must prove:

```text
core
vs
core + pack
```

The comparison should detect meaningful engineering differences, not only vocabulary changes.

## Pack authoring capability

The project should eventually expose a domain-native authoring skill or equivalent workflow:

```text
inspect catalogue
→ determine if an existing pack is sufficient
→ research authoritative ecosystem practice
→ define specialisation boundary
→ define core-skill effects
→ define verification and quality changes
→ implement pack
→ build showcase fixture + exact prompt
→ create behavioural evals
→ compare against core
→ validate and catalogue
```

## Exit criteria

The project can explain what makes a Software Engineering Extension Pack different from a framework prompt, project README or external specialist skill.

---

# 17. Stage 11 — Design Five Progressive Example Levels

## Purpose

Demonstrate progressively broader software-engineering responsibility through real repository changes.

Do not select the final examples by intuition alone.

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
2. research or generate at least 8–12 candidate examples;
3. represent each candidate as a small reproducible repository or fixture;
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

# 18. Stage 12 — Design Evals, Benchmarks and Regression Fixtures

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
```

## Exit criteria

The benchmark can detect incorrect code, poor engineering behaviour and meaningful regressions without pretending those are the same failure.

---

# 19. Stage 13 — Generate Six Canonical Specifications

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
pack dimensions
activation
precedence
core-skill integration
verification changes
pack-aware evaluation
pack packaging
pack authoring
boundaries
```

## Spec 06 — Extension Pack Catalogue

Owns:

```text
curated initial packs
selection rationale
engineering profiles
authoritative references
showcase fixtures
exact prompts
pack-specific evaluation
maturity/status
```

## Exit criteria

Implementation can proceed without inventing core engineering architecture in code.

---

# 20. Stage 14 — Design the Public README

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

The README must show actual repository changes and verification evidence, not only describe hypothetical capabilities.

Every primary example should link to:

```text
starting repository/fixture
exact prompt
resulting change
verification result
explanation of engineering behaviour demonstrated
```

## Exit criteria

A developer can understand, install and try the project from the README without reading the internal specs first.

---

# 21. Stage 15 — Cross-Project Review

Only after the software-engineering architecture exists, compare it with mature Video, Narrative, Music and UI/UX Production Skills.

Look for independently reproduced needs such as:

```text
cheap uncertainty reduction
approved-decision preservation
smallest-sufficient correction
progressive examples
skill-local commands
Extension Pack semantics
pack differential evaluation
clean installation testing
```

Record shared-abstraction candidates using the family evidence format.

Do not immediately extract:

```text
universal workflow engine
universal artefact graph
universal evaluator
universal pack interpreter
universal command runtime
```

## Exit criteria

Cross-domain similarities are documented without weakening software-native terminology or responsibilities.

---

# 22. Stage 16 — Scaffold the Repository

Create only structure justified by the specifications.

Candidate minimum:

```text
software-engineering-skills/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
├── docs/
├── skills/
├── examples/
├── benchmarks/
├── tests/
├── tools/                  # only if deterministic helpers are justified
└── .github/
```

Add Extension Pack surfaces only when they contain working content.

Do not create empty directories for symmetry with creative repositories.

## Exit criteria

A contributor can locate skills, examples, benchmarks and specifications with no speculative architecture in the scaffold.

---

# 23. Stage 17 — Implement the Core Vertical

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

# 24. Stage 18 — Implement Progressive Coverage and Extension Packs

Expand from the proven vertical.

Implement the selected 15 primary examples progressively rather than all at once.

Introduce representative Extension Packs only after the core works without them.

For each implemented pack prove:

```text
core works without pack
core + pack changes intended engineering behaviour
repository/project instructions outrank pack defaults
accepted architecture/contracts outrank pack defaults
pack-aware evaluation recognises valid specialisation
pack authoring can create or revise a valid pack
```

Every implemented catalogue pack must include:

```text
showcase fixture
exact prompt
observable specialised behaviour
behavioural evals
core-vs-pack comparison
```

## Exit criteria

The project demonstrates broad engineering responsibility and specialisation rather than only one polished fixture.

---

# 25. Stage 19 — Configure and Validate Skill Installation

Define canonical installation with the Agent Skills CLI.

Validate:

```text
full installation
selective installation
skill self-containment
skill-local references
skill-local scripts
no undocumented repository-relative runtime dependencies
provider/tool prerequisites
README commands
```

Local source-repository validation remains separate from consumer installation.

## Exit criteria

Every advertised skill can be installed selectively into a local test consumer and discovered by the target coding agent.

---

# 26. Stage 20 — Clean External Installation Smoke Test

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
```

The smoke test should expose accidental assumptions about source-repository paths or developer machine state.

## Exit criteria

The project works as an installable Agent Skills product, not only from its own checkout.

---

# 27. Stage 21 — Optional Pactwright Integration

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

# 28. Stage 22 — Register and Promote Maturity

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

Promotion is based on demonstrated behaviour.

For `mature`, require at least:

```text
core workflow works end to end
six spec responsibilities represented
public README accurately reflects implementation
5 × 3 primary examples represented
primary examples include exact prompts
domain benchmark operational
regression fixtures operational
Extension Pack architecture and catalogue represented
implemented packs have showcases and behavioural evals
pack-authoring capability exists
core remains useful without packs
clean consumer installation passes
quality claims are measured or explicitly marked unmeasured
```

---

# 29. Stage 23 — Review Shared Abstraction Candidates

After implementation evidence exists, apply `shared-abstraction-process.md`.

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

## Exit criteria

The project contributes reusable family evidence without creating a central software-production runtime.

---

# 30. Initial Research Questions for Later Stages

The following questions should be answered by the staged bootstrap rather than assumed now.

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

# 31. Early Over-Engineering Risks

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

# 32. Success Criterion

A successful `software-engineering-skills` bootstrap is not a generic coding checklist with Production Skills terminology added.

It should encode enough software-specific research questions, change semantics, contract preservation, verification strategy, repair behaviour, Extension Pack design, example discovery and benchmark architecture that later sessions can execute one stage at a time without redesigning the project from scratch.

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

Do not scaffold `software-engineering-skills` while generating this bootstrap specification. The bootstrap defines how the repository will be created.
