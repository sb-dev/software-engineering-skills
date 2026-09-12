# Stage 1: Project Goal and Domain Boundary

**Project:** `software-engineering-skills`  
**Stage:** 1, Define Project Goal and Domain Boundary  
**Status:** Complete for the initial boundary; corpus research, broader challenge and implementation remain unperformed on this branch  
**Version:** 1.0  
**Date:** 12 September 2026  
**Execution branch:** `feat/bootstrap-2`  
**Starting revision:** `main` at `684986785ceafbc031419d6fc7287dbfe0578dba`  
**Governing bootstrap:** [Software Engineering Skills bootstrap v1.1, Stage 1](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#8-stage-1--define-project-goal-and-domain-boundary)

## 1. One-page domain charter

**Mission.** Make reusable software-engineering judgement installable in AI coding agents so they can understand a software system, make a justified change, preserve unaffected behaviour and present credible evidence that the result meets its engineering obligations.

**Owned discipline.** The project owns the engineering of software changes: clarifying technical requirements and acceptance, inspecting system context, assessing impact, designing architecture and interfaces, implementing, testing, reviewing, diagnosing failures, maintaining software and establishing technical release readiness. These responsibilities belong together because a change can satisfy its immediate requirement while breaking a consumer, weakening a control or making future maintenance harder. Engineering judgement must connect intent, implementation and evidence.

**Owned outcomes.** Outcomes include an evidenced diagnosis, a reasoned design decision, working new behaviour, a repaired defect, a behaviour-preserving refactor, a compatible dependency or schema change, a measured quality improvement, and a reviewable release or handoff package. A well-supported decision that no code change is warranted is also a valid outcome. The project must eventually demonstrate these responsibilities in unrelated consuming repositories.

**Scope.** General engineering practice applies to services and APIs, web/mobile/desktop applications, libraries and SDKs, CLIs, automation and distributed systems. Software components of data, ML, games, infrastructure and embedded systems are included where the engineering obligation can be bounded; specialist semantics and assurance stay with their owners. This is a domain boundary, not a claim of implemented support for every ecosystem. Both architecture and implementation are owned. Brownfield work is the primary proving ground; greenfield work remains in scope. Corrective, adaptive, preventive and improvement-oriented maintenance are first-class.

**Users.** The direct users are AI coding agents working for developers and maintainers. Engineers, reviewers and technical leads consume the decisions, changes and evidence. Specialist teams and optional orchestrators exchange bounded work with the project. The consuming repository supplies its requirements, conventions, tools, operational constraints and authority.

**Boundaries.** Product owners decide value and priority; UX owns interaction intent; specialists own domain-specific security, data, model and gameplay judgements; platform/SRE owns shared infrastructure policy and live-service operation. Engineering still owns the correctness of its implementation and verification. Release readiness and explicitly authorised technical release work are included. Launch authority, service ownership and Pactwright lifecycle governance are not transferred to a skill.

**Quality and authority.** Success requires relevant correctness, compatibility, maintainability, security, performance, reliability, operability and trustworthy verification evidence. Preserve valid work and use the cheapest adequate investigation or check. Respect existing authorisations; seek an owner decision when work would otherwise cross an unapproved consequential boundary, such as changing a public contract or irreversibly modifying live data.

**Provisional matters.** The exact workflow, five-book corpus, core skill split, Extension Pack dimensions, tools and benchmark design remain for later stages. This charter establishes responsibility, not a production architecture or maturity claim.

## 2. Decision basis and execution scope

This stage executes the domain bootstrap at the starting revision above. That revision contains the minimal workspace, the research-log guide and the v1.1 bootstrap. It contains no completed stage logs, production skills or benchmark implementation. No `AGENTS.md` appears in the inspected repository tree. The separate `feat/bootstrap` branch is not the base of this execution, and none of its stage-completion claims are imported.

The sources in section 12 serve different purposes:

- **Governing requirements:** the domain bootstrap and current canonical family specifications constrain ownership, independence, evidence and stage execution.
- **Project intent:** the family brief identifies reusable implementation engineering and neighbouring disciplines. Its Worldstack-oriented technologies and proposed packs are examples, not a mandatory stack or catalogue for this repository.
- **Professional anchors:** directly read DORA, NIST and Google material provides limited checks on the proposed boundary. These are not a systematic literature review or evidence that the resulting skills work.
- **Stage decisions:** the scope, responsibility allocations and illustrative cases below are design judgements made for this bootstrap. They remain open to evidence-led revision.

The IEEE SWEBOK landing pages could not be directly read because access returned errors. No SWEBOK chapter or edition-specific finding is claimed. That access gap does not prevent an initial charter based on the governing sources and other examined anchors; source access must be resolved before later work relies on SWEBOK content.

Stage 1 does not select books, extract a corpus, settle the workflow, choose providers or design individual skills. The Seed → Five → Challenge sequence remains intact.

## 3. Owned outcomes and software scope

### 3.1 Outcomes and the evidence they require

These are outcome responsibilities, not proposed command names or fixed document templates. The evidence below describes what a future implementation should be able to supply; none has been produced by a working skill in this stage.

| Owned outcome | Engineering responsibility | Evidence needed to judge the outcome |
|---|---|---|
| Bounded change intent | Translate an approved need or defect into observable behaviour, constraints, exclusions and acceptance; expose material ambiguity. | Requirement or defect reference, affected behaviour, acceptance examples and unresolved owner decisions. |
| System understanding and impact assessment | Inspect relevant code, tests, interfaces, configuration, architecture and runtime assumptions before proposing a change. | Specific repository evidence, affected consumers and dependencies, preserved contracts and uncertainties. |
| Architecture or design decision | Compare plausible technical options at the scale of the change, including keeping the existing design. | Constraints, trade-offs, rejected alternatives, compatibility and migration implications; a diagram or experiment only when useful. |
| New or changed software behaviour | Implement coherent behaviour in the existing architecture, or establish the necessary structure for a greenfield system. | Reviewable implementation, acceptance evidence, integration impact and updated technical documentation where affected. |
| Defect diagnosis and repair | Reproduce or otherwise substantiate a failure, identify its owning cause and repair the sufficient scope. | Failure evidence, causal reasoning, corrective change and regression evidence proportionate to the defect. |
| Maintenance and evolution | Refactor, update dependencies or platforms, evolve contracts/data and remove obsolete code within approved intent. | Preserved behaviour, explicit intended differences, migration or deprecation treatment and affected-consumer evidence. |
| Verification and engineering review | Select checks that address the change's risks, inspect design and test quality, and report limitations honestly. | Actual results with revision, commands and relevant environment; failed, skipped and inconclusive checks remain visible. |
| Quality improvement | Address a concrete maintainability, security, performance, reliability or operability problem. | The problem and baseline, targeted change, dimension-specific evidence and any trade-off with other qualities. |
| Technical release and handoff readiness | Prepare reproducible delivery outputs, compatibility information and technical readiness evidence; execute an authorised release task when included in scope. | Artefact/revision identity, build and verification results, migration and recovery constraints, known risks and the receiving owner. |

A diagnosis, review or design-only request can finish without implementation. Conversely, a request for a working change is not satisfied by an attractive plan. The requested outcome determines the completion boundary.

### 3.2 Classes of software

| Class | Included responsibility | Boundary or qualification |
|---|---|---|
| Services, APIs and distributed applications | Behaviour, interfaces, persistence, concurrency, integration, resilience and software performance. | Business policy, service-level commitments and live operations are supplied by their owners. |
| Web, mobile and desktop applications | Application architecture, state and data behaviour, platform integration, accessibility implementation and delivery mechanics. | UX owns intended interactions and usability judgements; product owners set audience and feature goals. |
| Libraries, SDKs, CLIs and developer tools | Public contracts, compatibility, packaging, consumer behaviour and maintainability. | No requirement for a deployed service or service runbook where those concepts do not apply. |
| Scripts, build systems, CI/CD and configuration as code | Versioned software changes, reproducibility, tests, review and bounded automation. | Platform-wide policy, shared infrastructure operation and permission to affect an environment remain external. |
| Data pipelines, ML applications and game/simulation runtimes | Ordinary software obligations for code, APIs, persistence, failure handling and integration. | Data meaning, model validity, gameplay quality and scientific validity require the relevant specialist. |
| Embedded, real-time and other specialist systems | Applicable engineering methods within an explicit component and evidence boundary. | Hardware behaviour, timing guarantees, specialist certification and safety assurance are not established by this general-purpose charter. |

Domain inclusion does not promise immediate language, framework or platform coverage. Later capability research must determine which work can be executed and evaluated credibly. Existing repository tools remain the default execution context; this stage chooses no universal language or toolchain.

### 3.3 Architecture, greenfield and brownfield decisions

Architecture is owned wherever it determines whether a software change fits its system: module responsibilities, dependency direction, interfaces, data ownership, concurrency and deployment-related design. The required scope may be local or span components. Enterprise portfolio strategy, organisational restructuring and product prioritisation remain outside this ownership.

Brownfield work receives priority because it exposes obligations that an empty repository conceals: unknown dependencies, existing behaviour, local conventions, historical decisions, incomplete tests and real migration costs. This is a prioritisation decision, not a numerical coverage allocation. Stage 13 must still select a complementary set of examples rather than repeat one kind of legacy bug fix.

Greenfield work includes technical requirements, initial architecture, contracts, construction, testing and release preparation. It must consume product and domain intent, make assumptions explicit and establish only the structure justified by current uncertainty. A blank repository does not authorise the agent to invent the product or impose its preferred stack.

“Smallest responsible change” means the smallest coherent scope that solves the problem. It does not mean the fewest changed lines. A broader migration or redesign can be justified when a local patch would preserve the failure mechanism; material departures from accepted constraints must be surfaced to the authorised owner.

### 3.4 Maintenance is first-class

| Maintenance need | Initial owned boundary |
|---|---|
| Corrective | Defects, regressions, compatibility failures and vulnerability remediation in owned software. |
| Adaptive | Dependency/runtime upgrades, changed external APIs, platform changes and compatibility work. |
| Improvement-oriented | Maintainability, testability, performance, reliability and operability improvements with a concrete engineering purpose. |
| Preventive | Reducing evidenced future failure risk, removing demonstrated technical debt and strengthening weak verification; speculative generalisation is not enough. |
| Migration, deprecation and retirement | Safe code and contract evolution, schema transition design and removal of obsolete components; product retirement, retention policy and destructive execution need the relevant owner authority. |

Maintenance includes tests, build logic, configuration and technical documentation when these contribute to the change. Improving a test suite or diagnosing a flaky test can be a complete engineering task. Incidents can supply evidence for a code repair without transferring incident command to this repository.

## 4. Adjacent-domain map and handoffs

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

## 5. Intended users and consuming-project assumptions

| User | Need served | Responsibility retained by that user |
|---|---|---|
| AI coding agent acting for a developer or maintainer | Reusable judgement for inspecting, implementing, verifying and repairing a bounded engineering task. | Obey actual repository/task instructions, use available tools and report uncertainty and execution limits. |
| Developer or maintainer, including a solo project owner | A coherent change that fits the repository and has understandable evidence. | Supply intent and authority, resolve consequential ambiguity, and own acceptance under the project's policy. |
| Reviewer or technical lead | Traceable scope and trade-offs, preserved contracts, relevant test evidence and clear residual risks. | Independent review and approval decisions appropriate to the project. |
| Specialist collaborator or optional orchestrator | A bounded engineering capability with clear inputs, outputs and limits. | Own the adjacent discipline or orchestration responsibility and evaluate the assembled outcome. |

The skills must not assume a large organisation, a particular coding agent, a cloud provider, continuous deployment, comprehensive tests or Pactwright installation. A solo maintainer may hold several ownership roles without needing artificial handoff ceremony.

The consuming project provides the actual source tree, task intent, conventions, dependency/runtime constraints, build/test entry points and permitted environment access. Missing information is an investigation task where discoverable. An absent consequential requirement is an owner decision; it must not be filled by an undocumented default.

## 6. Initial quality dimensions

These dimensions define success for later research and evaluation design. The evidence examples are proposed measures, not results, fixed thresholds or a completed benchmark. Report each applicable dimension separately; a good result in one cannot erase a material defect in another.

| Dimension | Question for the change | Candidate evidence |
|---|---|---|
| Functional correctness | Does the intended behaviour hold, including relevant edge and failure cases? | Acceptance examples, focused behavioural tests and inspection of actual outputs. |
| Contract and data compatibility | Are existing consumers, data invariants and supported interfaces preserved or deliberately migrated? | Contract tests, consumer checks, migration validation and explicit intended incompatibilities. |
| Architectural fit | Does the change respect responsibilities and constraints, or justify reopening them? | Relevant architecture/code references, dependency impact and reviewed trade-offs. |
| Maintainability and simplicity | Can the code be understood, changed and tested without avoidable complexity? | Review of cohesion, duplication, coupling, naming and necessity; metrics alone are insufficient. |
| Security | Are relevant controls and threat-sensitive behaviours implemented and checked? | Control tests, review/scanner findings and specialist review where needed; residual risks stay visible. |
| Performance and resource use | Does the software meet the relevant latency, throughput, memory or cost constraint? | Workload and environment-qualified baseline/comparison, profiling and resource measurements. |
| Reliability and resilience | Does the software behave correctly under the relevant faults, retries and concurrency conditions? | Failure scenarios, concurrency reasoning and targeted resilience tests. |
| Operability and deployability | Can the change be built, delivered, observed and diagnosed in its intended environment? | Build/package evidence, useful telemetry, smoke checks and recovery constraints where applicable. |
| Test and verification quality | Do the checks detect the defect or risk they claim to cover? | A failing pre-fix case, a targeted negative case or appropriate fault-seeding evidence; distinguish test existence from effectiveness. |
| Scope and preservation | Is the change sufficient and are unrelated behaviour and valid work retained? | Impact review, focused diff and regressions relevant to preserved obligations. |
| Evidence and reproducibility | Can another engineer understand what was checked and reproduce the relevant result? | Revision, commands, environment assumptions, results and explicit limitations; no fabricated passes. |
| Engineering efficiency | Was effort spent on resolving the material uncertainty at a proportionate cost? | Investigation/check rationale, feedback time and avoided redundant work, without weakening necessary verification. |

Accessibility, internationalisation and domain-specific constraints remain explicit requirements when applicable. Technical checks support their implementation; specialised usability or domain judgement may still be needed.

The initial cost/fidelity principle is to choose the cheapest adequate evidence: inspection may settle a convention; a small reproduction may settle a defect; an interface sketch may expose a design conflict; a realistic workload may be necessary for a performance claim. There is no universal command sequence here. Stage 7 determines the risk and verification strategy, including when inexpensive checks are inadequate.

The software-specific interpretation is a design inference from the family principles. [Google review guidance](https://google.github.io/eng-practices/review/reviewer/looking-for.html) supports evaluating system context, design and useful tests; [DORA](https://dora.dev/capabilities/continuous-delivery/) supports attention to deployability; [NIST](https://csrc.nist.gov/pubs/sp/800/218/final) supports integrating software security into development. These anchors do not establish that the proposed capabilities improve engineering outcomes.

## 7. Human decisions and commitment candidates

Approval is tied to authority and consequence, not to every edit or command. Apply the consuming project's actual policy and the user's explicit authorisations. Carry existing permission forward. Read-only investigation and reversible work within agreed scope should proceed without repeated confirmation. A requested, authorised release or commit does not need a newly invented approval gate.

Where an action would cross an unapproved boundary, first prepare the useful reviewable work: options, affected contracts, proposed change, available verification and consequences. Ask the owner for the specific missing decision before the consequential action. If a choice is genuinely necessary before useful implementation can proceed, ask at that point rather than conceal the assumption.

| Candidate commitment | When an owner decision is material | Evidence to prepare and owning role |
|---|---|---|
| Requirements and acceptance | Ambiguity changes externally visible behaviour, policy or accepted scope. | Concrete behaviour/options and trade-offs; product or task owner. |
| Architecture and dependencies | A proposal reopens an accepted design, adds a material dependency or imposes a significant operating/migration burden beyond the brief. | Current constraints, alternatives, compatibility and ongoing cost; technical owner. |
| Public contract change | Consumers lose supported behaviour or must coordinate a migration not already authorised. | Affected consumers, compatibility options, version/deprecation plan; API/library and consuming owners. |
| Data mutation or removal | A migration risks irreversible loss, broad rewriting, changed retention or access beyond existing permission. | Rehearsal evidence, impact, integrity checks and actual recovery limits; data/environment owner. A rollback script is not proof that lost data is recoverable. |
| Security-sensitive decision | Privileges, trust boundaries, controls or acceptance of a known risk would materially change. | Threat/control implications, alternatives and verification; designated security/technical authority. |
| External commitment | Publishing, deploying or changing shared infrastructure is outside existing authorisation or materially exceeds its scope. | Exact target/revision, readiness results, migration/recovery implications; release/platform owner. |
| Quality exception | A material failing or unavailable gate is proposed for waiver, or risk is to be accepted despite contrary evidence. | Failure, impact, alternatives and explicitly bounded residual risk; project's acceptance authority. The agent cannot relabel an unrun check as passed. |
| Retirement or broad replacement | Removing supported behaviour, abandoning a component or undertaking a rewrite exceeds the agreed task. | Dependants, alternatives, migration and support implications; product and technical owners. |

A detected repository security problem or failing baseline does not authorise arbitrary unrelated repairs. Record it, determine whether it blocks the task, and either address the relevant cause within scope or obtain the decision needed to expand scope. Preservation applies to valid obligations; it does not require protecting the very defect an authorised change is meant to remove.

These are candidates for the Stage 7 commitment strategy. They do not define a central approval engine or replace consuming-project governance.

## 8. Reusable expertise versus project-specific context

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

## 9. Non-goals and rejected boundary models

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

## 10. Boundary probes

These are desk-based responsibility checks applied to the charter, not executed examples, test results or benchmark evidence. They test whether the boundary produces a clear owner and completion condition for contrasting requests.

| Probe | Decision under this charter | Boundary outcome |
|---|---|---|
| Repair a duplicate-processing defect in an existing event consumer. | Own inspection, causal diagnosis, concurrency/contract analysis, repair and regression evidence. Receive the required delivery semantics from the system owner. | Clear engineering ownership; no invented business semantics or unrelated runtime rewrite. |
| Add a feature to a new mobile application. | Own engineering requirements, architecture, implementation and technical verification. Receive product intent and UX behaviour. | Greenfield is supported without the agent becoming the product or design authority. |
| Upgrade a shared library with a breaking API. | Own impact assessment, compatible alternatives, code changes and consumer evidence. The relevant owners resolve unapproved breakage and migration commitments. | Maintenance and public-contract authority are both represented. |
| Fix a defect in a deployment workflow. | Own versioned automation and its verification against platform contracts. Execute changes to a live target only within actual authorisation. | CI/CD code is included; platform policy and live operation are not silently absorbed. |
| Drop a populated column after a data migration. | Own analysis, implementation, rehearsal and integrity evidence. Resolve retention and irreversible-loss authority before live deletion. | Data engineering handoff and commitment boundary remain visible. |
| Improve a game's frame time but change collision behaviour. | Own profiling and runtime engineering; preserve agreed gameplay invariants. Return any proposed gameplay change to game-development authority. | Faster software cannot hide an unintended change in the game's rules. |
| Integrate a model whose output fails its quality threshold. | Verify application/serving behaviour and diagnose integration defects; hand model-quality failure to ML ownership with reproducible evidence. | Software correctness does not falsely establish model validity. |
| Investigate a production incident traced to bad configuration. | Diagnose within available access, identify the owning configuration and prepare/perform an authorised bounded repair. Incident command and live recovery coordination remain with operators. | Engineering contributes to recovery without assuming unrestricted production authority. |
| Review an API change whose existing tests all pass but omit an affected consumer. | Identify the missing contract evidence and report the review as incomplete for that risk. | Passing tests do not substitute for adequate verification. |
| Ask an agent to determine whether any change is needed. | Permit an evidence-backed no-change conclusion when the suspected defect is disproved or the existing contract is correct. | Scope discipline is an outcome; code output is not mandatory for every task. |

All ten probes have a stated engineering responsibility, adjacent or consuming authority where needed, and a meaningful evidence boundary. Execution feasibility remains untested.

## 11. Open questions and handoff to later stages

The initial boundary is usable now. The following questions refine depth and implementation; none requires an arbitrary selection to finish Stage 1.

| Open question | Working boundary for now | Resolution stage and evidence needed |
|---|---|---|
| How broad and deep must architectural reasoning be? | Include architecture affecting the software outcome; exclude enterprise/product authority. | Stages 2–4 research decision practices; Stages 5–6 model change/context and artefacts; Stage 11 decides packaging. |
| How should infrastructure-as-code work be bounded? | Include versioned software change and platform-contract conformance; platform policy/operation stays external. | Stages 2–4 examine scope and practice; Stages 5–7 model context, risk and commitment. |
| What specialist depth is appropriate for embedded, real-time or strongly regulated work? | Permit bounded general engineering support; make no specialist assurance claim. | Stages 2–4 identify evidence gaps; Stages 8–10 determine available capabilities and remaining gaps. |
| When do security, performance and concurrency require specialist review? | They remain engineering quality obligations; specialist uncertainty is explicit. | Stages 2–4 research methods/limits; Stage 7 defines escalation criteria; Stage 14 defines evaluation. |
| How much project context should be reconstructed and persisted? | Inspect enough to justify the change; durable project facts remain in the consuming project. | Stages 5–6 define system context and artefacts; Stages 8–9 assess tools without assuming a universal graph. |
| How should testing, review and debugging be split into skills or commands? | All are owned responsibilities; no installation split is chosen. | Stage 11 uses the domain model and gap analysis to justify separability and reuse. |
| How should weak/flaky tests or missing environments affect completion? | Preserve known limitations and distinguish unverified from failed or passed; do not fabricate evidence. | Stage 7 defines risk-based response; Stage 14 defines behavioural and semantic evaluation. |
| Which ecosystems and specialisations deserve early implementation? | Domain scope stays broad; no language/framework is promised. | Stages 8–12 research and select capabilities/packs; Stage 13 selects complementary examples. |
| What is the useful greenfield/brownfield example balance? | Brownfield is primary; greenfield and multiple maintenance forms remain required coverage candidates. | Stage 13 selects the 5×3 examples through capability coverage, without an invented percentage quota. |
| What exactly constitutes technical release completion in different software classes? | Include readiness and authorised task execution; operational ownership remains external. | Stages 5–7 define class-specific artefacts, evidence and commitment; implementation later demonstrates them. |

Stage 2 should consume this charter, the owned-outcome table, adjacent boundaries, quality dimensions and open questions to derive its knowledge-coverage map. It must then compare a broader candidate pool and select exactly five complementary books under the source-access and supplied-book permission rules. No books are selected, removed, replaced or claimed as read by this stage.

The three directly read professional anchors remain available for bounded reconnaissance. SWEBOK access needs attention before reliance. Stage 3 still requires substantive direct examination of the selected corpus; Stage 4 still requires broader challenge. No claim here exempts either gate.

## 12. Source and applicability register

All access and applicability checks below were made on 12 September 2026. Repository sources are pinned so later stages can distinguish this decision basis from subsequent changes. Read scopes are explicit; listing a source does not claim a full review of every referenced document.

### 12.1 Governing repository sources

| Source | Examined scope and consequence |
|---|---|
| [Domain bootstrap v1.1](https://github.com/sb-dev/software-engineering-skills/blob/684986785ceafbc031419d6fc7287dbfe0578dba/docs/research-logs/2026-09-07-software-engineering-skills-new-project-bootstrap-process.md) | Purpose, governing sources, thesis, principles, stage execution, Stage 0/1, Stage 2 handoff and stage map. Defines the ten Stage 1 questions, twelve adjacent domains, eight outputs and one-page exit. |
| [Family system v1.0](https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/specs/01-production-skills-family-system.md) | Read in full. Governs domain-first design, cheap adequate evidence, preservation, targeted repair, independent use, project knowledge and evidence before shared abstractions. |
| [Project contract v1.3](https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/specs/02-production-skills-project-contract.md) | Read in full. Requires durable substantive stage records, minimal bootstrap workspace and distinction between designed responsibility and implemented maturity. Later packaging/example/install requirements remain deferred. |
| [Evaluation and Extension Packs v1.2](https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/specs/03-production-skills-evaluation-and-extension-packs.md) | Read in full. Keeps quality dimensions visible, requires domain evaluation and permits specialisation only with observable value. No pack catalogue or quality score is inferred here. |
| [Cross-domain integration v1.1](https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/specs/04-cross-domain-orchestration-and-integration.md) | Read in full. Establishes handoff ownership, consuming-project knowledge, optional Pactwright and separation of domain versus assembled-product evaluation. |
| [Bootstrap generation guide v1.1](https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/bootstrap/README.md) and [new-project process v1.4](https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/bootstrap/new-project-process.md) | Read governing/workspace/research rules and discipline/Stage 1 sections. Domain definition precedes architecture and substantive evidence must be committed. Reference-project comparisons used to generate a bootstrap are not misrepresented as fresh implementation research in this stage. |
| [Domain research process v1.0](https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/bootstrap/domain-research-process.md) and [accepted five-book decision v1.0](https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/research-logs/2026-09-10-five-book-bootstrap-research-foundation.md) | Read purpose/Seed entry and the accepted decision in full. Use the charter to drive coverage; retain separate selection/extraction/challenge gates and explicit supplied-book substitution authority. Five is a process requirement, not a proven optimal corpus size. |
| [Project-family brief](https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/research-logs/2026-09-07-production-skills-and-extension-packs-project-family-brief.md) | Examined Software Engineering, Game Development, Deep Research, UI/UX, QA, composition, specialisation and Pactwright sections. Supports reusable implementation engineering and handoffs. Its initial technology/pack proposals do not predetermine this project's architecture. |
| [Shared-abstraction process](https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/bootstrap/shared-abstraction-process.md) | Read in full. Cross-domain extraction requires independent implementation evidence; Stage 1 creates no new shared runtime or abstraction. |

The bootstrap's older historical copy in the central repository is not the execution authority. The user-linked domain repository contains the adopted v1.1 process. Where the earlier family brief suggests a common pack-creation capability, the current canonical domain-owned pack contract governs; pack design remains Stage 12 work.

### 12.2 Initial professional-practice anchors

| Source and actual access | Narrow observation | Application and limitation |
|---|---|---|
| [DORA, Continuous delivery](https://dora.dev/capabilities/continuous-delivery/), directly read the capability page, including its definition, implementation practices and pitfalls. | Describes deployability as a sustained technical capability and distinguishes continuous delivery from deploying every change. Identifies testing, security, configuration and observability among relevant practices. | Supports including technical release readiness and delivery-related software. The allocation of live-operation authority in this charter is a project decision. No causal performance estimate or mandated DORA workflow is claimed. |
| [NIST SP 800-218, SSDF v1.1](https://csrc.nist.gov/pubs/sp/800/218/final), directly read the official February 2022 publication record and abstract; the full publication was not extracted. | Describes secure development practices that can be incorporated into an SDLC and attention to vulnerability root causes. | Supports security as an engineering responsibility throughout development. Does not establish control-level compliance, full SSDF coverage or specialist assurance. No claim about this being the latest possible SSDF revision is needed. |
| [Google Engineering Practices, What to look for in a code review](https://google.github.io/eng-practices/review/reviewer/looking-for.html), directly read the review guidance. | Examines design, functionality, complexity, useful tests, documentation and system context; recognises cases needing qualified reviewers. | Supports a boundary wider than code generation and separate evidence for design/test quality. It is contextual practitioner guidance, not a universal operating model or empirical validation of these skills. |
| [IEEE Computer Society, SWEBOK](https://www.computer.org/education/bodies-of-knowledge/software-engineering) and [v4 page](https://www.computer.org/education/bodies-of-knowledge/software-engineering/v4), attempted direct access; unavailable. | No substantive finding retained from these pages. Search results were not used as a substitute for the guide. | Remains a source-access item for later research. No book/chapter extraction, knowledge-area coverage claim or version-currentness assertion is made. |

Only independently expressed observations are recorded. No source book, substantial copied passage or supplied private material is published.

## 13. Stage 1 completion review

### 13.1 Required questions

| Bootstrap question | Resolution in this record |
|---|---|
| What software outcomes can the project produce? | Sections 1 and 3.1 define intended outcomes and their evidence boundaries, including diagnosis/design-only outcomes. |
| What classes of software are in scope? | Section 3.2 defines general and specialist-component scope without promising implementation coverage. |
| Does the domain include architecture as well as implementation? | Section 3.3 includes both and bounds enterprise/product authority. |
| Where does engineering stop and product/UX/operations begin? | Section 4 assigns responsibility and two-way handoffs across all twelve requested adjacencies. |
| How are greenfield and brownfield weighted? | Section 3.3 prioritises brownfield while retaining greenfield; final example balance is deferred with a named stage. |
| What forms of maintenance are first-class? | Section 3.4 includes corrective, adaptive, improvement-oriented, preventive and migration/retirement work. |
| What release responsibility is owned? | Sections 1, 3.1 and 4 include readiness and authorised technical execution; launch and operating authority stay external. |
| Which human approval points matter? | Section 7 defines consequence-based candidates, existing-authorisation treatment, owners and review evidence. |
| What quality dimensions define success? | Section 6 supplies distinct dimensions and candidate evidence without a universal score or measured claims. |
| What is reusable versus repository-specific? | Section 8 allocates practice, local context, specialist knowledge and durable project records. |

### 13.2 Required outputs and exit criteria

| Required output or gate | Evidence | Result |
|---|---|---|
| Project mission and short charter | Section 1 gives a standalone one-page account of responsibility, coherence, users, boundaries and success. | Satisfied. |
| Owned outcomes | Section 3 defines outcomes, evidence needs and scope. | Satisfied. |
| Non-goals | Sections 4 and 9 define exclusions and rejected boundary models. | Satisfied. |
| Adjacent-domain map | Section 4 explicitly covers all twelve named disciplines and handoffs. | Satisfied. |
| Intended-user definition | Section 5 identifies users, retained authority and consumer assumptions. | Satisfied. |
| Quality dimensions | Section 6 distinguishes engineering qualities and credible evidence. | Satisfied. |
| Approval/commitment candidates | Section 7 identifies consequential decisions without imposing permission on every reversible task. | Satisfied. |
| Open boundary questions | Section 11 records provisional answers, resolution stages and evidence needs. | Satisfied. |
| Defensible initial boundary | The charter is supported by governing-source review, explicit trade-offs and ten desk-based boundary probes. | Satisfied for Stage 1, subject to later research. |
| Detailed durable record | This file preserves substantive decisions, source scope, limits and the downstream handoff; the research index links it. | Satisfied. |

**Blockers:** none for completion of this initial boundary. The SWEBOK access limitation is recorded; the missing evidence is not represented as examined material.

**Decisions requiring user input now:** none. This stage does not make a corpus substitution, choose a consequential product policy or act on a consuming production system.

**Review scope:** Stage 1 specification questions, expected outputs, named adjacencies, source applicability, stage boundaries and internal Markdown links. Boundary probes are analytical review only. Runtime, installation, benchmark and production-quality validation have not been run because no implementation exists at this stage.

**Validation result:** all ten required questions, eight expected outputs and twelve adjacent domains are accounted for above. The one-page charter contains 447 whitespace-separated words. Local document checks resolved all relative links and the bootstrap section anchor, found no unclosed code fences or merge-conflict markers, and confirmed that only the Stage 1 record and research-log index are intended commit changes.

**Stage handoff:** Stage 1 is complete at the initial-boundary level. Stage 2 is the next dependent task and has not been started on this branch. The repository remains a bootstrap workspace; this commit makes no registry promotion or production-readiness claim.

---

**Version 1.0 — 12 September 2026.** Initial Stage 1 domain charter, boundary analysis, source/access record and completion review for `feat/bootstrap-2`.
