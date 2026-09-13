# Stage 4: Professional-Practice Challenge

**Stage:** 4 — Challenge: Broader Professional Software-Engineering Research  
**Date:** 13 September 2026  
**Branch:** `feat/bootstrap-2`  
**Input commit:** `76e53a180a88baca7e6bbdfb0f6e0da41310523b`  
**Status:** Research complete; conformance review below records the stage gate.

## 1. Inputs, questions and method

The governing input is [bootstrap Stage 4](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#11-stage-4--challenge-broader-professional-software-engineering-research). Accepted inputs are the complete [Stage 1 charter](2026-09-12-stage-01-project-goal-and-domain-boundary.md), [Stage 2 coverage/corpus decision](2026-09-13-stage-02-knowledge-coverage-and-five-book-corpus.md), and [Stage 3 extraction](2026-09-13-stage-03-five-book-extraction-and-reconciliation.md). Their scope, twenty knowledge dimensions, 42 findings, eighteen capabilities and twelve research questions are retained as traceable inputs. No accepted Stage 1–2 file or corpus member changes.

The two research questions are whether the book methods are defensible under stated conditions, and which responsibilities the corpus leaves insufficiently grounded. The acceptance checklist is: inspect SWEBOK V4; investigate all sixteen named practice areas; assess all 42 findings, including contrary evidence; research all twelve workflow types with all eleven required fields; produce all nine outputs; inspect substance and conformance; commit this stage alone and verify remotely. Stage 4 requires research, not execution of its candidate workflows. No performance, benchmark, installation or production result is claimed.

The research used direct primary documentation, original practitioner accounts and primary empirical studies where available. Search results were leads, not substitutes for reading. First-party practice is evidence of a method in use, not proof of a universal causal benefit. Current product contracts were checked directly; they are not claims about an uninspected deployment. The source register gives actual examination scope. The workflow companion distinguishes documented practice from our proposed adaptations.

The user has explicitly reaffirmed authorisation for all remaining stages and instructed continued execution. After the remote gate this stage hands directly to Stage 5; there is no new approval request or voluntary stopping boundary.

## 2. Professional research log and supporting/contrary evidence

All sources below were accessed on 13 September 2026. `N` means normative guidance, `S` a formal or product specification, `P` primary practitioner experience, and `E` empirical observation. These types are distinct, not a ranking. Source scope is deliberately narrower than a claim to have read every linked work. Conclusions elsewhere identified as synthesis combine these observations with the accepted charter and book findings.

| ID and source | Actual examination | Evidence retained and limits |
|---|---|---|
| S01 — [IEEE Computer Society, SWEBOK V4](https://ieeecs-media.computer.org/media/education/swebok/swebok-v4.pdf) | Official PDF cover and contents across PDF pp. 1, 6–24; map only. Cover identifies v4.0a, released August 2026. | N: Coverage map across eighteen knowledge areas. This resolves the earlier landing-page access gap. Contents are not evidence that every chapter or referenced standard was examined. |
| S02 — [NASA, Technical Requirements Definition](https://www.nasa.gov/reference/4-2-technical-requirements-definition/) | Inputs and process activities, including stakeholder expectations, ConOps, rationale and validation. | N/P: Derive assessable technical needs iteratively, preserve rationale and validate them. Mission reviews and formal baselines are context-specific; they do not mandate a NASA process for small repositories. |
| S03 — [Google, Standard of Code Review](https://google.github.io/eng-practices/review/reviewer/standard.html) | Complete substantive guidance. | P: Review balances code health and progress; distinguish evidence from preference. It opposes perfection as a universal release condition. Institutional review authority does not transfer automatically. |
| S04 — [Bacchelli and Bird, Expectations, Outcomes, and Challenges of Modern Code Review](https://www.microsoft.com/en-us/research/publication/expectations-outcomes-and-challenges-of-modern-code-review/) | Original Microsoft publication record and abstract; ICSE 2013. Linked full paper was inaccessible. | E, limited: observations, interviews, surveys and comment analysis identify understanding and knowledge transfer alongside defect detection. Single organisation; abstract-only access does not establish effect size, detailed validity or causality. |
| S05 — [DORA, Continuous Delivery](https://dora.dev/capabilities/continuous-delivery/) | Definition, reported outcomes and technical-practice discussion. | P/research synthesis: Keep software deployable through feedback and automation; delivery differs from automatic deployment. Referenced reports were not independently examined. Reported associations do not prove the effect of adopting this project's workflow. |
| S06 — [NIST SSDF 1.1](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-218.pdf) | Tasks PS.3, PW.1, selected PW.2/PW.7, RV.2.2 and RV.3; publication status records. | N: Address design threats, code findings, release provenance and recurring vulnerability causes. Apply organisational risk decisions explicitly. [1.1 record](https://csrc.nist.gov/pubs/sp/800/218/final) is final; [1.2 record](https://csrc.nist.gov/pubs/sp/800/218/r1/ipd) remains an initial public draft as retrieved. This is not a compliance assessment. |
| S07 — [Fowler, Is High Quality Software Worth the Cost?](https://martinfowler.com/articles/is-quality-worth-cost.html) | Main internal-quality/economics argument and qualifications. | P: Internal quality affects later understanding and change costs. The illustrative graph and crossover estimate are practitioner reasoning, not measured universal ROI. Related DORA citations are not independent corroboration. |
| S08 — [PostgreSQL transaction isolation](https://www.postgresql.org/docs/current/transaction-iso.html) | Retrieved documentation identifies PostgreSQL 18; isolation table, Read Committed, Repeatable Read and Serializable sections. | S: Snapshot scope and anomalies depend on isolation; serialization failures require transaction-level retry. Sequence changes are not rolled back. This limits generic claims that transactions undo every side effect. No database was executed. |
| S09 — [RabbitMQ queues](https://www.rabbitmq.com/docs/queues) | Queue properties and message-ordering section. | S: A single channel's publication order has a narrower guarantee than global processing order. Multiple publishers/consumers, priorities and redelivery change the reasoning. This is direct counterevidence to unconditional FIFO assumptions. |
| S10 — [AWS, Making Retries Safe with Idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Caller identifiers, atomic token/effect recording, late requests and parameter mismatch. | P: Retry identity must express intent; identical parameters need not mean the same operation. Token lifetime and changed-parameter policy matter. Idempotency is a service contract, not a property conferred by a retry loop. |
| S11 — [GitLab, Avoiding Downtime in Migrations](https://docs.gitlab.com/development/database/avoiding_downtime_in_migrations/) | Dropping columns: ignore, later drop, later remove ignore rule; cached schema and views. | P/S: Real rollout instructions account for old processes and irreversible deletion across releases. The exact three-release Rails procedure is GitLab-specific, not a universal migration algorithm. |
| S12 — [Google SRE, Effective Troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Method, pitfalls, observations, reduction/bisection and recent changes. | P: Use discriminating hypotheses and evidence; urgent mitigation may precede complete causal analysis. A past cause or temporal correlation is a lead, not confirmation. Live interventions still require the operating context's authority. |
| S13 — [Gregg, USE Method](https://www.brendangregg.com/usemethod.html) | Definitions, resource inventory, metrics, interpretation and limits. | P: Examine utilisation, saturation and errors; averages can hide bursts. It is a bottleneck investigation aid, not a complete performance method or a guaranteed percentage improvement. |
| S14 — [Google AIP-180, Backwards Compatibility](https://google.aip.dev/180) | Guidance, source/wire/semantic compatibility, additions/removals and field changes. | N/S: Additive syntax can still break client meaning. Guidance assumes particular API consumers and protobuf/JSON; controlled consumers may have different obligations. Version labels alone do not prove compatibility. |
| S15 — [OWASP, Threat Modeling](https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html) | Overview, system modelling, trust/data boundaries and threat identification. | P: Update adversarial reasoning as the system changes. Method selection is contextual; a diagram or named mnemonic is not evidence that mitigations work. |
| S16 — [Tornhill and Borg, Code Red](https://arxiv.org/pdf/2203.04374) | 2022 author preprint: metrics, method, data, results, validity threats and conclusions, PDF pp. 2–9; abstract. | E: Repository mining of 39 proprietary projects associates a proprietary code-health metric with defects and issue-cycle time. Selection is undisclosed, groups imbalanced, time is inferred from issue/commit data, and causality is expressly uncertain. Useful support for investigating maintenance costs, not a refactoring ROI promise or tool mandate. |
| S17 — [etcd 3.6 API Guarantees](https://etcd.io/docs/v3.6/learning/api_guarantees/) | KV, watch, lease, completion and revision sections. | S: KV, serializable reads and watches have different guarantees. Watches lack a bounded delivery delay; timeout can leave completion unknown. Scope the guarantee by operation and history window; no end-to-end application guarantee follows automatically. |
| S18 — [Nygard, Documenting Architecture Decisions](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions) | Complete original ADR method and experience report. | P: Preserve significant decisions, context, status and consequences, including supersession. The small early experience report is not a controlled comparison; neither its folder nor document length is mandatory. |
| S19 — [npm 11, npm ci](https://docs.npmjs.com/cli/v11/commands/npm-ci/) | Description, lock mismatch, configuration, omission and script behaviour. Retrieved page labels 11.19.1 legacy. | S: Frozen dependency resolution requires a consistent lock and relevant configuration. A lock does not fix every environment input or establish component trust. This versioned example is not a recommendation to use legacy npm. |
| S20 — [NISTIR 8397, Developer Verification](https://nvlpubs.nist.gov/nistpubs/ir/2021/NIST.IR.8397.pdf) | Scope, sections 2.1–2.7 and 3.3; overview of remaining techniques. | N: Combine requirements-based, structural, historical and adversarial checks; tailor to the product. Its numeric coverage recommendation does not establish correctness; its coverage discussion explicitly limits high coverage. Specialised assurance and configuration are outside its full treatment. |
| S21 — [Java SE 25 Language Specification, chapter 17](https://docs.oracle.com/javase/specs/jls/se25/html/jls-17.html) | Reordering examples and §17.4.5 happens-before; associated race and synchronisation definitions. | S: Language memory semantics constrain valid concurrent observations. Correct synchronisation simplifies reasoning but does not establish application correctness. These rules are Java-specific, not portable guarantees for every language. |
| S22 — [Google, Small CLs](https://google.github.io/eng-practices/review/developer/small-cls.html) | Complete substantive guidance. | P: A change should be coherent, reviewable and leave a working system; separate large refactors and behaviour changes when useful. Conceptual size matters; illustrative line counts and Google's tests-for-every-change policy are not universal thresholds. |
| S23 — [Fowler, Refactoring](https://refactoring.com/) | Definition and day-to-day method; not the linked catalogue or book. | P: Refactoring preserves observable behaviour through small transformations; preparatory restructuring can enable a change. This does not establish safety of an arbitrary rename tool or require whole-system cleanup. |
| S24 — [W3C, WCAG 2.2](https://www.w3.org/TR/WCAG22/) | Introduction and §5.2.2–5.3 conformance scope. | N: Accessibility evaluation combines human and automated assessment; full pages and complete processes constrain conformance claims. This is a technical scope check, not legal advice or a claim of comprehensive accessibility expertise. |

Access limits: the SWEBOK landing page remained unavailable, but the public official PDF supplied the required map. The attempted ACM full text for Inozemtseva/Holmes's coverage study was inaccessible; it is not used as evidence. The Microsoft review paper is explicitly abstract-only. NISTIR 8397 supplies directly read testing guidance, without pretending to replace inaccessible empirical findings. No supplied book was substituted. No mandatory Stage 4 source remains missing.

### 2.1 Sixteen-area investigation using the SWEBOK map

Chapter numbers below refer to S01. The finding/decision columns are project synthesis, not chapter summaries. The source register provides the independent examination behind each decision.

| Area | SWEBOK chapters | Professional evidence | Consequence and boundary |
|---|---|---|---|
| Requirements and acceptance | 1 | S02, S14, S24 | Preserve meaning and assessability; numerical targets need a legitimate source. |
| Architecture and design | 2, 3 | S18, S15, S08 | Compare choices against actual qualities and failure mechanisms. No style wins by name. |
| Construction | 4 | S21, S22, S20 | Language semantics, coherent increments and appropriate verification belong together. |
| Code review | 5, 12, 14 | S03, S04, S22 | Review reasons and obligations, not just formatting or an approval token. |
| Testing | 5 | S20, S08, S24 | Distinguish oracle quality, scope and realism from counts. |
| Maintenance and evolution | 7 | S11, S14, S23 | Intermediate versions and retained obligations constrain change. |
| Configuration management | 8 | S19, S06 | Record effective inputs and artifact identity; dependency selection alone is insufficient. |
| Engineering process | 10 | S05, S22 | Use feedback and meaningful increments; no mandatory ceremony or branch count. |
| Quality | 12 | S16, S20, S24 | Separate quality dimensions and evidence; metrics are incomplete proxies. |
| Security | 13 | S06, S15, S20 | Integrate threats, verification, provenance and remediation; expert residual-risk decisions remain external. |
| CI / continuous delivery | 6, 8 | S05, S19 | Candidate identity and repeatable checks inform readiness; readiness and execution authority differ. |
| Observability and operability | 6 | S12, [SRE monitoring](https://sre.google/sre-book/monitoring-distributed-systems/) | Inspect user symptoms and internal causes; preserve actionable, proportionate telemetry. |
| Performance | 4, 6, 16 | S13, S21 | Measure the affected workload and contention; an average or intuition is insufficient. |
| Reliability | 6, 12 | S17, S10 | State completion/recovery semantics and test the relevant failure model. |
| Debugging and incident repair | 6, 16, 18 | S12, S06 | Separate urgent containment from evidence-backed permanent repair. |
| Technical debt and refactoring | 7, 15 | S07, S16, S23 | Prioritise demonstrated change friction; reject universal cleanup payback. |

Supplementary source **S25 — [Google SRE, Monitoring Distributed Systems](https://sre.google/sre-book/monitoring-distributed-systems/)**: directly examined definitions, symptoms/causes, black/white-box monitoring, four signals, tails and measurement granularity. P: internal telemetry and external observations answer different questions; noisy alerts and coarse averages can mislead. Its operational examples do not prescribe monitoring staffing, thresholds or a monitoring platform here.

### 2.2 Cross-source challenges

These are reasoning results, not additional experiments:

- The claim that review is valuable survives, but a generic defect-removal percentage does not. S03 describes desired judgement; S04 also observes knowledge outcomes. They do not establish that every extra reviewer improves a change.
- S20's coverage guidance is a useful challenge to a tests-only or metrics-only account. Adopt evidence suited to the obligation; reject treating its numerical recommendation as the bootstrap's universal pass threshold.
- S07 and S16 support taking maintainability seriously. Neither resolves local rewrite economics, the best abstraction size, or whether a specific cleanup will repay its cost. Those remain decision hypotheses.
- S08, S09 and S17 refute broad guarantees inferred from the labels transaction, FIFO and consistent. Evidence must name the operation, version, configuration and boundary. Repeated book advice cannot repair that missing scope.
- S11 shows why a smaller textual diff can have a larger operational risk. A safe intermediate state can legitimately require more changes than immediate deletion.
- S12 supports prompt mitigation while diagnosis continues. The governing root-cause-before-repair principle remains applicable to claiming a permanent fix; containment is recorded as containment, with residual uncertainty and existing operating authority.
- S02's formal process and S18's lightweight records are compatible when scaled by consequential decisions. Neither creates new approval requirements. Existing user and repository authority governs.

## 3. Dispositions of all material book findings

The IDs and original propositions are defined in Stage 3. `Supported finding` means the stated mechanism has corroboration within its scope, not empirical proof of this project's effectiveness. `Qualified/context-dependent method` retains a method with applicability limits. `Practical heuristic` remains a judgement aid. `Disputed claim`, `unresolved question` and `rejected idea` must not become unconditional production rules. The standing column describes evidence independently of that disposition; limitations in section 2 apply to every reference.

| Finding | Disposition | Evidential standing | Retained condition, counterexample or needed repair |
|---|---|---|---|
| G01 | Qualified/context-dependent method | P/E: S07, S16 | Lifetime costs matter; local ROI and future demand remain estimates. |
| G02 | Supported finding | P/E-limited: S03, S04 | Review includes understanding and decision quality; no universal reviewer quota. |
| G03 | Qualified/context-dependent method | P: S18 | Maintain consequential explanations canonically; extra prose is not evidence. |
| G04 | Qualified/context-dependent method | N/P: S20, S22 | Protect valid behaviour; correct a defective oracle when justified. |
| G05 | Qualified/context-dependent method | S/N: S08, S20 | A substitute can omit real constraints; choose its evidence boundary explicitly. |
| G06 | Supported finding | S/N: S19, S14 | Resolution and consumer compatibility are distinct continuing obligations. |
| G07 | Qualified/context-dependent method | P/S: S11, S14 | Supported intermediate states constrain deprecation; policy is local. |
| G08 | Supported finding | S/N: S19, S06 | Link verification to effective inputs and candidate identity. |
| G09 | Qualified/context-dependent method | P: S05, S11 | Readiness, deployment and exposure differ; rewrite benefit is unresolved. |
| L01 | Supported finding | P/N: S23, S14 | State intended delta and retained obligations before modifying them. |
| L02 | Qualified/context-dependent method | P/N: S22, S20 | Establish useful feedback before risky restructuring; no mandatory harness for trivial edits. |
| L03 | Practical heuristic | P/S: S23, S21 | A seam must preserve relevant semantics; language/runtime behaviour can defeat a naive cut. |
| L04 | Practical heuristic | P: S12 | Trace effects and useful observation points; static reachability can miss runtime paths. |
| L05 | Supported finding | N: S02, S20 | Observed output and accepted expectation are different evidence. |
| L06 | Qualified/context-dependent method | P/S: S12, S19 | Compilation aids understanding; unchanged code can fail under changed inputs or configuration. |
| A01 | Qualified/context-dependent method | P/S: S18, S08 | Compare feasible alternatives under actual obligations; invalid guarantees are not a trade-off preference. |
| A02 | Qualified/context-dependent method | S/P: S14, S17, S18 | Semantic/runtime dependencies matter beyond import structure. |
| A03 | Supported finding | N/P: S02, S13 | Give qualities conditions and evidence; inventing targets does not ground them. |
| A04 | Qualified/context-dependent method | N: S20 | A fitness check establishes its selected property, not architecture quality as a whole. |
| A05 | Practical heuristic | P/S: S25, S17 | Locate the actual quality boundary; module boundaries may not contain the failure. |
| A06 | Qualified/context-dependent method | P: S18; S: S09 | Keep significant rationale; reject treating a broker example as an unconditional FIFO contract. |
| A07 | Practical heuristic | N/P: S15, S18 | Risk ratings prompt investigation; ordinal values are not calibrated probabilities. |
| R01 | Supported finding | N: S02 | Distinguish need, proposed solution and accepted outcome. |
| R02 | Qualified/context-dependent method | N: S02; charter authority | Find affected stakeholders; do not manufacture universal approval ceremonies. |
| R03 | Qualified/context-dependent method | N/S: S02, S14 | Use goals/events/states where they expose ambiguity; no mandatory diagram set. |
| R04 | Supported finding | S: S08, S14 | Data meaning and producer/consumer expectations are part of the contract. |
| R05 | Qualified/context-dependent method | N/P: S02, S13 | Measure relevant qualities against sourced conditions, not invented thresholds. |
| R06 | Qualified/context-dependent method | N: S02, S20 | Analyse individual needs and interactions; a neat specification can still be wrong. |
| R07 | Practical heuristic | N/P: S02, S18 | Prototype to reduce a named uncertainty; priority remains with the actual decision owner. |
| R08 | Practical heuristic | P/N: S18, S02 | Use canonical terminology/rules when ambiguity warrants it; avoid duplicate authorities. |
| R09 | Supported finding | N: S02, S20, S24 | Verification evidence cannot alone establish stakeholder fitness or complete conformance. |
| R10 | Qualified/context-dependent method | P/S: S18, S14 | Track accepted changes and impact; recording reality does not approve a deviation. |
| D01 | Supported finding | S: S17, S21 | State fault, safety and progress assumptions; no universal failure model. |
| D02 | Qualified/context-dependent method | P: S13, S25 | Characterise workload and tails; speed in a different environment may not transfer. |
| D03 | Supported finding | S/P: S14, S11 | Account for mixed versions and historical state during evolution. |
| D04 | Qualified/context-dependent method | S: S17 | Visibility depends on read/replication semantics; name the actual API and settings. |
| D05 | Supported finding | S: S08, S17; P: S10 | Transaction scope and unknown completion require explicit reconciliation/retry policy. |
| D06 | Supported finding | S: S08, S21 | Check invariants across legal interleavings, not isolated statements alone. |
| D07 | Supported finding | S/P: S17, S10 | Timeout does not prove no effect; indiscriminate retries can duplicate effects. |
| D08 | Qualified/context-dependent method | S: S17; reasoning from fault model | Lease state alone is insufficient evidence of external-resource ownership. Resource fencing details remain implementation-specific. |
| D09 | Supported finding | S: S17, S09 | Separate operation consistency, causal/order requirements and delivery order. |
| D10 | Qualified/context-dependent method | S: S17 | Coordination progress depends on protocol/state assumptions; no complete consensus or 2PC implementation is validated here. |

Explicit narrower dispositions prevent apparent support from laundering an overclaim:

| Claim under challenge | Disposition | Standing and outcome |
|---|---|---|
| Bug fixes can never require changed test expectations | Rejected idea | Counterexample: authorised correction of a characterised defect; G04/L05/R09. |
| Unchanged source cannot be responsible for a new failure | Rejected idea | S12/S19 and changed-environment reasoning; retain context investigation. |
| FIFO queue implies global business completion order | Rejected idea | S09 supplies explicit ordering exceptions. |
| Green tests or high coverage establish all engineering quality | Rejected idea | S20/S24 and limited-oracle reasoning; preserve semantic review. |
| Refactoring, microservices or more delivery automation always repay their cost | Disputed claim | S07/S16/S05 do not establish universal causality; local evidence required. |
| One optimal test mix, document size, review count or risk score fits every repository | Unresolved question | No examined evidence establishes it; do not make it a core default. |
| A book's process advice grants permission to bypass a real owner or adds a new mandatory owner | Rejected idea | Accepted charter and user authority govern, independently of source prestige. |

## 4. Terminology and role/responsibility map

This is a project vocabulary, grounded in the distinctions above. It avoids claiming one discipline's terminology is universal.

| Term | Meaning for this project | Distinction that must survive |
|---|---|---|
| Requirement | A justified obligation on the outcome or system. | A proposal or observed behaviour need not be accepted. |
| Acceptance | Determination that the requested outcome satisfies the authorised need. | Verification of a written condition alone may not establish fitness. |
| Contract | Observable obligation between participants or over stored state. | Includes semantics and failures, not only types. |
| Preservation envelope | Valid obligations that the authorised change must retain. | Does not bless every pre-existing defect. |
| Verification | Evidence assessing a specified property. | Includes analysis/review; execution is one method. |
| Oracle | Basis for deciding whether an observed result is acceptable. | An assertion can encode the same mistake as the implementation. |
| Refactoring | Behaviour-preserving restructuring within a stated observation boundary. | A behaviour change needs its own justification. |
| Mitigation | Action reducing current harm or exposure. | Not automatically a confirmed permanent repair. |
| Diagnosis | Discrimination among possible causal explanations. | Correlation, recollection and a plausible story are insufficient alone. |
| Readiness | Evidence that a candidate meets applicable release conditions. | Does not itself authorise publication, exposure or operations. |
| Evidence standing | How a claim is supported and how far it transfers. | Separate from whether this project adopts the method. |
| Handoff | Transfer of a bounded decision/action with evidence and unresolved items. | A report is not proof that the receiver acted. |

| Responsibility holder | Software-engineering responsibility here | Receiving/supplied decision and boundary |
|---|---|---|
| Engineer/maintainer | Context, design, implementation, tests, diagnosis and change explanation. | Use actual repository ownership; no invented organisational role count. |
| Product/business owner | Supply goals, priority and domain meaning; engineer makes them assessable. | Engineer exposes ambiguity and feasibility, not business-policy invention. |
| UX/accessibility/design | Supply intended interaction and specialist criteria; engineer implements assessable behaviour. | Component checks do not certify a whole user journey (S24). |
| Reviewer/code owner | Assess obligations, reasoning and evidence under local rules. | Mechanical checks and substantive review have different scope (S03/S04). |
| Security/privacy specialist | Supply threat expertise and decide residual-risk exceptions when required. | Engineer owns routine secure construction and evidence, not blanket security certification. |
| QA/validation | Independently assess assembled-product behaviour where that role exists. | Engineer's local evidence remains necessary and bounded. |
| Platform/SRE/operator | Supply deployment environment, operational limits and authorised interventions. | Engineer prepares readiness/recovery evidence; live ownership remains external. |
| Data/ML/game/domain specialist | Supply semantic, statistical or domain-specific correctness criteria. | General engineering checks cannot decide model quality, game balance or data meaning. |
| Technical writing/research | Supply deeper domain evidence and user-facing communication when needed. | Engineer retains change rationale and technical handoff; this is not a general writing/research platform. |
| Orchestrator/Pactwright, if present | Coordinate cross-domain work and consuming-project records. | Optional composition; no runtime dependency or transfer of domain judgement. |

## 5. Twelve researched workflows

The [workflow companion](2026-09-13-stage-04-practitioner-workflows.md) records **twelve workflows × eleven fields = 132 populated fields**. Each names its primary practice source and separates the documented mechanism from the adapted procedure. These are research-derived lifecycle candidates, not reports of runs or observations of a private team. All include failure, repair and handoff, not just a happy-path sequence.

## 6. Gap analysis against the original boundary

The Stage 3 questions are closed as research decisions or explicitly bounded below. Bounded questions are not deferred mandatory Stage 4 work: their unresolved content is deliberately excluded from unconditional rules and assigned a future, already specified validation point. No new source substitution or scope reduction is proposed.

| Question | Evidence and resolution | Effect on model / remaining boundary |
|---|---|---|
| Q01 — Security/supply chain | S06/S15/S20 add threat, provenance and remediation duties. | Add explicit C19 below; specialist review and concrete tool controls remain contextual. |
| Q02 — Feedback/review/delivery effectiveness | S03–S05, S16, S22 support methods with observational/institutional limits. | Retain feedback and review; do not promise causal productivity gains. Stage 14 designs project evaluation. |
| Q03 — Rewrite economics | S07/S16 do not settle counterfactual ROI. | Unresolved per change: compare repair, gradual migration and rewrite against actual cost/risk. Never default to rewrite. |
| Q04 — Test design/adequacy | S20 gives independent black-box/structural/adversarial basis; S24 bounds conformance. | Strengthen C07; coverage and mutation sensitivity remain incomplete evidence. Concrete adequacy assessed in Stages 14/18. |
| Q05 — Debugging/performance/shared memory | S12/S13/S21 supply independent methods and semantic constraints. | Strengthen C09/C11/C13; language/runtime-specific details require exact applicable documentation. |
| Q06 — Operability/recovery | S25/S12/S17 separate symptoms, diagnosis and uncertain completion. | Strengthen C12/C16; no implicit live-operation authority. Recovery is a checked procedure, not a rollback slogan. |
| Q07 — Current products/protocols | S08/S09/S14/S17/S19 checked directly. | Old book defaults are not relied upon; verify deployed version/configuration before using a guarantee. |
| Q08 — Ordering/coordination | S09/S17 distinguish several guarantee boundaries. | Reject unconditional FIFO; lease fencing and coordination implementation correctness remain unproved until a concrete protocol is examined. |
| Q09 — Architecture/risk metrics | S16's validity limits, S18 and S20 resist metric substitution. | Keep risk reasons, alternatives and semantic review; no universal score. |
| Q10 — Proportionate requirements/docs | S02/S18/S22 expose both formal and lightweight practices. | Choose artifact depth from the decision and receiver, not a universal document quota. |
| Q11 — Broader ecosystems/specialists | S24/S21/S19 add web accessibility, language and build boundaries. | Web/mobile/desktop/CLI remain charter scope; specialised assurance requires receiving criteria. No claim of exhaustive ecosystem research. Stage 12 selects packs, Stage 13 examples. |
| Q12 — Authority/evidence integrity | S06/S18 and accepted charter support traceable state/decisions. | Preserve user authority and distinguish plans from actions. Exact provider capabilities are Stage 8 work, not a basis for the professional model. |

| Stage 1/2 knowledge dimensions | Coverage after challenge | Explicit bound |
|---|---|---|
| K01 requirements; K19 human decisions | S02/S18, C01/C03 | Product intent and specialist residual-risk decisions remain owned outside. |
| K02 architecture; K06 refactoring/debt; K18 economics | S07/S16/S18/S23, C04/C05/C18 | Local expected costs and trade-offs; no causal ROI guarantee. |
| K03 construction; K05 brownfield; K04 maintenance | S21/S22/S23/S11, C02/C06/C08 | Relevant language and deployment semantics must be checked. |
| K07 testing; K09 review | S20/S03/S04/S24, C07/C15 | Adequacy is obligation-specific; assembled-product assurance is separate. |
| K08 debugging; K13 performance/concurrency | S12/S13/S21/S08, C09/C11/C13 | Controlled observations and actual workload/fault assumptions required. |
| K10 APIs; K11 data/schema | S14/S11/S08, C10 | Consumer/data meaning and destructive-transition authority remain explicit. |
| K12 security; K17 configuration/dependencies | S06/S15/S19/S20, C14/C19 | No scanner, lockfile or provenance document alone proves security. |
| K14 reliability; K15 delivery; K16 observability | S05/S10/S17/S25, C12/C16 | Exact candidate, operating environment and recovery evidence constrain claims. |
| K20 documentation/handoff | S18/S06, C17 | Canonical, accessible records with accurate status; no universal knowledge platform. |

The sixteen-area map and all twenty dimensions support a broad engineering boundary without making every technique core. Common judgement belongs in the core candidate set; Java memory rules, PostgreSQL behaviour, accessibility conformance detail and broker configuration are specialisation/context material. Safety-critical, embedded, statistical and legal assurance remain specialist handoffs as accepted in Stage 1.

## 7. Software-change lifecycle candidates

These are synthesis for Stage 6 to test, not final commands or mandatory states.

| Candidate | Entry and working flow | Evidence/repair loops and completion |
|---|---|---|
| LC1 — Planned change | Accepted need → relevant context and obligations → alternatives where material → coherent implementation. | Choose checks before consequences; a failing check returns to the owning assumption/design/edit. Finish with assessed delta, preserved obligations and handoff. |
| LC2 — Failure-driven change | Symptom and impact → authorised containment if urgent → observation and competing hypotheses → discriminating check → causal repair. | New evidence can revise the hypothesis or reveal several causes. Recheck the original failure and affected obligations; distinguish mitigation from repair. |
| LC3 — Compatibility transition | Supported participants/state → intermediate-state plan → expand/adapt → migrate and verify → retire when justified. | A failed compatibility or reconciliation check stops contraction. Recovery may require a forward repair, not reversing a destructive action. |
| LC4 — Investigation/design-only | Decision needed → current constraints → bounded experiment or evidence review → alternatives and recommendation. | Do not fabricate implementation or acceptance evidence. Finish at the requested decision with unknowns and actionable handoff. |
| LC5 — Release preparation | Identified candidate and environment → applicable gates → migration/recovery/observability assessment → readiness decision. | Changed candidate invalidates affected evidence. Execute only already-authorised actions; record their actual outcome separately. |

Selection follows the problem; a small bug fix can use LC2 inside LC1, while a schema change adds LC3. These candidates share concepts without forcing every task through five workflows or requiring a graph runtime. The accepted cheap-to-expensive principle remains a risk-aware heuristic: a cheap irrelevant check cannot replace a costly necessary one.

## 8. Failure and repair taxonomy candidates

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

## 9. Evidence-quality model

For each consequential claim, retain: proposition; applicability/version; source or observation; method and oracle; identity of candidate/environment; result; uncertainty/counterevidence; decision; and receiving owner when relevant. A concise record can hold these fields; this stage does not prescribe a schema or platform.

| Evidence kind | Can support | Cannot establish alone |
|---|---|---|
| Accepted requirement/decision | The obligation and authority for a change. | That implementation meets it. |
| Specification/standard | Declared semantics or conditions of conformance. | Actual deployment behaviour or universal adoption. |
| Empirical study | Observed relationship within method/sample limits. | Universal causality or this project's benefit. |
| Practitioner account | An actionable mechanism and contextual experience. | A quantified effect transferable to every team. |
| Static/review evidence | Detected issues and bounded reasoning about structure/semantics. | Every runtime input, state or failure. |
| Executed check/experiment | Observed result for identified inputs and environment. | Untested obligations, different versions or unbiased oracle. |
| Operational observation | Actual system symptom/effect within instrumentation limits. | Causal attribution from correlation alone. |
| Synthesis/hypothesis | A reasoned candidate to evaluate. | An executed result or externally established fact. |

Assess **relevance, directness, independence, reproducibility, freshness, oracle quality, coverage and transfer limits** separately. Do not add them into an unexplained score. Repeated citations to one organisation or underlying study do not make independent replications. Distinguish missing evidence from negative evidence; unavailable tests from failing tests; a passing check from the larger conclusion. Label unresolved claims and select a disconfirming case before relying on them. Stale evidence is reassessed when its premises change.

## 10. Evidence-qualified capability model

This supersedes only the provisional evidential standing of Stage 3 capabilities. It neither creates skills nor selects providers. Each responsibility has a professional rationale independent of a particular book or coding system. Evaluation examples remain candidates.

| ID | Responsibility retained or strengthened | Independent basis | Conditional production/evaluation implication |
|---|---|---|---|
| C01 | Frame intent and actual authority. | S02/S18 + charter | Distinguish approved outcome from assumption; continue authorised work without invented gates. |
| C02 | Reconstruct relevant system context. | S12/S15/S19 | Trace affected paths, inputs and uncertainty; reveal a missed runtime dependency. |
| C03 | Specify assessable obligations. | S02/S14/S24 | Express acceptance, data and qualities; expose an unsupported target. |
| C04 | Compare feasible architectural alternatives. | S18/S08 | Include current design/local repair; explain decision and rejected alternatives. |
| C05 | Assess structural and quality risk. | S16/S18/S25 | Identify a concrete failure/change mechanism; do not substitute a metric verdict. |
| C06 | Establish feedback in weakly tested code. | S22/S23/S20 | Obtain enough trustworthy preservation evidence before consequential restructuring. |
| C07 | Select oracles and verification boundaries. | S20/S08/S24 | A relevant defect must be detectable; disclose untested qualities and substitute limits. |
| C08 | Implement a coherent authorised change. | S22/S21/S23 | Preserve valid obligations and separate material structural/behavioural decisions. |
| C09 | Diagnose and repair from discriminating evidence. | S12/S06 | Strengthened: track hypotheses, containment, causal confidence and regression evidence. |
| C10 | Evolve APIs and persistent state. | S14/S11/S08 | Check supported versions and intermediate states; do not assume easy rollback. |
| C11 | Protect concurrent invariants and progress. | S21/S08/S17 | Strengthened: distinguish language, database and distributed guarantees. |
| C12 | Reason about faults and recovery. | S10/S17/S25 | Strengthened: make completion, retry and recovery semantics explicit. |
| C13 | Repair measured performance problems. | S13/S25 | Strengthened: comparable workload, tails/resources and correctness remain visible. |
| C14 | Manage dependency/configuration change. | S19/S06 | Record effective resolution, trust and supported environment; a lock is incomplete evidence. |
| C15 | Review engineering quality. | S03/S04 | Assess obligations and reasoning; separate blocking defects from preference. |
| C16 | Prepare migrations and releases. | S11/S05/S06 | Link candidate, transition, recovery and readiness evidence to authorised action. |
| C17 | Preserve rationale and actionable handoff. | S18/S06 | Keep accurate status and canonical knowledge; receiver can identify what remains. |
| C18 | Allocate proportionate effort. | S07/S16/S22 | Reason about decision cost/risk; universal productivity/ROI claims remain excluded. |
| C19 | Integrate security and supply-chain reasoning. | S06/S15/S20 | New explicit cross-cutting responsibility: threats, controls, verification, provenance and repair, with specialist boundaries. |

Core candidates are the judgement responsibilities, not every source-specific technique. C19 applies across the lifecycle instead of becoming a final security pass. C09/C11/C12/C13 now have broader grounding than the corpus alone. Remaining uncertainty concerns implementation choices and measured effectiveness, not whether the professional responsibilities exist. The model deliberately contains no provider APIs, prompt format, orchestration runtime or prescribed technology stack.

## 11. Conformance review and handoff

The original Stage 4 section was reread and the main record plus companion inspected before the commit gate. The table records substantive checks, supplemented by an exact structural audit of IDs and workflow fields. No test suite is claimed for these research documents.

| Requirement | Evidence | Verification | Result |
|---|---|---|---|
| Consume complete requirements and accepted inputs | Section 1; unchanged Stage 1–3 identities | Reconstructed charter, corpus, findings, gaps and stage duties from repository records. | PASS |
| Answer defensibility and missing-responsibility questions | Sections 2–3, 6, 10 | Conditions and counterexamples retained; security made explicit; gaps bounded. | PASS |
| Use SWEBOK V4 as map | S01 and section 2.1 | Official V4-family PDF accessed; sixteen required areas mapped to chapters. | PASS |
| Investigate all sixteen areas | Section 2.1 and source register | Each has examined professional evidence and an explicit applicability decision. | PASS |
| Research all twelve workflows, all eleven fields each | Workflow companion W01–W12 | Twelve distinct types and 132 nonempty fields; source mechanism versus synthesis labelled. | PASS |
| Seek supporting/contrary evidence and current guarantees | Sections 2.2–3; S08/S09/S17/S19; SSDF status | Concrete counterexamples, empirical limits and version-sensitive boundaries checked. | PASS |
| Assess material book findings with separate standing/disposition | Section 3 | All 42 Stage 3 IDs exactly once; all five books represented; narrower rejected/unresolved readings explicit. | PASS |
| Produce professional-practice research log | Sections 1–2 | Actual read scope, source links, limits, method and decisions recorded. | PASS |
| Produce terminology and roles/responsibilities | Section 4 | Terms distinguish intent/evidence/authority; adjacent owners and handoffs retained. | PASS |
| Produce supporting and contrary evidence | Sections 2.2–3 | Support does not erase mechanism-specific counterevidence or limits. | PASS |
| Produce book-claim dispositions | Section 3 | 42 rows plus seven narrower claims; adoption and evidential standing separate. | PASS |
| Produce gap analysis against Stage 1 | Section 6 | All Q01–Q12 and K01–K20 accounted for; original specialist boundaries retained. | PASS |
| Produce lifecycle candidates | Section 7 | Planned, failure, transition, investigation and release flows include feedback/repair. | PASS |
| Produce failure/repair taxonomy | Section 8 | Thirteen mechanisms connect indication, repair and evidence. | PASS |
| Produce evidence-quality model | Section 9 | Evidence kinds, quality dimensions, freshness and inference limits explicit. | PASS |
| Produce evidence-qualified capability model | Section 10 | Nineteen responsibilities with independent professional basis and evaluation implications. | PASS |
| Exit: assess material claims, address/bound gaps, preserve unresolved questions | Sections 3, 6, 10 | No unresolved universal threshold, ROI or implementation guarantee promoted to core. | PASS |
| Exit: justify professional model independently of books/providers | Sections 2, 10 | Direct professional sources supply responsibility mechanisms; no provider architecture selected. | PASS |
| Preserve publication and stage boundaries | Intended three-file change set | Independent synthesis only; no private books/extracts; no later-stage implementation or fabricated runs. | PASS |

**Stage handoff:** Stage 5 consumes the qualified capability model, workflow records, lifecycle/failure candidates and unchanged charter. It must distinguish intended change from preserved contracts for every required change class and model the actual system context. Remaining Stage 4 blockers: none. Commit and remote-content verification are performed before Stage 5 begins.
