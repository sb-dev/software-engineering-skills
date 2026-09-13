# Stage 9: Execution Layer Decision

**Stage:** 9 — Choose the Execution Layer  
**Date:** 13 September 2026  
**Branch:** `feat/bootstrap-2`  
**Input commit:** `9c8bcfe91c1724a03b9ff6ff5dbe124402dadd81`  
**Status:** Complete for architecture selection; no universal execution framework is introduced.

## 1. Inputs and acceptance

The complete [Stage 9 requirement](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#16-stage-9--choose-the-execution-layer) governs the decision. Inputs are the accepted [domain boundary](2026-09-12-stage-01-project-goal-and-domain-boundary.md), [professional capability model](2026-09-13-stage-04-professional-practice-challenge.md), [change/contracts/context model](2026-09-13-stage-05-change-contract-and-context-model.md), [workflow and artifact semantics](2026-09-13-stage-06-workflow-and-artefacts.md), [verification/commitment policy](2026-09-13-stage-07-verification-risk-and-commitment.md), and Stage 8's [landscape](2026-09-13-stage-08-capability-landscape.md) and [46 evaluations](2026-09-13-stage-08-candidate-evaluations.md). The already-reconciled book/professional evidence behind these models remains qualified as recorded; this stage adds an architecture decision, not new empirical source claims.

Acceptance: assign all **ten proposed reasoning responsibilities** and **thirteen named execution responsibilities**; decide the strength of dependence on repository-native commands; state when a small helper is justified; demonstrate at the design boundary that replacing a tool does not redesign WF1–WF6. Persist the decision, rejected alternatives and conformance evidence, then commit and verify remotely. Tool installation, a production adapter and a benchmark run are not required by this stage; later implementation/evaluation gates remain required.

## 2. Decision: discover native commands and preserve their semantics

**Use the consuming repository's actual commands as the default execution interface.** Keep the core as provider-neutral engineering instructions and evidence/artifact conventions. Compilers, formatters, test runners, scanners, profilers, package managers, Git, containers and CI remain independently replaceable dependencies. The host supplies read/search/edit/shell/service access; its tool names, account and permission model remain outside the domain workflow.

The dependency on repository-native commands is strong for **execution semantics**, weak for **command spelling**. A checked-in wrapper or documented CI invocation usually carries important profiles, flags, environment and version assumptions. Preserve those unless the task explicitly changes them. The core must not assume that every repository has `npm test`, a root Makefile, pytest, a single language, a local clone or permission to run a live command. It asks what evidence is needed, finds an appropriate existing invocation, runs it where authorised, and interprets the actual result.

There is **no required universal build/test abstraction, central provider registry, persistent project graph or shared agent runtime**. A repo can choose to expose a stable script itself; use it as its own interface, not a new project-wide protocol. Future packs may teach versioned discovery patterns and special verification concerns without becoming another toolchain.

| Alternative | Benefits | Cost or failure mechanism from accepted inputs | Disposition |
|---|---|---|---|
| Fixed project commands for every language/tool | Simple-looking invocation surface | Hides profiles, services, exclusions and failure meanings; needs adapters before ordinary repositories work | Reject as required core architecture |
| One preferred agent plus its plugin ecosystem | Convenient packaging and known tool names | Stage 8 shows different host/approval/subagent dependencies; tool availability would redefine domain capability | Reject as mandatory provider dependence |
| Install every researched external skill | Broad immediate catalogue | Activates conflicting lifecycles, model pins, deletion/approval rules and unrelated dependencies | Reject; only selected, reviewed, scoped composition |
| Delegate everything to an unstructured coding agent | Minimal project code | Loses explicit obligations, verification adequacy, repair scope and evidence identity demonstrated by Stages 4–7 | Reject as the production-intelligence design |
| Repository-native execution with domain-owned decisions | Preserves real toolchain and allows host/tool replacement | Requires scoped discovery and honest handling of unavailable/ambiguous commands | Adopt |

## 3. Production-intelligence ownership: all ten responsibilities

Ownership means the project supplies decision guidance and evidence expectations. It does not mean writing a new executable for every responsibility, taking product policy from its owner, or packaging ten separate skills.

| ID / responsibility | Project-owned decision | Composed mechanics and boundary |
|---|---|---|
| O01 — How to inspect a system | Choose relevant Stage 5 SI surfaces, inspect actual behaviour/configuration and stop at adequate bounded context; preserve material unknowns | File/symbol/text/history/service reads return observations with provenance; the core assesses completeness for this change |
| O02 — How to classify a change | Apply CT01–CT12 as relevant, allow mixed changes and identify intentional versus preservation obligations | Manifest/diff/schema tools expose facts; they do not infer authorised intent |
| O03 — How to determine affected contracts | Trace CO01–CO13 through actual consumers, data and supported combinations, including semantic/default/error behaviour | Search/schema/contract tooling narrows evidence; absence of a match is not proof of no consumer |
| O04 — How to choose change scope | Select the smallest coherent approach that meets intent and preserves valid obligations; identify justified structural work | Editor/refactoring tools perform bounded edits; their convenience does not justify broader scope |
| O05 — How much design is necessary | Compare meaningful alternatives for consequence/uncertainty, record significant rationale and avoid obligatory ADRs for local edits | Existing ADR/spec systems retain decisions; templates do not decide whether another layer/service is needed |
| O06 — What verification is appropriate | Select an oracle and boundary that can expose the relevant failure; escalate according to Stage 7 risk and existing gates | Tools run checks and calculate reports; the core decides sufficiency and interprets exclusions/unavailable evidence |
| O07 — How to diagnose a failure | Distinguish observation, hypothesis, product/environment/oracle failure, containment and causal repair | Logs, reproductions, profilers, queries and history supply discriminating observations; no blind patch-count rule |
| O08 — How to preserve unaffected behaviour | Define a valid preservation envelope and verify actual contracts through change/transition; do not preserve the reported defect as required behaviour | Existing tests, compatibility tools and diff review supply bounded evidence; compiler success alone is insufficient |
| O09 — How to review engineering quality | Assess obligations, structure, maintainability, tests, security, performance and evidence in context; separate defects from preference | Static analysis and optional reviewer supply findings; identify reviewer provenance and resolve concerns against evidence |
| O10 — How to choose bounded repair | Route correction to the failure's owning decision/artifact, preserve valid work and rerun affected evidence only | Patching, version control and runners execute the chosen repair; do not restart the whole workflow or rewrite to simplify tools |

C01/C03/C17/C18 provide intent, handoff and proportionality across these decisions. C10–C14/C16/C19 supply compatibility, state, concurrency, performance, dependency, release and security reasoning where the change requires it. These special concerns refine the same workflow rather than create a universal execution engine.

## 4. Existing execution ownership: all thirteen responsibilities

Stage 8 identifiers name researched examples. The dependency is on the appropriate capability already chosen by the repository, not on that example brand.

| ID / execution responsibility | Owner/example | What the project supplies | What the project must not reimplement |
|---|---|---|---|
| X01 — Compilation | Repository compiler/build, e.g. D01/D05 | Relevant target/config/version and expected evidence scope | Type system, compiler, language parser or cross-language compilation engine |
| X02 — Formatting | Existing formatter, e.g. D02 | Changed paths, actual style policy, check/mutation choice | A parallel formatter or invented style standard |
| X03 — Linting | Existing linter, e.g. D02 | Config/rules/exclusions and interpretation of findings | Rule engine or universal lint score |
| X04 — Test execution | Existing runners, e.g. D03/D04 | Selected obligations/cases, prerequisites, oracle and escalation | A universal test runner or hidden replacement for the repository suite |
| X05 — Coverage calculation | Existing coverage tool, e.g. D06 | Source/branch/process scope and meaning of omissions | Instrumentation or a universal coverage adequacy threshold |
| X06 — Static analysis | Existing analyser, e.g. D07 | Rule relevance, target scope and source-linked triage | Generic AST/index/analysis framework |
| X07 — Security scanning | Approved scanners and data, e.g. D07/D08 | Threat/control context, target/version, exclusions and residual questions | Vulnerability database or scanner; a clean report is not a security verdict |
| X08 — Profiling | Existing runtime profiler, e.g. D09 | Workload, window, permissions, hypothesis and interpretation | Sampling/instrumentation engine |
| X09 — Benchmark execution | Existing harness/runner, e.g. D10 | Representative fixture, controlled comparison, accepted budgets and correctness conditions | Universal timing/load framework or claimed gain without measurements |
| X10 — Git operations | Git or available authorised host API, e.g. D15/P01 | Exact base/candidate, branch/workspace preservation and requested action | Version-control engine, mandatory worktree orchestrator or GitHub CLI dependency |
| X11 — Package installation | Existing package manager, e.g. D14/D05 | Approved versions/locks/config and legitimate setup need | Resolver, package registry or universal install script |
| X12 — Container execution | Existing runtime/scripts, e.g. D12 | Image/volume/network identity, readiness and cleanup expectations | Container engine, mandatory runtime or automatic live infrastructure provisioning |
| X13 — CI execution | Repository CI service/runner, e.g. D13 | Relevant trigger/jobs, candidate identity and result interpretation | CI engine, scheduler or required central workflow graph |

The core can author or repair repository commands/configuration when the requested change genuinely requires it. That is ordinary project engineering work: inspect existing semantics, make a reviewable local change and verify it. It does not establish a separate universal execution layer.

## 5. Discovery, invocation and result boundaries

### 5.1 Discover the command that actually governs the work

Use this order as evidence precedence, not a rigid whole-repository crawl:

1. Read applicable user/project instructions and existing accepted context. Identify workspace/revision, allowed actions and the change's affected module(s).
2. Inspect relevant repository documentation, checked-in wrappers/scripts and actual CI definitions. They can disagree; record the difference and inspect which environment/profile each serves instead of selecting the easiest passing command.
3. Inspect manifests, lockfiles, tool configs, workspace membership and runtime/container setup needed for that invocation. A pyproject does not prove Poetry, a package.json does not prove npm, and a Dockerfile does not prove a local container daemon exists.
4. Confirm the executable/runtime and required services are available. A PATH miss can be resolved by an existing virtual environment, wrapper, container or remote CI; it is not permission to install a new toolchain automatically. Use an already-authorised setup path when appropriate.
5. Select the cheapest relevant scope that preserves actual dependencies and mandatory gates. For example, selecting a module's tests must not silently omit its required integration fixture or supported client combination.
6. Record the chosen invocation and why it answers the obligation. If it is ambiguous, inspect help/config and recent CI evidence first. Ask only when a material meaning, required authority or unavailable capability remains unresolved.

The output can be a few lines in the working note or A11 verification evidence. There is no mandatory new manifest, lock schema or database. Reuse existing canonical project records.

### 5.2 Information crossing the execution boundary

These information requirements are conceptual, not a new API or a fixed serialization contract:

| Boundary | Required information | Owner and failure semantics |
|---|---|---|
| Request to execute | Purpose/obligation; target base/candidate and working directory; actual command/tool arguments; effective relevant config/version; prerequisites; expected output; scope and authority | Engineering responsibility selects it; host executes only within available permissions. A proposed command is not evidence that it ran. |
| Observed execution | Actual command/environment identity; completion/exit status; raw output/artifact reference; run cases or analysed scope; skips/timeouts/missing prerequisites | Executing tool/host produces observations. Avoid suppressing a failed process or confusing tool failure with a product assertion failure. |
| Interpreted result | Passed/failed/inconclusive/unavailable/not-applicable with reason; obligations covered/uncovered; identified defect or uncertainty; candidate freshness | Engineering responsibility interprets observations and selects bounded repair or further evidence; authority remains separate. |

Keep native output accessible when it matters. A helper may extract a failing test name, but must not discard diagnostics or convert a missing/unsupported report into success. If a command can change files, data, processes or remote state, retain the actual resulting state and cleanup/reconciliation needs. A missing output after an uncertain remote action is not a reason to repeat it blindly.

Shell command construction is code: preserve literal arguments, use the host's structured arguments where available, and quote/validate data before embedding it. Do not execute retrieved README snippets merely because they exist. Read-only source inspection, package installation, test fixtures and live deployment have different effects even when they all use a shell.

### 5.3 Valid evidence and cache lifetime

Use Stage 6 A11 and Stage 7 evidence semantics. A tool replacement, rule/config change, new generated artifact or candidate edit invalidates the affected result's assumptions. It need not invalidate unrelated analysis or every check. Retain the specific source/tool/candidate identity that makes reuse defensible. Do not demand a global cache engine to remember a few checked facts.

A failed native command is not automatically grounds to substitute a weaker check. First classify its cause. If the alternative covers the same obligation in the permitted context, explain the equivalence and limits. If it omits a required property, the result remains unavailable/inconclusive and the affected decision does not pass. This prevents replaceability from becoming a way to waive gates.

## 6. Small-helper policy and optional skills

A small deterministic helper is justified only by a concrete composition problem: for example, an existing machine-readable report needs a bounded extraction, or a repeated command needs reliable server cleanup. Before adding it, check whether the repository/host/upstream tool already provides the needed interface. Define input/output, scope, failure behaviour, supported environment and a direct way to call the underlying tool without the helper where feasible.

The helper must preserve native exit/timeout meanings, relevant output and command identity; keep dependencies proportionate; avoid a new persistent runtime; and have meaningful checks for parsing/error/cleanup behaviour. Its existence does not permit a semantic success claim. No specific helper has yet demonstrated a need in this stage, so none is introduced. Stage 8's S06/S24 helpers remain unexecuted optional candidates requiring source review and evaluation before reuse.

External generative skills are a separate optional composition boundary. Their instructions can suggest domain patterns, not replace accepted intent or the core's evidence responsibilities. REFERENCE does not mean activated. ADAPT requires a reviewed, licensed compatible variant before use. Preserve full context of the selected supporting reference, provider constraints and updated source when actually consuming it. A packaging convention can vary by host without changing O01–O10 or WF1–WF6.

## 7. Tool-replacement checks

These are **six synthetic architecture desk exercises**, not installations or execution benchmarks. Each deliberately changes an execution mechanism and tests whether the same intent/context/approach/change/verify/handoff responsibilities still make sense. Illustrative command roles refer to hypothetical consuming repositories, not commands discovered in this research-only snapshot.

| Probe | Replacement | What changes | What stays invariant | Assessment |
|---|---|---|---|---|
| ER01 — Test runner | Repository pytest command → repository unittest command | Discovery evidence, selection syntax, fixture arrangement and output parser; inspect collection equivalence | Accepted behaviour/oracle, affected boundary, actual execution evidence and repair decision | WF3 selects the same obligation; WF4/5 invoke the new runner; no workflow redesign. If equivalent cases cannot run, retain an evidence gap. |
| ER02 — Compiler/build | Existing Maven build → existing Gradle build | Wrapper, JDK/config/tasks, dependency resolution and test-phase semantics | Intended change, supported participants, artifact identity and relevant verification | Revalidate target/phase equivalence; O06 is unchanged. Merely finding a new command is not proof of equivalent coverage. |
| ER03 — Formatting/lint | Ruff → repository's established formatter plus separate linter | Two invocations/configs instead of one executable; check output/automatic-edit scope | Mechanical versus semantic evidence distinction and unchanged behaviour obligations | No new core command vocabulary required; avoid running or installing the alternative on unrelated repositories. |
| ER04 — Version control access | Local Git/gh workflow → authorised GitHub Git Data connector | Source acquisition, tree creation, single-parent commit and ref-update mechanism | Exact intended diff, parent/candidate identity, branch authority and remote-content verification | This bootstrap already demonstrated connector commits in Stages 3–8. That observation supports the boundary; it is not a controlled Git-versus-connector performance comparison. |
| ER05 — Container/CI location | Local container-backed integration test → existing CI job with the required service | Environment setup, asynchronous run/log access and artifact retrieval | Same contract/oracle, tested candidate, dependency version and pass/fail meaning | Remote result can satisfy the obligation only if provenance and coverage are adequate; missing service/job remains unavailable evidence. |
| ER06 — Reasoning host | Codex/Work → Claude Code with available read/edit/shell | Skill discovery, tool names, connectors, permission/context handling | WF1–WF6, O01–O10, artifact roles, authority and evidence semantics | Documented capabilities support an architecture-level path; installation, actual execution and comparative quality are not asserted. Serial execution remains valid without subagents. |

The replacement condition is semantic: the selected execution can still produce evidence for the required property, or the workflow can accurately report the uncovered obligation. Workflow independence does not promise that every pair of tools has equivalent features. A missing race detector, unsupported browser or insufficient scanner rule set may require another execution capability; it never authorises declaring the underlying risk covered.

## 8. Conformance and handoff

The original Stage 9 section was re-read and this decision inspected against the accepted workflow and Stage 8 alternatives. No existing accepted stage is rewritten.

| Requirement | Evidence | Verification | Result |
|---|---|---|---|
| Separate production intelligence from execution | Sections 2–4 and boundary table | Decisions belong to engineering responsibilities; tool/host executes and returns observations | PASS |
| Assess all project-ownership candidates | O01–O10 | Ten explicit responsibilities, each with composed mechanics and semantic limit | PASS |
| Delegate all named mechanical responsibilities | X01–X13 | Thirteen explicit execution owners; no duplicate engine justified | PASS |
| Decide native commands versus universal abstraction | Sections 2 and 5 | Strong native-semantics preference; no mandatory command spelling/build/test protocol; rejected alternatives explained | PASS |
| Allow justified small helpers | Section 6 | Concrete-need, existing-interface, failure, scope and verification criteria; none invented without need | PASS |
| Exit: execution-tool replacement without workflow redesign | ER01–ER06 | Six desk exercises vary runner/build/lint/Git/environment/provider while preserving workflow and evidence obligations | PASS |
| Preserve risk, authority and evidence semantics | Sections 5–7 | Missing/weak replacements cannot waive gates; standing authority and optional subagents retained | PASS |
| Durable research/decision record and stage isolation | This record and progress index | Source links, architecture alternatives, truthful exercise labels and next-stage handoff recorded | PASS |

**Handoff:** Stage 10 classifies remaining coverage gaps against this chosen boundary. Native work is justified by missing production decisions, while low-level mechanics remain reused. Stage 9 has no blocker requiring user input; continue after its commit and remote verification.
