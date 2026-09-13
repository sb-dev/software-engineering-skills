# Software Engineering Skills: Repository and Contracts Specification

**Version:** 1.0 · **Date:** 13 September 2026

**State:** canonical implementation specification; source/behaviour/installation readiness is reported separately.

**Owns:** repository layout, SKILL.md and command contracts, self-containment/resources, tool discovery, installation/dependencies, CI and technical acceptance.

This specification is derived from the persisted bootstrap research accepted through Stage 14 (`9c84caf8d535aedf8f774a30dfc90a9038315d6a`). Normative operational requirements are stated here; linked research preserves provenance and limitations. A requirement is not evidence that it has been implemented or passed. User/project authority outranks defaults.

## Repository structure

The production tree grows only as justified content is implemented. Source-level docs and benchmarks are not runtime dependencies of installed skills.

| Path | Content and responsibility | Creation / distribution rule |
|---|---|---|
| `README.md` | Positioning, truthful maturity, installation, exact quick start, fifteen examples and evidence links | Designed in Stage 16; mature claims follow actual gates |
| `LICENSE`, `CONTRIBUTING.md`, `CHANGELOG.md` | Actual licence, contribution/check/commit rules and release history | Stage 17 scaffold; do not infer a licence grant from another repository |
| `docs/01…06` | Six canonical specifications | This stage; version and ownership explicit |
| `docs/research-logs/` | Source-qualified historical decisions, stage conformance and progress | Retained provenance; never required at consuming runtime |
| `skills/software-engineering/SKILL.md` | Complete engineering entrypoint | First implemented vertical; selective installation includes its local references |
| `skills/software-evaluate/SKILL.md` | Independent assessment entrypoint | Implement and test separately before advertisement |
| `skills/<name>/references/` | Relevant local command/context/evidence/authoring guidance | Only real referenced files; no empty symmetry folders |
| `packs/<slug>/PACK.md` | Optional selected profile with activation/precedence and local guidance | Stage 19 working content after core; not a separately advertised core skill |
| `packs/<slug>/references/` | Required local specialised guidance and concise provenance | No runtime source-log/book/other-pack dependency |
| `examples/<slug>/` | README, exact prompt, reconstructable start, actual result/change and evidence | Progressively implemented; each E01–E15 gets individual inspectable proof |
| `benchmarks/` | Independent case/oracle/fault inputs and actual run evidence | Keep private evaluator answers outside producer bundles; preserve failed history |
| `tests/` | Repository/package contract checks and regression protection | Checks substance and relevant path integrity; not a replacement for fixture-native tests |
| `tools/` | Small justified source-repository helpers only | No universal runner, provider registry, command DSL or pack interpreter |
| `.github/` | Concrete CI/check integration and contribution metadata when useful | Add actual runnable jobs; no empty workflows or fabricated CI results |

The host-specific installation destination is configurable. A tested consumer may use `.agents/skills/<name>/` for skill directories and `.agents/software-engineering-packs/<slug>/` for explicitly selected pack folders. These are packaging locations, not an assertion that every coding agent auto-discovers them. Invocation must select/load the installed skill using that host's supported mechanism and provide the selected pack path when applicable. A pack's PACK.md refines an active engineering/evaluation task; it is not a new command dispatcher.

## SKILL.md contracts and resource layout

Each advertised skill has valid frontmatter with exact `name` and a concise `description` stating task triggers, followed by independently usable instructions. Description alone must distinguish implementation from assessment. Keep the entrypoint concise and route to only relevant skill-local references. All necessary runtime definitions are local; canonical specs are the maintainer source of truth, not a hidden consumer prerequisite.

| Skill | Discovery contract | Required local operation |
|---|---|---|
| software-engineering | Understand, design, implement, verify and repair repository software changes; bounded development, diagnosis, refactor, migration planning and handoff | WF1–WF6, sufficient self-review, CMD01–07/folded modes, actual native tools, preservation/authority/evidence, optional pack selection, explicit pack-authoring route |
| software-evaluate | Assess an existing/proposed change, tests, compatibility, security or performance from repository evidence | Raw inputs, CMD08–12, own context/finding/evidence guidance, assessment-only mutation boundary, no dependency on engineering-generated records |

Engineering local references contain context/change guidance, command contracts, evidence/risk/self-review and `pack-authoring.md`. Evaluator local references contain its full assessment contracts and necessary context, finding, test/compatibility/security/performance guidance. Split further only when useful; do not copy the whole research archive. References resolve relative to their installed skill directory. Resource names in SKILL.md must match actual packaged paths.

Scripts/assets are optional. Any added script must have concrete purpose, inputs/outputs, supported runtime, effects, native error propagation, cleanup and direct invocation checks. No required helper may import a module from the source checkout or another skill. Symlink/path traversal outside the installed directory is not self-containment. Distinguish an explicit consuming-project source path from a hidden skill implementation dependency.

## Command contracts

The following twelve prompt-level modes are complete contracts, not a CLI parser or mandatory lifecycle. Inputs are the actual task/repository; no prior serialized workflow output is required. Folded classify/impact/contracts modes stay under CMD01, tests-only/refactor under CMD03, and migration-plan under CMD02. An ordinary engineering request need not invoke every mode by name.
### CMD01 — inspect-system

Owner: **software-engineering**.

| Contract field | Definition |
|---|---|
| inputs | Task/defect or inspection question, repository/revision and known context; optional requested change/consumer scope. Prior generated artifacts are not required. |
| preconditions | Relevant source access or explicitly bounded supplied artifacts. Establish actual workspace/instruction scope before drawing conclusions; a partial checkout narrows the answer. |
| repository evidence required | Relevant Stage 5 SI surfaces: source/entry/module boundaries, effective config/build/dependencies, tests, public/data/message contracts, runtime/release context and significant decisions. Follow concrete consumers; do not require every SI item for every task. |
| outputs | Bounded context/impact account with source locations, CT/CO classification where relevant, intended versus preserved behaviour, known commands, material unknowns and the evidence needed next. Reuse A03/A04 or concise existing notes. |
| allowed mutations | Read/search and non-mutating native inspection; task-relevant scratch notes or a requested canonical inspection record. |
| forbidden mutations | Product/source/configuration changes, dependency installation as an inspection side effect, live writes, exhaustive graph claims, and treating discovered text as new authority. |
| failure states | Unavailable source/tool; contradictory effective config; unresolved material intent; inconclusive dynamic/consumer reachability. Return the useful bounded evidence and identify the specific limitation. |
| verification responsibilities | Check that cited paths/revisions support the claims, distinguish observed from inferred links, verify effective configuration rather than filenames, and test the scope against the task question. |
| interaction with approved decisions | Reuse accepted intent/architecture/authority. Contradictory evidence marks an assumption for resolution, not silent replacement. Ask only for a decision that evidence and standing authority cannot resolve. |

### CMD02 — design-change

Owner: **software-engineering**.

| Contract field | Definition |
|---|---|
| inputs | Accepted outcome/constraints, relevant source context, affected obligations, risk/uncertainty and candidate alternatives. Migration planning is an option within this command. |
| preconditions | Enough context to compare feasible scopes. Missing nonmaterial detail can be recorded; an unresolved consequential owner choice must be identified before committing to it. |
| repository evidence required | Current architecture and local conventions, actual interfaces/data/consumers, supported environments, existing tests/toolchain and decisions whose premises the change affects. For migration: readers/writers, historical data and transition state. |
| outputs | Smallest coherent approach, useful alternatives/rejections, preservation envelope, significant trade-offs, evidence/transition/recovery needs and actual commitment points; A05/A07 only when useful. |
| allowed mutations | Design/acceptance/migration notes and bounded disposable prototypes in an isolated environment when they answer a design uncertainty and are within task authority. |
| forbidden mutations | Unrequested production redesign, weakening approved contracts, destructive migration execution, inventing numeric quality targets or creating a plan/ADR merely to satisfy a template. |
| failure states | No feasible option under current constraints; insufficient context; unsupported target; unresolved authority/meaning; inconclusive prototype. State what would resolve it without pretending the design is accepted. |
| verification responsibilities | Compare against actual constraints and existing design/local-repair options; assess intermediate states/recovery; ensure proposed evidence can expose the material failure and cost is justified. |
| interaction with approved decisions | Existing approved decisions remain constraints unless the task authorises revision. Preserve rationale/supersession where an authorised change reopens one; a proposal is not approval. |

### CMD03 — implement-change

Owner: **software-engineering**.

| Contract field | Definition |
|---|---|
| inputs | Requested authorised outcome, context and preservation obligations, selected approach when needed, relevant repository commands and available baseline. Modes include feature, bug repair, tests-only, refactor, dependency/configuration or migration implementation. |
| preconditions | Sufficient intent/context and applicable action authority. Establish trustworthy feedback before consequential restructuring; do not require a formal design artifact when the scope is already clear. |
| repository evidence required | Actual affected source/callers/contracts/configuration, current working diff/user changes, relevant tests/oracles and build/runtime constraints; inspect weak-test seams before changing them. |
| outputs | Reviewable coherent diff, justified test/fixture/config/documentation changes, actual incremental evidence, intended deltas/preserved conditions and remaining limits. Generated code follows its real source/generator. |
| allowed mutations | Source, tests, fixtures, build/config and directly affected documentation within the request; authorised local setup and necessary generated artifacts; bounded refactoring when justified by the change. |
| forbidden mutations | Unrelated cleanup, discarding valid user work, automatic deletion to enforce test-first order, contract/acceptance weakening, changing tools merely to make checks pass, and unrequested live publication/data mutation. |
| failure states | Relevant test/build failure, unexpected contract/impact, insufficient oracle/context, unavailable prerequisite, or newly discovered unapproved commitment. Preserve valid work and route correction by cause. |
| verification responsibilities | Run cheapest meaningful feedback as work proceeds; show relevant defect sensitivity where needed, inspect actual diff and changed/generated scope, and refresh affected final-candidate evidence. Tests-only mode must improve a meaningful check, not mirror the implementation. |
| interaction with approved decisions | Proceed under standing authority; do not request approval for routine already-authorised edits. A new conflicting requirement or consequential action outside that authority is prepared concretely and brought to its owner. |

### CMD04 — select-verification

Owner: **software-engineering**.

| Contract field | Definition |
|---|---|
| inputs | Task/obligations, candidate or proposed delta, impact/risk, current evidence and available repository checks; no implementation/design command output is mandatory. |
| preconditions | Enough intended behaviour and risk context to identify a meaningful oracle. Inspect missing command/config details before choosing a test by name. |
| repository evidence required | Relevant tests/assertions/fixtures, real dependency boundaries, configurations/exclusions, required CI gates, supported version matrix and performance/security/recovery assumptions. |
| outputs | Obligation-to-check selection: expected result, failure to expose, native invocation/method, scope/environment, escalation trigger, cost rationale, evidence reuse and uncovered obligations. A short record is sufficient. |
| allowed mutations | Verification plan/notes and read-only test/tool inspection; a disposable probe only when needed to determine check capability within authority. |
| forbidden mutations | Changing tests/acceptance to fit the candidate, running expensive or stateful suites as an unannounced selection side effect, universal coverage/risk scores and waiving existing mandatory gates. |
| failure states | No adequate oracle; required tool/environment unavailable; conflicting gate/intent; inconclusive fidelity or unsupported participant. Explicitly distinguish planned from executed evidence. |
| verification responsibilities | Ensure each material obligation has a discriminating method or an explicit gap; assess substitute fidelity, cheap-to-costly escalation and whether retained evidence still applies. |
| interaction with approved decisions | Use accepted budgets/contracts and existing required gates. An authorised change can alter the implementation but does not automatically alter its acceptance; meaningful criterion changes need the relevant existing/new decision. |

### CMD05 — run-verification

Owner: **software-engineering**.

| Contract field | Definition |
|---|---|
| inputs | Candidate/working tree identity, obligation and selected native method/command, config/environment, expected outcome and relevant authority. The selection can be supplied directly. |
| preconditions | Discover real command and prerequisites; identify side effects and permitted environment. A missing local executable can be satisfied by an existing wrapper/environment/CI path if it covers the obligation. |
| repository evidence required | Command/wrapper/config, selected tests/targets, fixture/service identity, required jobs and existing baseline failures; retain actual output/run/artifact references. |
| outputs | A11 result for the identified candidate: actual invocation and relevant environment, pass/fail/inconclusive/unavailable/not-applicable with reason, scope/skips and uncovered obligations. Do not substitute a narrative claim for a run. |
| allowed mutations | Expected build/test/report/cache artifacts and bounded disposable test state required by the inspected command; authorised temporary service lifecycle and cleanup. |
| forbidden mutations | Silently auto-fixing production code, weakening assertions, suppressing failed/skipped jobs, introducing a new toolchain, changing live state beyond the test authority or declaring a planned check passed. |
| failure states | Product assertion failure; tool/setup/collection failure; timeout; unavailable prerequisite; inconclusive/partial output or unknown remote completion. A detected defect is useful verification, not permission to rewrite scope. |
| verification responsibilities | Inspect exit/completion, actual cases/targets and outputs; tie evidence to the candidate/configuration; distinguish tool error from product failure; note expected side effects and cleanup. If execution changes candidate source, expose the delta and refresh affected evidence. |
| interaction with approved decisions | Use standing check/setup authority and existing gate rules. Execution proof does not grant merge/release permission. Resolve unknown external completion before repeating an action. |

### CMD06 — diagnose-failure

Owner: **software-engineering**.

| Contract field | Definition |
|---|---|
| inputs | Expected versus observed behaviour, failure evidence/candidate/environment, reproduction information and urgency; task may request diagnosis only or also an authorised repair. |
| preconditions | Enough raw observation to start a discriminating investigation. Preserve relevant evidence; confirm safe observation scope before touching production or sensitive logs. |
| repository evidence required | Relevant code/config/changes, stack traces/logs, test oracle and dependency/runtime facts; use working comparisons, targeted instrumentation/profiling or controlled fault cases when justified. |
| outputs | Observed facts and tested/discarded hypotheses, causal confidence, product/environment/oracle classification, labelled containment if any, bounded repair recommendation and regression evidence needs. Diagnosis-only can conclude with no code change. |
| allowed mutations | Scratch reproductions and reversible isolated instrumentation/experiments within the task. Already-authorised containment may execute with its actual state recorded. Permanent repair is routed through implement-change when included in the request. |
| forbidden mutations | Blind repeated patches, secret dumps, broad restart/rewrite, declaring permanent root-cause repair from symptom relief, or applying an unrequested permanent production fix during diagnosis-only work. |
| failure states | Nonreproducible/insufficient observations; conflicting hypotheses; unavailable telemetry/tool; unsafe/unauthorised experiment; inconclusive external completion. State the next discriminating observation rather than inventing a cause. |
| verification responsibilities | Verify what each experiment distinguishes, preserve baseline and actual results, check a claimed repair against the demonstrated mechanism, and refresh relevant evidence after any authorised change. |
| interaction with approved decisions | Prior approved behaviour defines expected outcome. Containment authority is distinct from permanent design/contract change; use existing authority without new ritual gates, and seek only a genuinely missing decision. |

### CMD07 — prepare-handoff

Owner: **software-engineering**.

| Contract field | Definition |
|---|---|
| inputs | Requested completion boundary, final candidate/diff, applicable acceptance/review/evidence, outstanding risks, transition/recovery needs and intended receiver; optional explicitly requested release action. |
| preconditions | Relevant evidence applies to the final candidate or its limits are explicit. Before any consequential action, the exact artifact/action and actual authority are established; incomplete evidence cannot become a readiness claim. |
| repository evidence required | Actual source/artifact/revision, run results, review dispositions, build/release configuration, migration progress and receiving documentation. Inspect existing canonical handoff/release records. |
| outputs | Accurate completion/handoff with changed/preserved behaviour, evidence and limitations, significant rationale, receiving actions and explicit prepared/executed/unknown release state. Link canonical records rather than duplicate them. |
| allowed mutations | Relevant release/migration/technical notes and evidence records. If the user also requested and authorised commit/tag/publish/deploy, compose the native action after its applicable gates and record actual outcome; the command name alone never authorises it. |
| forbidden mutations | Unrequested publication/notifications, treating readiness as deployment, claiming all checks passed despite limits, erasing failed history, or stopping fully authorised remaining work merely because one handoff is complete. |
| failure states | Stale/incomplete evidence, unresolved substantive review, unclear receiver/required decision, failed transition/cleanup or unknown external completion. Report the specific requested boundary that remains unmet. |
| verification responsibilities | Reconcile final candidate with evidence, verify intended committed/published files when such action is requested, preserve recovery/forward-repair state and make remaining receiver work actionable. |
| interaction with approved decisions | Carry standing authority forward; no repeated permission for already-authorised stages/actions. A new irreversible/out-of-scope action requires its actual missing decision after preparation, not a generic approval ceremony. |

### CMD08 — review-change

Owner: **software-evaluate**.

| Contract field | Definition |
|---|---|
| inputs | Review question, actual base/candidate or supplied diff/artifacts, accepted intent/constraints and available evidence. No software-engineering installation or prior command output is required. |
| preconditions | Enough actual candidate/context to assess the requested scope; missing baseline/source narrows findings. Identify whether this is self-review, a fresh agent or another reviewer without implying independence from a skill name. |
| repository evidence required | Affected code/contracts/consumers/configuration, significant design rationale, tests/oracles and actual run identity. Inspect surrounding context for substantive claims; use supplied evidence when direct access is unavailable and label the limit. |
| outputs | A12 findings tied to source/revision, violated obligation/mechanism, consequence/confidence, blocking versus preference, bounded repair and verification need; assessed/unassessed quality dimensions and completion limits. |
| allowed mutations | Review notes/report and bounded non-mutating inspections or isolated reproductions/check artifacts when authorised. Production repair is outside evaluation mode. |
| forbidden mutations | Editing production/source/tests to make the candidate pass, approving product policy or release, broad unsolicited security audit, hiding limits or inventing findings to fill categories. |
| failure states | Insufficient/stale candidate evidence, unavailable relevant check, unsupported assumption or inconclusive quality. Finding a real defect is a successful review outcome with a failed obligation, not an execution failure. |
| verification responsibilities | Validate findings against actual source/behaviour and accepted obligations; distinguish reproducible defect from hypothesis/preference; consider test quality, compatibility, security and performance only to relevant depth. Do not mark unassessed dimensions passed. |
| interaction with approved decisions | Judge against approved intent/architecture/pack traits; approved choices can still have implementation defects. Findings propose bounded repair; they do not silently revoke or rewrite an accepted decision. |

### CMD09 — evaluate-test-quality

Owner: **software-evaluate**.

| Contract field | Definition |
|---|---|
| inputs | Tests/fixtures and code or behaviour they claim to verify, accepted oracle, relevant change/risk and any results/coverage/mutation reports. |
| preconditions | Identify the claimed obligation and enough production/test context to judge sensitivity. Access constraints and missing real dependency behaviour must be explicit. |
| repository evidence required | Assertions, fixtures/mocks, expected error/edge cases, setup/selection/exclusions, relevant source boundary and actual baseline/candidate reports. Inspect dependency fidelity where it affects the obligation. |
| outputs | Assessment of oracle validity, sensitivity, isolation/fidelity, diagnostic value and material omissions; proposed smallest useful test repair with a case that would expose the defect. No universal adequacy percentage. |
| allowed mutations | Evaluation notes and isolated fault-seeding/reproduction artifacts within authorised scope; existing test runs when useful and safe. |
| forbidden mutations | Weakening approved acceptance, rewriting target tests during an assessment-only task, applying mutants to user work, universal per-method test mandates or declaring coverage equivalent to correctness. |
| failure states | No known oracle, unsuitable fixture/substitute, unavailable runner/dependency, inconclusive mutant, unsupported coverage scope. Classify equivalent/invalid/timed-out cases rather than treating every survivor as a real defect. |
| verification responsibilities | Demonstrate or reason precisely about a relevant failure the test would catch; when execution is claimed, inspect the actual failing/passing result. Separate test improvement proposals from implemented repairs. |
| interaction with approved decisions | Approved behaviour supplies the oracle; tests are evidence, not a source of authority to redefine it. An intentional behaviour change can justify updating obsolete tests with traceable rationale. |

### CMD10 — evaluate-compatibility

Owner: **software-evaluate**.

| Contract field | Definition |
|---|---|
| inputs | Proposed/actual interface, dependency, schema or protocol change; supported consumers/versions and accepted intentional deltas; transition/historical-state context. |
| preconditions | Identify what compatibility is promised and to whom. Unknown consumers/version support are material uncertainty, not automatic permission to assume only latest/latest. |
| repository evidence required | API/wire/source/semantic contracts, defaults/errors, generated clients, schemas/data, reader/writer deployment order, migration implementation and meaningful existing compatibility results. |
| outputs | Supported/broken/unverified combinations, concrete semantic/data counterexamples, transition/recovery concerns and bounded repair/verification recommendations; distinguish intended break from unintended regression. |
| allowed mutations | Compatibility report, non-mutating diff/analysis and isolated consumer/transition probes with representative synthetic or permitted data. |
| forbidden mutations | Changing public contracts/data/support policy, executing destructive live migration, accepting schema shape as complete semantics or assuming Git rollback restores durable/external state. |
| failure states | Unknown supported matrix, absent historical data evidence, unsupported consumer generation, failing/inconclusive transition, unavailable real dependency or unresolved approved-intent conflict. |
| verification responsibilities | Check relevant old/new and intermediate states, actual semantic oracles and recovery assumptions; exact executed cases remain bounded. Do not require all theoretical version combinations without a support obligation. |
| interaction with approved decisions | Accepted support/deprecation/architecture rules constrain judgment. An approved breaking change is evaluated for its intended transition and unaffected obligations, not rejected merely for differing from old behaviour. |

### CMD11 — evaluate-security-risk

Owner: **software-evaluate**.

| Contract field | Definition |
|---|---|
| inputs | Requested security assessment or materially changed trust/control surface, scope, assets/actors, accepted policy, candidate and relevant scanner/evidence inputs. |
| preconditions | Establish the actual security question, permitted inspection/experiment environment and relevant language/framework version. Specialist depth beyond available evidence is explicit. |
| repository evidence required | Affected auth/input/data/control paths, configuration/secrets handling, component provenance/resolution, trusted boundaries and applicable negative/positive tests/scanner rules and exclusions. |
| outputs | Concrete threat/control findings with source/attack preconditions, consequence/confidence, verification gaps and bounded remediation; identify residual decisions needing the actual specialist/owner. |
| allowed mutations | Scoped report, read-only scans and isolated authorised negative/positive probes; retain only necessary redacted evidence. |
| forbidden mutations | Unrequested live exploitation, broad control/policy changes, exposing secret values, treating a clean scanner as security proof, or converting ordinary unrelated engineering work into a blanket audit. |
| failure states | Unsupported framework/control, missing threat/policy facts, unavailable scanner/rules, inconclusive reachability or contradictory evidence. No unsupported claim of safety or confirmed vulnerability. |
| verification responsibilities | Ground claims in actual paths and conditions, test legitimate and forbidden behaviour when appropriate, retain scanner scope/version limits and distinguish possibility from demonstrated exploitability. |
| interaction with approved decisions | Approved policy and selected specialisation constrain expected behaviour; approval does not prove controls are implemented. The evaluator cannot accept residual business/security risk on another owner's behalf. |

### CMD12 — evaluate-performance-risk

Owner: **software-evaluate**.

| Contract field | Definition |
|---|---|
| inputs | Candidate/change, accepted workload and performance/resource/reliability constraints, baseline/measurement data, concurrency/fault/recovery context and the assessment question. |
| preconditions | A defined outcome and comparable evidence or a clearly labelled plan to obtain it. Unknown target workload/budget remains explicit instead of inheriting a benchmark default. |
| repository evidence required | Hot paths/resources, profile/benchmark settings and samples, candidate/environment identity, state/invariant/retry/cancellation paths and relevant fault/interleaving tests. |
| outputs | Workload-qualified performance/resource findings, comparability limits, concurrency/progress/reliability risks, causal hypotheses and bounded repair/measurement needs; correctness trade-offs remain visible. |
| allowed mutations | Assessment notes and bounded isolated benchmark/profile/fault probes when authorised; no production tuning by an assessment-only command. |
| forbidden mutations | Invented speedups, a new universal budget, live stress without authority, optimisation that silently changes semantics, treating retries as harmless or converting a stress pass into proof of every schedule. |
| failure states | Noncomparable/noisy samples, unknown workload/budget, unavailable profiler/environment, inconclusive cause, correctness failure or unknown external completion/recovery. |
| verification responsibilities | Inspect raw conditions/results and the mechanism linking change to outcome; compare relevant tails/resources, preserve correctness and check stated concurrency/fault assumptions. Clearly separate measured regression from risk requiring investigation. |
| interaction with approved decisions | Use approved workload/budgets/invariants and intentional pack traits. A new performance target or loss/consistency trade-off is an owner decision; avoid rejecting a valid specialisation solely for differing from generic defaults. |
## Tool discovery and execution

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
## Runtime dependencies and helper limits

A small deterministic helper is justified only by a concrete composition problem: for example, an existing machine-readable report needs a bounded extraction, or a repeated command needs reliable server cleanup. Before adding it, check whether the repository/host/upstream tool already provides the needed interface. Define input/output, scope, failure behaviour, supported environment and a direct way to call the underlying tool without the helper where feasible.

The helper must preserve native exit/timeout meanings, relevant output and command identity; keep dependencies proportionate; avoid a new persistent runtime; and have meaningful checks for parsing/error/cleanup behaviour. Its existence does not permit a semantic success claim. Source-repository helpers require concrete implementation evidence and verification; none is automatically inherited from a researched external example.

External generative skills are a separate optional composition boundary. Their instructions can suggest domain patterns, not replace accepted intent or the core's evidence responsibilities. REFERENCE does not mean activated. ADAPT requires a reviewed, licensed compatible variant before use. Preserve full context of the selected supporting reference, provider constraints and updated source when actually consuming it. A packaging convention can vary by host without changing O01–O10 or WF1–WF6.

## Installation contract

Use existing Git/GitHub acquisition and the target agent's supported skill installation/discovery mechanism. Full installation includes both advertised skill folders and advertised selected packs; selective installation includes exactly the requested folders and their local resources. Preserve relative layout and exact revision/file identity. Do not overwrite a consumer's modified existing installation silently. Do not install unrelated researched skills or every ecosystem dependency.

The minimum engineering consumer receives only `software-engineering`; evaluator alone is a valid separate selection. A pack consumer receives its selected pack and the relevant core/evaluator, without another pack. Acquiring committed GitHub bytes through an authenticated host's GitHub tools is a valid source-origin path; a local copy is not evidence of GitHub acquisition. Record actual path and operation. Installation commands and invocation spelling in public docs must be tested as advertised; label untested host alternatives rather than claim success.

The source checkout, research logs, original PDFs and other skill directories must be absent from the consumer task's accessible bundle. Invoke the actual target coding agent against the installed skill and fixture, read needed local references, perform the requested bounded mode and run relevant native checks. Static reference validation is a separate gate and cannot impersonate this run. Each advertised skill must be discovered and exercised selectively; representative packs require the same clean-use evidence. Specification 04 IN01–IN06 defines the separate local/external oracles.

## CI and technical acceptance

Repository CI, when introduced, runs actual versioned source/package checks and deterministic benchmark entrypoints with declared runtime prerequisites. Preserve native nonzero exits and diagnostics; no `continue-on-error` for mandatory gates, empty collection pass, synthetic green status or hidden download/credential requirement. Keep model-generation evidence separate from deterministic revalidation: CI replay of existing outputs is not a fresh coding-agent production run. Report if a workflow file exists but remote CI has not actually run.

Technical acceptance requires valid described entrypoints, twelve complete mode contracts, real local reference resolution, no hidden source-checkout dependencies, tested full/selective installation, actual target-agent use for every advertised skill, explicit prerequisites, working README/benchmark invocations, protected user changes and candidate-specific verification. The exact production files first appear in the designated implementation stages; this specification does not advertise them as already usable.


## Provenance and specification ownership

[S01 charter](research-logs/2026-09-12-stage-01-project-goal-and-domain-boundary.md), [source-qualified C/S/W models](research-logs/2026-09-13-stage-04-professional-practice-challenge.md), [CT/CO/SI context](research-logs/2026-09-13-stage-05-change-contract-and-context-model.md), [WF/A/RR semantics](research-logs/2026-09-13-stage-06-workflow-and-artefacts.md), [VL/RF/CP policy](research-logs/2026-09-13-stage-07-verification-risk-and-commitment.md), [D/S/P capability inventory](research-logs/2026-09-13-stage-08-candidate-evaluations.md), [execution architecture](research-logs/2026-09-13-stage-09-execution-layer.md), [core design](research-logs/2026-09-13-stage-11-core-skills-and-commands.md), [pack research](research-logs/2026-09-13-stage-12-extension-packs-completion.md), [example selection](research-logs/2026-09-13-stage-13-progressive-examples.md) and [evaluation design](research-logs/2026-09-13-stage-14-evaluation-and-benchmarks.md) preserve the decision/source register and research limitations. These links are maintainer provenance, not installed runtime dependencies.

The six specifications divide canonical responsibilities: [01 system](01-software-engineering-skills-system-spec.md), [02 workflows/artefacts](02-software-engineering-skills-workflows-and-artifacts-spec.md), [03 repository/contracts](03-software-engineering-skills-repository-and-contracts-spec.md), [04 testing/benchmark](04-testing-and-benchmark-spec.md), [05 packs](05-software-engineering-extension-packs-spec.md), [06 catalogue](06-software-engineering-extension-pack-catalogue.md). Operational details copied into role-local installed guidance must preserve the owning specification's meaning and be checked for drift; no shared runtime is implied.

---

Version 1.0 — 13 September 2026. Initial canonical specification from accepted research.
