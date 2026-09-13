# Software Engineering Skills: Workflows and Artefacts Specification

**Version:** 1.0 · **Date:** 13 September 2026

**State:** canonical implementation specification; source/behaviour/installation readiness is reported separately.

**Owns:** change/contract taxonomy, inspection, workflow, artefacts, decision semantics, impact, verification flow, failure/repair and handoffs.

This specification is derived from the persisted bootstrap research accepted through Stage 14 (`9c84caf8d535aedf8f774a30dfc90a9038315d6a`). Normative operational requirements are stated here; linked research preserves provenance and limitations. A requirement is not evidence that it has been implemented or passed. User/project authority outranks defaults.

## Change taxonomy

A change has a **primary intended outcome** and any applicable secondary classes. Classes are not mutually exclusive and do not define a required skill split. A security fix can also repair a bug, evolve an API and require a migration. Classify the consequential behaviour and transition, not the filename or commit title. A configuration-only edit can be high consequence. An investigation may finish with evidence that no change is needed.

For every class distinguish: authorised delta; valid preservation obligations; current observed behaviour of unknown validity; and deliberately changed obligations. A pre-existing bug is not legitimised by a characterisation test. Conversely, calling a difference a bug fix does not authorise breaking a valid consumer contract. The user or existing policy may already authorise the decision; do not ask again by default.

| ID / class | Intended delta and trigger | What must be preserved | Impact and useful evidence | Grounding |
|---|---|---|---|---|
| CT01 — New behaviour | Add a justified capability or accepted case, including greenfield work. | Existing valid behaviour, shared rules, supported interfaces, data and relevant quality/security constraints. Greenfield still has supplied external/platform obligations. | Trace entry path and shared policy; test new acceptance plus affected existing cases; inspect unnecessary abstraction. | S02/S22; W01; C01/C03/C08 |
| CT02 — Bug repair | Correct a substantiated deviation from accepted behaviour. | Valid neighbouring behaviour, intended failure semantics and unrelated obligations. The defect itself is the explicit delta, not something to preserve. | Establish expected/actual distinction, causal mechanism and regression sensitivity; inspect impacts beyond the reproducer. | S12/S20; W02; C09 |
| CT03 — Refactor without intended behaviour change | Improve internal structure against demonstrated change friction. | All valid externally observable obligations within the declared boundary, including relevant errors, ordering, resource and timing constraints. Internal structure may change. | Explain transformation and pressure, inspect dynamic consumers, retain meaningful baseline checks and review architecture fit. | S23/S22; W03; C05/C06/C08 |
| CT04 — Interface / API evolution | Add, adapt, version or retire an interface under accepted compatibility intent. | Supported old source/wire/semantic use, defaults, errors and lifecycle commitments except specifically authorised changes. | Identify producers/consumers and supported combinations; distinguish a schema diff from semantic compatibility; plan deprecation when needed. | S14; W04; C10 |
| CT05 — Data / schema migration | Convert structure, representation, constraints or location of durable state. | Data meaning, integrity, ownership/access, retention decisions and supported readers/writers throughout intermediate states. | Model conversion and compatibility; check constraints, restart/resume, volume/locking and recovery feasibility before destructive contraction. | S11/S08; W05; C10/C16 |
| CT06 — Dependency or platform upgrade | Change an effective external component, runtime, build input or supported platform. | Required behaviour, compatibility, trust policy, reproducibility and supported consumer environments. | Inspect version/configuration/lock changes, used APIs, release/advisory evidence and installation/build in relevant environments. | S19/S06/S14; W06; C14 |
| CT07 — Performance change | Improve a demonstrated workload/resource property or meet an accepted budget. | Correctness, failure semantics and other approved quality budgets unless a trade-off is authorised. “Faster” does not permit dropped work. | Establish comparable baseline/workload, measure relevant distribution/resource use, diagnose cause and check affected correctness. | S13/S25; W08; C13 |
| CT08 — Security change | Repair a control or implement an accepted protection requirement. | Legitimate authorised use, data integrity and other obligations subject to the explicit security-policy delta. An exploit is not a compatibility entitlement. | Identify assets/trust boundary, relevant attacker preconditions, bypass/sibling paths, negative and positive evidence and residual-risk owner. | S15/S06/S20; W07; C19 |
| CT09 — Reliability / resilience change | Improve safety, recovery, progress or degradation under a stated fault model. | Normal behaviour and required invariants during failure; do not silently weaken consistency, durability or completion meaning to increase availability. | Trace partial effects, retries, timeouts and stale actors; test the chosen failure model and define remaining progress assumptions. | S17/S10; W09/W11; C11/C12 |
| CT10 — Operability / observability change | Make behaviour diagnosable or operation actionable. | Behaviour, privacy/security, resource budgets and operational interface commitments. Telemetry must not introduce sensitive exposure or disruptive overhead. | Connect signal to a diagnostic/operating question; check content, cardinality, failure behaviour and receiving instructions. | S25/S12/S15; W08/W12; C12/C17 |
| CT11 — Decommissioning / removal | Retire a capability, contract, dependency or stored state under accepted retirement intent. | Remaining users/services, retention/access obligations, supported transition and required audit/decision history. | Establish that supported consumers are migrated or deliberately retired; verify removal completion and distinguish code rollback from data recovery. | S11/S14/S06; Stage 3 G07; C10/C16 |
| CT12 — Architecture migration | Change responsibility, dependency, state or deployment boundaries to satisfy demonstrated constraints. | Accepted end-to-end behaviour, data and qualities across each intermediate architecture, not only the final design. | Compare local repair and migration alternatives; expose new failure/ownership boundaries; sequence compatibility/recovery and assess semantic structure. | S18/S11/S17; W03/W11; C04/C05/C16 |

CT03 is not a synonym for CT12: a migration can intentionally change latency, consistency or public interfaces. CT11 is not ordinary deletion until consumer and retention obligations are understood. CT09 and CT10 differ: a new log can aid diagnosis without improving fault tolerance. CT07 requires a relevant baseline and target; “optimisation” in a commit title is not a measured outcome. These distinctions survive multi-class composition.
## Contract taxonomy

A contract record needs only enough detail to identify its participants/boundary, valid obligation, evidence/source, relevant versions/conditions and planned treatment. It can be a link to existing canonical material with a short delta; a new standalone document is not compulsory. Record observed undocumented dependence as evidence, then determine whether it is supported or needs an authorised transition. Do not treat absent documentation as absence of consumers.

| ID / class | Obligations to discover | Evidence and affected participants | Typical false inference / check |
|---|---|---|---|
| CO01 — User-visible behaviour | Outcomes, interaction states, errors, accessibility, formats and accepted defaults. | Accepted examples/designs, current paths and user-facing observations. | Passing a unit test does not establish the intended journey; assess the affected behaviour and receiver criteria. |
| CO02 — API contracts | Input/output meaning, auth, errors, pagination, idempotency and version/support policy. | Interface/schema docs, implementation, generated clients and actual callers. | An optional field can change defaults; check old requests and meaning, not syntax alone. |
| CO03 — Schemas and persisted data | Meaning, constraints, identity, null/missing distinctions, retention and conversion. | Schema/migrations, data contracts and representative historical state with authorised access. | A successful new-row test says nothing about old records or lost information. |
| CO04 — Message / event contracts | Envelope/payload, producer identity, ordering scope, duplication, delivery and acknowledgement. | Producers, consumers, broker/transport settings and failure cases. | Queue order does not imply business completion order; locate the actual effect boundary. |
| CO05 — CLI contracts | Arguments/options, exit status, stdout/stderr, encoding, machine-readable formats and automation use. | Help/docs, parser/dispatch, scripts and subprocess checks. | Human-readable wording may be parsed elsewhere; inspect supported automation before changing it. |
| CO06 — Library contracts | Public symbols/types, source/binary compatibility where relevant, exceptions, side effects and thread/lifecycle behaviour. | Export surface, callers, package versions and language/ABI constraints. | A local source build does not prove old binary or downstream source compatibility. |
| CO07 — Configuration contracts | Names/types/defaults, precedence, validation, secret handling, reload/restart behaviour and supported combinations. | Declared configuration, environment/CLI overrides and effective runtime values. | Repository defaults may differ from effective values; resolve precedence before explaining a result. |
| CO08 — Protocols | State transitions, framing, version negotiation, sequencing, timeout and error/recovery semantics. | Protocol specification, implementation states and peer interaction evidence. | A valid message shape can still violate the protocol state machine. |
| CO09 — Performance budgets | Workload, latency distribution, throughput, memory/CPU/network/storage/cost limits and conditions. | Accepted budget and comparable measurements; specialist hardware constraints where relevant. | Lower mean latency cannot establish tail or resource compliance. |
| CO10 — Security properties | Identity/access, trust boundaries, confidentiality, integrity, safe input handling and component trust. | Threat/control requirements, sensitive surfaces and adversarial/analysis evidence. | No reported scanner finding does not prove enforcement or accepted residual risk. |
| CO11 — SLO / reliability assumptions | Service indicators/objectives, fault model, durability, consistency, recovery and progress/degradation conditions. | Supplied operational agreements, actual API semantics and failure observations. | A timeout does not prove abort; an SLO is not invented from a book example. |
| CO12 — Build / packaging contracts | Inputs/toolchain, resolution, supported environments, artifact contents, entry points and installation. | Build/package manifests, scripts, release layout and clean consumer evidence. | Source-repository success can rely on undeclared files or dependencies absent from the package. |
| CO13 — Backward compatibility | Which old participants, states and expectations remain supported for which transition/window. | Support policy, usage/dependency evidence and producer/consumer/version matrix. | A version number or empty search result is not proof of compatibility or safe retirement. |

CO13 cross-cuts the other twelve classes; it is not another wire format. CO08 covers interaction semantics even without messaging. CO09/CO10/CO11 remain distinct quality obligations with different oracles. The model is supported by Stage 4's compatibility, semantics, configuration, security, quality and release research; the CLI/library adaptations extend those mechanisms under the accepted scope without claiming every platform's details have been researched.
## Change-impact model

Use a bounded **obligation-and-effect record**, not a universal system graph. Begin from the request and available context. Each consequential path should connect the proposed edit to a behaviour, consumer, state or quality; record what observation supports the path and where inference remains. Static search can propose a path; runtime configuration, data or consumer evidence may be necessary to confirm it.

### 4.1 Minimal useful record

| Part | Contents and decision supported |
|---|---|
| Intent | Requested outcome, applicable authority, primary/secondary CT classes and exclusions. |
| Baseline | Revision/artifact, relevant environment/configuration, current accepted behaviour and observed deviations. |
| Touched surfaces | Direct code/configuration/data/docs, generated outputs and runtime entry paths. |
| Effects | Relevant callers/readers/writers, shared state, external effects and quality/security surfaces. |
| Obligations | Relevant CO classes; retain, intentionally change, migrate/retire, unknown or not applicable with reason. |
| Transition | Supported old/new/intermediate states, commitment points and recovery constraints. |
| Evidence | Existing and proposed checks with their oracles, cost, scope and identity; unresolved evidence remains visible. |
| Decision/handoff | Sufficient scope, next investigation, actual owner decision if needed, and receiving obligations. |

For a tiny local task this may be several sentences plus links. A multi-service migration may require several tables and a diagram. Keep the original input and current conclusions distinguishable. Do not expand the record merely to fill every possible contract category.

### 4.2 Investigation and change propagation

1. Classify the intended delta and identify the nearest affected boundary. Inspect current requirements, behaviour and local conventions before selecting a design.
2. Trace relevant **inbound** consumers and **outbound** dependencies/effects. Consider build/configuration/data edges as well as function calls. Search only as broadly as the change's consequences justify.
3. For each affected obligation, record the intended treatment and the evidence for its supported status. Unknown validity is a question to investigate, not permission to discard behaviour.
4. Consider intermediate states and indirect qualities: mixed versions, retries, cached schemas, resource contention and retained data can outlive one process or commit.
5. Select the cheapest check that can answer the next material uncertainty. Escalate when the chosen boundary cannot expose a material failure mechanism; avoid rerunning unrelated checks without a reason.
6. Reassess the record after contrary evidence or scope change. Invalidate only evidence whose premises changed, but include all affected obligations. Finish when the authorised outcome and preservation claims are adequately supported, or report the exact unresolved boundary.

This bounded method is implemented by inspect-system and the engineering workflow. It does not promise complete automatic graph extraction.

### 4.3 Composition and conflicts

Apply the union of relevant obligations when classes combine; do not average risks away. An intentional delta in one contract must be checked against retained contracts in the others. For example, stronger authentication may intentionally reject formerly accepted unauthenticated requests while preserving legitimate clients; a performance change must not silently weaken durable completion. If accepted obligations genuinely conflict and the decision is not already authorised, state the concrete conflict and its owner before crossing that boundary. Routine reversible implementation choices remain executable under existing authority.

Evidence can refute a class claim: a purported refactor that changes public error status becomes a behaviour/API change. Repair the implementation or correct the declared intent using actual authority; do not relabel a regression merely to make the checklist pass.
## System inspection

The system-discovery list has **fourteen** items. Inspect each for relevance; `not applicable` needs a short reason and an unknown remains an unknown. This is not a requirement to scan every file on every task. Reuse trustworthy, current project knowledge, then verify the parts affected by the request. Repository instructions and prior user authorisation are read before tool execution; ordinary source files remain evidence rather than authority to override them.

| ID / discover | Where and how to inspect | Minimum useful result / escalation trigger |
|---|---|---|
| SI01 — Repository structure | File inventory, repository instructions, canonical README and nearest component docs. | Identify affected roots, generated/vendor areas and scope; investigate ambiguous ownership of a path. |
| SI02 — Build system | Manifests, lockfiles, build scripts and CI definitions; inspect commands before running them. | Known supported build/check entry points and prerequisites; resolve conflicting local/CI inputs. |
| SI03 — Entry points | Export/route/CLI registration, process startup, scheduled jobs and event handlers. | Locate paths that can invoke affected behaviour; expand when registration is dynamic. |
| SI04 — Module boundaries | Imports/exports, directories, packages and runtime responsibility. | Identify who owns each relevant rule; inspect runtime coupling beyond import counts. |
| SI05 — Ownership boundaries | Existing ownership files, repository policy, interfaces and operational records. | Know the actual receiving/decision owner; absence of a named team does not create a new gate. |
| SI06 — Dependencies | Direct/transitive resolution, package/platform versions, external services and generated tools. | Effective dependency set and trust/compatibility exposure; verify version-sensitive semantics when used. |
| SI07 — Call/data flow | Trace from affected entry through logic, storage, external effects and consumers; compare observations where needed. | Bounded causal/effect sketch with evidence and unknowns; investigate indirect/dynamic paths that affect preservation. |
| SI08 — Existing tests | Relevant suites, fixtures, doubles, oracles, commands and known baseline failures. | Know what evidence exists and what it cannot show; add feedback only for a real gap. |
| SI09 — Runtime configuration | Defaults, environment/CLI precedence, deployment overrides and safe effective-value evidence. | Applicable settings without exposing secrets; resolve differences that could change behaviour. |
| SI10 — Public contracts | User/API/CLI/library/message/schema/protocol documentation and consumer usage. | Relevant CO obligations and supported versions; inspect undocumented but material dependencies. |
| SI11 — Architecture decisions | Current ADRs/design notes, supersession and relevant history. | Understand constraints and rationale; stale decisions prompt reassessment, not automatic reversal. |
| SI12 — Observability | Existing logs/metrics/traces, error reports, diagnostic hooks and run instructions. | A way to observe the changed effect and distinguish causes; avoid collecting irrelevant/sensitive telemetry. |
| SI13 — Security-sensitive surfaces | Trust/data boundaries, identity/access checks, parsing, secret handling, build/install scripts and external inputs. | Applicable threat/control obligations and uncertainty; use specialist handoff for unresolved specialist judgement. |
| SI14 — Release model | Packaging, distribution, environment promotion, mixed-version support, migration and recovery conventions. | Actual technical completion boundary and authority; do not conflate local success, merge, publication and exposure. |

CMD01 owns bounded inspection and its classify/impact/contracts modes. Stop expansion when relevant decisions have adequate evidence; disclose remaining material unknowns.
## Engineering workflow

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
## Artefact responsibilities

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
## Decision and evidence semantics

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

## Verification flow

For each material obligation identify expected result, relevant failure, actual invocation/boundary, environment and candidate, existing reusable evidence and remaining gap. Specification 01's risk policy chooses depth; Specification 04 owns benchmark measurement. Execute cheap useful feedback, inspect real output and required gates, then review actual diff/quality. A failure returns to the owning cause below; a changed candidate invalidates affected evidence. Final handoff confirms fresh evidence and actual requested action state. The flow is conditional; design-only or diagnosis-only can finish without construction.

Keep source, test/oracle, configuration, dependency, runtime and transition-state identity where relevant. Distinguish tool/setup failure from a product assertion; skipped/unknown is not passed. Do not select a weaker passing command merely because the required one failed. A materially equivalent authorised execution path can be used with its limits recorded.
## Failure taxonomy

The rows are project synthesis from the identified mechanisms. A failure may span several rows; classification helps choose repair and evidence rather than assign blame.

| ID / failure | Observable indication and likely uncertainty | Targeted repair | Evidence to seek |
|---|---|---|---|
| F01 — Wrong intended outcome | Tests pass but the request remains unmet; requirement/oracle mismatch. | Reconcile meaning with accepted intent; change the requirement or implementation only with authority. | Assessable example and receiver validation. |
| F02 — Incomplete context | Missed caller, runtime path or effective setting. | Expand inspection around the missed effect; revise impact boundary. | Actual call/data/configuration evidence. |
| F03 — Contract regression | Supported client or stored value stops working. | Restore valid compatibility or complete an authorised transition. | Old/new participant and data cases. |
| F04 — Inadequate oracle | Tests mirror the implementation or omit a relevant failure. | Correct expectation and add a discriminating boundary case. | Defective candidate fails for the right reason. |
| F05 — Structural damage | Coupling or duplicated policy raises real change cost. | Local restructuring tied to a named pressure; preserve behaviour. | Semantic review plus relevant regression evidence. |
| F06 — Lost or duplicated effect | Retry, timeout or partial commit produces ambiguous state. | Reconcile identity/state; implement correct retry/compensation boundary. | Failure and repetition cases with effect observations. |
| F07 — Concurrency/progress defect | Legal interleaving violates invariant or stalls work. | Correct synchronisation, atomic boundary or coordination protocol. | Invariant reasoning and targeted interleaving/progress checks. |
| F08 — Resource/performance regression | Tail delay, saturation, allocation or contention increases. | Repair demonstrated cause or revise a justified workload assumption. | Comparable baseline/candidate measurements and correctness checks. |
| F09 — Security boundary failure | Unauthorised access, unsafe input or untrusted artifact. | Fix the control and investigate similar paths; handle residual risk with its owner. | Adversarial cases, applicable analysis and provenance. |
| F10 — Migration/recovery defect | Intermediate deployment or stored-state conversion fails. | Stop destructive progression; reconcile and repair the affected stage. | Transition and recovery rehearsal under stated assumptions. |
| F11 — Evidence drift | Results refer to another candidate, configuration or context. | Re-establish relevant identity and rerun affected checks. | Traceable commands/observations and exact candidate. |
| F12 — Unactionable operation/handoff | Alert has no response, diagnosis lacks evidence, receiver cannot act. | Improve the necessary telemetry, instructions or ownership record. | Receiver can reproduce/interpret the bounded result. |
| F13 — Process overreach | Speculative rewrite, unnecessary ceremony or invented approval stalls useful work. | Return to authorised scope and cheapest adequate evidence. | Explain why each remaining action addresses a real obligation. |
## Repair routes

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
## Handoffs

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

## Workflow acceptance

All twelve CT classes distinguish delta/preservation; all thirteen CO classes identify obligations/participants; fourteen SI surfaces support bounded discovery. WF1–WF6 cover the fourteen candidate responsibilities without requiring fourteen documents. A00–A13 each retain eight responsibility/lifetime/authority fields; RR1–RR9 cover all thirteen failure classes. Small work may use concise notes; risky transition must preserve intermediate-state and recovery obligations. An implementation is accepted only with actual relevant evidence and a truthful requested completion boundary, not because it emitted these labels.


## Provenance and specification ownership

[S01 charter](research-logs/2026-09-12-stage-01-project-goal-and-domain-boundary.md), [source-qualified C/S/W models](research-logs/2026-09-13-stage-04-professional-practice-challenge.md), [CT/CO/SI context](research-logs/2026-09-13-stage-05-change-contract-and-context-model.md), [WF/A/RR semantics](research-logs/2026-09-13-stage-06-workflow-and-artefacts.md), [VL/RF/CP policy](research-logs/2026-09-13-stage-07-verification-risk-and-commitment.md), [D/S/P capability inventory](research-logs/2026-09-13-stage-08-candidate-evaluations.md), [execution architecture](research-logs/2026-09-13-stage-09-execution-layer.md), [core design](research-logs/2026-09-13-stage-11-core-skills-and-commands.md), [pack research](research-logs/2026-09-13-stage-12-extension-packs-completion.md), [example selection](research-logs/2026-09-13-stage-13-progressive-examples.md) and [evaluation design](research-logs/2026-09-13-stage-14-evaluation-and-benchmarks.md) preserve the decision/source register and research limitations. These links are maintainer provenance, not installed runtime dependencies.

The six specifications divide canonical responsibilities: [01 system](01-software-engineering-skills-system-spec.md), [02 workflows/artefacts](02-software-engineering-skills-workflows-and-artifacts-spec.md), [03 repository/contracts](03-software-engineering-skills-repository-and-contracts-spec.md), [04 testing/benchmark](04-testing-and-benchmark-spec.md), [05 packs](05-software-engineering-extension-packs-spec.md), [06 catalogue](06-software-engineering-extension-pack-catalogue.md). Operational details copied into role-local installed guidance must preserve the owning specification's meaning and be checked for drift; no shared runtime is implied.

---

Version 1.0 — 13 September 2026. Initial canonical specification from accepted research.
