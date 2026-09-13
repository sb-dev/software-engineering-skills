# Software Engineering Skills: System Specification

**Version:** 1.0 · **Date:** 13 September 2026

**State:** canonical implementation specification; source/behaviour/installation readiness is reported separately.

**Owns:** mission, scope/boundaries, principles, architecture, core skills, execution, risk/verification, approval/commitment, build order and system acceptance.

This specification is derived from the persisted bootstrap research accepted through Stage 14 (`9c84caf8d535aedf8f774a30dfc90a9038315d6a`). Normative operational requirements are stated here; linked research preserves provenance and limitations. A requirement is not evidence that it has been implemented or passed. User/project authority outranks defaults.

## Mission, users and scope

**Mission.** Make reusable software-engineering judgement installable in AI coding agents so they can understand a software system, make a justified change, preserve unaffected behaviour and present credible evidence that the result meets its engineering obligations.

**Owned discipline.** The project owns the engineering of software changes: clarifying technical requirements and acceptance, inspecting system context, assessing impact, designing architecture and interfaces, implementing, testing, reviewing, diagnosing failures, maintaining software and establishing technical release readiness. These responsibilities belong together because a change can satisfy its immediate requirement while breaking a consumer, weakening a control or making future maintenance harder. Engineering judgement must connect intent, implementation and evidence.

**Owned outcomes.** Outcomes include an evidenced diagnosis, a reasoned design decision, working new behaviour, a repaired defect, a behaviour-preserving refactor, a compatible dependency or schema change, a measured quality improvement, and a reviewable release or handoff package. A well-supported decision that no code change is warranted is also a valid outcome. The project must eventually demonstrate these responsibilities in unrelated consuming repositories.

**Scope.** General engineering practice applies to services and APIs, web/mobile/desktop applications, libraries and SDKs, CLIs, automation and distributed systems. Software components of data, ML, games, infrastructure and embedded systems are included where the engineering obligation can be bounded; specialist semantics and assurance stay with their owners. This is a domain boundary, not a claim of implemented support for every ecosystem. Both architecture and implementation are owned. Brownfield work is the primary proving ground; greenfield work remains in scope. Corrective, adaptive, preventive and improvement-oriented maintenance are first-class.

**Users.** The direct users are AI coding agents working for developers and maintainers. Engineers, reviewers and technical leads consume the decisions, changes and evidence. Specialist teams and optional orchestrators exchange bounded work with the project. The consuming repository supplies its requirements, conventions, tools, operational constraints and authority.

**Boundaries.** Product owners decide value and priority; UX owns interaction intent; specialists own domain-specific security, data, model and gameplay judgements; platform/SRE owns shared infrastructure policy and live-service operation. Engineering still owns the correctness of its implementation and verification. Release readiness and explicitly authorised technical release work are included. Launch authority, service ownership and Pactwright lifecycle governance are not transferred to a skill.

**Quality and authority.** Success requires relevant correctness, compatibility, maintainability, security, performance, reliability, operability and trustworthy verification evidence. Preserve valid work and use the cheapest adequate investigation or check. Respect existing authorisations; seek an owner decision when work would otherwise cross an unapproved consequential boundary, such as changing a public contract or irreversibly modifying live data.

## Boundaries and adjacent owners

The boundary follows the judgement being made, not a filename, team title or programming language. One task may need several disciplines. This map names responsibilities even when no separate skill repository implements the adjacent capability yet; a human specialist can be the handoff owner.

| Adjacent discipline | Software Engineering owns | Adjacent owner retains | Handoff and integration evidence |
|---|---|---|---|
| Product management | Technical feasibility, requirement clarification, acceptance translation and implementation trade-offs. | Customer problem, value, priority, business rules and intended product scope. | Receive intent, constraints and success conditions; return feasible options, unresolved policy questions and acceptance evidence. Product owner resolves a choice that changes the product promise. |
| UI/UX design | Implement approved interactions, state transitions, responsive/platform behaviour and accessibility requirements; verify technical behaviour. | Interaction intent, information architecture, usability research and design acceptance. | Receive designs, states, content and accessibility criteria; return implemented flows, technical constraints and behavioural evidence. UX evaluates experience; engineering fixes implementation defects. |
| Security engineering | Apply relevant secure design/construction practices, implement controls, investigate software vulnerabilities and verify fixes. | Specialist threat assessment, security policy, independent assurance and acceptance of residual security risk. | Receive threat/control requirements; return design assumptions, control behaviour, findings and remediation evidence. Escalate specialist uncertainty rather than treating a clean scan as assurance. |
| Platform engineering | Engineer application-facing build, packaging, configuration and infrastructure-as-code changes against known platform contracts. | Shared platform design, tenancy, provisioning policy and platform service ownership. | Receive supported platform interfaces and environment constraints; return versioned changes, compatibility evidence and required platform actions. |
| DevOps / SRE | Software deployability, instrumentation, resilience code, delivery automation, defect repair and authorised technical release steps. | Live-service operation, incident command, capacity and reliability objectives, production change authority and recovery coordination. | Receive operational requirements and failure evidence; return artefacts, readiness results, telemetry changes and migration/recovery constraints. SRE evaluates live effects; engineering remains accountable for its software. |
| QA / testing specialists | Developer verification, test quality, defect reproduction, automated test implementation and code-level/integration regression repair. | Independent exploratory assessment, assembled-product evaluation and any separately assigned acceptance authority. | Receive quality risks and reproducible failures; return exact build/revision, test evidence and known gaps. Integrated QA complements the domain's evaluation; it does not excuse unverified engineering. |
| Data engineering | Persistence APIs, schemas and migrations as software, transaction and failure semantics, and implementation of agreed pipeline behaviour. | Data definitions, lineage, transformation meaning, quality policy and ownership of datasets. | Receive data contracts and invariants; return migration plans, integrity checks and integration evidence. A passing script does not establish that the business meaning of the data is correct. |
| ML engineering | Application and serving integration, software interfaces, dependency behaviour, reproducibility mechanics and system reliability. | Dataset/model choices, training and inference methodology, model evaluation, drift judgement and model-specific assurance. | Receive model interface, version and acceptance envelope; return integration and failure-mode evidence. Correct transport of model output does not prove that output is valid. |
| Game development | Runtime architecture, networking, persistence, concurrency, performance and implementation correctness for agreed game behaviour. | Game rules, mechanics, balance, game feel, simulation intent and gameplay acceptance. | Receive mechanics, invariants, timing targets and acceptance scenarios; return working runtime behaviour and measurements. Gameplay evaluation remains necessary even when code is correct. |
| Deep research | Bounded investigation needed for an engineering decision: repository evidence, reproductions, official technical references and focused experiments. | Broad literature/research strategy, source evaluation and synthesis beyond the immediate technical task. | Receive evidence with provenance and limits; return an implementation question, contextual applicability judgement or findings requiring wider investigation. Source support and implementation proof remain separate. |
| Technical writing | Accuracy of change-related API documentation, migration notes, build/test instructions, design rationale and engineering handoff records. | Editorial strategy, audience research and larger documentation or educational programmes. | Provide verified technical facts and executable examples; receive clarity and audience requirements. Engineering verifies technical corrections to its documentation. |
| Pactwright lifecycle governance | Domain execution expertise and engineering evidence. | Contracts, lifecycle state, delivery authority, project governance and Project Graph semantics. | Receive a bounded responsibility, relevant constraints and authorisation; return artefacts, results and unresolved decisions. The same engineering capability must work without Pactwright. |

A handoff should identify the producing and receiving owner, the specific decision or artefact, its revision and constraints, and who evaluates the integrated result. Use the consuming project's existing records. This stage does not introduce a universal handoff schema or runtime.

Boundary disagreements must be made explicit. For example, engineering can demonstrate that an API behaves as specified while product concludes that the specified behaviour is wrong. Both findings should survive; responsibility for changing the requirement is distinct from repairing an implementation defect.
## Reusable expertise and consuming-project context

| Knowledge | Reusable part owned here | Project-specific instance and home |
|---|---|---|
| Repository understanding | How to locate relevant instructions, trace a behaviour, inspect dependencies and distinguish facts from assumptions. | This repository's modules, entry points and architecture, held in its source/docs or project knowledge. |
| Contracts | How to identify invariants, consumers and compatibility consequences. | Actual API/event schemas, accepted behaviour and consumer agreements in the consuming project. |
| Verification | How to choose adequate checks and judge evidence. | Exact build/test commands, environment setup, baselines and CI policy in the consuming repository. |
| Architecture and conventions | How to assess a change against existing constraints and justify an exception. | Approved decisions, language/style rules and dependency choices in local instructions and design records. |
| Failures and diagnosis | Reusable reasoning for isolating causes and correcting the responsible scope. | Incident history, environment-specific failure evidence and temporary workarounds in project records. |
| Release and operation | How to assess delivery readiness and communicate migration/recovery limits. | Deployment targets, service objectives, access rules and authorisation records owned by the project and operators. |
| Specialisation | Knowledge reusable across several projects that materially changes engineering behaviour, if later justified as a pack or composed specialist capability. | A single project's preferred framework, package layout or topology remains project context unless independently generalised and evaluated. |

Consume authoritative local instructions and accepted decisions before applying generic defaults. When they conflict with the requested outcome, expose the conflict and use the applicable authority to resolve it. Do not silently normalise the repository to a preferred architecture. Do not copy customer code, secrets or project-specific findings into public skill references as a side effect of learning.

Durable project knowledge may live in Project Intelligence when present, or in ordinary repository documentation and issue/decision records. The method must work with either. A persistent universal code graph or agent memory service is not required by this boundary.
## Non-goals

The project does not own product strategy, UX research, organisation-wide governance, unrestricted production operation or the specialist truth of a data/model/game/scientific result. It does not certify regulatory compliance, safety or security simply because technical checks pass.

It does not aim to replace compilers, build tools, test runners, debuggers, profilers, scanners, package managers, coding agents or existing capable specialist skills. It directs and composes them. Nor is it a language encyclopaedia, provider router, universal workflow engine, repository knowledge database or mandatory Pactwright runtime.

| Alternative boundary | Reason rejected |
|---|---|
| Own only code generation | Excludes the system understanding, compatibility, diagnosis and verification needed to make a change dependable. |
| Own every activity touching software | Absorbs product, domain, platform and governance authority; removes meaningful specialist handoffs. |
| Restrict the domain to the family brief's browser/game stack | Confuses a consuming project's initial examples with reusable software engineering. Technology-specific depth remains an evidence-led later decision. |
| Own architecture advice but delegate correctness and testing | Separates the design from the evidence needed to judge its consequences. Responsibilities may later be separately installable without ceasing to belong to this discipline. |
| Own deployability but forbid all release execution | Creates an artificial gap for explicitly authorised engineering delivery tasks. The useful boundary is technical responsibility and actual authority, with service operation assigned separately. |
| Put every framework or quality concern into a pack now | Predetermines the architecture before research. Some responsibilities are core, some belong to tools/specialists, and some may later justify packs. |

## Governing principles

1. Inspect relevant source, real bindings, effective configuration and accepted decisions before consequential edits; keep unknowns explicit.
2. Separate intended delta, valid preservation and observed behaviour of unknown validity. Characterisation does not approve a bug; a bug label does not authorise breaking valid consumers.
3. Choose the smallest coherent scope, which may cross multiple files/layers. Avoid unrelated cleanup, speculative abstractions and whole-system rewrites.
4. Match oracles and real dependency boundaries to the risk. A green test is useful only for what it observes; preserve failing/inconclusive/unavailable evidence.
5. Diagnose with discriminating observations, preserve valid work and repair the owning cause. Distinguish mitigation, restored service and permanent regression prevention.
6. Treat verification evidence, acceptance and action authority separately. Carry standing authorisation through the requested outcome without repeated ritual gates.
7. Keep twelve quality dimensions distinct. Correctness cannot be traded silently for performance, and style preference is not a product defect.
8. Keep skills and packs locally complete and tools replaceable. No central lifecycle, graph, evaluator, pack interpreter or provider runtime is required.

## System architecture and core skills

The consuming repository supplies task intent, contracts, architecture, conventions, native tools and authority. The coding-agent host supplies file/search/edit/shell/service access. This project supplies engineering judgement and evidence contracts. Its outputs are the requested diagnosis/design/change/evaluation/handoff plus actual evidence, using existing canonical project records.

| Component | Owned responsibility | Independence / boundary |
|---|---|---|
| `software-engineering` | Complete WF1–WF6 loop: inspect, design, implement, select/run checks, diagnose, self-review, bounded repair and handoff | Minimum complete-workflow installation; no evaluator, pack, subagent or orchestrator prerequisite |
| `software-evaluate` | Optional assessment-only entrypoint: review, test quality, compatibility, security and performance | Accepts raw task/repository/candidate without engineering-generated artifacts; does not silently edit production |
| Selected Extension Pack | Reusable specialised decision/verification guidance under actual activation and precedence | Optional; each pack carries necessary local guidance; no inheritance from another pack or original books |
| Domain pack-authoring workflow | Explicit create/refine/research/evaluate pack request within engineering, using local authoring reference | Distinct from ordinary application editing; no third generative skill or thirteenth application command |
| Native tools / host | Existing compiler, runner, package manager, profiler, scanner, Git and CI execution | Preserve actual invocation semantics and permission limits; do not reimplement them |

Natural-language requests are the primary interface. CMD01–CMD07 belong to engineering; CMD08–CMD12 to evaluator, as defined completely in Specification 03. Names are prompt-level modes, not promised slash commands or a compulsory sequence. Engineering retains sufficient self-review when evaluator is absent. A compound review-and-fix request carries existing repair authority; review-only stays assessment-only. A same-context evaluator invocation is still self-review.

Specification 02 owns WF/CT/CO/SI/artifact/evidence/repair semantics. Specification 03 owns packaging, modes and installation. Specification 04 owns test and release evidence. Specification 05 owns pack contracts and authoring; Specification 06 owns actual entries/status. This ownership avoids a central runtime while allowing concise role-local guidance to be checked for semantic drift.
## Engineering decision ownership

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
## Execution architecture

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
## Verification ladder and evidence selection

Choose evidence by **obligation and failure mechanism**, then cost. The following order is a default search order for cheap feedback, not a mandatory sequence or assertion of identical cost in every repository. Some systems have cheap integration tests and expensive typechecking; a focused security check may be the first relevant executable check. Do not run every command that happens to exist.

| ID / activity | What it can establish | When to select it | Limit / escalation signal |
|---|---|---|---|
| VL01 — Static repository inspection | Relevant intent, paths, contracts, build inputs, existing evidence and bounded reasoning. | Before a change; reuse and verify current context where available. | Dynamic use, hidden configuration or uncertain effects need targeted observation, not an invented complete graph. |
| VL02 — Formatter / linter / syntax validation | Mechanical conformance and issues covered by the actual rules/parser. | Changed files/languages for which the repository uses these checks and they provide relevant evidence. | Passing says little about intended behaviour; inspect config and whether rules ran on the actual files. |
| VL03 — Compile / typecheck | Constraints enforced by the actual compiler/type system/build configuration. | Relevant compiled/typed/build surfaces or a required project gate. | Cannot establish semantic contracts, all runtime paths or correct packaging; a failure may be environment-related. |
| VL04 — Focused tests | Selected acceptance/regression properties at a meaningful boundary. | A change has relevant executable obligations or a known failure mechanism; reuse adequate existing tests. | Check oracle sensitivity and substitute fidelity. A new test is not needed merely to mirror a low-impact edit. |
| VL05 — Affected module tests | Interacting behaviour within identified modules/packages. | Local changes affect shared code/state or focused checks leave a material module risk. | Module boundaries may not contain the impact; inspect real consumers. |
| VL06 — Integration / contract tests | Interoperability, runtime boundaries and supported participant behaviour within tested conditions. | API/schema/protocol/real-dependency risks cannot be established locally. | Fakes or one new/new combination may miss constraints, old clients and intermediate states. |
| VL07 — Security or compatibility checks | Specific control, trust, supported-version or consumer obligations. | Changed trust/control/dependency/public surfaces or applicable project gates. | A clean scan or schema diff cannot establish all security/semantic compatibility. Use targeted adversarial/consumer evidence. |
| VL08 — Performance / concurrency checks | A measured workload property, legal interleaving, race/progress condition or bounded model result. | Change affects an accepted budget, shared-state invariant or relevant failure mechanism. | Environment/workload/oracle limits matter; a stress pass is not proof of every schedule. |
| VL09 — Broad regression suite | Known wider regressions covered by the suite. | Cross-cutting impact, substantial uncertainty or an existing mandatory gate justifies its cost. | Broad success does not fill a missing critical oracle. Diagnose relevant baseline failures; do not hide them. |
| VL10 — Smoke / end-to-end validation | Key integrated behaviour of the actual assembled candidate/environment. | Packaging, startup, delivery, interaction or cross-system changes require it. | A happy-path smoke cannot replace a destructive migration or failure/recovery check. |
| VL11 — Release/deployment verification | Actual artifact identity, transition and post-action result within the requested boundary. | The task includes release readiness or an authorised release/deployment action requiring such evidence. | Readiness is not execution. Check operating authority and report observed outcome, including uncertain completion. |

### 2.1 Selecting and interpreting evidence

For each material obligation, name the expected result and failure the check must expose. Reuse adequate existing evidence only when candidate, inputs, oracle and context still apply. Prefer a focused discriminating check to unrelated breadth. Use review for design/semantics that execution does not decide. Multiple weak checks do not collectively establish an untested invariant.

Evidence selection records: obligation; selected method/command; oracle and environment; expected scope; relevant pre-existing failures; escalation trigger; and actual outcome when executed. A short plan/result in an issue or handoff can suffice. Stage 6 A11 owns evidence identity and lifetime. Before a costly check, establish that prerequisites and cheaper relevant blockers are resolved; do not spend time proving an already-invalid candidate.

Preserve five result meanings: passed, failed, inconclusive, unavailable and not applicable with reason. Separate a tool/setup failure from an observed product defect. A check designed but not executed is planned evidence only. Do not claim full coverage, security, performance or production readiness from a result with narrower scope.
## Risk-sensitive verification policy

Stage 5 RK1–RK4 remain qualitative consequence/uncertainty categories. Refine them using the eleven required factors below. Keep observations and unknowns visible instead of producing a universal numeric score. A one-line security/retention edit can warrant stronger evidence than a large mechanical refactor.

| ID / factor | Questions and evidence | Verification consequence |
|---|---|---|
| RF01 — Blast radius | Which users, modules, tenants, environments or downstream systems can be affected? | Add evidence at actual affected boundaries; broad suite only when its coverage helps. |
| RF02 — Reversibility | Can code, data and external effects be undone, and at what cost? | Rehearse recovery or plan a forward repair before consequential action. |
| RF03 — Contract exposure | Who controls consumers and supported versions? Are semantics public? | Check relevant old/new combinations and accepted deprecation/transition rules. |
| RF04 — Data impact | Can meaning, integrity, access, retention or durable state be changed/lost? | Validate representative historical state, constraints, intermediate steps and recovery. |
| RF05 — Security impact | Which trust boundary/control/secret/component changes? | Use threat-driven negative/positive evidence and relevant analysis; specialist gaps remain explicit. |
| RF06 — Concurrency | Which actors share state or create effects under interleaving/retry? | State invariant/progress assumptions; select schedule/atomicity/protocol evidence. |
| RF07 — Runtime criticality | What happens if the path fails, stalls or is unavailable? | Assess fault/degradation/recovery and receiving operational requirements. |
| RF08 — Performance sensitivity | Which workloads/resources/latency distributions matter? | Use comparable measurements and maintain correctness/other budgets. |
| RF09 — Test coverage confidence | Do existing tests have valid oracles and relevant boundaries? What is unobserved? | Improve the specific feedback gap; do not confuse coverage percentage with adequacy. |
| RF10 — Change novelty | Is the pattern understood in this repository or does it introduce unfamiliar semantics? | Add a bounded prototype/primary-reference check or design review tied to the uncertainty. |
| RF11 — Cross-service coupling | Can independently deployed participants observe incompatible or partial state? | Verify supported transition/failure combinations and end-to-end effect ownership. |

Additional context such as consumer control and observability qualifies these factors; it is not an unbounded scoring exercise. Failure likelihood may be unknown. Record the concrete adverse outcome and choose a check that reduces the uncertainty affecting the decision. Existing authority resolves permission, not technical adequacy.

### 3.1 Policy by change mechanism

This table makes Stage 5's twelve change classes actionable. “Start” is evidence to consider, not a guarantee that every listed command is needed. Existing mandatory repository gates remain mandatory even when a cheaper check appears adequate; do not silently waive them.

| Change class | Start with | Escalate when | Evidence required before claiming the intended outcome |
|---|---|---|---|
| CT01 — New behaviour | Intent/context and targeted acceptance/preservation evidence. | Shared rule, public consumer, integrated journey or quality exposure changes. | New outcome plus affected valid obligations; relevant semantic review. |
| CT02 — Bug repair | Expected/actual distinction, causal evidence and sensitive regression case. | Cause crosses environment/service/state boundaries or reproducer underrepresents impact. | Repair of the demonstrated mechanism; original and neighbouring cases assessed. |
| CT03 — Refactor | Preservation envelope, baseline feedback and semantic diff. | Dynamic consumers, shared state, build/export changes or weak feedback obstruct preservation. | Relevant behaviour preserved and structural rationale justified; compilation alone is insufficient. |
| CT04 — API evolution | Contract delta and affected consumer cases. | Old/generated clients, wire/state semantics, public support or retirement is involved. | Supported combinations and explicit intentional breaks/transition treatment. |
| CT05 — Schema/data migration | Data/reader/writer map and small conversion/constraint checks. | Durable mutation, representative volume, mixed versions, locks or nontrivial recovery applies. | Intermediate-state correctness, reconciliation and credible recovery evidence. |
| CT06 — Dependency/platform upgrade | Effective resolution/configuration, release/advisory information and used-interface checks. | Native/toolchain, transitive, trust or supported-environment changes matter. | Actual candidate builds/works in required environments with compatibility/trust obligations addressed. |
| CT07 — Performance change | Valid baseline/workload and focused measurement/profile. | Resource interaction, tails, sustained load or concurrency can invalidate the local result. | Comparable improvement against accepted target with correctness and other budgets retained. |
| CT08 — Security change | Specific threat/control analysis and positive/negative cases. | Bypass/sibling path, novel mechanism, sensitive exposure or specialist uncertainty remains. | Enforced control within stated scope; valid use and residual-risk decision explicit. |
| CT09 — Reliability/resilience | Stated fault model, invariant, partial-effect and recovery reasoning. | Distributed state, stale actors, retry identity or progress assumptions cross boundaries. | Meaningful fault/recovery evidence with untested assumptions disclosed. |
| CT10 — Operability/observability | Diagnostic question, signal content and focused behaviour check. | Sensitive data, cardinality, overhead, startup or operational integration is affected. | Useful observation/action without violating relevant security/resource/behaviour obligations. |
| CT11 — Removal | Supported usage/retention/transition evidence and remaining-behaviour checks. | Durable data, external consumers or irreversible retirement applies. | Retirement is authorised and complete at the requested scope; retained obligations hold. |
| CT12 — Architecture migration | Constraints/alternatives, effect boundaries and transition plan. | Independently deployed state, changed qualities, trust or ownership affects the migration. | Every supported intermediate architecture meets required obligations; no final-only success claim. |

### 3.2 Escalation and stopping algorithm

1. Establish relevant obligations and authority from existing sources. Inspect RF01–RF11 for applicability and uncertainty, using the bounded system context.
2. Select evidence that can expose each material failure mechanism. Identify already-required gates, what can be reused and what needs fresh execution. Do not add tests for merely reversible, low-impact edits without a concrete risk or required gate.
3. Resolve cheap relevant blockers first. Execute broader checks when their boundary is necessary, not because they appear later in the ladder.
4. On failure, diagnose whether the issue is product, oracle, environment, evidence identity or an unrelated baseline. Use Stage 6's owning repair route, preserve valid work and recheck affected claims.
5. Stop optional verification when the authorised outcome and relevant preservation claims have adequate evidence, required gates pass, material findings are resolved and the final candidate is identified. Additional checks need a concrete remaining risk or gate.
6. Escalate to a user/owner decision only for a real unresolved ambiguity, conflicting accepted constraint, missing authority, required unavailable capability or proposed scope exception. First do all authorised preparation needed to make the question concrete and reviewable.
7. If required evidence cannot be obtained, evaluate a materially adequate alternative without misrepresenting its scope. If none satisfies the requirement, stop at that boundary, report what failed and ask the necessary question. Do not call missing evidence a pass or proceed to dependent acceptance.

These rules terminate completed work, not the user's already-authorised multi-stage objective. A completed stage with no blocker proceeds to its next authorised stage after its commit gate. The current bootstrap's contract supplies the stage-level requirements; this general domain policy does not weaken them.
## Approval and commitment policy

A commitment is a point where changing direction becomes consequential: a public promise, durable mutation, expensive resource, or irreversible action. Preparation, technical review and execution are different decisions. Review is evidence; approval is authority. Both may already exist. Do not require a second approval merely because a skill has reached a named phase.

Before the commitment, check: the concrete action and target; the existing authorisation's scope; technical prerequisites; effects and recovery; and any actual owner/policy gate. If authorisation is sufficient, proceed when the technical gate passes. Otherwise prepare a reviewable candidate/plan and ask the specific decision. No blanket “human approval required” rule is imposed on routine reversible tasks.

| ID / category | Deliberate decision or locking appropriate | Authority treatment | Evidence prepared before any needed question |
|---|---|---|---|
| CP01 — Public API breaks | Fix the intended contract/version and supported transition before exposing the break. | A previously authorised break/support decision is sufficient; otherwise the actual contract owner decides. | Affected consumers, alternatives, semantic delta, compatibility evidence and migration cost. |
| CP02 — Schema migrations | Bind the reviewed sequence to schema/application versions and supported intermediate states. | Local reversible preparation is ordinary engineering; apply existing environment/data authority to execution. | Conversion/constraint tests, deployment sequence, lock/volume effects, recovery and stop conditions. |
| CP03 — Data-destructive operations | Identify exact target/data, effect boundary and recoverability before deletion. | Require applicable authority for the destructive action; do not infer it from a generic code-edit request. | Preview/scope, retention decision, backup/restore or irreversibility facts, and safer adequate alternatives. |
| CP04 — Security model changes | Establish which access/trust promise changes and any accepted residual risk. | Routine implementation of accepted policy is authorised; changing policy or specialist risk acceptance uses its actual owner. | Control delta, legitimate/illegitimate cases, threat impact, alternatives and unresolved specialist questions. |
| CP05 — Architecture migrations | Fix important constraints and transition choices before broad dependent work or exposure. | Existing migration scope permits routine design/implementation; new consequential trade-offs need an owner only when outside that scope. | Alternatives, preserved obligations, intermediate states, risks and rollback/forward-repair plan. |
| CP06 — Large dependency/platform upgrades | Bind target versions, support matrix and effective configuration before rollout. | Size alone does not create approval; changed trust/support/cost or existing gates may require a decision. | Used/transitive impacts, clean build/install evidence, compatibility, advisories and recovery limits. |
| CP07 — Irreversible release operations | Bind exact artifact/target and action; distinguish publication, deployment and exposure. | Execute when specifically within existing release authority and gates; otherwise ask after candidate preparation. | Exact candidate evidence, release/transition instructions, irreversible consequences and recovery constraints. |
| CP08 — High-cost infrastructure consequences | Identify resource, cost/range and duration before provisioning or load operations. | Existing budget/environment authorisation governs; code readiness does not authorise new spend. | Estimated/known cost basis, target, purpose, cheaper adequate options and cleanup/stop conditions. |

**Deliberate locking** here means stabilising the decision/candidate whose evidence is being assessed: revision or content digest, relevant inputs, migration version and target. It does not require a global lock service or freeze all development. If that identity changes, reassess affected evidence and authority. Use existing platform concurrency locks only where that platform's semantics and the action require them; do not invent a lock runtime for skills.
## Recovery and reversibility

Rollback is an evidenced recovery option, not a universal inverse operation. Distinguish code/configuration restoration, durable-state recovery, external-effect compensation and forward repair. Restoring an old binary does not restore deleted data or make it compatible with a changed schema. A backup's existence is weaker evidence than a demonstrated usable restore for the relevant context.

| Surface | What may be reversible | What remains or can make reversal unsafe | Required reasoning/evidence |
|---|---|---|---|
| Local source/diff | Restore a known version while preserving unrelated user work. | Other edits or dependent changes may make blind reversion wrong. | Identified base/candidate, bounded patch and affected checks. |
| Runtime configuration | Restore previous effective values. | Processes may cache state; external effects may already have occurred. | Actual precedence/reload semantics, resulting state and observation. |
| Dependency/platform | Rebuild or redeploy a supported prior version. | Data formats, ABI, caches or removed platform support may prevent safe downgrade. | Supported matrix and exact artifact/configuration evidence. |
| Schema/data | Reverse a proven lossless transformation or restore/reconcile state. | Destructive conversion, new writes, partial backfill and privacy/retention obligations may block reversal. | Intermediate-state/reconciliation plan and realistic recovery check. |
| External effects | Compensate where domain semantics allow. | An email/payment/publication may not be retractable; compensation is another effect. | Actual effect identity, domain authority and idempotent/conditional recovery semantics. |
| Distributed rollout | Stop exposure or return compatible participants. | Version skew, delayed messages and shared durable state outlive one deployment. | Compatibility/fault assumptions and observed transition status. |

For a risky transition define the observation that triggers stop, who can act, what safe state is reachable and how it is verified. If completion is unknown, reconcile before repeating the action. Do not turn a failed recovery into a successful release report. Temporary mitigation, restored service and eliminated root cause are separate claims.

## Build order and system acceptance

Build in the authorised bootstrap order: Stage 16 public README design; Stage 17 justified scaffold; Stage 18 installed core-only E01 external vertical and defective-candidate detection; Stage 19 progressive E01–E15 plus both selected packs' real P6/P7; Stage 20 separate local integrity and clean GitHub consumer use; Stage 21 optional bounded Pactwright binding; Stage 22 evidence-based registry/maturity; Stage 23 independently evidenced shared-abstraction review; then full-bootstrap audit. Do not implement every command/ecosystem before the first vertical works.

Each top-level stage is one complete reviewed task and **one commit**, with its stage number in the subject: `docs(bootstrap): stage N - description` for documentation, or an appropriate conventional type for implementation. Internal P-stage research/evidence remains distinct and traceable within the owning top-level stage; do not split that stage's branch history into extra commits. This incorporates the user's explicit commit correction. Existing accepted historical research references remain accessible through the preserved backup history.

System acceptance requires: complete core outcome without packs; both advertised skills independently usable; all six spec responsibilities implemented; exactly fifteen complete primary examples, three per level, with exact prompts and actual changes/results; operational deterministic/behavioural/quality/regression benchmark; selected packs with actual showcase, distinct reuse, fair differential and authoring evidence; separate clean installation of every advertised skill and pack; accurate README/catalogue and measured or explicitly unmeasured claims. Technical readiness never by itself authorises merge, publication, live migration or deployment.

At Specification 1.0 these are required future gates, not passed results. The source is specified; production scaffold, skill implementation, generation benchmarks and installation remain unperformed. Registry promotion occurs only at its owning authorised stage against actual evidence. No numerical productivity, quality, security or general pack-superiority claim is supported by the research alone.


## Provenance and specification ownership

[S01 charter](research-logs/2026-09-12-stage-01-project-goal-and-domain-boundary.md), [source-qualified C/S/W models](research-logs/2026-09-13-stage-04-professional-practice-challenge.md), [CT/CO/SI context](research-logs/2026-09-13-stage-05-change-contract-and-context-model.md), [WF/A/RR semantics](research-logs/2026-09-13-stage-06-workflow-and-artefacts.md), [VL/RF/CP policy](research-logs/2026-09-13-stage-07-verification-risk-and-commitment.md), [D/S/P capability inventory](research-logs/2026-09-13-stage-08-candidate-evaluations.md), [execution architecture](research-logs/2026-09-13-stage-09-execution-layer.md), [core design](research-logs/2026-09-13-stage-11-core-skills-and-commands.md), [pack research](research-logs/2026-09-13-stage-12-extension-packs-completion.md), [example selection](research-logs/2026-09-13-stage-13-progressive-examples.md) and [evaluation design](research-logs/2026-09-13-stage-14-evaluation-and-benchmarks.md) preserve the decision/source register and research limitations. These links are maintainer provenance, not installed runtime dependencies.

The six specifications divide canonical responsibilities: [01 system](01-software-engineering-skills-system-spec.md), [02 workflows/artefacts](02-software-engineering-skills-workflows-and-artifacts-spec.md), [03 repository/contracts](03-software-engineering-skills-repository-and-contracts-spec.md), [04 testing/benchmark](04-testing-and-benchmark-spec.md), [05 packs](05-software-engineering-extension-packs-spec.md), [06 catalogue](06-software-engineering-extension-pack-catalogue.md). Operational details copied into role-local installed guidance must preserve the owning specification's meaning and be checked for drift; no shared runtime is implied.

---

Version 1.0 — 13 September 2026. Initial canonical specification from accepted research.
