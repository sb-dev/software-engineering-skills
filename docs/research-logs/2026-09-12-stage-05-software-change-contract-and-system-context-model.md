# Stage 5 — Software Change, Contract and System Context Model

**Project:** `software-engineering-skills`  
**Bootstrap stage:** 5 — Model Software Change Types, Contracts and System Context  
**Status:** Complete  
**Date:** 12 September 2026  
**Input domain model:** `software-engineering-domain-model-r1`  
**Change model revision:** `software-change-model-r1`

## 1. Stage purpose

This stage turns the evidence-qualified Software Engineering model into a reusable way to reason about **what kind of software change is being made, what must be preserved, and what system evidence must be discovered before editing**.

The output is not the final engineering workflow and is not a universal repository graph.

The model separates five questions:

```text
What is the intended change?
What effective contracts can the change affect?
What system context must be discovered?
What impact is supported by evidence versus still unknown?
What risk characteristics should influence later verification and approval?
```

The core idea is:

> A software change is defined not only by the files it edits, but by the behaviour, contracts, state, runtime assumptions and release relationships that can change as a consequence.

---

## 2. Governing evidence

### Repository evidence

This stage is derived primarily from:

- [`2026-09-12-stage-01-project-goal-and-domain-boundary.md`](2026-09-12-stage-01-project-goal-and-domain-boundary.md)
- [`2026-09-12-stage-03-five-book-extraction-and-reconciliation.md`](2026-09-12-stage-03-five-book-extraction-and-reconciliation.md)
- [`2026-09-12-stage-04-professional-software-engineering-challenge.md`](2026-09-12-stage-04-professional-software-engineering-challenge.md)
- [`2026-09-07-software-engineering-skills-new-project-bootstrap-process.md`](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md)

Stage 4 is the authority for the evidence-qualified domain model. The five-book corpus remains useful supporting evidence but is not independently authoritative.

### Additional bounded contract research

Stage 5 checked current authoritative specifications only where they materially sharpen the contract model:

- Semantic Versioning 2.0.0 — https://semver.org/
- Protocol Buffers language guide — https://protobuf.dev/programming-guides/proto3/
- Protocol Buffers best practices — https://protobuf.dev/best-practices/dos-donts/
- OpenAPI Specification 3.2.1 — https://spec.openapis.org/oas/latest.html
- SLSA v1.2 provenance — https://slsa.dev/spec/v1.2/provenance

These sources reinforce several Stage 4 conclusions:

- compatibility only has meaning relative to a declared or effective contract;
- old and new versions often coexist even when teams intend a coordinated update;
- wire/schema evolution has representation-specific compatibility rules;
- public API versioning does not substitute for testing actual consumer behaviour;
- release artefacts have provenance and build relationships that can themselves be part of release evidence.

No source above is treated as a universal software architecture or lifecycle method.

---

# 3. Modelling principles

## 3.1 Do not infer change class from filenames

The same edited file can represent very different changes.

Examples:

```text
schema.sql
→ additive online migration
→ destructive cleanup
→ performance index change
→ security permission change

application.yaml
→ harmless test configuration
→ production endpoint change
→ authentication-control change
→ load / retry change

Foo.java
→ bug repair
→ refactor
→ API break
→ concurrency repair
```

Classification starts from **intended effect and affected contracts**, then uses repository evidence to confirm implementation scope.

## 3.2 Change classes are not mutually exclusive

A task should have a **primary change intent** plus zero or more material modifiers.

Example:

```text
Primary intent:
  dependency/platform upgrade

Modifiers:
  security-sensitive
  public API compatibility
  performance-sensitive
  mixed-version rollout
  build provenance affected
```

This is more useful than choosing one label and hiding the rest.

## 3.3 Contracts are effective, not merely documented

A declared contract is important, but software users can depend on observable behaviour that documentation does not mention.

Therefore contract discovery should distinguish:

```text
declared contract
observed / executable contract
consumer dependency
project convention
accidental behaviour with no evidence of dependency
unknown
```

An undocumented behaviour is not automatically a promise, but it is not automatically safe to break either.

## 3.4 Compatibility is a relationship, not a contract type

“Backward compatible” is too vague without saying:

```text
which contract?
which two versions?
which producer / consumer direction?
which runtime period?
which semantic expectations?
```

The model therefore records specific compatibility relationships instead of using compatibility as a catch-all category.

## 3.5 Preserve the smallest coherent set of invariants

The default is not “nothing may change.” The default is:

```text
change exactly the intended behaviour / quality / structure
while preserving the relevant unaffected contracts and invariants
```

Different change types intentionally preserve different things.

## 3.6 Uncertainty is part of impact

Unknown consumers, missing tests, missing runtime evidence and unclear ownership are not “no impact.” They are **unresolved impact** and should increase later verification or approval requirements.

## 3.7 System context is discovered on demand

Do not build or maintain a universal system graph merely because graph-shaped information exists.

The system-context model is an investigation frame. Persist a graph only if a consuming project has an independent reason to maintain one.

---

# 4. Software change taxonomy

The core taxonomy contains **15 primary change intents**.

A task can carry several secondary intents, but one primary intent should answer:

> If this work succeeds, what material property of the software is intentionally different?

## CH-01 — Additive behaviour / feature change

**Intent:** introduce new user-visible or system-visible behaviour while preserving unaffected existing behaviour.

Typical examples:

- new endpoint;
- new command;
- new business rule;
- new event producer;
- new application capability;
- new optional field or feature flag.

Primary preservation concerns:

```text
existing behaviour
existing consumers
existing data
security properties
performance / reliability budgets where relevant
release path
```

Common failure:

- the “addition” silently modifies an existing semantic contract;
- scope expands into unrelated redesign;
- acceptance is unclear and implementation invents product policy.

## CH-02 — Corrective bug repair

**Intent:** make behaviour conform to the intended or accepted contract where current behaviour is defective.

Primary preservation concern:

> Change the defective behaviour while preserving surrounding behaviour that was not part of the defect.

Required distinction:

```text
observed behaviour
versus
intended behaviour
```

When intended behaviour is ambiguous, the task is blocked on an acceptance or product decision rather than being “just a bug fix.”

Typical evidence:

- reproducer;
- failing regression test;
- runtime trace/log/metric;
- historical change/bisect evidence;
- accepted expected behaviour.

## CH-03 — Behaviour-preserving refactor

**Intent:** alter structure, design or internal implementation without intentionally changing externally relevant behaviour.

Typical examples:

- extract module/class/function;
- remove duplication;
- replace internal algorithm with equivalent behaviour;
- simplify dependency structure;
- improve testability.

Preserve unless explicitly reopened:

```text
functional semantics
public contracts
persistent data semantics
security properties
reliability semantics
material performance budgets
```

A refactor that intentionally changes semantics is not only a refactor; reclassify the semantic portion separately.

## CH-04 — Interface / API / contract evolution

**Intent:** add, change, deprecate, version or remove an interface consumed outside the immediate implementation boundary.

Applies to:

- service APIs;
- library APIs;
- events/messages;
- CLI interfaces;
- configuration schemas;
- plugin interfaces;
- extension points.

This class requires explicit compatibility reasoning because the changed artefact is itself a contract surface.

Key questions:

```text
Who consumes it?
Which contract dimensions are changing?
Will old and new versions coexist?
Can consumers migrate atomically?
What is the deprecation/removal path?
```

## CH-05 — Persistent data / schema migration

**Intent:** change persistent representation, data shape, storage semantics or invariants.

Examples:

- relational schema evolution;
- document structure migration;
- event-store representation change;
- index/backfill work;
- data correction;
- storage-engine transition.

Preservation concerns:

```text
data integrity
application compatibility
mixed-version access
availability
migration resumability
recovery / restore
retention / privacy requirements
```

Destructive or lossy transformations are consequential changes even if the code diff is tiny.

## CH-06 — Dependency / platform / runtime upgrade

**Intent:** adapt software to a new version or replacement of a dependency, language, runtime, operating system, framework, SDK, managed service or platform.

Examples:

- Java/runtime upgrade;
- framework major version;
- database engine upgrade;
- library replacement;
- container base-image change;
- package dependency update.

Primary risks:

```text
source/API incompatibility
binary incompatibility
wire/semantic behaviour change
transitive dependencies
build/release changes
performance changes
security/provenance changes
```

A security-driven dependency upgrade should be primary CH-06 with CH-09 as a material modifier when the immediate production goal is dependency replacement, or primary CH-09 when remediation of exposure is the central objective.

## CH-07 — Performance / resource behaviour change

**Intent:** materially alter latency, throughput, memory, CPU, I/O, storage, network usage or capacity behaviour while preserving required functional semantics.

The contract is the measurable workload/budget, not “make it faster.”

Required evidence pattern:

```text
representative workload
→ baseline
→ profile / bottleneck evidence
→ bounded change
→ equivalent re-measurement
```

A performance change can become architectural when the necessary improvement requires changing topology, data ownership or communication patterns.

## CH-08 — Concurrency / ordering / consistency repair

**Intent:** change synchronization, ordering, atomicity or coordination to preserve a required invariant under concurrent execution.

Typical invariant failures:

- race;
- lost update;
- atomicity violation;
- ordering violation;
- deadlock/livelock;
- starvation;
- duplicate execution;
- unsafe publication;
- unbounded concurrency.

A change that merely reduces the probability of reproducing the problem is not sufficient evidence.

## CH-09 — Security / trust-control change

**Intent:** alter a security property, trust boundary or control, or repair a vulnerability.

Examples:

- authentication/authorisation change;
- tenant isolation;
- input-validation control;
- secret handling;
- dependency vulnerability remediation;
- cryptographic integration;
- permission/policy change;
- sandboxing or privilege reduction.

Material security changes often require specialist review. The generic core must not claim specialist cryptographic or adversarial assurance.

## CH-10 — Reliability / resilience change

**Intent:** change failure behaviour so faults remain bounded or recovery improves.

Examples:

- timeout policy;
- retry/idempotency behaviour;
- circuit breaking;
- load shedding;
- backpressure;
- failure isolation;
- degraded mode;
- recovery/restart behaviour.

The mechanism may live in application code, client libraries, runtime, service mesh or managed platform. Avoid duplicate/conflicting resilience controls.

## CH-11 — Observability / operability change

**Intent:** change diagnostic visibility or software-level operational behaviour without necessarily changing user functionality.

Examples:

- logs/metrics/traces/profiles;
- correlation identifiers;
- health/readiness semantics;
- diagnostic endpoint;
- runtime status exposure;
- domain-specific diagnostic events.

Important distinction:

> Telemetry may itself be a contract when alerts, dashboards, automation or consumers depend on signal names, labels or semantics.

Renaming a metric can therefore be a breaking change even when application behaviour is otherwise unchanged.

## CH-12 — Configuration / build / packaging / release change

**Intent:** change the way software is configured, built, packaged, promoted or made releasable.

Examples:

- build definition;
- CI release workflow;
- environment configuration schema;
- packaging metadata;
- container build;
- signing/provenance policy;
- feature-flag rollout configuration;
- release candidate composition.

This is a software change because production behaviour can change through configuration and release machinery even with no source-code change.

## CH-13 — Decommissioning / removal

**Intent:** remove behaviour, interface, data, dependency, service or obsolete path.

Typical work:

```text
prove or bound remaining usage
migrate consumers
prevent backsliding
remove implementation
remove configuration/data/infrastructure
verify no required contract remains
```

Removal is frequently more consequential than addition because the target may have unknown consumers or historical data.

## CH-14 — Architecture migration

**Intent:** materially change structural boundaries, topology, ownership, deployment units, communication model or persistence architecture.

Examples:

- monolith modularisation;
- service extraction/merge;
- event-driven migration;
- database ownership split;
- synchronous/asynchronous redesign;
- platform topology transition.

Architecture migration is not “large refactoring” by default. It requires explicit quality/constraint rationale and usually a staged coexistence model.

## CH-15 — Engineering-support / verification-system change

**Intent:** change developer-facing engineering systems used to construct, validate or maintain software while preserving intended production semantics.

Examples:

- test-harness redesign;
- static-analysis configuration;
- code generator;
- repository automation;
- developer CLI/tooling;
- CI test selection;
- fixture or simulator infrastructure.

This class exists because the project owns engineering quality, not only production source code.

A test-only diff can still be high risk if it weakens the oracle that provides release evidence.

---

# 5. Change modifiers

Primary change intent is not enough. Record material modifiers when they affect preservation, verification or authority.

## 5.1 External visibility

```text
internal-only
team/repository-visible
known external consumers
public ecosystem
unknown consumers possible
```

## 5.2 State impact

```text
stateless
ephemeral state
persistent reversible state
persistent migration
lossy / destructive state change
```

## 5.3 Rollout relationship

```text
atomic replacement
mixed versions possible
rolling deployment
consumer/provider versions independent
long-lived persisted representation
offline migration window
```

Protocol Buffers guidance is a useful concrete reminder: clients and servers are not actually updated at exactly the same time, and rollback can reintroduce older binaries. The reusable model therefore assumes coexistence whenever evidence does not prove atomic replacement.

## 5.4 Reversibility

```text
trivially revertible
revertible with migration
recoverable from backup/replay
hard to reverse
irreversible
unknown
```

## 5.5 Runtime criticality

```text
non-runtime artefact
non-critical runtime path
user-facing critical path
shared infrastructure path
safety / high-assurance path
```

## 5.6 Security sensitivity

```text
no material security surface identified
input/trust boundary touched
authentication/authorisation touched
secrets/cryptography/isolation touched
known vulnerability remediation
```

## 5.7 Performance / capacity sensitivity

```text
not material
budget exists
hot path
high fan-out / high volume
capacity boundary
```

## 5.8 Concurrency / distribution

```text
single-threaded/local
concurrent shared state
distributed coordination
asynchronous/eventual consistency
cross-region / partition-sensitive
```

## 5.9 Supply-chain / build trust

```text
first-party source only
new external dependency
build platform change
artifact-signing/provenance change
unverified origin
```

## 5.10 Evidence uncertainty

```text
contracts and consumers well evidenced
some inferred consumers
runtime behaviour weakly evidenced
unknown consumers
missing rollback evidence
missing representative test environment
```

Uncertainty is a modifier in its own right and should not be silently interpreted as low risk.

---

# 6. Maintenance-mode overlay

Stage 1 treats maintenance as first-class. Maintenance mode and change intent describe different dimensions.

| Maintenance mode | Meaning | Example primary change class |
| --- | --- | --- |
| Corrective | repair a defect | CH-02 bug repair |
| Adaptive | respond to external environment/platform change | CH-06 platform upgrade |
| Additive | add capability to an existing system | CH-01 feature |
| Perfective | improve quality while retaining intended function | CH-03 refactor, CH-07 performance |
| Preventive | reduce evidenced future risk | CH-09 security, CH-13 decommission, CH-15 verification |
| Emergency | contain/restore acceptable behaviour urgently | any class, with emergency modifier |

Do not infer risk or verification solely from the maintenance label.

---

# 7. Contract taxonomy

A **contract** is any externally or internally depended-upon property that a change must preserve, intentionally evolve, or explicitly retire.

The contract can be documented, executable, observed or inferred from known consumers.

## CT-01 — User-visible behavioural contract

Includes:

- functional behaviour;
- user-visible state transitions;
- externally observable errors;
- workflow semantics;
- output content and meaning.

UI/UX design ownership remains adjacent, but faithful software behaviour is an engineering contract.

## CT-02 — Service / API semantic contract

Includes:

- operations/endpoints;
- request/response shapes;
- status/error semantics;
- idempotency expectations;
- pagination/filter/order semantics;
- authentication requirements;
- side effects;
- lifecycle/deprecation promises.

An OpenAPI document can describe parts of this contract, but machine-readable syntax alone rarely captures every semantic dependency.

## CT-03 — Library / package interface contract

Potential dimensions:

```text
source compatibility
binary / ABI compatibility
public symbols and types
behavioural semantics
exception/error behaviour
thread-safety guarantees
supported runtime/platform versions
```

Semantic Versioning is useful only after the package has a clear public API. A version number does not itself establish that the implementation is compatible.

## CT-04 — Message / event contract

Includes both representation and semantics:

```text
field/schema shape
field identifiers
meaning of fields
producer/consumer responsibilities
ordering
partitioning/keying assumptions
delivery semantics
deduplication/idempotency expectations
retention/replay assumptions
```

Protocol Buffer compatibility guidance demonstrates why representation-specific rules matter: field numbers must not be casually reused, deleted identifiers should be reserved, and even apparently parseable type changes may be unsafe to roll out.

## CT-05 — Persisted data / schema / invariant contract

Includes:

- schema;
- persisted representation;
- constraints/invariants;
- identifiers;
- interpretation of historical records;
- ownership/source-of-truth rules;
- retention and deletion semantics;
- migration/recovery assumptions.

The contract can outlive the software version that wrote the data.

## CT-06 — CLI contract

Includes when externally depended upon:

```text
command names
arguments/options
stdin/stdout/stderr behaviour
exit codes
machine-readable output
filesystem effects
configuration lookup
shell/script compatibility
```

Changing human-readable formatting can still be breaking when scripts parse it despite contrary documentation; consumer evidence determines risk.

## CT-07 — Configuration contract

Includes:

- keys and types;
- defaults;
- required/optional fields;
- precedence rules;
- environment variables;
- dynamic versus restart-required behaviour;
- secret references;
- feature-flag semantics;
- invalid-value handling.

Configuration is executable system input, not incidental text.

## CT-08 — Wire / serialization / protocol contract

Includes:

```text
encoding
field/tag identities
framing
negotiation/versioning
unknown-field handling
canonicalisation assumptions
protocol state machine
```

This contract may differ from an API's source-level interface.

## CT-09 — Performance / resource contract

Examples:

- latency percentile budget;
- throughput under stated load;
- memory/CPU/storage ceiling;
- startup time;
- payload size;
- target-device constraints;
- batch completion window.

Thresholds are project-specific facts. The reusable knowledge is how to discover, measure and preserve them.

## CT-10 — Security / trust contract

Includes properties such as:

```text
identity/authentication
permission/authorisation
confidentiality
integrity
tenant isolation
secret handling
input trust boundaries
cryptographic protocol expectations
supply-chain trust
```

Security properties often do not appear as ordinary API types, but breaking them can be more consequential than a functional API break.

## CT-11 — Reliability / failure-semantics contract

Includes:

- availability/recovery assumptions;
- timeout expectations;
- idempotency;
- retry ownership;
- duplicate handling;
- partial-failure behaviour;
- ordering/durability guarantees;
- SLO or reliability assumptions where the project defines them.

SLO thresholds remain consuming-project context, not universal core policy.

## CT-12 — Build / package / runtime compatibility contract

Includes:

```text
build inputs
compiler/runtime versions
package format
artefact layout
platform/OS compatibility
container/runtime assumptions
dependency lock state
reproducibility expectations
signatures/provenance
```

SLSA provenance is one current mechanism for expressing verifiable information about where, when and how an artefact was produced. The core should understand provenance evidence without requiring SLSA for every project.

## CT-13 — Observability / diagnostic contract

Telemetry becomes a contract when humans or systems depend on it.

Examples:

- metric names/labels/units;
- log event identifiers/fields;
- trace attribute semantics;
- health/readiness endpoints;
- alert predicates;
- support/debugging diagnostic output.

Do not treat all logging text as public API. Determine whether there is a dependent consumer or operational process.

---

# 8. Cross-cutting contract relationships

Several important concepts are **relationships over contract types**, not additional contract types.

## 8.1 Compatibility relationship

For each material change, record the exact pair being compared.

Prefer statements like:

```text
old client → new server: compatible
new client → old server: not compatible
old reader → new persisted record: compatible
new reader → old record: compatible
old CLI script → new CLI output: unknown
```

Avoid:

```text
“backward compatible”
```

without direction and contract type.

### Compatibility state

Use qualitative states:

```text
preserved
additive / compatible
conditionally compatible
migration required
breaking by intent
unknown
```

No global numeric compatibility score is justified.

## 8.2 Coexistence relationship

Ask whether two versions or representations must operate at the same time.

Examples:

- old/new service binaries during rolling deployment;
- old/new mobile clients against one server;
- historical/new persisted records;
- old/new event consumers;
- old/new schema during backfill.

If coexistence is possible, design and verification must cover it unless a project-specific mechanism proves it cannot occur.

## 8.3 Deprecation relationship

Deprecation has at least four states:

```text
supported
new use discouraged / blocked
migration in progress
removed
```

A warning without ownership and migration completion is not decommissioning.

## 8.4 Transition / migration relationship

For non-atomic changes capture:

```text
initial state
compatible bridge state
migration/backfill
consumer transition
removal/cleanup state
rollback/recovery boundary
```

This pattern generalises across APIs, schemas, events, dependencies and architecture migrations.

---

# 9. Preservation model by change class

This table states the **default preservation target**. A consuming project can intentionally reopen any item with explicit authority and evidence.

| Change class | Intended change | Preserve by default | Typical special evidence |
| --- | --- | --- | --- |
| CH-01 Additive behaviour | new behaviour | existing behaviour/contracts/data/security/release path | acceptance + affected regression/integration |
| CH-02 Bug repair | incorrect behaviour | unaffected semantics and effective contracts | reproducer + focused regression |
| CH-03 Refactor | internal structure | external behaviour + relevant quality budgets | characterisation/contract/static evidence |
| CH-04 Interface evolution | contract surface | unaffected contract dimensions; coexistence where needed | consumer/compatibility/migration evidence |
| CH-05 Data/schema | representation/state | logical data/invariants + version coexistence + recoverability | migration rehearsal/invariant checks |
| CH-06 Dependency/platform | underlying dependency | owned external semantics, supported runtime path | compatibility/build/integration/provenance |
| CH-07 Performance | resource/time behaviour | functional/security/data correctness | controlled benchmark/profile |
| CH-08 Concurrency | ordering/synchronisation | functional semantics and liveness/safety invariants | race/stress/invariant evidence |
| CH-09 Security | security control/property | required business semantics + adjacent controls | threat/abuse case + specialist evidence as needed |
| CH-10 Reliability | failure behaviour | normal-path correctness + data/security | fault/overload/recovery evidence |
| CH-11 Observability | diagnostics | user semantics; existing telemetry consumers if contractual | consumer/alert/dashboard compatibility |
| CH-12 Config/build/release | configuration/delivery behaviour | tested artefact semantics and promotion integrity | build/config/artefact provenance + smoke |
| CH-13 Removal | chosen old contract/path | all non-target behaviour; migration commitments | usage evidence + migration completion |
| CH-14 Architecture migration | structure/topology | external semantics unless explicitly changed + target qualities | staged coexistence + characteristic evidence |
| CH-15 Engineering support | verification/developer system | production semantics + strength of existing oracle | self-tests / known-defect detection / workflow validation |

---

# 10. System-context model

Before editing, discover only the context needed to answer the change's preservation and risk questions.

The model has **13 evidence surfaces**.

## SC-01 — Repository topology

Discover:

```text
modules/packages/workspaces
source/test/config/docs locations
generated code boundaries
vendored/external code
repository-local ownership markers
```

Do not infer architecture solely from directory names.

## SC-02 — Build and package system

Discover:

- build entry points;
- dependency declarations/locks;
- compilation/type/static-analysis steps;
- generated sources;
- package/container output;
- reproducibility/cache assumptions;
- supported runtime/toolchain versions.

## SC-03 — Executable entry points

Discover how the relevant software actually starts or is invoked:

- service/application main entry;
- request handlers;
- jobs/workers;
- CLI entry;
- event consumers/producers;
- plugin/load points;
- library exported surface.

## SC-04 — Module and architecture boundaries

Discover evidence for:

```text
logical components
public/internal boundaries
dependency direction
data ownership
deployment units
architecture constraints
```

Use code, build dependencies, interfaces, ADRs/design docs and runtime topology together.

## SC-05 — Ownership / authority boundaries

Discover where available:

- code/service owners;
- API/data owners;
- security/platform owners;
- decision authority for breaking changes;
- standing release/deployment authority.

Missing ownership is an impact uncertainty, not permission.

## SC-06 — Dependency graph

Inspect:

```text
direct dependencies
transitive dependencies relevant to the change
runtime integrations
version constraints
internal call relationships
external services/platforms
```

Do not enumerate the entire dependency universe if only one bounded slice matters.

## SC-07 — Call, event and data flow

Trace the relevant path far enough to identify:

- change point;
- callers/producers;
- consumers/callees;
- persisted state;
- side effects;
- asynchronous boundaries;
- failure propagation;
- interception/verification points.

## SC-08 — Existing verification evidence

Discover:

```text
unit/component/contract/integration/system tests
static analysis/type checks
fixtures/simulators
benchmarks/load tests
security checks
race/concurrency checks
release smoke/probers
known test gaps/flakiness
```

A test's existence is weaker evidence than proof that it detects the relevant failure.

## SC-09 — Runtime configuration and environment

Discover:

- configuration sources and precedence;
- environment variables;
- feature flags;
- secrets references;
- environment-specific dependencies;
- runtime limits/timeouts/resources;
- target platform differences.

## SC-10 — Effective contracts and consumers

Discover the CT-01–CT-13 contracts relevant to the change using:

```text
specifications
public interfaces
schemas
code search
consumer repositories where available
usage telemetry
compatibility tests
runtime traces
support/deprecation records
```

Unknown consumers must remain explicit.

## SC-11 — Architecture decisions and constraints

Look for:

- ADRs;
- design docs;
- architecture tests/fitness checks;
- explicit invariants;
- prior migration rationale;
- constraints imposed by platform or adjacent domains.

Do not blindly obey stale documents when executable evidence contradicts them; surface the mismatch.

## SC-12 — Observability and security-sensitive surfaces

Discover only what is relevant:

```text
logs/metrics/traces/profiles
health/readiness
trust boundaries
authn/authz
sensitive data
secrets
external input surfaces
dependency/provenance controls
```

## SC-13 — Release / promotion model

Discover:

- branch/source revision relationship;
- build artefact identity;
- configuration promotion;
- deployment/distribution targets;
- mixed-version possibility;
- migration ordering;
- rollback/recovery;
- release authority;
- package/app-store/library/service-specific release rules.

---

# 11. Evidence-strength model for system context

Each material impact statement should carry an evidence state.

## Confirmed

Direct evidence establishes the relationship.

Examples:

- code/build dependency;
- schema definition;
- runtime trace;
- known consumer test;
- explicit configuration;
- current owner/ADR;
- production usage telemetry.

## Strongly inferred

Several reliable artefacts imply the relationship, but it has not been directly observed.

Example:

- static call path plus build dependency but no runtime trace.

## Weakly inferred

Filename, naming, stale documentation or convention suggests a relationship without executable corroboration.

Do not base consequential change decisions on weak inference alone when stronger evidence is reasonably obtainable.

## Unknown

The question remains unresolved.

Examples:

- public API with no consumer inventory;
- event schema with unknown historical consumers;
- rollback plan never exercised;
- undocumented production configuration.

Unknown is a first-class output.

## Conflicting

Evidence sources disagree.

Example:

```text
ADR says service A owns data
runtime/config shows service B writes it directly
```

Resolve or explicitly carry the conflict before a high-consequence change.

---

# 12. Change-impact model

The impact model is a bounded, evidence-labelled map created for a proposed change.

## 12.1 Impact dimensions

Assess only applicable dimensions, but do not skip one merely because no source file is obviously associated with it.

| Dimension | Question |
| --- | --- |
| Behaviour | What observable behaviour intentionally changes and what should remain invariant? |
| Code/structure | Which implementation/module boundaries change? |
| Consumers | Which callers/users/systems may depend on affected behaviour? |
| Dependencies | Which upstream/downstream/internal/external dependencies are involved? |
| Data | What state, schema, invariant or historical representation is affected? |
| Configuration | Which keys/defaults/flags/environment assumptions change? |
| Runtime | Which topology, resource, concurrency or failure behaviour changes? |
| Security | Which trust boundaries, identities, permissions, secrets or vulnerable dependencies are touched? |
| Performance | Which workload/resource budgets could move? |
| Reliability | Which failure/recovery/idempotency/retry semantics could move? |
| Observability | Which diagnostic signals or telemetry consumers change? |
| Build/release | Which build/package/provenance/promotion/migration/rollback relationships change? |
| Ownership/authority | Who owns affected contracts and which decisions require approval? |
| Verification | Which existing evidence can detect regressions, and what evidence is missing? |

## 12.2 Bounded impact expansion

Start from the proposed change point and expand until the relevant contract boundary is understood.

```text
change intent
→ candidate change point
→ direct effects
→ relevant contract(s)
→ known consumers / state / runtime dependencies
→ release / migration relationship
→ verification boundary
```

Stop expanding when:

- additional nodes cannot affect an identified contract/risk dimension; or
- the next boundary belongs to an adjacent owner and the required handoff is clear.

Do not recursively map the entire organisation.

## 12.3 Impact record

A lightweight record may contain:

```text
primary change class
material modifiers
intended changed property
contracts to preserve/evolve/retire
affected components
known consumers/producers
state/data impact
runtime/release impact
security/performance/reliability impact
evidence strengths
unknowns
required authority/handoffs
candidate verification surfaces
```

This is a candidate artefact for Stage 6, not a mandatory document for every code edit.

---

# 13. System-inspection checklist / command hypothesis

Stage 6/11 may eventually encode this as one or several skills/commands. Stage 5 defines only the behavioural hypothesis.

## Candidate inspection sequence

```text
1. establish change intent and likely primary class
2. inspect repository/build entry points
3. locate executable path and relevant module boundary
4. inspect existing tests and current behaviour
5. trace direct call/event/data effects
6. identify effective contracts and known consumers
7. inspect data/config/runtime/security surfaces when applicable
8. inspect release/migration/coexistence model
9. record evidence strength and unresolved unknowns
10. classify whether local change is sufficient or structural decision is needed
```

This sequence is **cheap-first** and collapsible.

A one-line internal implementation fix may require only steps 1–5 and 9–10. A schema or public API migration may require every step.

## Inspection output hypothesis

The minimum useful output is not a prose report. It is enough evidence to answer:

```text
where should the change be made?
what must be preserved?
what can break?
what remains unknown?
what evidence can verify the change?
who must decide if a consequential contract changes?
```

---

# 14. Risk-classification candidates

Stage 7 owns the final verification/risk/commitment strategy. This stage identifies the inputs that such a strategy should use.

No universal numeric risk score is justified.

## 14.1 Risk drivers

### Contract exposure

- internal implementation only;
- shared internal contract;
- known external consumers;
- public/unknown consumers.

### State consequence

- no persistent state;
- reversible state update;
- migration/backfill;
- destructive/lossy data.

### Reversibility / recovery

- immediate revert;
- rollback with migration;
- restore/replay required;
- hard/irreversible;
- untested/unknown recovery.

### Blast radius

- one local component;
- multiple modules/services;
- shared library/platform;
- broad public or organisation-wide surface.

### Security consequence

- no material security effect;
- trust/input boundary;
- authn/authz/secret/isolation;
- cryptography/high-risk security control;
- active vulnerability/exposure.

### Runtime/concurrency consequence

- offline/local;
- user-facing runtime;
- concurrency/shared state;
- distributed coordination;
- high-volume/shared critical path.

### Migration/coexistence complexity

- atomic replacement;
- short mixed-version window;
- independent consumers/providers;
- long-lived historical data or clients;
- unknown coexistence.

### Evidence uncertainty

- strong existing verification;
- partial evidence;
- weak oracle;
- unknown consumers;
- missing production-like evidence.

### Supply-chain / platform consequence

- no external/build trust change;
- dependency update;
- new dependency/vendor;
- build platform/provenance/signing change;
- untrusted/unsupported source.

## 14.2 Candidate qualitative bands

These are policy candidates, not final Stage 7 definitions.

### Local / routine

Typical profile:

```text
bounded internal surface
reversible
no persistent/destructive data change
no material security/trust change
strong local verification
known ownership
```

Likely behaviour:

- focused verification;
- normal review policy;
- no special approval beyond repository/project policy.

### Cross-boundary / elevated

Typical triggers:

```text
shared interface
mixed versions
data migration
performance/concurrency change
external dependency/platform change
cross-service behaviour
weak consumer evidence
```

Likely behaviour:

- explicit impact record;
- broader/specialist verification;
- owner review;
- migration/rollback evidence where applicable.

### Consequential

Any of the following may independently place a change here:

```text
intentional external breaking change
destructive/lossy data
material authn/authz/isolation/secret change
irreversible operation
large architecture commitment
known quality/security waiver
production action outside standing policy
unknown consumer surface with high potential blast radius
```

Likely behaviour:

- explicit authority before commitment;
- stronger representative evidence;
- rollback/recovery or accepted irreversibility;
- specialist review when required.

### Specialist / high-assurance

Examples:

- safety-critical regulated software;
- cryptographic primitive design;
- formal-certification domain;
- kernel/low-level changes where general evidence is inadequate;
- other domains explicitly requiring specialist standards.

Core behaviour:

> Handoff or activate a domain-specific pack; do not pretend generic Software Engineering Skills are sufficient assurance.

## 14.3 Escalation rule candidate

Risk is governed by the **strongest applicable driver**, not an average.

A tiny one-line authorisation bug can be consequential. A thousand-line generated mechanical refactor may be lower risk if its behaviour and verification are well bounded.

---

# 15. Worked classification examples

These examples test the model; they are not final benchmarks.

## Example A — Add an optional response field

```text
Primary class: CH-04 Interface/API evolution
Secondary intent: CH-01 Additive behaviour
Contracts: CT-02 API semantic, possibly CT-08 wire
Modifiers: external consumers; mixed versions
```

Questions:

- do old clients ignore the field?
- do serializers/validators reject unknown fields?
- does the field alter response size/performance materially?
- is the OpenAPI/schema updated?

Default target: additive compatibility with old consumers.

## Example B — Rename a production metric

```text
Primary class: CH-11 Observability
Contracts: CT-13 diagnostic contract
Modifiers: unknown dashboard/alert consumers
```

The application API may be unchanged, but the operational change can still be breaking.

Safe options include dual-emission or consumer migration before removal where cost justifies it.

## Example C — Upgrade a dependency to remediate a CVE

```text
Primary class: CH-06 Dependency upgrade
Modifier: CH-09 security-sensitive
Contracts: CT-03/CT-12 + affected application contracts
```

Inspect:

- vulnerable version reachability/exposure;
- transitive graph;
- release provenance;
- API/behaviour changes;
- supported runtime;
- regression/security evidence.

## Example D — Rename and split a database column during rolling deployment

```text
Primary class: CH-05 Data/schema migration
Secondary: CH-04 contract evolution
Contracts: CT-05 persisted data + application/API contracts
Modifiers: mixed versions, persistent state, rollback complexity
```

Direct rename is unsafe when old and new application versions can coexist.

Model a bridge/migration/removal sequence and verify both old/new access paths during transition.

## Example E — Refactor an untested legacy method

```text
Primary class: CH-03 refactor
Contracts: CT-01 effective behaviour, possibly CT-02/03
Modifier: evidence uncertainty
```

Before editing:

- identify affected behaviour;
- find the cheapest adequate feedback boundary;
- add characterisation or higher-level contract evidence if it materially reduces risk;
- do not define the entire codebase as “legacy” merely because one unit lacks tests.

## Example F — Change a retry policy

```text
Primary class: CH-10 reliability/resilience
Contracts: CT-11 failure semantics, CT-09 performance/resource
Modifiers: distributed system, overload risk
```

Inspect retry ownership across layers before adding another retry. Evidence should include failure/overload behaviour, not only happy-path tests.

## Example G — Change the CI test-selection algorithm

```text
Primary class: CH-15 engineering-support
Contracts: release evidence + CT-12 build/release
Modifier: broad repository blast radius
```

Production code is untouched, but the change can weaken the oracle that keeps releases safe. Validate against known affected/unaffected changes and preserve a fallback path.

---

# 16. Decisions made

Stage 5 establishes the following model decisions:

1. Software changes are classified by **intended effect**, not by filenames or repository location.
2. The taxonomy uses one primary change intent plus material secondary intents/modifiers; categories are not mutually exclusive.
3. The initial taxonomy contains 15 primary change classes, including explicit concurrency, configuration/release and engineering-support changes in addition to the minimum bootstrap set.
4. Maintenance mode is an orthogonal overlay and does not replace change classification.
5. Contracts are effective depended-upon properties, not only formal documents.
6. The initial contract taxonomy contains 13 contract types covering behaviour, APIs, libraries, events, persistent data, CLI, configuration, protocols, performance, security, reliability, build/runtime and diagnostic surfaces.
7. Compatibility is a relationship between specific versions/participants/contracts, not a standalone contract type or one vague boolean.
8. Coexistence must be assumed when independent clients/providers, rolling releases or persisted representations make atomic replacement unproven.
9. Migration/deprecation is modelled as a transition relationship across contracts rather than as only a version-number change.
10. A public semantic version communicates intent but does not prove behavioural, wire, data or runtime compatibility.
11. Configuration, telemetry and build/release machinery can be real contract surfaces and must not be ignored because no application source file changed.
12. System inspection uses 13 evidence surfaces and is bounded by the proposed change rather than requiring a permanently maintained universal graph.
13. Impact statements carry evidence strength: confirmed, strongly inferred, weakly inferred, unknown or conflicting.
14. Unknown consumers, missing rollback evidence and other unknowns are explicit risk inputs rather than being treated as absence of risk.
15. The impact model covers behaviour, structure, consumers, dependencies, data, configuration, runtime, security, performance, reliability, observability, release, authority and verification.
16. Stage 7 should use qualitative risk drivers rather than a universal numeric score unless later evidence provides a defensible project-specific measurement method.
17. Candidate risk bands are local/routine, cross-boundary/elevated, consequential and specialist/high-assurance; the strongest material driver should govern escalation.
18. A tiny change can be consequential and a large mechanical change can be bounded; diff size alone is not a risk model.
19. The system-inspection sequence is a command/skill hypothesis for later stages, not a final workflow.
20. High-assurance domains remain outside generic core adequacy without specialist evidence.

---

# 17. What remains provisional

Stage 5 deliberately does **not** decide:

- final risk thresholds or approval policy;
- mandatory artefacts for each risk band;
- final verification ladder;
- final workflow sequence;
- final skill or command decomposition;
- whether impact records are persisted for every change;
- one graph representation for system context;
- one API/schema compatibility tool;
- one release strategy;
- one observability stack;
- project-specific SLO/performance/security thresholds;
- specialist high-assurance Extension Packs;
- AI/tool-provider behaviour.

These belong to later stages.

---

# 18. Stage 5 exit-criteria verification

| Exit criterion | Evidence | Status |
| --- | --- | --- |
| Minimum change taxonomy investigated | Section 4 includes all required bootstrap classes and additional evidence-backed classes | PASS |
| Change classes can explain what intentionally changes | Each CH entry defines intent and preservation concerns | PASS |
| Contract taxonomy exists | Section 7 defines CT-01 through CT-13 | PASS |
| User/API/schema/event/CLI/library/config/protocol/performance/security/reliability/build compatibility represented | Section 7 explicitly covers each required contract dimension | PASS |
| Backward compatibility modelled | Section 8 treats compatibility as directional relationship with explicit states | PASS |
| Change-impact model exists | Section 12 | PASS |
| System-context discovery model exists | Section 10 covers repository, build, entry points, modules, ownership, dependencies, call/data flow, tests, config, contracts, ADRs, observability/security and release | PASS |
| System inspection does not rely on filenames alone | Sections 3.1 and 10 require executable/documentary corroboration | PASS |
| System-inspection checklist / command hypothesis exists | Section 13 | PASS |
| Risk-classification candidates exist | Section 14 | PASS |
| Risk model avoids unjustified universal score | Section 14 uses qualitative drivers/bands and defers final policy to Stage 7 | PASS |
| Unknown consumers / evidence gaps remain explicit | Sections 5.10, 11 and 14 | PASS |
| Model can distinguish what must be preserved for different change classes | Section 9 preservation matrix | PASS |
| No universal system graph invented | Section 3.7 and Section 12 define bounded investigation only | PASS |

## Completion decision

Stage 5 is complete.

`software-change-model-r1` can now distinguish materially different software-change classes, identify the contract dimensions each can affect, define what evidence must be discovered from the real system, and explain what should normally be preserved for each class.

Stage 6 may now derive the smallest credible engineering workflow and supporting artefacts from this change/contract model without treating every software task as the same sequence.