# Stage 5: Change, Contract and System-Context Model

**Stage:** 5 — Model Software Change Types, Contracts and System Context  
**Date:** 13 September 2026  
**Branch:** `feat/bootstrap-2`  
**Input commit:** `81902d88e2d74a3d6d4ae19d45785bcc4fdb0214`  
**Status:** Complete at the model/research level; implementation remains later work.

## 1. Inputs and acceptance

The governing requirements are the complete [Stage 5 section](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#12-stage-5--model-software-change-types-contracts-and-system-context). Accepted inputs are the [Stage 1 charter](2026-09-12-stage-01-project-goal-and-domain-boundary.md), [Stage 2 coverage record](2026-09-13-stage-02-knowledge-coverage-and-five-book-corpus.md), [Stage 3 findings/capabilities](2026-09-13-stage-03-five-book-extraction-and-reconciliation.md) and [Stage 4 professional challenge](2026-09-13-stage-04-professional-practice-challenge.md), including its [twelve workflows](2026-09-13-stage-04-practitioner-workflows.md). The applicable charter responsibility, preservation, authority and specialist-boundary sections were reconstructed alongside the qualified model. The five-book corpus and accepted Stage 1–2 decisions remain unchanged.

Acceptance: investigate **12 change classes**, **13 contract classes** and **14 system-discovery items**; produce change taxonomy, contract taxonomy, impact model, inspection checklist/hypothesis and risk candidates; explain preservation for every change class; inspect actual outputs; commit only this stage and verify remotely. These are the literal counts in the governing lists. No executed benchmark or production graph is required by Stage 5.

This stage synthesises already examined evidence rather than inventing a new source authority. Stage 4 source IDs are reused with their exact scope and limitations. S14/S11 ground compatibility/transition reasoning, S08/S17/S21 state semantics, S12/S13/S25 failure/quality investigation, S19/S06 effective-input and trust reasoning, and S02/S18/S22/S23 intent and bounded change. These sources were assessed in Stage 4; neither their product examples nor their process policies become universal defaults here. New tables and probes below are project design reasoning, not empirical findings.

## 2. Change taxonomy

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

## 3. Contract taxonomy

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

## 4. Change-impact model

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

This is a command/workflow hypothesis for later design. Stage 5 does not implement dependency discovery or promise completeness of a graph extraction tool.

### 4.3 Composition and conflicts

Apply the union of relevant obligations when classes combine; do not average risks away. An intentional delta in one contract must be checked against retained contracts in the others. For example, stronger authentication may intentionally reject formerly accepted unauthenticated requests while preserving legitimate clients; a performance change must not silently weaken durable completion. If accepted obligations genuinely conflict and the decision is not already authorised, state the concrete conflict and its owner before crossing that boundary. Routine reversible implementation choices remain executable under existing authority.

Evidence can refute a class claim: a purported refactor that changes public error status becomes a behaviour/API change. Repair the implementation or correct the declared intent using actual authority; do not relabel a regression merely to make the checklist pass.

## 5. System-inspection checklist and command hypothesis

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

**Hypothesis:** one inspection operation could accept a bounded intent and return relevant context, contracts, impacts, unknowns and recommended next checks. It should stop expanding when those outputs answer the decision, preserve source links, and disclose gaps. It may be embedded within a broader engineering workflow rather than exposed as a separate command. Stage 11 will decide the skill/command boundary; Stage 8 will first investigate existing discovery capabilities. No universal graph storage, agent coordinator or new scanner is selected.

## 6. Risk classification candidates

Risk classification guides evidence and commitment handling; it is not a quality score, probability or instruction to ask permission for every edit. The class name alone does not determine risk. Inspect consequences, exposure, uncertainty and recoverability. Unknowns affecting a consequential boundary require investigation before relying on optimistic assumptions.

| Candidate | Defining conditions | Proportionate response |
|---|---|---|
| RK1 — Local and understood | Bounded effect, clear obligation, low harm, good existing feedback and easy recovery. | Inspect affected path, make coherent change, use focused evidence and concise handoff. |
| RK2 — Coupled or incompletely understood | Multiple affected consumers or a material feedback/context gap, with controlled consequences. | Trace the relevant coupling, improve the missing evidence and review preservation. |
| RK3 — Persistent or broadly exposed | Public contracts, shared state, multiple deployments, significant security/resource/reliability exposure or costly recovery. | Make intermediate states and owners explicit; obtain representative contract/failure/recovery evidence. |
| RK4 — Consequential unresolved boundary | Irreversible effects, specialist assurance, conflicting accepted obligations or missing execution authority. | Prepare concrete evidence/options first; resolve the actual missing decision/capability before that action. Continue other authorised preparation where it does not cross the boundary. |

Modifiers to inspect separately: blast radius; data/value at risk; consumer control; quality sensitivity; reversibility; deployment/version skew; fault/concurrency exposure; test/oracle strength; observability; and confidence in context. Do not multiply ordinal ratings. A large generated mechanical diff can be RK1/RK2; a one-line retention deletion can be RK3/RK4. Existing approval can resolve authority without resolving technical risk, and strong tests can resolve uncertainty without granting authority.

These remain candidates for Stage 7's verification/risk model. “RK4” does not mean the task is blocked at Stage 5: it identifies circumstances to recognise in future consuming work, not a current missing approval for this authorised bootstrap.

## 7. Model probes: change versus preservation

These are **twelve synthetic desk-review probes**, one for each required change class. They exercise the model conceptually; no code or runtime was executed. Each tests a distinction that a generic edit/test sequence can miss.

| Probe / primary class | Scenario and explicit intended delta | Preservation and model result |
|---|---|---|
| P01 / CT01 | Add an optional CSV column selector. | Existing default output and callers remain; CO01/CO05/CO13 trigger CLI-consumer inspection. Do not silently reorder default columns. |
| P02 / CT02 | Fix a parser that accepts an invalid date; acceptance already defines valid dates. | Correct the invalid acceptance while keeping valid inputs/error contracts; CO01/CO06 separate desired oracle from characterisation. |
| P03 / CT03 | Extract a shared formatter without intending output changes. | Preserve formatting, exceptions and relevant performance; reflection/dynamic entry use is an SI03/SI07 unknown, not proof of safe rename. |
| P04 / CT04 | Add pagination to a previously complete response. | CO02/CO13 expose semantic incompleteness for old callers; require a compatible default or authorised transition. “Additive” does not settle it. |
| P05 / CT05 | Rename a persisted field while old workers run. | CO03/CO07/CO13 require intermediate reader/writer treatment and historical data checks; a final-schema-only test fails the model. |
| P06 / CT06 | Upgrade a package while CI uses a different install flag. | CO12/SI02/SI06/SI09 identify different effective inputs; lockfile equality alone is insufficient. |
| P07 / CT07 | Cache a permission-sensitive lookup to reduce latency. | CO09 cannot override CO10; invalidation/access semantics need evidence alongside the timing result. |
| P08 / CT08 | Enforce tenant access on an export endpoint. | CO10 changes illegitimate access, while CO01/CO02 preserve valid tenant export and errors; scan sibling paths for the same control gap. |
| P09 / CT09 | Retry job submission after a timeout. | CO04/CO08/CO11 expose unknown completion and duplicate effects; choose identity/reconciliation rather than assuming abort. |
| P10 / CT10 | Add a request trace to diagnose intermittent errors. | CO10/CO09 require sensitive-data and overhead checks; SI12 ties the signal to a real diagnostic question. |
| P11 / CT11 | Delete a deprecated endpoint and its table. | CO13/CO03 require supported-consumer and retention evidence; source deletion and irreversible data deletion are separate commitments. |
| P12 / CT12 | Move processing into an independently deployed worker. | CO04/CO08/CO11/CO13 expose ordering, duplicates, failures and version skew; preserve the end-to-end obligation in every transition state. |

The probes distinguish all twelve classes without pretending they are disjoint. They reveal preservation and authority separately, and produce bounded investigation needs rather than a mandatory whole-repository graph. They are candidates for later example/benchmark design, not accepted replacements for Stage 13's exact fifteen complete examples.

## 8. Decisions, rejected alternatives and conformance

Decisions: adopt multi-label change classification; make preserved and intentionally changed obligations explicit; treat compatibility as a cross-cutting contract; inspect effective runtime/build/data context; keep impact records proportional; retain nonnumeric risk candidates for Stage 7. The five outputs are sections 2, 3, 4, 5 and 6 respectively.

Rejected alternatives: a taxonomy based only on files; mutually exclusive change labels; tests as the only contracts; all observed behaviour as approved; version numbers as compatibility proof; fixed line-count risk; a universal dependency graph; and obligatory owner approval for already-authorised routine work. Each would erase a distinction demonstrated by the research/probes. No unresolved question requires changing the accepted charter or asking the user now.

| Requirement | Evidence | Verification | Result |
|---|---|---|---|
| Read complete stage and accepted prior inputs | Section 1 and linked records | Requirements and relevant charter, research, capability/workflow inputs reconstructed at input commit. | PASS |
| Investigate all twelve change classes | CT01–CT12 | Counted twelve; each has intent, preservation, impact/evidence and grounding. | PASS |
| Investigate all thirteen contract classes | CO01–CO13 | Counted thirteen; each has obligations, participants/evidence and a counterexample/check. | PASS |
| Model discovery of all fourteen system-context items | SI01–SI14 | Literal list accounted for; methods, minimum result and escalation conditions supplied. | PASS |
| Produce change taxonomy | Section 2 | Composite cases and class distinctions examined; preservation explicit for every class. | PASS |
| Produce contract taxonomy | Section 3 | Behavioural, technical and quality obligations represented; compatibility cross-cuts types. | PASS |
| Produce change-impact model | Section 4 | Intent through effects, contracts, transition and evidence; contrary evidence revises scope. | PASS |
| Produce inspection checklist/command hypothesis | Section 5 | Fourteen discovery items plus bounded command hypothesis; no premature skill split. | PASS |
| Produce risk classification candidates | Section 6 | Four consequence/uncertainty candidates with independent modifiers and authority treatment. | PASS |
| Avoid invented universal system graph | Sections 4–5 | Bounded records and relevant paths suffice; no graph schema, runtime or tool built. | PASS |
| Exit: distinguish changes and explain preservation for each | Sections 2 and 7 | Twelve conceptual probes inspected; class-specific and cross-contract counterexamples accounted for. | PASS |
| Persist substantive research/design and truthful evidence | Whole record | Source applicability retained; probes labelled synthetic and unexecuted; no runtime/benchmark claims. | PASS |
| Preserve accepted scope and stage boundary | Intended log/index changes | No Stage 1–2 changes, no corpus substitution and no Stage 6+ implementation. | PASS |

**Handoff:** Stage 6 consumes CT/CO/SI, the impact record, risk candidates and Stage 4 lifecycle/workflow evidence to design workflows and artifacts. Stage 7 settles verification/risk details; Stage 8 researches tools before command/skill boundaries are selected. Stage 5 blockers: none. Proceed to Stage 6 only after this stage's commit and exact remote verification.
