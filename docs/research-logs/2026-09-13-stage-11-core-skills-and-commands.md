# Stage 11: Core Skills and Command Design

**Stage:** 11 — Design Core Skills and Commands  
**Date:** 13 September 2026  
**Branch:** `feat/bootstrap-2`  
**Input commit:** `5e3348cd6d34520c73f0a90ceb6bcebfee7f168f`  
**Status:** Complete for skill/command design; production skill files, installation and behavioural evaluation are not yet implemented.

## 1. Inputs and acceptance

The complete [Stage 11 requirement](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#18-stage-11--design-core-skills-and-commands) governs this stage. Inputs are the accepted [charter](2026-09-12-stage-01-project-goal-and-domain-boundary.md), [professional capability model](2026-09-13-stage-04-professional-practice-challenge.md), [context/contracts](2026-09-13-stage-05-change-contract-and-context-model.md), [workflow/artifacts](2026-09-13-stage-06-workflow-and-artefacts.md), [verification/risk](2026-09-13-stage-07-verification-risk-and-commitment.md), [existing capabilities](2026-09-13-stage-08-capability-landscape.md), [execution layer](2026-09-13-stage-09-execution-layer.md) and [gap shortlists](2026-09-13-stage-10-gap-analysis.md). Stage 10's six N groups were not a predetermined skill count.

Acceptance: compare the three named skill hypotheses and possible architecture/debugging/testing/review splits; assess all **18 candidate commands**; retain only modes with concrete evaluation/reuse/composition/diagnosis/repair/benchmark value; give every retained command all **9 contract fields**; test workflow coverage, independent use and scope boundaries at the design level. Persist the design and conformance, commit only this stage and verify remotely. This stage does not satisfy later implementation, benchmark or external-installation gates.

The global requirement for a domain-native pack-authoring capability is retained. The governing Stage 12 section explicitly permits an authoring skill **or equivalent workflow**; this design uses the equivalent workflow, whose full pack research/authoring contract is the next stage's work. No required pack research or authoring verification is dropped.

Skill Creator guidance was applied to self-containment, narrow triggers, progressive disclosure and meaningful behaviour verification. The user requested this GitHub repository, not a personal skill installation; no personal skill store is modified and no install success is claimed. The repository's stage order also means no premature `skills/` scaffold is created here.

## 2. Skill-set decision and rejected splits

**The minimum complete-workflow installation is one skill: `software-engineering`.** It owns the whole WF1–WF6 loop, including verification, self-review, diagnosis, bounded repair and handoff. It works without the evaluator, packs, subagents or an orchestration runtime.

The designed catalogue also contains **`software-evaluate` as an optional, independently installable evaluator**. It serves an assessment-only request against raw repository/artifact evidence and exposes focused semantic evaluation modes. A user can install only it to review work produced by a human or any coding agent. It does not depend on `software-engineering` having produced an artifact first. Thus the catalogue has two justified entrypoints, while the core's minimum runtime dependency remains one skill.

| Hypothesis / alternative | Analysis against gaps and independent use | Decision |
|---|---|---|
| One `software-engineering` skill for complete work | N01–N06 are one coherent outcome loop; dividing routine inspection/design/build/feedback creates redundant context handoffs | Adopt as minimum complete-workflow installation |
| Separate `software-evaluate` | G05/G08/G09/G10/G11/G12 require assessment of supplied changes and evidence; assessment-only intent has a distinct mutation boundary and independently useful testable output | Adopt as optional standalone evaluator; not a mandatory step/dependency of engineering |
| Separate `software-extension-pack-creator` | Required pack authoring needs P-stage research, a core baseline and differential evidence; Stage 10 I01 does not by itself justify another generative entrypoint or generic runtime | Use a domain-native equivalent authoring workflow/contract in Stage 12; do not ship an unproven catch-all creator skill |
| Separate architecture skill | Design-only work is independently useful, but raw-context `design-change` already supports it without construction | Keep a command/mode in engineering; no distinct installation dependency justified |
| Separate debugging skill | Diagnosis-only has useful scope, but the same evidence/repair semantics belong beside implementation and can be invoked independently as a command | Keep `diagnose-failure`; no duplicate diagnosis runtime or mandatory external skill |
| Separate testing skill | Authoring tests and evaluating test quality have different mutation intentions | Tests-only implementation belongs to engineering; test-quality assessment belongs to evaluator; no third generic testing skill |
| Separate code-review skill in addition to evaluator | It would duplicate evaluation inputs, finding/evidence semantics and read-only boundary | Keep `review-change` in evaluator; engineering retains adequate self-review when evaluator is absent |
| One skill per N/C responsibility or language/job title | Would multiply overlapping triggers and shared context before independent value is demonstrated | Reject; specialise commands/references/packs where evidence warrants |

The evaluator is justified by a distinct consumer request and artifact/authority boundary, not by claiming that two prompts make review independent. A review performed in the same agent/context is self-review even if a different skill is loaded. Actual later evaluation must disclose provenance and control answer leakage.

### 2.1 Entrypoint contracts and trigger design

These are proposed discovery descriptions and behavioural boundaries for later implementation, not installed metadata.

| Skill | Proposed description | Standalone contract | Mutation boundary |
|---|---|---|---|
| `software-engineering` | Understand, design, implement, verify and repair software changes in a repository. Use for bounded development, diagnosis, refactoring, migration planning or technical handoff; preserve existing contracts and use project-native tools. | Accept a task plus accessible repository/artifacts; reconstruct relevant context; deliver the requested outcome with evidence. All WF phases are responsibilities, not mandatory separate documents. | Mutate only what the authorised task and selected mode require. Inspection/design/diagnosis-only requests remain bounded; the full driver can carry authorised implementation/release work through completion. |
| `software-evaluate` | Assess an existing or proposed software change, its tests, compatibility, security or performance using repository evidence. Use for review or evaluation; return findings and bounded repair advice without modifying production code. | Accept a review question and raw candidate/context/evidence, even if another skill or human produced it. Supply its own relevant inspection and result interpretation; no hidden core installation required. | Reports, read-only inspection and authorised isolated checks only. If the request also includes fixes, route into engineering work using existing authority rather than silently changing the evaluator's role. |

Natural language is the primary interface. When both skills are installed, implementation/fix requests select engineering; assessment-only requests select evaluator. An explicit user choice wins when the chosen skill can perform the task within its contract. A compound “review and fix” task can assess then repair, but does not require a second permission for the already-requested repair. Ordinary implementation can self-review without loading every specialised evaluation mode.

Skill-local command names are optional prompt-level selectors. They are not promised native slash commands, executable CLI subcommands, a parser or a provider API. For example, a user can ask the engineering skill to inspect the affected payment path; they need not type a lifecycle expression or first create a state object. Host-specific invocation syntax belongs in the later installation documentation and must be tested there.

## 3. Disposition of all eighteen command candidates

Twelve commands are retained; six candidate names are folded into a more coherent mode. Folding preserves the responsibility and targeted use case, not a requirement to execute the containing command's unrelated work. The benefit column identifies why each retained boundary is useful under the literal Stage 11 criteria.

| Candidate | Disposition / owner | Retained contract or mode | Concrete benefit or folding reason |
|---|---|---|---|
| inspect-system | Retain — engineering | CMD01 | Isolated evaluation of relevant context/impact and reuse by design, implementation and review without prior workflow artifacts |
| classify-change | Fold — engineering | CMD01 requested classification scope | Classification depends on intent/contracts/context; a separate command would repeat inspection and invite unsupported filename-only labels |
| assess-impact | Fold — engineering | CMD01 requested impact scope | Same source/consumer/uncertainty evidence as system inspection; impact can be the sole requested output without a new command |
| identify-contracts | Fold — engineering | CMD01 requested contract scope | Contract discovery is part of the context/impact account; preserve all CO responsibilities without a competing artifact protocol |
| design-change | Retain — engineering | CMD02 | Independently useful design-only work; benchmark option/scope/trade-off reasoning without requiring implementation |
| implement-change | Retain — engineering | CMD03 | Isolated construction/preservation evaluation and targeted repair of a scoped requested delta |
| add-or-update-tests | Fold — engineering | CMD03 tests-only mode | Same edit/feedback/evidence contract; can author meaningful tests without changing production code and without requiring a feature change |
| select-verification | Retain — engineering | CMD04 | Separates evidence-selection quality from tool availability; useful for isolated risk/oracle evaluation and reuse before execution |
| run-verification | Retain — engineering | CMD05 | Precise boundary for actual native-command evidence, failure interpretation and candidate freshness; does not implement a universal runner |
| diagnose-failure | Retain — engineering | CMD06 | Diagnosis-only reuse and precise hypothesis/containment/repair-scope evaluation; accepted failure can return here from any responsibility |
| review-change | Retain — evaluator | CMD08 | Standalone review of raw candidate evidence, finding validity and bounded repair; useful without an implementation skill |
| refactor | Fold — engineering | CMD03 preservation-focused mode | Refactor is a change class with stricter preservation, not a separate editing lifecycle. Retain no-new-behaviour oracle and local structural rationale |
| plan-migration | Fold — engineering | CMD02 transition-planning mode | Significant design mode with readers/writers, intermediate states, recovery and authority; a separate command would duplicate planning state |
| evaluate-test-quality | Retain — evaluator | CMD09 | Isolated oracle/fidelity/sensitivity diagnosis that cannot be replaced by running tests or counting coverage |
| evaluate-compatibility | Retain — evaluator | CMD10 | Focused semantic/version/state-transition evaluation and targeted repair advice; distinguishes intentional breaks from defects |
| evaluate-security-risk | Retain — evaluator | CMD11 | Scoped threat/control/evidence assessment and diagnosis where genuinely relevant; scanner findings alone are insufficient |
| evaluate-performance-risk | Retain — evaluator | CMD12 | Workload/comparability/concurrency/fault reasoning with separate correctness constraints; enables precise benchmark evaluation |
| prepare-handoff | Retain — engineering | CMD07 | Isolated evaluation of final evidence identity, readiness/action status and actionable transition/handoff; composes requested authorised release mechanics |

The [command contracts](2026-09-13-stage-11-command-contracts.md) define **inputs, preconditions, repository evidence required, outputs, allowed mutations, forbidden mutations, failure states, verification responsibilities, and interaction with approved decisions** for every retained command: **12 × 9 = 108 entries**. Seven commands belong to engineering and five to evaluator. All twelve support direct invocation from the user task/repository; no serialised output from another command is mandatory.

## 4. Composition without a lifecycle DSL

WF1–WF6 remain the domain responsibilities from Stage 6. Commands isolate decisions that benefit from targeted invocation or evaluation. They do not form a compulsory sequence, task-state machine, dependency graph or transaction protocol. A completed diagnosis, review, design or justified no-change conclusion is a valid requested outcome.

| Workflow responsibility | Minimum engineering installation | Optional evaluator composition | Information that survives |
|---|---|---|---|
| WF1 intent | Entrypoint identifies outcome, scope and actual authority; CMD01 clarifies technical context when needed | Evaluator independently reads the accepted criteria for its assessment | Accepted source, intentional delta, preservation and unresolved owner decisions |
| WF2 context/contracts | CMD01, including classify/impact/contracts modes | Every evaluator command can inspect the bounded context it needs | Actual paths/revision/configuration/consumers and uncertainty |
| WF3 approach/evidence | CMD02 plus CMD04 where independent selection helps | CMD09–CMD12 can assess proposed test/compatibility/security/performance treatment | Justified scope/alternatives/oracle and transition/recovery assumptions |
| WF4 change/feedback | CMD03; useful checks through CMD05 | Evaluator returns findings, not silent edits | Coherent diff, meaningful tests and actual incremental evidence |
| WF5 verify/review | CMD05 and the engineering entrypoint's local semantic self-review; CMD06 for failures | CMD08 broad review or a relevant focused evaluation mode | Candidate-specific evidence, substantive concern/disposition and review provenance |
| WF6 completion/handoff | CMD07; native authorised actions when requested | Assessment can inform readiness, but does not grant action authority | Actual prepared/executed/unknown state, recovery/receiving needs and canonical rationale |

Return to the owning responsibility when evidence contradicts an assumption. A bad expected value may require oracle/intent correction; a missing runtime dependency requires context; a test failure can be product or environment; a stale result requires affected re-verification. The core does not blindly restart every command or rewrite accepted design to suit a failing implementation.

Actual evidence and action authority remain independent. Commands do not issue approval tokens. Standing authorisation persists; missing required authority is asked for only when it is material and after useful preparation. No command's name grants permission to install tools, send messages, publish or mutate live data.

## 5. Self-containment and resource design

Each advertised skill must be selectively installable with its own required references/scripts. It must not load `../../docs`, another skill's folder, research logs, source-repository tests or a global shared Python module at runtime. The current logs are design inputs, not install-time dependencies. Runtime guidance will be distilled from the source-qualified model and checked against the later canonical specifications.

The planned resource boundary is small:

| Resource responsibility | Engineering skill | Evaluator skill | Reason for the boundary |
|---|---|---|---|
| Entrypoint | Outcome/scope, WF decision loop, applicable commands and necessary reference routing | Assessment scope/mutation boundary, finding/evidence meaning and applicable evaluation routing | Keep descriptions and loaded instructions focused; no entire research archive in context |
| Context and change guidance | Local reference for relevant inspection, contracts, native commands and preservation/design/diagnosis modes | Local guidance sufficient to reconstruct review context from raw artifacts | Either skill can run alone; evaluator never requires a generated engineering report |
| Evidence and quality guidance | Necessary self-review, risk-sensitive checks and final evidence/authority rules | Detailed finding/oracle/compatibility/security/performance assessment as relevant local references | Shared definitions have one canonical specification; role-local instructions contain the necessary applicable rules and are checked for semantic drift |
| Specialisation | Load selected pack material only when its actual applicability/precedence is established | Read the selected pack's intentional traits/quality changes when assessing specialised work | Packs refine decisions; core works without them and does not load all ecosystems |
| Scripts/assets | Add only for an evidenced repeated deterministic composition problem | Add only for a concrete check/report/fixture need | Stage 9 helper policy remains; no empty directories or universal dispatcher justified |

Common result/authority definitions must agree across the two skills, but no runtime shared registry or module is required. When a rule is implemented in role-local guidance, keep it concise and trace it to the canonical specification during repository validation. Avoid copying whole reference chapters simply to make the folders look symmetric.

The engineering skill's self-review is sufficient to perform the minimum workflow; it must not silently omit review because the evaluator is missing. The standalone evaluator must not attempt installation of engineering simply to inspect a diff. Optional host adapters can change discovery/invocation syntax without altering command semantics or requiring a particular provider, browser or subagent.

## 6. Design checks: targeted use, routing and boundaries

These **fourteen synthetic desk checks** exercise the designed contracts. They are not forward-test runs of installed skills, actual model routing results or completed Stage 14/17/20 evidence. Their purpose is to detect gaps/overlap before implementation.

| Probe / request | Intended route | Required outcome / boundary checked |
|---|---|---|
| SD01 — Explain the affected API path in this repository | Engineering CMD01 | Evidence-based context/contracts and unknowns; no source edit or unrelated whole-system graph |
| SD02 — Compare an additive schema path with a rewrite; give a plan only | Engineering CMD02 migration mode | Alternatives, old/new states and recovery; no migration execution |
| SD03 — Add one bounded behaviour and retain current clients | Engineering CMD03 | Coherent change, preservation and relevant actual evidence; no compulsory extra planning ceremony |
| SD04 — Which checks distinguish this one-line auth edit from a harmless rename? | Engineering CMD04 | Risk/oracle distinction by consequence, not line count; selection is not an executed pass |
| SD05 — Run this repository's required affected-module checks | Engineering CMD05 | Native wrapper/config/candidate evidence; missing executable or skipped case not converted to success |
| SD06 — Diagnose the timeout; do not fix production code | Engineering CMD06 | Discriminating observations and causal confidence; no permanent repair or secret dump |
| SD07 — Prepare the verified change and perform the already-authorised commit | Engineering CMD07 | Exact candidate/files/remote outcome, not a renewed permission question or a deployment claim |
| SD08 — Review this human-written patch for material engineering defects | Evaluator CMD08 alone | Source-grounded findings, scope/confidence and bounded repair; no engineering installation prerequisite |
| SD09 — Do these mocked tests actually protect the invariant? | Evaluator CMD09 alone | Oracle/fidelity/sensitivity assessment; coverage or green tests not accepted as sufficient by themselves |
| SD10 — Will old workers and stored rows survive this rollout? | Evaluator CMD10 alone | Supported combinations, semantic/data/transition limits; no destructive live test |
| SD11 — Assess this tenant-boundary change | Evaluator CMD11 | Relevant control/threat/legitimate/forbidden paths; no broad unrelated audit or residual-risk self-approval |
| SD12 — Does this retry optimisation improve the defined workload safely? | Evaluator CMD12 | Comparable measurements plus duplicate-effect/progress/correctness reasoning; no invented gain |
| SD13 — Review and fix the demonstrated defect | Evaluator assessment → engineering repair if both installed; engineering self-review/repair if alone | Carry existing repair authority and useful evidence; don't stop after review or let assessment silently overwrite code |
| SD14 — Create a reusable specialised pack for another project | Domain-native authoring workflow, specified in Stage 12 | Research baseline, evidence, behavioural difference, precedence and evaluation; do not activate ordinary engineering or invent a generic pack runtime |

All twelve retained commands have a targeted use case. The six folded names retain independent requests through their containing mode: classification/impact/contracts use CMD01 with a narrow question; tests-only/refactor use CMD03 with constrained mutations; migration plan uses CMD02 without execution. These modes therefore remain benchmarkable without a separate command registry.

### 6.1 Gap and capability coverage

| Responsibility | Engineering coverage | Optional evaluator coverage | Accepted gap trace |
|---|---|---|---|
| N01 / C01–C03, C14 | CMD01 plus entrypoint intent/authority | Context reconstruction in CMD08–CMD12 | G01/G02/G03/G10/G11/G13 |
| N02 / C04/C05/C07/C18 | CMD02/CMD04; significant trade-offs and scope | CMD08–CMD12 assess relevant assumptions/criteria | G02/G04/G05/G08/G10/G11/G12 |
| N03 / C06/C08/C10/C11/C14 | CMD03/CMD05; tests-only/refactor/migration implementation modes | CMD09/CMD10 plus relevant broad/security review | G03/G04/G07/G09/G10/G11/G13 |
| N04 / C07/C15/C19 | CMD04/CMD05 and entrypoint self-review | CMD08–CMD12; separate findings from repair | G03/G05/G08/G09/G10/G11/G12/G13 |
| N05 / C09/C11/C12/C13 | CMD06 → bounded CMD03/05 when repair requested | CMD08/CMD09/CMD11/CMD12 diagnose evidence/quality concerns | G06/G07/G11/G12 |
| N06 / C01/C10/C12/C16/C17 | CMD02/CMD07 with evidence freshness | Assessment informs readiness but cannot grant authority | G05/G10/G11/G12 |

C18 proportionality and C19 security remain cross-cutting throughout; they are not optional just because specialised evaluator modes exist. I01 external installation remains a mandatory later proof for **both advertised skills** and any advertised representative pack. The authoring workflow's packaging/validation and actual pack creation/revision evidence remain required in their owning stages.

## 7. Conformance and handoff

The complete Stage 11 section was re-read after writing both outputs. Verification inspected actual command definitions, their mutation/authority boundaries and their coverage, rather than treating the presence of a name as implementation.

| Requirement | Evidence | Verification | Result |
|---|---|---|---|
| Derive skill set without predetermined count | Section 2 hypothesis comparison | One minimum complete-workflow skill, optional standalone evaluator, equivalent authoring workflow; no split by job title | PASS |
| Assess named/alternative skill hypotheses | Section 2 | Engineering/evaluator/creator plus architecture/debugging/testing/review alternatives explicitly considered | PASS |
| Assess all command candidates | Section 3 | All 18 named candidates disposed: 12 retained, 6 folded with preserved targeted mode | PASS |
| Retain commands only for allowed benefits | Section 3 and SD01–SD14 | Each retained boundary has isolated evaluation/reuse/composition/diagnosis/repair/benchmark value | PASS |
| Define every command contract | Companion CMD01–CMD12 | 12 unique commands × 9 required fields = 108 nonempty substantive entries; 7 engineering and 5 evaluator | PASS |
| Standalone usefulness and self-containment | Sections 2.1, 4–6 | Either skill accepts raw task/repository evidence; no hidden other-skill/source-checkout dependency; installation evidence still required later | PASS |
| Preserve authority and evidence semantics | Companion mutation/failure/verification/approved-decision fields | Assessment does not silently edit; existing authority persists; planned/actual evidence and failed/unknown states remain distinct | PASS |
| Cover complete workflow and evidenced native gaps | WF1–WF6 table and N/C/G trace | Engineering alone retains all workflow responsibilities, semantic self-review and bounded repair; evaluator is optional | PASS |
| Retain domain-native pack-authoring requirement | Sections 1–2 and SD14 | Explicit equivalent workflow allowed by Stage 12; full contract and creation/revision proof stay required | PASS |
| Exit: minimum skill set without universal lifecycle DSL | Sections 2–6 | Direct modes accept raw evidence; no state machine, command parser, compulsory sequence, provider registry or shared runtime | PASS |
| Durable design and stage isolation | This record, companion and index | No premature production scaffold, installation or behavioural success claim | PASS |

**Handoff:** Stage 12 designs the Extension Pack catalogue and runs each selected pack's required P1–P5 research against this core decision baseline, while recording that the executable core is not yet implemented. No Stage 11 blocker requires user input. Continue after the stage's commit and remote verification.
