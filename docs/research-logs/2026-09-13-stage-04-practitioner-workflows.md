# Stage 4: Practitioner Workflow Research

This companion supplies the twelve real workflow types required by [Stage 4](2026-09-13-stage-04-professional-practice-challenge.md). Source IDs link to the main record's examined primary sources. The **documented practice** paragraph identifies what was actually researched. The eleven fields are **our engineering synthesis** for applying that mechanism within the accepted charter, informed also by Stage 3. They are not copied source procedures, reports of project execution, or claims that a private team was observed. Cheap and expensive are relative to the consuming project.

## W01 — Small feature change

Documented practice: Google's coherent-change guidance keeps review context and related verification with a working increment; NASA derives technical needs from the intended outcome (S22/S02). Neither supplies a universal size threshold.

- **Inputs:** Accepted feature intent, current behaviour, affected user/consumer and local conventions.
- **Working artefacts:** Bounded change description, relevant code, acceptance examples and focused diff.
- **Uncertainties:** Ambiguous defaults, overlooked callers and scope of shared behaviour.
- **Cheap checks:** Read the entry path and analogous implementation; inspect an acceptance example and focused test.
- **Commitment points:** Choosing externally visible behaviour; exposing the increment to consumers.
- **Review points:** Acceptance interpretation, shared-policy placement and final semantic diff.
- **Expensive checks:** Relevant integrated journey or supported-environment run when the feature crosses those boundaries.
- **Failure modes:** Happy-path-only implementation, duplicated rules, unrelated cleanup or omitted preservation.
- **Repair strategies:** Correct the responsible boundary; reduce unrelated scope; update the oracle only when intent warrants it.
- **Handoffs:** Explain the implemented delta, evidence and any unresolved product decision to the actual owner.
- **Quality criteria:** Accepted outcome works, valid existing behaviour remains and the change is understandable without hidden context.

## W02 — Bug fix

Documented practice: SRE troubleshooting develops and tests hypotheses; mitigation can precede full diagnosis (S12). Developer verification includes historical cases (S20 overview).

- **Inputs:** Failure report, affected revision/environment, expected behaviour and impact.
- **Working artefacts:** Reproduction or substantiated observations, competing hypotheses, cause explanation and regression case.
- **Uncertainties:** Whether the fault is code, data, configuration, environment or an incorrect expectation.
- **Cheap checks:** Compare expected/actual output, recent relevant changes and a focused failing case.
- **Commitment points:** Applying an operational mitigation or changing a supported behaviour.
- **Review points:** Evidence discriminating the cause; scope of repair and validity of the regression oracle.
- **Expensive checks:** Representative environment reproduction or integrated regression where local evidence cannot cover the mechanism.
- **Failure modes:** Suppressing the symptom, asserting the wrong oracle, hiding errors or overfitting one input.
- **Repair strategies:** Reopen the hypothesis; isolate the causal boundary; restore observability and retain a sensitive regression case.
- **Handoffs:** State mitigation versus permanent repair, actual results, remaining causal uncertainty and follow-up owner.
- **Quality criteria:** The relevant failure is eliminated for a defensible reason and affected valid obligations remain satisfied.

## W03 — Refactor

Documented practice: Fowler describes small behaviour-preserving transformations; Google separates substantial restructuring from behaviour changes while allowing small local cleanup (S23/S22).

- **Inputs:** Demonstrated change friction, current contracts, observation boundary and baseline evidence.
- **Working artefacts:** Preservation envelope, transformation sequence, focused diff and any necessary decision note.
- **Uncertainties:** Dynamic uses, reflection, error/timing behaviour and inadequacy of existing tests.
- **Cheap checks:** Trace consumers, inspect tool preview and run relevant baseline/after checks.
- **Commitment points:** Altering shared structure or interfaces on which other work depends.
- **Review points:** Whether the restructuring addresses the named pressure and remains behaviour-preserving.
- **Expensive checks:** Integration or representative runtime checks for dynamic boundaries not resolved statically.
- **Failure modes:** Hidden behaviour change, speculative abstraction, broken dependency direction or mass rename blind spots.
- **Repair strategies:** Revert the faulty transformation, restore a meaningful seam and split behaviour changes into explicit decisions.
- **Handoffs:** Explain changed structure, preserved contracts and evidence limits to maintainers.
- **Quality criteria:** Lower demonstrated change friction with preserved valid behaviour and proportionate complexity.

## W04 — API change

Documented practice: AIP-180 separately considers source, wire and semantic compatibility and recognises that consumer control changes obligations (S14).

- **Inputs:** Current interface, supported clients, accepted new need and compatibility policy.
- **Working artefacts:** Contract delta, old/new examples, consumer matrix and migration/deprecation note if needed.
- **Uncertainties:** Undocumented use, omitted-field defaults, generated clients and error semantics.
- **Cheap checks:** Inspect callers, schema diff and old-request/new-server boundary tests.
- **Commitment points:** Publishing a contract or ending a supported behaviour.
- **Review points:** Consumer impact and whether a superficially additive change alters meaning.
- **Expensive checks:** Supported client/runtime combinations or consumer-owned integration evidence.
- **Failure modes:** New required input, changed default, incompatible enum handling or silent semantic truncation.
- **Repair strategies:** Restore compatibility, add a justified adaptation/version path or stage consumer migration.
- **Handoffs:** Give consumers exact delta, compatibility evidence and action required under actual release policy.
- **Quality criteria:** Supported interactions remain valid or an authorised transition accounts for each affected participant.

## W05 — Database/schema change

Documented practice: GitLab's column-removal workflow accounts for cached schemas and old processes across releases; PostgreSQL documents transaction-specific limits (S11/S08).

- **Inputs:** Schema/data meaning, volume, supported application versions and allowed disruption.
- **Working artefacts:** Reader/writer map, intermediate states, migration script, reconciliation criteria and recovery plan.
- **Uncertainties:** Long-lived readers, hidden views, lock duration, bad historical data and reversal feasibility.
- **Cheap checks:** Inspect constraints/consumers; validate a small representative conversion and empty/invalid cases.
- **Commitment points:** Starting durable mutation, switching readers/writers and deleting information.
- **Review points:** Compatibility at every intermediate state, preservation of data meaning and recovery assumptions.
- **Expensive checks:** Migration/recovery rehearsal with representative volume, locks and mixed application versions.
- **Failure modes:** Destructive contraction too early, partial backfill, inconsistent dual writes or nonrecoverable loss.
- **Repair strategies:** Halt contraction, reconcile progress, resume idempotently where designed or perform an evidenced forward repair.
- **Handoffs:** Give operators and data owners the sequence, verification, stop conditions and exact remaining obligations.
- **Quality criteria:** Correct data and supported operation across the transition, with truthful recovery capability.

## W06 — Dependency upgrade

Documented practice: npm's frozen-install contract depends on lock/configuration consistency; SSDF preserves release/component evidence (S19/S06). This is an ecosystem example, not a package-manager choice.

- **Inputs:** Existing dependency purpose, resolved graph, target release notes/advisories and support policy.
- **Working artefacts:** Resolution/lock diff, affected API/configuration usage and compatibility evidence.
- **Uncertainties:** Transitive changes, install scripts, native builds, licensing/approval obligations and undocumented behaviour.
- **Cheap checks:** Inspect changelog and used interfaces, resolution diff, integrity metadata and targeted tests.
- **Commitment points:** Accepting a new trust/dependency boundary and releasing consumers against it.
- **Review points:** Why the upgrade is needed, effective configuration and unresolved breaking changes.
- **Expensive checks:** Clean installation/build on supported environments and integration with the actual upgraded component.
- **Failure modes:** Stale lock, accidental unrelated upgrade, phantom dependency, unsafe script or changed defaults.
- **Repair strategies:** Correct resolution/configuration, adapt a bounded caller or retain a supported version with explicit rationale.
- **Handoffs:** Record exact versions, compatibility/security findings and any required consumer/operator action.
- **Quality criteria:** The intended upgrade works reproducibly under stated inputs and respects trust and compatibility obligations.

## W07 — Security fix

Documented practice: SSDF links design/code findings, remediation and recurrence analysis; OWASP uses system-specific adversarial reasoning (S06/S15).

- **Inputs:** Validated finding, affected versions, protected assets, trust boundary and authorised remediation scope.
- **Working artefacts:** Minimal safe failure case, threat/control explanation, fix, sensitive-evidence handling and release notes as appropriate.
- **Uncertainties:** Exploit preconditions, sibling paths, bypasses, compatibility cost and residual risk.
- **Cheap checks:** Trace the trust boundary, inspect the control and run isolated negative/positive cases.
- **Commitment points:** Changing access policy, exposing sensitive evidence or releasing a security-sensitive change.
- **Review points:** Control correctness and whether specialist assessment or existing disclosure policy applies.
- **Expensive checks:** Relevant adversarial integration, fuzzing or specialist assessment where warranted by the mechanism.
- **Failure modes:** Pattern matching without understanding, bypass through another path, denied legitimate access or suppressed evidence.
- **Repair strategies:** Fix the responsible control, examine related paths and improve the detecting check/process.
- **Handoffs:** Supply affected scope, tested mitigation, residual risk and release/disclosure needs to their actual owners.
- **Quality criteria:** The identified boundary is enforced, valid use remains and claims match the assessment performed.

## W08 — Performance repair

Documented practice: USE investigates resource bottlenecks with explicit limitations; SRE monitoring distinguishes tails and failed requests (S13/S25).

- **Inputs:** Accepted workload/target, observed regression, baseline environment and resource limits.
- **Working artefacts:** Measurement method, profile/resource observations, causal hypothesis and comparable results.
- **Uncertainties:** Noise, warmup, workload drift, hidden contention and whether a fast error is masking failure.
- **Cheap checks:** Confirm comparable inputs, inspect a focused profile/query and check resource saturation/error signals.
- **Commitment points:** Trading memory/cost/correctness for speed or changing infrastructure assumptions.
- **Review points:** Whether the measured cause explains the symptom and the chosen trade-off meets real requirements.
- **Expensive checks:** Controlled representative load, tail-latency/resource measurement and sustained behaviour where relevant.
- **Failure modes:** Benchmark gaming, changed workload, average-only conclusions or optimisation that breaks semantics.
- **Repair strategies:** Correct the experiment, address the demonstrated bottleneck and rerun affected correctness/performance checks.
- **Handoffs:** Report conditions, baseline/candidate comparison, variability and operational implications.
- **Quality criteria:** The agreed workload improves under comparable conditions without unacceptable correctness or resource regressions.

## W09 — Concurrency repair

Documented practice: JLS §17.4.5 specifies Java visibility/order; PostgreSQL isolation specifies database anomalies and retries (S21/S08). Their guarantees are different.

- **Inputs:** Violated invariant/progress condition, participants, shared state and exact runtime semantics.
- **Working artefacts:** Legal interleaving trace, ownership/atomicity model, focused schedule case and repair reasoning.
- **Uncertainties:** Memory visibility, transaction scope, cancellation, starvation and other writers.
- **Cheap checks:** Write a minimal interleaving, inspect synchronisation/transaction boundaries and run a targeted reproducer.
- **Commitment points:** Selecting lock/atomicity/coordination semantics or changing public concurrency guarantees.
- **Review points:** Invariant preservation over all relevant actors and whether progress remains possible.
- **Expensive checks:** Appropriate race detection, controlled schedule exploration, stress or formal analysis for uncovered risk.
- **Failure modes:** Locking the wrong object, partial critical section, deadlock, duplicate retry effects or a test that merely gets lucky.
- **Repair strategies:** Correct the ownership/atomic boundary, reduce shared state or redesign the protocol with explicit assumptions.
- **Handoffs:** Explain the failing schedule, mechanism, checked conditions and unresolved runtime coverage.
- **Quality criteria:** The invariant and required progress have defensible evidence beyond one passing run.

## W10 — Legacy-system change

Documented practice: Preparatory refactoring can expose usable structure, while troubleshooting supplies effect observations (S23/S12); Stage 3 supplies the directly examined seam methods.

- **Inputs:** Authorised delta, existing deployment/code, known obligations and weak-feedback limitations.
- **Working artefacts:** Relevant context sketch, classified observed behaviour, conservative seam and preservation checks.
- **Uncertainties:** Hidden consumers, stale comments, nondeterminism and whether observed quirks are valid obligations.
- **Cheap checks:** Trace entry/effect paths, inspect history where available and characterise a relevant observation boundary.
- **Commitment points:** Changing dependencies or behaviour before adequate preservation evidence exists.
- **Review points:** Whether the seam affects semantics and which observations are accepted versus defective/unknown.
- **Expensive checks:** Representative runtime or integration evidence that substitutes cannot supply.
- **Failure modes:** Whole-system rewrite, legitimising a defect, an invasive harness or broad cleanup with no feedback.
- **Repair strategies:** Shrink the intervention, restore behaviour, improve the observation point and separate desired change from characterisation.
- **Handoffs:** Leave discovered context, preserved obligations, limitations and next safe action with maintainers.
- **Quality criteria:** The requested change works with credible preservation evidence and no speculative renovation.

## W11 — Cross-service change

Documented practice: AWS retry design, RabbitMQ ordering and etcd's distinct KV/watch guarantees expose concrete distributed boundaries (S10/S09/S17).

- **Inputs:** End-to-end obligation, service owners, contracts, version rollout and fault assumptions.
- **Working artefacts:** Interaction/state sketch, identity/retry policy, compatibility sequence and reconciliation checks.
- **Uncertainties:** Partial completion, stale reads, delayed/reordered messages and independent deployment timing.
- **Cheap checks:** Inspect contracts and enumerate one duplicate, missing-response and mixed-version case.
- **Commitment points:** Introducing a durable external effect, publishing a protocol or contracting old behaviour.
- **Review points:** End-to-end invariant, ownership of each effect and validity of claimed ordering/consistency.
- **Expensive checks:** Integrated failure injection, supported rollout combinations and recovery/reconciliation rehearsal.
- **Failure modes:** Exactly-once claims without an effect boundary, retry storms, stale decisions or incompatible rollout.
- **Repair strategies:** Correct identity/atomicity, add bounded reconciliation or change sequencing while retaining supported participants.
- **Handoffs:** Give each service/operator owner the contract, sequence, observations and remaining joint obligations.
- **Quality criteria:** The business invariant and required progress survive the stated failure and version conditions.

## W12 — Release preparation

Documented practice: DORA separates deployability from deployment; SSDF retains release evidence; GitLab demonstrates why transition steps need sequencing (S05/S06/S11).

- **Inputs:** Identified release candidate, target environment, accepted changes and applicable release authority/gates.
- **Working artefacts:** Evidence manifest, change/migration notes, configuration/dependency identity and recovery instructions.
- **Uncertainties:** Environment drift, untested packaging, data reversibility and unresolved operational ownership.
- **Cheap checks:** Check candidate identity, gate results, package contents and unresolved findings.
- **Commitment points:** Publishing an artifact, mutating durable data or exposing behaviour to users.
- **Review points:** Readiness evidence, transition/recovery feasibility and actual authorisation for the next action.
- **Expensive checks:** Clean consumer installation, representative release rehearsal and necessary integrated acceptance.
- **Failure modes:** Testing one artifact and shipping another, mistaking merge for deployment or claiming untested rollback.
- **Repair strategies:** Rebuild/reverify the affected candidate, fix packaging/transition and update readiness honestly.
- **Handoffs:** Deliver exact candidate, evidence, remaining limitations and actionable operating instructions.
- **Quality criteria:** Applicable gates pass for the actual candidate; authorised execution and its observed result are recorded separately.
