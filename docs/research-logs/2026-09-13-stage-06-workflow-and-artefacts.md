# Stage 6: Engineering Workflow and Artefacts

**Stage:** 6 — Map the Engineering Workflow and Artefacts  
**Date:** 13 September 2026  
**Branch:** `feat/bootstrap-2`  
**Input commit:** `26027076e45ea88207d8aa426f85460992e6986f`  
**Status:** Complete for workflow and artifact design; no production runtime is implemented.

## 1. Inputs, acceptance and design evidence

The complete [Stage 6 requirement](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#13-stage-6--map-the-engineering-workflow-and-artefacts) governs this stage. Accepted inputs are the [charter](2026-09-12-stage-01-project-goal-and-domain-boundary.md), [Stage 2 coverage/corpus](2026-09-13-stage-02-knowledge-coverage-and-five-book-corpus.md), [Stage 3 findings](2026-09-13-stage-03-five-book-extraction-and-reconciliation.md), [Stage 4 evidence-qualified model](2026-09-13-stage-04-professional-practice-challenge.md) and [workflows](2026-09-13-stage-04-practitioner-workflows.md), and [Stage 5 change/contract/context model](2026-09-13-stage-05-change-contract-and-context-model.md). Their meaning and applicability are retained: brownfield is primary, valid obligations matter, cheap adequate evidence is preferred, and existing authority is respected. No source is promoted beyond Stage 4's recorded standing.

Acceptance: evaluate the fourteen-step candidate; define an end-to-end workflow; account for the primary codebase and all thirteen supporting artifact candidates with **eight fields each**; specify production state/decision semantics, handoff and repair; trace a small feature and a defect; inspect five outputs and conformance; commit only this stage and verify remotely. Artifact count is fourteen including the codebase; supporting artifacts are conditional, not a mandatory file set.

Research basis: Stage 4 W01/W02 demonstrate planned and failure-driven work; W03/W10 require trustworthy baseline evidence before risky restructuring; W04/W05/W11 require transition-aware contracts; W06/W12 distinguish effective candidate inputs and release readiness. S22/S23 support coherent increments, S12 supports hypothesis-driven repair, S18 supports useful decision records, and S20 bounds verification. Stage 5 CT/CO/SI adds preservation and context. This stage is a reasoned design comparison using that examined evidence, not a new empirical effectiveness claim.

| Workflow alternative | Evidence-based assessment | Decision |
|---|---|---|
| Fixed fourteen-step pipeline, exactly once | Easy to narrate, but baseline checks may be needed before implementation and any later finding can invalidate earlier assumptions. | Reject literal single-pass execution; retain all responsibilities and explicit return routes. |
| Full plan/ADR and complete repository analysis for every edit | Provides records, but adds work unrelated to many bounded changes; conflicts with the charter and S18/S22 proportionality. | Reject unconditional ceremony and whole-system inspection. |
| Write code, run tests, report success | Cheap initially, but omits intent, preservation, oracle quality, transition and authority; contradicted by W04–W12 and Stage 5 probes. | Reject as an adequate domain workflow. |
| Bounded decision loop with conditional artifacts | Handles local work and consequential transitions while preserving the same intent/evidence responsibilities. | Adopt below; Stage 7 determines verification detail and Stage 11 command boundaries. |

## 2. Domain workflow

The workflow describes responsibilities, not a mandatory engine, task graph, or persisted status object. One person or one agent may perform several steps. Reuse accepted intent, current project knowledge and valid evidence. The codebase and its actual change remain the primary production output.

| Phase | Required decision and activity | Output sufficient to advance | Return route |
|---|---|---|---|
| WF1 — Establish intent | Identify requested outcome, acceptance, actual authority and exclusions; distinguish proposal, defect and observation. | Clear bounded outcome or a concrete unresolved owner decision. | Conflicting intent returns here; ask only if investigation/session authority cannot resolve it. |
| WF2 — Understand the affected system | Inspect relevant Stage 5 SI items, current behaviour and evidence; classify CT/CO, preservation and uncertainty. | Bounded effect/contract context with sourced assumptions and baseline limitations. | A missed consumer, effective setting or state expands only the relevant inspection. |
| WF3 — Choose an approach and evidence | Select the smallest coherent feasible scope; compare alternatives when consequential; choose useful oracles/checks and transition/recovery treatment. | Justified approach, applicable evidence needs and identified commitment points. | Infeasible design, weak oracle or unexpected risk returns to the owning decision. |
| WF4 — Make the change with feedback | Implement coherent increments; add or revise tests when justified; establish a conservative seam first when weak feedback obstructs safe change. | Reviewable implementation and affected supporting artifacts, with cheap meaningful checks as work proceeds. | Local failure goes to diagnosis; scope-changing evidence returns to WF2/WF3. |
| WF5 — Verify and review | Run the cheapest adequate checks, escalate for uncovered material risk, inspect actual results and review the diff, contracts, structure, tests and evidence. | Candidate-specific results and resolved material findings; remaining limits explicit. | Diagnose failures and route correction by cause; do not rerun blindly. |
| WF6 — Confirm completion and hand off | Confirm final candidate identity and applicable obligations; execute already-authorised release actions if requested; report actual outcome and receiving needs. | Requested outcome with traceable evidence and accurate limitations/action status. | Changed candidate or failed transition invalidates affected evidence and re-enters its owning phase. |

WF1–WF3 can be a short inspection and a few sentences for a small task. WF4–WF5 form a loop rather than a single write followed by a single test. Review can happen before an expensive test to avoid wasting it, and final review still considers the actual resulting candidate. A consequential design may need review before construction. None of these choices waives the evidence required for the obligation.

For urgent incidents, authorised containment can reduce harm while diagnosis proceeds. Label it mitigation, preserve observations and carry causal uncertainty. A claim of permanent repair requires an adequate cause/effect account and relevant regression evidence. This preserves the governing root-cause principle without requiring service harm to continue until every contributing cause is understood.

### 2.1 Disposition of every candidate workflow step

| Candidate step | Retained placement and qualification |
|---|---|
| Understand change intent | WF1, re-entered if accepted intent is contradicted. |
| Inspect repository and current behaviour | WF2; scoped inspection may recur during diagnosis. |
| Identify affected contracts / risk | WF2, refined by WF3 and contrary results. |
| Select smallest coherent approach | WF3; coherent may require several files or migration steps. |
| Record design only when useful | WF3/A05; significant decisions survive, transient reasoning need not. |
| Implement | WF4 when implementation is the requested outcome; absent for valid diagnosis/review-only work. |
| Add or revise targeted tests | WF3 selects evidence; WF4 implements/revises justified checks. Baseline tests may precede risky edits. |
| Run cheapest meaningful validation | WF2/WF4/WF5 as soon as it answers a relevant question. |
| Escalate validation according to risk | WF3 plans and WF5 executes broader checks for uncovered obligations. |
| Review diff and quality | WF5, with earlier design review when the commitment warrants it. |
| Diagnose failures | From any phase; classify failure versus environment, oracle or unsupported assumption. |
| Bounded correction | Return to the owner of the failure; preserve valid work and avoid unrelated reconstruction. |
| Final verification | WF6 confirms evidence applies to the final candidate; rerun affected checks after change. |
| Handoff / release evidence | WF6; completion is the requested boundary, and release action status remains separate. |

## 3. Artifact responsibilities

The following two tables join on stable IDs. Together they give **all eight required fields for each of fourteen artifacts**: justification, creator, source of truth, consumers, preserved decisions, change semantics, approval semantics and retention/disposal. These are roles, not mandatory separate people. The engineer may draft any technical artifact; the actual owner controls accepted intent or consequential decisions.

An artifact is justified by a decision or receiver. Prefer the consuming repository's existing issue, specification, code, test, ADR or release record. Link to canonical sources and preserve status; do not create competing copies to satisfy this table. The primary codebase includes executable code and applicable configuration/build assets, not merely application files.

### 3.1 Creation, authority of content and consumers

| ID / artifact | When justified | Creator | Source of truth | Consumers |
|---|---|---|---|---|
| A00 — Codebase | A requested implemented change or the baseline being inspected. | Engineer/maintainer through the authorised workflow. | Actual versioned source and effective generated/build inputs; deployed artifact identity is separately recorded. | Maintainers, build tools, downstream consumers, reviewers and operators. |
| A01 — Change brief / issue / specification | Intent, scope or constraints need to survive the interaction or already exist canonically. | Request/requirement owner; engineer supplies technical clarification. | Existing accepted request/issue/specification with status and links to decisions. | Engineer, reviewer, acceptance owner and affected specialists. |
| A02 — Acceptance criteria | Needed to decide whether the requested outcome is achieved. | Engineer translates supplied intent; actual owner resolves meaning. | Canonical request/specification/examples; tests operationalise but do not silently redefine intent. | Implementer, reviewer, QA and receiver. |
| A03 — System inspection notes | Discoveries or material unknowns must survive or support another worker/reviewer. | Inspecting engineer. | Evidence links to revision, configuration and observations; notes are a bounded model. | Implementer, reviewer and future maintainer. |
| A04 — Impact analysis | Multiple obligations, consumers or consequential changes make effects non-obvious. | Engineer using Stage 5 model. | Referenced contracts and inspected effects, with intentional delta and uncertainty. | Reviewer, consumer owners, specialists and release owner. |
| A05 — Design note or ADR | A significant alternative/constraint/trade-off must remain understandable. | Engineer/architect acting within local ownership. | Existing architecture record system with explicit proposal/accepted/superseded status. | Implementers, reviewers and future decision makers. |
| A06 — Interface/schema definition | A public/inter-component/persisted shape or interaction contract exists or changes. | Owning engineer; domain owner supplies semantics. | Chosen canonical schema/interface plus linked semantic constraints and generation configuration. | Producers, consumers, generators and validators. |
| A07 — Migration plan | A transition spans supported versions, durable state or consequential retirement. | Engineer with data/operator/consumer context. | Versioned transition sequence linked to applicable contracts and exact migration implementation. | Implementers, operators, data/consumer owners and reviewer. |
| A08 — Implementation diff | Review or provenance needs the precise delta. | Version-control comparison of engineer's candidate against stated baseline. | Actual base/candidate content, not a manually copied patch description. | Reviewer, maintainer and evidence consumer. |
| A09 — Tests and fixtures | Existing or new checks supply meaningful evidence for an obligation. | Engineer/test specialist. | Versioned test code/data and explicit oracle origin with required environment. | Check runner, reviewer and maintainer. |
| A10 — Benchmark fixture | Performance or judgement/quality comparison requires repeatable measurement. | Engineer/evaluation author with workload/domain criteria. | Versioned workload/cases, oracle, measurement procedure and environment definition. | Evaluator, reviewer and decision owner. |
| A11 — Verification evidence | Any claim that a check ran, a condition held or an action completed. | Executing tool/engineer records actual output; engineer interprets it. | Identified raw result/artifact plus exact command, candidate and relevant inputs. | Reviewer, acceptance owner, maintainer and receiver. |
| A12 — Review findings | Substantive concerns, decisions or unresolved limitations need action/history. | Reviewer or self-reviewing engineer, identified honestly. | Canonical review record tied to the candidate and obligation. | Implementer, reviewer, decision owner and receiver. |
| A13 — Release note / migration note | Consumers/operators need the delta, transition or action needed for a release. | Engineer/release writer using verified facts. | Canonical release/change record linked to exact artifact and migration plan. | Consumers, operators, support and maintainers. |

### 3.2 Decision, update, approval and lifetime semantics

| ID | Decisions preserved | Change semantics | Approval semantics | Retention / disposal |
|---|---|---|---|---|
| A00 | Implemented behaviour/structure and effective construction choices. | Version edits coherently; generated outputs follow their actual generator; preserve valid work. | Existing user/repository authority governs edits, merge and release separately. | Retain according to repository/release history; never dispose of user changes to simplify the task. |
| A01 | Why the outcome is needed, scope and accepted constraints. | Clarification records its source; material intent change has explicit status. | Existing accepted intent is reusable; unresolved product choices go to their actual owner. | Keep canonical durable decision; transient restatement can be discarded once linked. |
| A02 | Observable success and valid preservation conditions. | Revise when intent is legitimately corrected/changed; do not weaken to match a failing implementation. | Technical formulation can be routine; changing an accepted promise needs existing or new relevant authority. | Retain with the behaviour's lifetime; supersede stale criteria explicitly. |
| A03 | What was established, from which evidence, and what remains unknown. | Refresh affected premises; distinguish observations from inferred paths. | Factual notes need no new approval; they do not themselves authorise a change. | Retain useful discoveries; discard temporary searches/notes with no receiving value. |
| A04 | Why effects and obligations are in/out of scope and what needs transition. | Update after contrary evidence or changed scope; invalidate affected conclusions. | Analysis is preparatory; owner decision is needed only for an unapproved consequential boundary. | Preserve with significant change; concise local analysis may live only in review/handoff. |
| A05 | Context, alternatives, decision, consequences and assumptions. | Preserve supersession rather than erasing decision history; revisit when premises change. | Local ownership determines acceptance; a written proposal is not self-approval. | Retain significant history; dispose of discarded exploratory drafts without pretending they were accepted. |
| A06 | Interoperability and semantic obligations, supported versions and defaults. | Change source/generator consistently; assess old/new participants and persistent state. | Existing interface ownership/support policy applies; no extra gate merely because a schema file exists. | Retain supported versions/history and required migration context; obsolete copies are explicitly retired. |
| A07 | Intermediate states, sequence, verification, stop/recovery conditions and owners. | Version with implementation; reconcile actual progress before resume/change. | Preparation is authorised engineering; destructive/live steps require the actual action authority. | Retain through transition and needed operational/audit lifetime; remove obsolete execution instructions clearly. |
| A08 | Exact scope of the candidate compared with its baseline. | Regenerate on change; a prior review is reassessed for affected deltas. | A diff is review evidence, not an approval or deployed state. | Version history is durable; stale exported copies may be removed when canonical identity remains. |
| A09 | Cases, oracle and evidence boundary, including intentional failure conditions. | Add/revise for relevant risk; preserve a useful test through equivalent restructuring; classify oracle corrections. | Routine tests use existing authority; changing acceptance via a test needs a valid source. | Retain useful regressions; retire obsolete cases with rationale; temporary probes may be discarded after useful evidence is captured. |
| A10 | Workload/case selection, comparison conditions and adequacy criteria. | Version changes independently from measured candidate; disclose comparability effects. | Technical fixture work is routine; changing an accepted budget/evaluation criterion needs its owner. | Retain reproducible cases and necessary provenance; dispose of regenerable transient data when no longer needed. |
| A11 | What actually happened and how far the conclusion is supported. | Append/supersede with new identity; never overwrite a failure into a claimed historical pass. | Evidence is not permission; actual gate/acceptance rules determine sufficiency. | Retain decision-relevant results and failure diagnosis; follow existing limits for sensitive/large logs. |
| A12 | Obligation violated, severity/consequence, disposition and rationale. | Resolve with linked correction/evidence; reopen if new candidate invalidates resolution. | Distinguish self-review, peer review and required approval; do not label one as another. | Preserve substantive decisions and unresolved findings; transient nits need not become project knowledge. |
| A13 | User-visible delta, compatibility, required action and known limitations. | Update for actual released candidate; draft, published and superseded remain distinct. | Drafting is routine; publication follows the user's release scope and repository policy. | Retain supported release/migration history; redirect obsolete instructions rather than leaving contradictory copies. |

No artifact can launder authority: an accepted-looking filename, checked box, baseline snapshot or generated report does not approve an otherwise unapproved change. Conversely, a skill must not block previously authorised work just to obtain another copy of the same approval.

## 4. Production state and decision semantics

These labels clarify claims; they need not be written to disk or implemented as a state machine. Work may be represented by the existing issue/PR and evidence records. A state applies to a **scope and candidate**, not to a whole repository forever.

| State / decision | Meaning | Evidence needed / allowed transition |
|---|---|---|
| Intent established | The requested outcome and material constraints are understood sufficiently for the next decision. | Referenced accepted request plus bounded assumptions; consequential ambiguity returns to WF1. |
| Context sufficient | Relevant effects, contracts and current feedback are known enough for the chosen approach. | Evidence-backed scope and explicit unknowns; completeness of the whole system is not claimed. |
| Approach selected | A feasible, coherent option and evidence plan fit the current obligations. | Rationale and alternatives where material; only significant rationale requires an ADR. |
| Candidate in progress | Implementation/supporting artifacts exist but acceptance is not established. | Actual content/revision; neither tests nor delivery are presumed. |
| Evidence assessed | Relevant checks ran or analyses were performed and their results were interpreted. | Distinguish passed, failed, inconclusive, unavailable and not applicable per check. |
| Review resolved | Material review findings for the candidate are repaired, validly accepted by their owner, or explicitly prevent completion. | Linked reasons/evidence and actual required approvals; equivalent preferences need not block. |
| Ready for requested handoff | Candidate-specific obligations for the requested scope are adequately evidenced. | All applicable gates satisfied, actual limitations known and next action authority checked. |
| Requested outcome complete | The authorised task boundary has been reached and reported accurately. | If action was requested, its observed result exists; if design/review was requested, no implementation is implied. |
| Decision needed / blocked | A specific missing input, authority or capability prevents the next necessary action. | State exact question, prepared evidence and affected boundary; do not describe unrelated future possibilities as blockers. |

Check result semantics: **passed** is a supported property for the stated case; **failed** is an observed mismatch; **inconclusive** means the result cannot decide; **unavailable** means it was not executed/accessible; **not applicable** requires a scope reason. “Skipped” is never a synonym for passed. Existing baseline failures remain identified; assess whether they affect this task instead of hiding them or automatically owning all of them.

Candidate changes invalidate evidence according to changed premises: code, fixture/oracle, dependency, configuration, environment, acceptance or transition state. A documentation-only correction may not invalidate a runtime test. A rebuilt artifact or changed runtime configuration can invalidate a release claim despite unchanged source. Decide and record the relevant recheck; do not indiscriminately replay the whole pipeline.

Authority is orthogonal to technical state. A well-tested candidate may lack publication authority. An authorised release can still fail its technical gate. Existing authorisation persists until its scope or a genuine consequence changes; no extra confirmation is introduced by these labels.

## 5. Handoff model

The receiving party can be the user, maintainer, reviewer, QA, specialist or operator. A handoff carries an actionable bounded outcome; it does not imply the receiver accepted it or performed a later action. No external message is sent merely because a handoff table names a person or team.

| Handoff component | Required information when relevant |
|---|---|
| Outcome and scope | Requested result, actual completed delta, retained obligations and exclusions. |
| Identity | Candidate/revision/artifact plus relevant environment, configuration and dependency identity. |
| Decision and evidence | Material rationale, actual checks/results and where details can be inspected. |
| Limitations | Failed, unavailable or inconclusive evidence and their effect on the claim. |
| Action | Any remaining receiver decision, migration/installation step or authorised operational action; distinguish suggested from completed. |
| Ownership and knowledge | Actual owner/receiver and canonical records needed to continue; preserve specialist boundaries. |

A small feature's handoff can be a short change/test explanation. A schema migration needs the supported transition, data/recovery constraints and operation results. A review-only task returns findings and evidence, without fabricating a patch or release. When no receiving action remains, say the task is complete and continue any already-authorised next work; do not create a new permission boundary.

## 6. Repair routes

Each route starts from actual failure evidence, locates the owning cause, preserves unaffected valid work and reruns the smallest sufficient set of affected checks. These routes cover Stage 4 F01–F13. No route weakens an acceptance gate to make the current result pass.

| Route | Trigger / failure class | Owning correction and preserved work | Recheck and return |
|---|---|---|---|
| RR1 — Intent/oracle | F01/F04: wrong outcome, contradictory criteria or self-confirming test. | Return to WF1/WF3; establish legitimate expectation. Preserve correct implementation/criteria; do not silently approve changed intent. | Discriminating acceptance case, then affected WF4/WF5 work. |
| RR2 — Context/evidence identity | F02/F11: missed path, wrong revision/configuration or stale result. | Return to WF2; correct the bounded context or exact candidate inputs. Preserve still-applicable evidence. | Recheck only claims whose premises changed; revisit approach if impacts widen. |
| RR3 — Local implementation/structure | F03/F05: behavioural regression or structural defect owned locally. | Correct the causal diff/transformation in WF4; keep unrelated working changes. | Relevant regression plus semantic diff review; broader checks if affected obligations demand them. |
| RR4 — State/concurrency/protocol | F06/F07: duplicate/lost effect, invariant or progress failure. | Revisit WF2/WF3's effect/atomicity/coordination boundary; reconcile actual state before retry. | Targeted failure/interleaving and integration evidence, then readiness reassessment. |
| RR5 — Performance | F08: measured workload/resource mismatch. | Correct workload/measurement if invalid, otherwise repair demonstrated cause. Preserve correctness and other budgets. | Comparable measurements with uncertainty plus affected functional checks. |
| RR6 — Security | F09: control, trust or provenance failure. | Repair the owning boundary and inspect related paths; use actual specialist authority for residual-risk decisions. | Positive/negative/adversarial and applicable analysis evidence; retain unresolved limits. |
| RR7 — Transition/release | F10/F11: migration, packaging, installation or release mismatch. | Stop unsafe progression, reconcile intermediate state and repair/recover at the owning step. | Verify recovery/transition and exact resulting candidate before resuming authorised action. |
| RR8 — Observability/handoff | F12: result cannot be diagnosed, interpreted or acted on. | Correct needed signals/instructions/ownership in WF2/WF6; avoid logging sensitive or irrelevant data. | Demonstrate usable observation or receiving instructions within scope. |
| RR9 — Unnecessary work/authority error | F13: speculative rewrite, needless ceremony or invented approval. | Return to accepted intent and actual authority; remove unjustified scope without discarding valid user work. | Confirm the sufficient scope and proceed with required evidence and authorised work. |

An unavailable check is not automatically an implementation defect. Diagnose missing environment/tool/access, use an adequate available alternative if one exists, and preserve the limitation. If a required gate cannot be satisfied, report a genuine blocker rather than inventing success. A failed tool invocation also does not establish that the software under test failed.

## 7. End-to-end traces

The following are **synthetic design traces**, not runs, benchmark results or complete Stage 13 examples. They show the semantics that implementation must later demonstrate.

### T01 — Small feature: optional compact CLI output

1. **WF1:** An accepted request asks for `--compact` output while retaining the default format. No new product or publication decision is needed. A01 already exists; A02 is a pair of assessable default/compact expectations.
2. **WF2:** Inspect parser, formatter, command dispatch, subprocess consumer tests and packaging entry point. CT01 with CO05/CO13 identifies default output, stderr and exit status as preserved. A03/A04 can be short notes in the working issue; no whole-repository map is justified.
3. **WF3:** Compare a formatter option with duplicating command dispatch. Choose the coherent local option because dispatch semantics remain shared. No enduring architectural trade-off warrants A05. Select the relevant default-output regression and new compact-boundary test; existing evidence is reused only if it matches current content.
4. **WF4:** Add the option and targeted test. A00/A08/A09 are real production artifacts when implemented. If a cheap check shows the default output changed, RR3 repairs that formatter path while retaining the new option and unrelated user changes.
5. **WF5:** Inspect the actual candidate diff and test oracle. Run the selected parser/formatter or subprocess checks; use packaging evidence if the entry point changed. Record actual result and limitations in A11, and resolve substantive A12 findings. This trace does not invent a pass.
6. **WF6:** Confirm results apply to the final candidate and report the option, preserved default, checks and any limitation. A13 is updated only if the repository's user-facing change convention calls for it. The requested code change ends here; a release is not implied. Continue further already-authorised tasks without asking again.

### T02 — Defect: duplicate work after lost submission response

1. **WF1:** The accepted obligation is one logical submission per request identity. The symptom is duplicate processing after a response timeout. CT02/CT09 with CO04/CO08/CO11 separates the fault from valid retry behaviour.
2. **WF2:** Inspect client retry, request identity, persistence and worker acknowledgement paths. Distinguish failed, successful and unknown completion. Gather a minimal substantiated trace; inability to reproduce on demand does not justify claiming a specific cause without evidence.
3. **WF3:** Construct the hypothesis that the server accepted the work before the response was lost and the retry used a new identity. A controlled reproducer can discriminate that explanation from worker redelivery. If durable identity/effect coupling requires a migration, CT05/A07 is added; the label bug fix does not hide that scope.
4. **WF4:** Correct the responsible identity/atomicity boundary, preserving distinct legitimate submissions. Add the targeted lost-response/duplicate case plus the independent-request case. A fake that omits durable uniqueness is inadequate for that property; RR1/RR4 repairs the evidence boundary rather than accepting a misleading pass.
5. **WF5:** Verify the relevant interleaving/effect and supported transition. Review whether retries, cancellation and caller intent still work. An unexpectedly duplicated effect reopens the hypothesis; no blind rerun or unbounded retry is treated as repair. Record actual results only when implementation executes them.
6. **WF6:** Handoff states cause confidence, actual corrected boundary, candidate, checks, residual failure assumptions and any migration/operator action. If a live incident also exists, containment and operating authority are separate from claiming this permanent fix. Technical readiness does not assert an unexecuted deployment.

Both traces name entry, context, decision, artifacts, check selection, failure route, final identity and completion. The feature needs no architecture ceremony; the defect becomes broader only when its causal mechanism and preserved obligations require it.

## 8. Conformance and handoff

| Requirement | Evidence | Verification | Result |
|---|---|---|---|
| Consume complete stage and accepted evidence-qualified inputs | Section 1 | Reconstructed prior charter, workflow/capability and CT/CO/SI models at input commit. | PASS |
| Derive smallest credible end-to-end workflow | Sections 1–2 | Four alternatives evaluated; six phases retain all fourteen candidate responsibilities with conditional/loop placement. | PASS |
| Avoid obligatory design/planning ceremony | WF3, A05 and T01 | Design records depend on enduring decision value; small task traced without an ADR. | PASS |
| Codebase is primary artifact | A00 and WF4 | Implementation/diff remain central; supporting records do not replace requested work. | PASS |
| Account for all thirteen supporting candidates | A01–A13 | Every named candidate present, plus A00 codebase. | PASS |
| Eight responsibility fields for each artifact | Sections 3.1–3.2 | Fourteen joined rows in each table; 112 nonempty responsibility cells inspected. | PASS |
| Do not require files for transient reasoning | Section 3; A03/A04/A09; T01 | Existing canonical records reused; disposal and transient treatment explicit. | PASS |
| Produce domain workflow | Section 2 | Decisions, advance evidence and return routes specified. | PASS |
| Produce artifact responsibilities | Section 3 | Creator, truth, consumers, decisions, updates, authority and lifetime are distinguishable. | PASS |
| Produce production state/decision semantics | Section 4 | Evidence outcomes, candidate validity, completion and authority separated. | PASS |
| Produce handoff model | Section 5 | Outcome, identity, evidence, limits, action and owner; no implied receiver action. | PASS |
| Produce repair routes | Section 6 | Nine routes cover F01–F13, preserving valid work and requiring targeted rechecks. | PASS |
| Exit: trace small feature and defect end to end | T01/T02 | Both contain initial intent through final handoff, with failure and repair semantics. | PASS |
| Truthful research/implementation boundary | Sections 1, 7 and intended change set | Traces synthetic/unexecuted; no skill, runtime, benchmark or installation success claimed. | PASS |

**Handoff:** Stage 7 consumes WF1–WF6, artifact identity/lifetime, state semantics and repair routes alongside Stage 5 risk candidates. It must define verification escalation, commitment points and risk decisions without turning this conditional workflow into a mandatory ceremony. Stage 6 blockers: none. Commit and exact remote verification precede Stage 7.
