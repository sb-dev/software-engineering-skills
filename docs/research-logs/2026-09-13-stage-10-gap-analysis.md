# Stage 10: Evidenced Gap Analysis

**Stage:** 10 — Gap Analysis  
**Date:** 13 September 2026  
**Branch:** `feat/bootstrap-2`  
**Input commit:** `1a08a4528a6d7504289d0cf180054e0535831b7b`  
**Status:** Complete for gap classification and responsibility shortlists; implementation/evaluation remains unperformed.

## 1. Inputs, acceptance and classification

The complete [Stage 10 requirement](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#17-stage-10--gap-analysis) governs this stage. Inputs are the accepted [charter](2026-09-12-stage-01-project-goal-and-domain-boundary.md), Stage 4's [capability/failure model](2026-09-13-stage-04-professional-practice-challenge.md) and [twelve workflows](2026-09-13-stage-04-practitioner-workflows.md), Stage 5's [change/contracts/context model](2026-09-13-stage-05-change-contract-and-context-model.md), Stage 6's [workflow/artifacts](2026-09-13-stage-06-workflow-and-artefacts.md), Stage 7's [verification/risk policy](2026-09-13-stage-07-verification-risk-and-commitment.md), Stage 8's [landscape](2026-09-13-stage-08-capability-landscape.md) and [candidate records](2026-09-13-stage-08-candidate-evaluations.md), and Stage 9's [execution boundary](2026-09-13-stage-09-execution-layer.md). The original qualified book/professional findings are consumed through these accepted models, not replaced with generic skill listings.

Acceptance: explicitly test coverage of all **14 named gap areas**, classify coverage using **covered / partially covered / missing**, assess all **8 over-engineering candidates**, and produce the five required outputs: gap matrix, native shortlist, reused shortlist, deferred ideas and early over-engineering risks. Every proposed native responsibility must map to an evidenced gap. Re-read the governing section, inspect actual records, persist conformance, commit only this stage and verify remotely.

Coverage here means availability of the required capability in the **inspected landscape at the chosen Stage 9 boundary**. It is not an installation status, a comparison of model intelligence or a measured accuracy score:

- **Covered:** an existing tool/host provides the mechanical responsibility; compose it. Repository-specific configuration and execution verification still apply.
- **Partially covered:** relevant mechanisms exist, but an inspected policy conflict, missing decision boundary or insufficient evidence prevents adopting them as the complete project responsibility.
- **Missing:** a required project deliverable or integration proof is absent from the current repository/evidence. Lack of a selected implementation is not proof that no such solution exists anywhere.

The matrix contains the fourteen required areas plus six grouped execution surfaces so that covered mechanics remain visible. N01–N06 below are **responsibility groups**, not final skill names or an obligatory six-skill architecture. I01 is packaging/verification work, not a new generative engineering skill. Stage 11 chooses actual skill/command boundaries; later stages must prove implementation, examples, benchmarks and installation.

## 2. Gap matrix

The challenge witnesses are analytical cases based on accepted failure mechanisms and inspected sources. They are not executed tests or claims that a named agent actually failed on a benchmark. Each row states what a later implementation must demonstrate to close the gap.

| ID / required area | Coverage | Available evidence and analytical challenge | Remaining gap / disposition | Evidence that would close it |
|---|---|---|---|---|
| G01 — Brownfield repository understanding | partially covered | Stage 8 host reads/search and S27 Kafka inventory expose paths/config. Stage 4 F02/W10 and Stage 5 SI show that a runtime-selected consumer may be absent from a simple text/call search. | N01 chooses bounded context, traces effective runtime/data/configuration and distinguishes observed/inferred/unknown links. No universal graph justified. | On a fixture with a hidden configuration path, identify the affected consumer with source evidence and avoid claiming the rest of the repository is exhaustively understood. |
| G02 — Change-impact analysis | partially covered | S18 calculates caller-based blast radius; schema/search tools find shapes. A one-line policy change can affect all tenants without many callers (Stage 7 VP03). | N01/N02 relate CT/CO changes to exposed behaviour, data, deployment and uncertainty; counts alone are insufficient. | Identify material direct/indirect consumers, intentional delta and preserved obligations, including a small but high-consequence change. |
| G03 — Contract preservation | partially covered | D01/D03/D04 execute checks; S02 supplies test-first mechanics. Stage 4 F03/F04 and Stage 7 VP05 show a passing fake can omit a real uniqueness/compatibility constraint. | N01/N03/N04 define valid preservation and choose meaningful boundary evidence; do not freeze an identified defect as the contract. | Preserve supported neighbouring cases, expose a deliberately weak fake/oracle, and verify the actual contract boundary where needed. |
| G04 — Smallest-responsible-change behaviour | partially covered | S09 begins from line-count smells/pattern application; S02 demands deletion of implementation written first. Both conflict with accepted C08/C18 and F13. | N02/N03 justify a coherent local change and necessary restructuring, preserve valid work and exclude unrelated cleanup. | Deliver the requested delta without opportunistic rewrite; explain any multi-file scope by contract/mechanism rather than convenience or file size. |
| G05 — Risk-sensitive verification selection | partially covered | Runners/scanners/coverage exist (D01–D11). Stage 7 contrasts local delimiter repair with durable mixed-version migration; neither a universal suite nor a green unit test answers both. | N02/N04 choose oracle, scope, escalation and stopping by obligation/risk and mandatory project gates. | Different evidence selections for bounded and consequential cases, correct treatment of unavailable/skipped checks and no weakened gate to obtain a pass. |
| G06 — Root-cause diagnosis | partially covered | S01 provides reproduction and hypotheses but prohibits fixes before completed root-cause work and infers architecture problems after a fixed count. S29 and accepted Stage 4 S12 distinguish restoration from deeper diagnosis. | N05 uses discriminating observations, records causal confidence and separates authorised containment from permanent repair. | Diagnose product versus environment/oracle failure, test a relevant hypothesis, label mitigation honestly and demonstrate regression sensitivity for causal repair. |
| G07 — Repair scope discipline | partially covered | Editing/Git mechanics exist. S01's patch-count threshold and S02's deletion rule do not implement Stage 6 RR1–RR9's correction at the owning decision. | N05/N03 preserve valid work, change the cause and refresh only affected evidence; intent/design/test/tool failures have different repair routes. | A failed check routes to its actual cause without broad restart, unrelated edits, repeated blind retries or lost user changes. |
| G08 — Architecture-quality evaluation | partially covered | S07 supplies layered/hexagonal/DDD patterns, but every-layer abstraction and a framework-free unit test do not establish fit. Stage 4 C04/C05/C18 requires alternatives and local costs. | N02/N04 compare current/local/structural options and assess separate quality dimensions against actual constraints. | Explain a defensible trade-off, including rejecting an unnecessary abstraction; name consequences/assumptions and evidence beyond pattern conformance. |
| G09 — Test-quality evaluation | partially covered | D03/D04 run tests; D06 measures coverage; D11 mutates code. S02's every-method mandate does not establish oracle fidelity. Stage 4 F04 and Stage 7 VP05 supply contrary mechanisms. | N03/N04 assess expected behaviour, sensitivity, substitution limits and useful retention; generated tests must not mirror the implementation. | A relevant defective candidate is detected for the intended reason; weak assertions/fakes and untested material boundaries are identified, not masked by coverage. |
| G10 — Compatibility reasoning | partially covered | S08 offers versioning/deprecation; S21/S27/S28 offer data/schema guidance. Stage 4 S08/S11/S14 and W04/W05/W11 require semantic and intermediate-state reasoning beyond shape compatibility. | N01/N02/N03/N04/N06 handle supported old/new readers/writers/clients, historical data, rollout order and irreversible effects. | A transition handles required mixed states, preserves intended semantics and identifies a real recovery/forward-repair path; a clean schema diff is not sufficient. |
| G11 — Security integration | partially covered | S18/S25 and D07/D08 provide review/scanning with language, rule and provider limits. S18's LOW UI/logging category and S25's limited language set cannot establish cross-cutting C19. | N01–N06 apply assets/trust/control reasoning where affected, compose specialist guidance and retain residual-risk ownership. | Legitimate and forbidden paths, config/dependency provenance and relevant threat assumptions are tested/reviewed; clean scanning and generic recommendations are not treated as security acceptance. |
| G12 — Performance/reliability reasoning | partially covered | S10/S19–S21/S29 and D09/D10 provide useful mechanisms. S21's payment-before-transaction example lacks a duplicate/reconciliation protocol and advertises unmeasured gains; accepted F06–F08/C11–C13 expose the gap. | N02/N04/N05/N06 connect workload, tails/resources, concurrency/progress, unknown completion and recovery while preserving correctness. | Comparable workload evidence and relevant fault/interleaving cases support a bounded claim; no unsupported speedup, retry or rollback guarantee. |
| G13 — Project-native tool discovery | partially covered | Stage 8 tool interfaces and host access are available. S04's inspected generic setup can assume a package manager; actual PATH inventory lacks several listed executables. Stage 9 requires wrappers/config/CI semantics. | N01/N03/N04 discover actual commands and prerequisites, preserve profiles and distinguish missing tools from passing checks. | Work in an external repository with nondefault wrapper/module/config; select the real check, retain scope and accurately handle missing prerequisites without inventing a universal runner. |
| G14 — External installability | missing | Current repository contains accepted research/design only, no implemented distributable skill set or install evidence. Upstream plugin instructions and provider documentation are useful precedents, not this project's success. | I01 must package the selected skills/references/helpers, document real consumption and verify external installation/discovery with the required later evidence. This is a mandatory bootstrap gap, not a deferred optional idea. | Actual independent consumer installation/discovery and representative invocation with exact source/version, dependencies, observed output and limitations under the later stage's criteria. |
| G15 — Compiler/build execution | covered | D01/D05 document native compilation/build; Stage 9 X01 assigns it to the toolchain. | Reuse R01; native work is target/evidence selection, not compiler construction. | Repository command execution validates the actual selected candidate/configuration when the task requires it. |
| G16 — Formatting/lint execution | covered | D02 exposes mechanical format/lint commands and config; Stage 9 X02/X03. | Reuse R02; no parallel style engine. | Check actual paths/rules and inspect any automatic edits. |
| G17 — Tests/coverage/mutation mechanics | covered | D03/D04/D06/D11 provide executable interfaces; Stage 9 X04/X05. | Reuse R03; test adequacy remains G05/G09. | Real selected cases/reports and error/skip interpretation; tooling existence alone is not a product pass. |
| G18 — Analysis/scanning/profiling/benchmark mechanics | covered | D07–D10 provide configured execution/measurement; Stage 9 X06–X09. | Reuse R04/R05; security/performance interpretation remains G11/G12. | Actual target/rule/database/workload identity and bounded reports where applicable. |
| G19 — Git/package/container/CI mechanics | covered | D12–D15 and observed remote commits; Stage 9 X10–X13. | Reuse R06/R07; no CI/runtime/registry engine. | Actual action/candidate/result and environment/authority evidence, especially for remote effects. |
| G20 — Host read/search/edit/shell access | covered | P01 operations observed; P02 capabilities documented but not executed. | Reuse R08; one host suffices for core execution, with optional adapters and serial operation. | Host-specific invocation/discovery evidence; no universal model/provider quality claim. |

Matrix totals: **13 partially covered, 1 missing, 6 covered**. All fourteen specifically requested areas are G01–G14. A partially covered area is not grounds to discard reusable mechanics; it identifies the narrow decision that remains. A covered mechanical area does not waive its runtime prerequisites or the later install/evaluation gate.

## 3. Native-capability shortlist

| ID / responsibility group | Evidenced gaps | Production responsibility to retain | Smallest initial form and explicit boundary |
|---|---|---|---|
| N01 — Understand intent, context and contracts | G01/G02/G03/G10/G11/G13 | Reconstruct affected system and accepted meaning, classify change, identify consumers/obligations/unknowns and actual authority | Scoped instructions and optional relevant references; read/search existing tools. No whole-system index, product strategy or new project database. |
| N02 — Choose approach, scope and evidence | G02/G04/G05/G08/G10/G11/G12 | Compare feasible options, choose coherent scope/design effort and plan risk-relevant verification/transition | A concise plan/decision when useful; no mandatory architecture template, numeric risk score or planning runtime. |
| N03 — Implement and preserve with feedback | G03/G04/G07/G09/G10/G11/G13 | Make coherent changes, establish trustworthy feedback where weak, preserve valid behaviour and use native commands | Editing plus relevant tests/config; no compiler/test-runner recreation or deletion of valid work to force TDD. |
| N04 — Verify and review engineering quality | G03/G05/G08/G09/G10/G11/G12/G13 | Interpret candidate-specific evidence, evaluate contracts/structure/tests and separate defects from preference | Actual tool results plus semantic review; no universal coverage/quality score or compulsory second agent. |
| N05 — Diagnose and perform bounded repair | G06/G07/G11/G12 | Separate symptom, mitigation and cause; run discriminating observations; route local correction and recheck affected evidence | Reuse logs/reproducer/profiler/patch tools; no fixed retry count proving architecture failure or speculative whole-system rewrite. |
| N06 — Prepare transitions and actionable completion | G10/G11/G12 plus G05 evidence freshness | Confirm artifact/transition/recovery/authority, preserve rationale and hand off an accurate requested outcome | Existing release/migration/ADR records and authorised actions; no platform operations takeover, automatic publication or repeated approval when authority exists. |

**I01 — External packaging and installation verification:** closes G14 through the required repository structure, skill/reference discovery, documented dependencies and actual external validation. It is implementation/distribution work, not a seventh catch-all skill. Its absence does not imply the project needs a provider registry, package manager or custom installer service. First inspect and use a standard host/repository consumption path.

### 3.1 Trace every accepted capability to the shortlist

| Capability | Owning shortlist group(s) | Gap evidence |
|---|---|---|
| C01 — Intent and authority | N01/N06 | G02/G04; Stage 8 S05/S26 confirmation-policy mismatch and accepted standing-authority boundary |
| C02 — System context | N01 | G01/G02/G13 |
| C03 — Assessable obligations | N01/N02 | G02/G03/G05/G10 |
| C04 — Architectural alternatives | N02 | G08 |
| C05 — Structural/quality risk | N02/N04 | G02/G04/G08 |
| C06 — Feedback in weak tests | N03 | G03/G09 |
| C07 — Oracles and verification | N02/N04 | G05/G09 |
| C08 — Coherent change | N03 | G03/G04/G07 |
| C09 — Diagnosis and repair | N05 | G06/G07 |
| C10 — API/state evolution | N01/N02/N03/N04/N06 | G03/G10 |
| C11 — Concurrency/progress | N02/N03/N04/N05 | G12 |
| C12 — Faults/recovery | N02/N04/N05/N06 | G12 |
| C13 — Performance repair | N02/N04/N05 | G12 |
| C14 — Dependency/configuration | N01/N03/N04/N06 | G11/G13 |
| C15 — Engineering review | N04 | G05/G08/G09/G11 |
| C16 — Migration/release preparation | N02/N06 | G10/G11/G12 |
| C17 — Rationale and handoff | N02/N06 | G08/G10/G12 and Stage 4 F11/F12: stale evidence/inactionable receiving state |
| C18 — Proportionate effort | N01–N06 | G04/G05/G07/G08 and Stage 4 F13 |
| C19 — Security/supply chain | N01–N06 | G11, refined by G02/G10/G12/G13 |

No native responsibility is justified solely by a language, provider, popular skill name or opportunity to automate. Cross-cutting capabilities such as C18/C19 refine each group's decisions; this table does not require duplicate policy in six files. Stage 11 must choose one canonical home for shared rules and avoid overlapping triggers.

## 4. Reused-capability shortlist

| ID / reused surface | Stage 8 candidates | Consumption decision | Boundary retained by native intelligence |
|---|---|---|---|
| R01 — Compiler/build | D01/D05 or actual equivalent | Use repository wrapper/version/config/targets; no default replacement | G02/G05/G13 scope and sufficiency |
| R02 — Formatter/linter | D02 or actual equivalent | Use existing check/fix policy and changed-file scope | Behavioural preservation and justified automatic changes |
| R03 — Test/coverage/mutation execution | D03/D04/D06/D11 or actual equivalent | Run selected meaningful checks with proper environment; mutation only for an adequacy question | G03/G05/G09 oracle, fidelity and escalation |
| R04 — Static/security/dependency scanning | D07/D08 or actual equivalent | Preserve rule/database/target versions and report limits; no mandatory account-backed platform | G11 threat/control/repair interpretation |
| R05 — Profiling/benchmarking | D09/D10 or actual equivalent | Use representative workload and existing harness; retain raw measurement context | G12 comparability, causal account, correctness and recovery |
| R06 — Git/package operations | D14/D15; available authorised GitHub interface | Preserve workspace, source/lock/version and action identity; use standing authority | G04/G07/G13 scope and effective candidate/trust |
| R07 — Containers/CI | D12/D13 or actual equivalent | Consume repository environment and required jobs; no runtime/service provisioning by default | G05/G10/G12 readiness, provenance and recovery |
| R08 — Host access and optional references | P01; P02 as an untested alternative; scoped S references | Use available read/search/edit/shell. Optional S01/S02/S03/S06/S24 require the Stage 8 ADAPT work before activation; other references retain their stated limits | N01–N06 own decisions; subagents and browser integrations are optional capabilities, not architecture prerequisites |

The five ADAPT candidates are not five mandatory copied dependencies. Their useful mechanisms can also be expressed through the project's independently sourced professional model without copying an entire upstream workflow. If a concrete adapter/reference is included later, retain its licence, source and evaluation evidence. S09 and S23 remain rejected for their specific default roles. G14 still requires this project's actual external installation even if every upstream candidate has installation documentation.

## 5. Deferred ideas and early over-engineering risks

All eight suggested capabilities are placed in **follow-up research**, outside the first core proof. None is needed to demonstrate a bounded change using the Stage 9 execution boundary. Deferral applies to these optional architectures, not required examples, packs, specifications, benchmarks or installation evidence in later bootstrap stages.

| ID / deferred idea | Why it is not currently required | Existing bounded alternative | Evidence required to reopen |
|---|---|---|---|
| OE01 — Universal dependency graph | No demonstrated need for exhaustive cross-runtime edges; dynamic/config/data links make false completeness dangerous | Relevant path/consumer investigation with source-linked unknowns (N01) | Repeated evaluated failures specifically caused by missing graph queries that bounded inspection cannot handle at acceptable cost |
| OE02 — Universal AST framework | Reimplements parser/type ecosystem and expands language maintenance before proving change quality | Compiler, language tooling, repository search and a narrow helper if necessary | A concrete repeated semantic transformation with inadequate existing parser/refactoring support and a measured benefit from a bounded language-specific first step |
| OE03 — Cross-language semantic index | Requires language/runtime integration and freshness management unrelated to many local tasks | Module/API/schema/config inspection and existing language/server indexes | An evaluated multi-language fixture where available tools fail a defined relationship query; compare a scoped index against simpler remedies |
| OE04 — Custom CI engine | Existing CI already executes jobs and exposes evidence; scheduling adds service/operational ownership | Current repository CI and host/GitHub access | A required execution behaviour impossible with available CI/adapters and a justified operating owner; convenience alone is insufficient |
| OE05 — Universal build/test runner | Hides toolchain-specific flags/profiles/fixtures and becomes an adapter framework | Discover native wrappers/commands; preserve result semantics | Repeated concrete composition failure across real repositories that a small helper cannot address; evaluate without weakening native gates |
| OE06 — Central provider registry | Couples core workflow to provider inventory/version/account machinery | Host capability discovery and small optional installation notes | Actual supported-host distribution needs demonstrate a versioned mapping that cannot remain simple metadata/documentation |
| OE07 — Shared agent runtime | Duplicates host scheduling/context/permissions and makes serial work harder | One available host, optional authorised subagents, durable artifacts | Measured task/evaluation requirement unavailable in supported hosts, with explicit lifecycle/permission ownership and a simpler alternative comparison |
| OE08 — Persistent software project graph | Introduces storage/schema/freshness costs before bounded context has failed | Repository-native artifacts and refreshed relevant inspection | Long-lived multi-task use demonstrates recurring lost knowledge that canonical notes/versioned links cannot solve; define staleness and disposal first |

### 5.1 Immediate design risks to control

| Risk | Evidence in this analysis | Required control in subsequent design |
|---|---|---|
| Turn the capability model into one skill per row | N01–N06 and C01–C19 overlap intentionally | Package by distinct user/workflow outcome; share cross-cutting references rather than duplicate policy or force an exact count |
| Overstate gap evidence as model incompetence | Source review finds policy/coverage limits; no comparative execution yet | Keep the baseline and actual later benchmark; a coherent design still needs effectiveness evidence |
| Treat every researched ecosystem as a required core pack | Stage 8's twelve categories are discovery examples | Stage 12 must justify pack boundaries and reuse; no automatic twelve-pack backlog |
| Confuse tool availability with product correctness | G15–G20 are covered mechanically while G03/G05/G09 remain partial | Interpret actual oracle/scope/candidate evidence and preserve unavailable/inconclusive status |
| Solve installability with a platform | G14 lacks a distributable project/evidence, not a registry service | Use standard host/repository consumption first, then execute the specified external gate |
| Import upstream ceremony and overwrite valid work | S01/S02/S09/S24/S26 expose process conflicts | Use standing authority, preserve scope, and explicitly review an adaptation before activation |
| Hide optional deferral inside a mandatory later requirement | OE ideas are optional; G14 and later required outputs are not | Keep every bootstrap gate intact; cannot mark examples, comparison or installation complete from this analysis |

## 6. Exit review and conformance

The original Stage 10 section was re-read and the actual output checked. The substance review verified each required gap against a concrete accepted failure mechanism or an inspected Stage 8 policy/interface, then traced the residual decision to a shortlist. It did not count filenames as implementation or assign empirical pass/fail to unexecuted cases.

| Requirement | Evidence | Verification | Result |
|---|---|---|---|
| Consume accepted workflow and available-capability evidence | Section 1; Stage 8 S/D/P and Stage 9 O/X references | Accepted boundary preserved; scoped source findings remain qualified | PASS |
| Classify covered/partially covered/missing | G01–G20 and definitions | 6 covered, 13 partially covered, 1 missing; availability and execution proof separated | PASS |
| Test all specially named gap areas | G01–G14 | Fourteen explicit analytical challenge witnesses, residual gaps and closing evidence | PASS |
| Produce gap matrix | Section 2 | Each row includes status, evidence, disposition and demonstrable closure | PASS |
| Produce native shortlist | N01–N06 and I01 boundary | Six responsibility groups map to gaps; packaging remains required implementation work, not an invented skill | PASS |
| Produce reused shortlist | R01–R08 | Existing mechanical and host/reference surfaces retained; adaptations not falsely marked installed | PASS |
| Produce deferred ideas | OE01–OE08 | All eight suggestions moved to follow-up research with a concrete reopening condition | PASS |
| Produce early over-engineering risks | Section 5.1 | Scope, duplication, provider/platform, evidence and mandatory-gate risks tied to findings | PASS |
| Exit: every proposed native responsibility maps to an evidenced gap | Section 3 and C01–C19 trace table | All nineteen accepted capability candidates accounted for; no proposed core mechanism justified merely by popularity or technical appeal | PASS |
| Persist truthful research and individual stage boundary | This record and index | Analytical cases labelled; no implementation, installation or benchmark success invented | PASS |

**Handoff:** Stage 11 chooses skill and command boundaries from the N/C gap trace and R execution surface. No Stage 10 blocker requires user input. Continue after this stage's commit and exact remote verification; later mandatory outputs and execution remain authorised.
