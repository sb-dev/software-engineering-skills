# Stage 7: Verification, Risk and Commitment Strategy

**Stage:** 7 — Define Verification, Risk and Commitment Strategy  
**Date:** 13 September 2026  
**Branch:** `feat/bootstrap-2`  
**Input commit:** `a970ffd1c4b422063ae53699746553442c55e3b6`  
**Status:** Complete for policy design; evaluation of an implementation belongs to later stages.

## 1. Inputs, research basis and acceptance

The complete [Stage 7 requirement](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#14-stage-7--define-verification-risk-and-commitment-strategy) governs this stage. Inputs are the accepted [charter](2026-09-12-stage-01-project-goal-and-domain-boundary.md), [Stage 2 coverage](2026-09-13-stage-02-knowledge-coverage-and-five-book-corpus.md), [Stage 3 extraction](2026-09-13-stage-03-five-book-extraction-and-reconciliation.md), [Stage 4 professional model](2026-09-13-stage-04-professional-practice-challenge.md) and [workflow evidence](2026-09-13-stage-04-practitioner-workflows.md), [Stage 5 context/contracts/risk candidates](2026-09-13-stage-05-change-contract-and-context-model.md), and [Stage 6 workflow/artifacts/states](2026-09-13-stage-06-workflow-and-artefacts.md). The accepted preservation, existing-authority and truthful-evidence boundaries remain unchanged.

Acceptance: assess all **eleven candidate ladder activities**, **eleven named risk factors** and **eight commitment categories**; produce all five required outputs; distinguish local-fix and migration treatment; inspect actual policy against original requirements; commit only this stage and verify remotely. There is no required live deployment, performance run or new test framework in Stage 7.

Research synthesis uses Stage 4's directly examined sources and qualifications: S20 distinguishes verification techniques and their limits; S03/S22 distinguish useful review from ritual; S08/S14/S17 scope technical guarantees; S11 supplies a real transition counterexample; S13/S21/S25 inform specialised evidence; S06 links threats, provenance and repair; S02/S18 inform consequential decisions. Their recommendations do not prescribe a universal command list, coverage percentage or organisational approval structure. This stage converts those mechanisms into conditional policy; it does not claim causal effectiveness has been measured.

## 2. Verification ladder

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

## 3. Risk factors and risk-to-verification policy

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

## 4. Commitment and approval policy

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

## 5. Rollback and reversibility considerations

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

## 6. Contrasting policy probes

These are **synthetic analytical probes**, not executed tests. They demonstrate the exit criterion and challenge an overly simplistic line-count policy.

| Probe | Risk, verification and authority decision | Why other treatment would be wrong |
|---|---|---|
| VP01 — One-line local defect fix | A local formatter uses the wrong delimiter in one mode; accepted output is clear, effect is bounded and existing tests cover adjacent modes. Inspect callers, run the focused regression/appropriate syntax check, review the diff and identify the candidate. Existing edit authority is sufficient. | Requiring a full deployment rehearsal and architecture approval adds no evidence for the stated bounded obligation. A new redundant test need not be written if existing evidence is adequate. |
| VP02 — Schema migration | A durable identifier representation changes while old/new workers coexist. RF02/RF03/RF04/RF11 require conversion integrity, historical data, mixed versions, lock/volume and recovery evidence. Prepare the exact sequence before any needed destructive/live decision; execute only under applicable existing authority. | A local unit pass cannot establish intermediate-state safety or recoverability. A generic request to edit code does not itself authorise destructive live mutation. |
| VP03 — One-line access-control change | A one-line predicate affects every tenant. RF01/RF05 dominate textual size; check legitimate and forbidden cross-tenant paths, related bypasses and accepted policy. Routine correction to approved policy can proceed; new access policy needs its owner. | Treating all one-line changes as low risk misses the exposed security boundary. |
| VP04 — Large generated rename | The change is mechanically generated within a bounded private module with a trustworthy refactoring mechanism and strong relevant evidence. Inspect dynamic uses, verify generation/diff and affected checks. | Line count alone does not justify a universal high-risk score or new approval ceremony. Tool correctness and relevant semantics still need evidence. |
| VP05 — Passing fake, failing real constraint | A fake store accepts duplicate identities, so all focused tests pass. CO03/CO11 and RF09 expose an oracle/fidelity gap. Add or use a real-boundary/invariant check rather than repeatedly running the fake suite. | More passes on the wrong boundary do not make the missing guarantee true. |
| VP06 — Ready candidate, release not requested | All task-specific implementation gates pass, and the requested code change is complete. Report readiness facts without claiming publication. | Technical evidence neither creates publication authority nor forces an unnecessary permission question when no release action is requested. |
| VP07 — All remaining stages authorised | Current stage gates pass and its remote commit is verified. Start the next stage under the standing execution contract. | “No blockers” cannot justify stopping and asking for permission to do already-authorised work. |

## 7. Conformance and handoff

The original Stage 7 section was reread and the actual policy inspected before committing. Counts check completeness, not effectiveness. Runtime/evaluation evidence will be required when these policies are implemented and benchmarked.

| Requirement | Evidence | Verification | Result |
|---|---|---|---|
| Consume complete stage and accepted inputs | Section 1 | Prior qualified evidence, CT/CO/SI/RK and WF/artifact semantics reconstructed at input commit. | PASS |
| Research/select risk-sensitive ladder | VL01–VL11, sections 1–2 | All eleven candidate activities assessed with relevance, capability and limits; order is conditional. | PASS |
| Decide necessary evidence, not run everything | Sections 2.1, 3.1–3.2 | Obligation/mechanism selection, reuse, mandatory gates and stop rule explicit. | PASS |
| Research all eight commitment categories | CP01–CP08 | Concrete decision/locking, authority and reviewable evidence defined for every category. | PASS |
| Define all eleven named risk factors | RF01–RF11 | Each has questions/evidence and verification consequence; no universal numeric score. | PASS |
| Produce verification ladder | Section 2 | Eleven activities with applicability and escalation limits. | PASS |
| Produce risk-to-verification policy | Section 3 | Eleven factors, all twelve change classes and decision algorithm. | PASS |
| Produce commitment/approval policy | Section 4 | Preparation/review/authority separated; existing authorisation retained. | PASS |
| Produce stopping/escalation rules | Section 3.2 | Adequacy, failure diagnosis, actual blocker, alternative evidence and continued authorised work covered. | PASS |
| Produce rollback/reversibility considerations | Section 5 | Six surfaces distinguish restoration, compensation, reconciliation and forward repair. | PASS |
| Exit: distinguish local fix and schema migration | VP01/VP02 | Different evidence and authority justified by consequence/uncertainty, not line count; VP03/VP04 challenge overgeneralisation. | PASS |
| Retain truthful evidence and stage boundary | Whole record and intended log/index changes | Seven probes explicitly synthetic; no executed benchmark, skill/runtime or live action claimed. | PASS |

**Handoff:** Stage 8 consumes the professional capabilities, workflow, contract/context and verification obligations to research existing implementations and tools. Discovery starts from those obligations, not from whatever a current provider happens to expose. Stage 7 blockers: none. Commit and exact remote verification precede Stage 8.
