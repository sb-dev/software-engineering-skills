# Stage 11: Skill-Local Command Contracts

Companion to [the core skill design](2026-09-13-stage-11-core-skills-and-commands.md). These **12 commands × 9 required fields = 108 contract entries** specify bounded operating modes, not a lifecycle DSL, shell dispatcher or mandatory sequence. Names are prompt-level skill-local labels; host-specific slash-command registration is not assumed.

All inputs can be reconstructed from the user's task and repository; no command requires another command's serialized output or an invented project state file. A missing material precondition is a reason for focused investigation or a specific unresolved decision, not automatic failure of all other useful work. Outputs use the repository's existing canonical artifacts where available.

Stage 6's five result meanings apply to individual obligations: passed, failed, inconclusive, unavailable and not applicable with reason. An assessment can complete usefully by finding a failed obligation. Actual authority is separate from result status. The command-specific mutation limits below are narrower than the host's raw capability; a user request that includes repair can route to engineering without a repeated approval, but review alone never silently becomes repair.

These are design contracts. No command is advertised as implemented, installed, executed or benchmarked by this document. Later implementation must verify behavioural contracts and selective installation, including skill-local resources and unavailable-tool handling.


## CMD01 — inspect-system

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

## CMD02 — design-change

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

## CMD03 — implement-change

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

## CMD04 — select-verification

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

## CMD05 — run-verification

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

## CMD06 — diagnose-failure

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

## CMD07 — prepare-handoff

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

## CMD08 — review-change

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

## CMD09 — evaluate-test-quality

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

## CMD10 — evaluate-compatibility

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

## CMD11 — evaluate-security-risk

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

## CMD12 — evaluate-performance-risk

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
