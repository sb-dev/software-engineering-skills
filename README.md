# Software Engineering Skills

**Make software changes that fit the system and come with credible verification.**

Reusable engineering judgement for AI coding agents working in existing repositories: understand the system, choose a coherent change, preserve its contracts, verify the result and repair the cause of failures.

**Status: specified; implementation is next.** The six specifications and researched example/pack designs are complete. Skills, example results, benchmarks and clean installation have not yet been demonstrated. The installation and quick-start sections below describe the target workflow; they are not a claim that an installable release already exists.

## Engineering work

The specified workflow covers:

- Repository inspection, technical requirements and architecture decisions.
- Features, defect repair and behaviour-preserving refactoring.
- API, persistent-data, dependency and configuration changes.
- Tests, compatibility, security, performance and reliability checks.
- Root-cause diagnosis, bounded repair and technical release handoff.

A useful outcome can also be an evidenced diagnosis, design or review that needs no code change. Brownfield work is the primary proving ground; greenfield remains in scope.

## Change scope, preservation and verification

Inspect the actual affected paths and repository conventions before editing. Preserve valid behaviour, supported consumers, data meaning and approved work. Make the smallest coherent change, which may span several files or layers.

Use repository-native tools and checks that can expose the relevant failure. Keep functional results, observed engineering behaviour and twelve quality dimensions separate. Diagnose a failure, repair its owning cause and refresh affected evidence. Passing tests are evidence for their stated scope, not permission to weaken contracts or claim an unmeasured quality gain.

Carry existing authorisation through the requested work. Ask only when a real unresolved requirement, capability or consequential action needs a new decision. Code readiness, publication and live-service operation are different outcomes.

## Installation

The minimum planned installation is `software-engineering` alone. Add `software-evaluate` for independent assessment tasks. Packs are optional and explicitly selected; they do not replace either skill's core responsibilities.

When the implementation is available, use a coding agent with GitHub access and local file tools. A copyable installation request is:

```text
Install only the software-engineering skill from sb-dev/software-engineering-skills, branch feat/bootstrap-2, into this consumer repository's skill directory supported by this coding agent. Resolve and record the exact GitHub commit, preserve the selected skill folder and all its local references, and do not overwrite an existing modified installation. Do not copy the source repository's research logs, benchmarks, other skills or packs. Report the installed revision and path, and use the installed skill for the next task.
```

For a full installation, request both `software-engineering` and `software-evaluate`; add `data-migration` or `reliable-event-processing` only when needed. Skill sources use `skills/<name>/SKILL.md`; pack sources use `packs/<slug>/PACK.md`. Preserve each folder's local resources and give the active skill the actual selected pack path. Host discovery and invocation syntax must match the coding agent being used.

Consumer projects provide their own build/test/runtime prerequisites. The examples are designed around Python, Node.js and Java 17; there is no mandatory database server, broker, cloud account or universal runner for the core. See the [installation contract](docs/03-software-engineering-skills-repository-and-contracts-spec.md#installation-contract). A release may advertise only the installation methods and hosts actually exercised by the [separate local and clean-consumer gates](docs/04-testing-and-benchmark-spec.md#end-to-end-and-installation-gates).

## Quick start: repair a missing final page

Start with E01, a small existing Python repository whose catalogue caller loses the final page when the item count is an exact multiple of the page size. The [fixture and oracle design](docs/04-testing-and-benchmark-spec.md#fc01--e01--page-boundary) specifies the starting behaviour and verification. Actual fixture/result links will be added after the core vertical runs.

After installing and selecting `software-engineering`, give it this exact task:

```text
Fix the pagination defect in this repository: when the item count is an exact multiple of page_size, catalogue.pages omits the final full page. Preserve ordering, empty-input behaviour, invalid-size errors and the public API, and do not mutate the input. Inspect the existing caller and tests, make the bounded repair, add a regression that catches the defect, run the repository's native checks and review the resulting diff. Finish with the actual verification evidence.
```


The intended result is a bounded caller-connected repair, a regression that detects the original defect, passing native checks and an inspected diff. This is a planned demonstration, not a result already produced by this README.

## Learn by engineering

Exactly three primary examples at each of five levels. All fifteen are currently **designed, not executed**. Links open their complete fixture/task/evidence requirements. Each implemented example will expose its starting repository, exact prompt, actual resulting change, verification result and explanation of the engineering behaviour demonstrated.


### Level 1: Make a bounded local change

Inspection, focused feedback and a coherent small diff.

| Example | Engineering problem | Status |
|---|---|---|
| [E01: Repair a missing final page](docs/04-testing-and-benchmark-spec.md#e01--repair-a-missing-final-page-l1c01) | one visible missing record group | Designed |
| [E02: Validate a service port](docs/04-testing-and-benchmark-spec.md#e02--validate-a-service-port-l1c02) | one new rule with explicit exceptions | Designed |
| [E03: Extract duplicated report formatting](docs/04-testing-and-benchmark-spec.md#e03--extract-duplicated-report-formatting-l1c03) | readable small structural diff | Designed |

### Level 2: Preserve module and interface contracts

Multi-file changes, supported callers and actual integration boundaries.

| Example | Engineering problem | Status |
|---|---|---|
| [E04: Add an exact decimal library entrypoint](docs/04-testing-and-benchmark-spec.md#e04--add-an-exact-decimal-library-entrypoint-l2c01) | two clients expose compatibility | Designed |
| [E05: Make a preferences update durable and atomic](docs/04-testing-and-benchmark-spec.md#e05--make-a-preferences-update-durable-and-atomic-l2c02) | module boundary and external state | Designed |
| [E06: Add a streaming CLI summary command](docs/04-testing-and-benchmark-spec.md#e06--add-a-streaming-cli-summary-command-l2c03) | multi-file interface beyond local parser | Designed |

### Level 3: Deliver a complete feature across layers

Architecture fit, end-to-end behaviour, persistence/state and useful observability.

| Example | Engineering problem | Status |
|---|---|---|
| [E07: Add tenant-scoped project notes](docs/04-testing-and-benchmark-spec.md#e07--add-tenant-scoped-project-notes-l3c01) | complete feature with security boundary | Designed |
| [E08: Add cooperative cancellation to an export worker](docs/04-testing-and-benchmark-spec.md#e08--add-cooperative-cancellation-to-an-export-worker-l3c02) | one deployable async state-machine feature | Designed |
| [E09: Add an inventory import with dry-run and atomic apply](docs/04-testing-and-benchmark-spec.md#e09--add-an-inventory-import-with-dry-run-and-atomic-apply-l3c03) | complete non-CRUD feature through layers | Designed |

### Level 4: Evolve or repair a risky system

Diagnosis, mixed-version preservation, measured performance and dependency risk.

| Example | Engineering problem | Status |
|---|---|---|
| [E10: Migrate invoice storage during mixed-version writes](docs/04-testing-and-benchmark-spec.md#e10--migrate-invoice-storage-during-mixed-version-writes-l4c01) | visible transition and failure schedules | Designed |
| [E11: Diagnose an N+1 catalogue regression](docs/04-testing-and-benchmark-spec.md#e11--diagnose-an-n1-catalogue-regression-l4c02) | mechanism plus actual measurements | Designed |
| [E12: Upgrade a local provider SDK contract](docs/04-testing-and-benchmark-spec.md#e12--upgrade-a-local-provider-sdk-contract-l4c03) | actual resolution and incompatible API make upgrade visible | Designed |

### Level 5: Complete an engineering thesis

Research, alternatives, staged implementation, multi-contract evaluation and actionable handoff.

| Example | Engineering problem | Status |
|---|---|---|
| [E13: Extract a legacy billing policy without rewriting service](docs/04-testing-and-benchmark-spec.md#e13--extract-a-legacy-billing-policy-without-rewriting-service-l5c01) | thesis with staged evidence and explicit rejected rewrite | Designed |
| [E14: Implement an approved audit-export product handoff](docs/04-testing-and-benchmark-spec.md#e14--implement-an-approved-audit-export-product-handoff-l5c02) | complete production feature from explicit nonvisual UX handoff | Designed |
| [E15: Repair repeated stock reservations after an incident](docs/04-testing-and-benchmark-spec.md#e15--repair-repeated-stock-reservations-after-an-incident-l5c03) | incident class with durable prevention and handoff | Designed |


## Project structure grows with the work

| Work | Useful repository artefacts |
|---|---|
| Local defect or refactor | Existing source, meaningful tests, actual diff and concise verification note |
| Module/API change | Relevant caller contracts and compatibility evidence |
| Cross-layer feature | Accepted interface/state/schema changes and real integration checks |
| Migration or incident repair | Transition/fault cases, reconciliation or recovery instructions, candidate-specific results |
| Larger architectural/product change | Significant alternatives, inspectable vertical changes, broader evaluation and receiving notes |

Use the consuming project's existing structure and canonical records. Add an ADR, migration plan, benchmark or handoff document when a decision or receiver needs it. No compulsory project graph, global state directory or new document for every step.

## Core skills

| Planned skill | Responsibility |
|---|---|
| `software-engineering` | Complete inspection, design, implementation, native verification, self-review, diagnosis, repair and handoff; works alone |
| `software-evaluate` | Standalone review of raw candidate evidence, tests, compatibility, security and performance; assessment does not silently edit production |

The [twelve command contracts](docs/03-software-engineering-skills-repository-and-contracts-spec.md#command-contracts) are optional prompt-level modes. They are not a universal command-line runtime or a mandatory sequence. Engineering includes an explicitly requested [pack-authoring workflow](docs/05-software-engineering-extension-packs-spec.md#domain-native-authoring-contract); a separate creator skill is not required.

## Software Engineering Extension Packs

| Researched pack | Specialisation | Current evidence |
|---|---|---|
| [data-migration](docs/06-software-engineering-extension-pack-catalogue.md#data-migration-data-migration) | Existing data, mixed readers/writers, resumable work, reconciliation and contraction | P1–P5 researched; runtime/showcase/reuse/comparison/install not run |
| [reliable-event-processing](docs/06-software-engineering-extension-pack-catalogue.md#reliable-event-processing-reliable-event-processing) | Request identity, durable effects, acknowledgement, crash/retry and recovery | P1–P5 researched; runtime/showcase/reuse/comparison/install not run |

Explicit project instructions and accepted architecture/contracts/approved work outrank pack defaults. A valid exclusive migration or compensated workflow is allowed. Pack-aware review preserves justified specialisation while rejecting real corruption, lost/duplicate effects and unsupported evidence. No general superiority over the core is claimed; the [comparison design](docs/04-testing-and-benchmark-spec.md#pack-evaluation-and-comparison-design) requires the same substantive tasks in both arms.

## Execution layer

The skills decide what engineering work and evidence are needed. Existing repository compilers, formatters, test runners, package managers, scanners, profilers, Git and CI execute it. Discover the real command/configuration, inspect actual results and keep required gates intact. Providers and optional specialists remain replaceable; no central runtime or mandatory Pactwright installation is introduced.

## Repository checks and benchmarks

The [benchmark specification](docs/04-testing-and-benchmark-spec.md) separates deterministic integrity, command/skill behaviour, functional correctness, engineering quality, preservation/repair, pack evaluation, end-to-end work and installation.

The planned benchmark uses independent behavioural oracles, meaningful defect/fault seeds and actual native commands. It must distinguish a wrong implementation, an out-of-scope edit, weak tests and unavailable tooling. Failed/inconclusive runs remain visible. Working entrypoints and measured results will be linked only after implementation and execution; no command or pass rate is invented here.

## Documentation

| Specification | Responsibility |
|---|---|
| [01 System](docs/01-software-engineering-skills-system-spec.md) | Mission, architecture, scope, risk, authority and acceptance |
| [02 Workflows and artefacts](docs/02-software-engineering-skills-workflows-and-artifacts-spec.md) | Changes, contracts, inspection, evidence, repair and handoff |
| [03 Repository and contracts](docs/03-software-engineering-skills-repository-and-contracts-spec.md) | Skill/mode contracts, resources, native tools and installation |
| [04 Testing and benchmark](docs/04-testing-and-benchmark-spec.md) | All fifteen prompts/oracles, evaluation, regression and install gates |
| [05 Extension Packs](docs/05-software-engineering-extension-packs-spec.md) | Selection, activation, precedence, authoring and proof |
| [06 Catalogue](docs/06-software-engineering-extension-pack-catalogue.md) | Two researched entries, sources, exact briefs and independent status |

[Research and stage progress](docs/research-logs/README.md) retain the five-book extraction, professional challenge, decisions and conformance evidence.

## Project boundary

Engineering owns correct implementation and relevant verification. Product/UX owners retain intended value and interaction decisions; specialists retain domain-specific assurance; platform/SRE retain live-service policy and operations. Technical release work is performed only within actual authority. The skills can work with an optional orchestrator but do not own its lifecycle, governance or Project Graph.

## Contributing

Follow the accepted specifications, preserve valid work and use repository-native checks. During bootstrap, complete and verify one top-level stage per commit, with its stage number in the conventional commit message. Keep source provenance, actual execution results and limitations. Do not commit supplied books, private source locations or copied proprietary examples. Contributor/check instructions will become executable alongside the Stage 17 scaffold.

## Licence

A project licence has not yet been recorded. The scaffold must include the owner's selected open-source licence before this repository is advertised as licensed for reuse. Licences of referenced external tools or other Production Skills repositories do not license this project's content.

