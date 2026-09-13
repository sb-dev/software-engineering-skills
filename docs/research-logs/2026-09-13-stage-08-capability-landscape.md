# Stage 8: Existing Skills, Tools and Provider Capability Landscape

**Stage:** 8 — Research Existing AI Skills, Tools and Providers  
**Date:** 13 September 2026  
**Branch:** `feat/bootstrap-2`  
**Input commit:** `b34bb36db446dfeea2b7820000bf08dfd8d692ff`  
**Status:** Complete for landscape research and composition decisions. No new skill, external installation or comparative benchmark is claimed.

## 1. Inputs, acceptance and research method

The complete [Stage 8 requirement](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#15-stage-8--research-existing-ai-skills-tools-and-providers) governs this stage. Accepted inputs are the [charter](2026-09-12-stage-01-project-goal-and-domain-boundary.md), [coverage/corpus](2026-09-13-stage-02-knowledge-coverage-and-five-book-corpus.md), [five-book extraction](2026-09-13-stage-03-five-book-extraction-and-reconciliation.md), [professional challenge/capabilities](2026-09-13-stage-04-professional-practice-challenge.md) and [practitioner workflows](2026-09-13-stage-04-practitioner-workflows.md), [change/contracts/context model](2026-09-13-stage-05-change-contract-and-context-model.md), [workflow/artifact model](2026-09-13-stage-06-workflow-and-artefacts.md), and [verification/risk/commitment policy](2026-09-13-stage-07-verification-risk-and-commitment.md). The nineteen accepted C01–C19 responsibilities are candidates for production intelligence, not nineteen predetermined skills.

Acceptance: investigate all **13 general skill areas**, all **12 named ecosystem examples**, all **16 deterministic-tool categories**, and all **9 provider capability areas**; evaluate every selected candidate on the **13 specified fields**; produce a capability landscape, dependency map, reuse decisions and justified project-owned gaps. Inspect the real records against the original stage, commit only this stage, and verify the remote branch and exact files. Stage 8 requires research/assessment, not installation or a generated-code benchmark; later execution gates remain binding.

Research used primary repositories, actual instruction files, selected supporting rules and official provider/tool documentation. GitHub repository metadata and full, non-truncated trees identified candidates. For the original nine skill repositories, the default-branch references were separately resolved before reading revision-pinned files. Confluent and Cassandra repositories were found through targeted Kafka/Cassandra searches and their full trees and files were inspected. The exact read scope is in each candidate record: a complete primary instruction, a named supporting rule, or a bounded prefix covering the relevant policy. This is not a claim that every file in a large marketplace was read.

The [46 candidate records](2026-09-13-stage-08-candidate-evaluations.md) contain all 598 required field entries. Records S01–S29 assess individual skills, commands, instruction files, agents or a named process; they are not all interchangeable Agent Skills. D01–D15 assess executable tools; P01–P02 assess hosts. Repository recency and publisher identity are useful maintenance signals, not production validation. Source metadata saying no licence was not silently converted into permission: per-skill licences were inspected for Anthropic/OpenAI; Vercel's selected files declare MIT but unresolved distribution notices keep them at REFERENCE. The research copies no third-party skill implementation or supplied book into this repository.

Two outdated tool repository addresses redirected: `nedbat/coveragepy` now points to `coveragepy/coveragepy`, and `containers/podman` to `podman-container-tools/podman`. The current canonical sources were resolved through official project documentation and inspected. The moved-address API response was not treated as a successful content read. Codex documentation URLs redirected to current ChatGPT Learn pages; substantive HTML sections were read after markdown fetches failed. Search snippets and navigation-only responses were not accepted as findings.

## 2. Capability landscape

### 2.1 General engineering skills: all thirteen areas

| Area | Inspected candidates | Reuse finding and residual responsibility |
|---|---|---|
| Software engineering | S01–S05; Superpowers README workflow/install sections | Existing processes already combine planning, construction, review and completion. Keep their useful mechanisms as comparisons; do not embed a competing mandatory lifecycle. |
| Architecture | S07, S13–S15 | Patterns and ecosystem options exist. Native value is deciding whether a pattern is justified by the actual change and constraints. |
| Code review | S03, S18, S25 | Review prompts can accept a diff and return findings. The project must supply obligations, evidence identity, risk and honest reviewer provenance. |
| Systematic debugging | S01, S29 | Reproduction, hypotheses, resource/outlier comparison are reusable. Mitigation, causal confidence and bounded repair need consistent project treatment. |
| Refactoring | S02, S07, S09 | Existing TDD and cleanup instructions are available; S09's fixed line thresholds/pattern agenda are rejected as the default. Preserve valid behaviour and choose locally justified scope. |
| TDD / testing | S02, S06, D03/D04/D06/D11 | Compose sensitive checks and real runners. A universal TDD mandate, coverage percentage or screenshot is not verification adequacy. |
| Security review | S18, S25, D07/D08 | Specialist prompts and scanners are reusable. Threat/control reasoning, version/coverage limits and residual-risk ownership remain explicit. |
| Performance engineering | S10, S19–S21, S29, D09/D10 | Reuse profiling and scoped platform guidance. Choose representative load and measure accepted budgets while preserving correctness. |
| API design | S08, S27 | Shapes and schema inventory have useful references. Business semantics, compatibility and unknown completion need engineering interpretation. |
| Database design | S21–S23, S28 | Stronger database-specific starting points exist, but claims about indexing, cost and storage migration need challenge. No one SQL/NoSQL rule set is universal. |
| CI/CD | S11, S24, D13 | Reuse workflow execution and failure-log access. Connect exact candidate, transition and recovery to the requested boundary. |
| Git / worktrees | S04, D15 | Native Git/host mechanics are sufficient; no project Git engine is justified. Inspect existing isolation and preserve unrelated work. |
| Requirements/spec-driven development | S05, S08, S27 | Consume accepted specifications, models and examples from existing systems. The native layer translates them into assessable change/preservation obligations without becoming the product owner. |

### 2.2 Ecosystem skills: all twelve research examples

These are research results, not a commitment to implement twelve packs. A large catalogue with an agent named after a language is not evidence of high-quality execution in that language.

| Ecosystem | Inspected source and scope | Suitability decision for this project |
|---|---|---|
| TypeScript / Node.js | S12 primary instructions; S08 API guidance; D01 compiler | Reference existing Node patterns; use repository compiler/scripts. Check runtime input and existing framework rather than treating types as runtime assurance. |
| Java / Spring Boot | S13 capability catalogue; S26 existing-app versus scaffold branch; D05 build | References identify testing/profiling/integration choices. Version-sensitive Java/Spring semantics must be checked; a model frontmatter pin is not required by the core. |
| Scala | S14 capability catalogue | Reference effect/runtime and JVM concerns. Do not require a rewrite into a different effect stack or claim tested agent competence. |
| Python | S10 performance; S25 security routing; D02/D03/D06/D09/D11 | Reuse language-native tools and relevant references. Testing, profiling and mutation remain conditional on the actual obligation. |
| Go | S15 concurrency/performance catalogue; S25 security routing | Reference cancellation/lifetime/race concerns and discover existing Go tooling. No blanket microservice/architecture prescription. |
| Rust | S16 primary instructions | Useful bounded Tokio guidance; preserve current executor/features and verify cancellation/error paths. Simulated sample networking is not production evidence. |
| React / React Native | S19/S20 primary excerpts and two full rules | Reference web request isolation and mobile list performance with version/workload checks. Do not install a new list or image library merely to comply with a rule. |
| Kubernetes | S17 primary instructions; S11 rollout examples; D12 containers | Reference configuration considerations and compose current validators/runtime. Authorised engineering configuration work does not imply cluster mutation authority. |
| Kafka | S26/S27 inspected requirements, environment and schema-discovery workflows | Dedicated skills exist. Their Confluent-specific serializers, infrastructure and confirmation gates are not universal Kafka requirements. Retain producer/consumer, ordering and duplicate-effect obligations. |
| SQL / PostgreSQL | S21 instruction plus index/lock rules; Stage 4 S08/S11 | Reference query/lock mechanisms but reject unsupported fixed gains and missing external-effect reconciliation. Use actual plans, version and migration states. |
| MongoDB | S22 full DBA instruction | Useful discovery/specialist lead, insufficient as a complete engineering skill. Do not install an IDE extension or administer a cluster without task need. |
| Cassandra | S28/S29 version/query/diagnostic sections; S23 conversion exclusions | Dedicated Cassandra modelling/diagnosis material exists. S23 is rejected as generic coverage because it changes storage and excludes important Cassandra/data-migration behaviour. |

### 2.3 Deterministic execution: all sixteen categories

The named executables are researched examples, not an obligatory installation list. If a repository already uses an adequate alternative, discover and invoke it. This includes native compiler/test/build commands in ecosystems whose examples below use a different language.

| Category | Candidate | Discovery evidence in a consuming repository | Result to retain and interpret |
|---|---|---|---|
| Compiler / typechecker | D01 TypeScript | Manifest/lock, tsconfig/project references, wrapper and CI script | Version, config, selected files/projects, exit status and diagnostics; runtime semantics remain outside. |
| Formatter | D02 Ruff | pyproject/config, pre-commit/CI and existing formatting command | Check versus mutation mode, paths, rules and diff; no behavioural verdict. |
| Linter | D02 Ruff | Enabled/ignored rules, target language, script scope | Actual findings and exclusions; distinguish missing configuration from a pass. |
| Unit/integration/E2E runner | D03 pytest; D04 Playwright | Test config, fixtures, markers/projects, dependency services and CI | Collected/run/skipped cases, oracle, environment, artifacts and meaningful failures. |
| Build tool | D05 Maven | Wrapper, POM/reactor/profiles, JDK and CI lifecycle | Artifact identity and actual phases/modules/plugins executed. |
| Coverage tool | D06 Coverage.py | Source/exclusions, branch/subprocess settings, existing thresholds | Coverage scope/denominator and reports; not the quality of assertions. |
| Static analyser | D07 Semgrep | Local rule config, language support, changed/full scan selection | Rule/version, findings, suppressions and unsupported/unscanned surfaces. |
| Security scanner | D08 Trivy; D07 configured rules | Target kind, input identity, policy and sensitive output handling | Concrete findings, rule/database state and analysis limits. |
| Dependency scanner | D08 Trivy | Manifest/lock/SBOM/image inventory and database freshness | Resolved component findings and scope; reachability/exploitability need further assessment. |
| Profiler | D09 py-spy | Existing profiler script, runtime/PID, workload and privileges | Sampling window/settings and traces; distinguish observation from cause. |
| Benchmark runner | D10 hyperfine | Versioned workload, preparation/warmup/repetitions and accepted budget | Raw samples/export, environment and comparison limits. |
| Mutation tester | D11 mutmut | Source/test scope, fork capability, config and baseline | Killed/surviving/equivalent/invalid/timed-out cases; no automatic quality threshold. |
| Container tooling | D12 Podman | Existing image/build/compose scripts, digests, volumes/ports and cleanup | Image/runtime identity, startup/readiness and cleanup result. |
| CI tooling | D13 GitHub Actions | Triggers, required/reusable jobs, permissions, runner and action pins | Exact revision/run/job identity and actual logs/status, including missing jobs. |
| Package manager | D14 npm | Node/package versions, manifests/locks, registry and lifecycle policy | Effective resolution/install status and lock delta; execution/registry effects remain visible. |
| Version control | D15 Git | Current worktree/branch/status, base/candidate, remote and authority | Precise diff/commit/ref evidence; database/external effects do not roll back with Git. |

### 2.4 Current provider capabilities: all nine areas

P01 and P02 contain their full evaluation records and official sources. **Observed** means an operation actually occurred in this bootstrap, **documented** means an inspected primary source describes it, **exposed** means a tool interface exists in this session, and **unmeasured** means no competence claim. A capability may be documented but unavailable to a particular account, client, environment or policy.

| Capability | Codex / current Work host (P01) | Claude Code (P02) | Portable composition requirement |
|---|---|---|---|
| Repository inspection | Observed local file reads and GitHub repository/file reads. | Documented codebase reads and read-only Explore; not run here. | Accept bounded evidence with file/revision provenance; expose missing material. |
| Code editing | Observed apply_patch/Python file creation. | Documented multi-file edits; not run here. | Review actual diff and preserve accepted/user work. |
| Shell execution | Observed bash/Python commands; terminal docs inspected. | Documented command execution and host-specific shell prerequisites. | Carry working directory, command, prerequisites, permissions and result. |
| Test execution | Shell capability exists; prior-stage structural checks executed. No Stage 8 generated-product test claimed. | Official overview shows running tests; repository runner required. | Execute actual repository checks and inspect their output, not a provider assertion. |
| Code search | Observed rg/file search and GitHub reads. | Documented read-only code-search agent capability. | Bound search by paths/symbols and follow runtime/config references; no assumed complete graph. |
| GitHub interaction | Observed Git Data tree/commit/ref writes and exact remote verification. | Overview documents Git/PR workflows and GitHub Actions integration; not run here. | Credentials/allowed operations vary; no core dependency on gh or one connector. |
| Browser interaction | Browser interfaces exposed; not exercised in Stage 8. Web source retrieval is not browser interaction. | Chrome docs describe connected extension, navigation and site permissions; not run here. | Discover available browser/test mode and relevant authority; keep observed UI evidence distinct from claims. |
| Long-context repository reasoning | Available generative context/retrieval; official docs discuss context limits and progressive skill loading. Accuracy unmeasured. | Overview claims codebase understanding; subagent docs separate contexts. Accuracy unmeasured. | Retrieve relevant facts incrementally, preserve durable obligations/evidence and acknowledge omissions. No minimum model window or whole-repo comprehension guarantee. |
| Parallel subagents | Exposed and documented; not invoked because this session has no explicit delegation instruction. | Documented separate contexts/tools/permissions; not invoked. | Optional acceleration only when authorised/available; same workflow must work serially. Separate threads are not proof of independent review. |

The active environment PATH probe found Git, Node/npm/npx, Python, Java and rg. It did not find gh, pytest, Ruff, tsc, Go, Rust/Cargo, Maven, sbt, Docker/Podman, Codex CLI or Claude CLI. This only reports PATH lookup, not exhaustive installed-package discovery or inability to install. No private credentials were inspected. The current host's GitHub tools already satisfy authorised remote commit operations despite gh and a local clone being absent.

## 3. Candidate dependency map and reuse decisions

The dependency direction is **engineering responsibility → needed capability → discovered tool/optional reference → observed evidence**. Provider adapters execute actions; they do not redefine intent, contracts or verification adequacy. The map is logical composition, not a universal build/test API or workflow runtime.

| Workflow responsibility | Candidate composition | Required information at the boundary | Dependency decision |
|---|---|---|---|
| WF1 intent and obligations | Existing user/issue/spec artifacts; S05 as comparison | Accepted source, intended delta, preservation conditions and actual authority | No mandatory spec process. Consume existing sources and own technical clarification. |
| WF2 relevant system context | Host file/search/GitHub tools, D15; S12–S17/S22/S26–S29 as relevant references | Revision, paths, effective config, consumers, observed versus inferred links and unknowns | Use available host mechanics; load only task-relevant ecosystem material. |
| WF3 alternatives and verification design | S07/S08/S10/S18/S21 references; S02 only through reviewed adaptation | Feasible options, invariants, failure modes, selected oracle/check and escalation trigger | Native judgement remains; no architecture or test-first framework dependency. |
| WF4 implementation and feedback | Host editing/shell, D01–D05/D14/D15; S01/S06 adapted only when needed | Coherent scope, exact command/config, actual result and failure classification | Existing repository execution first; do not replace a working toolchain. |
| WF5 evidence and review | D06–D11/D13; S03/S24 adapted; S18/S25 references | Candidate identity, evidence scope/limits, substantive findings and disposition | No mandatory second agent, scanner platform or metric verdict. |
| WF6 release/handoff | D12–D15 and existing release system; S11/S27 references | Artifact/transition/authority, recovery state, remaining actions and receiver | Readiness and execution remain distinct; no forced live deployment. |

The exact inventory disposition is **16 USE, 5 ADAPT, 23 REFERENCE, 2 REJECT**. The USE set is fifteen existing-tool candidates plus the already available host; it creates no package installation backlog. ADAPT is S01/S02/S03/S06/S24, each with a concrete policy or host mismatch recorded. No adapted copy has been implemented at this stage. REFERENCE candidates can inform a future pack only after the relevant instructions, dependencies, version scope and evaluation are reviewed. The two rejected defaults are S09's metric/pattern-driven cleanup and S23 as general Cassandra coverage.

### 3.1 Rules for consuming an optional dependency

1. Find a task-specific need using accepted intent, affected contracts and risk. A matching language name alone does not justify loading a large marketplace or installing a plugin.
2. Inspect the exact selected version, supporting files, installation effects and licence. Pin the reviewed source when shipping or testing an integration; a moving branch is a discovery source, not reproducible dependency identity.
3. Resolve conflicting instructions before invocation. Preserve user/repository authority, bounded inspection, coherent scope and actual evidence. Do not silently activate a reference that imposes another lifecycle, deletes valid work or demands unnecessary confirmations.
4. Prefer a repository-native executable for mechanics. Read its wrapper/config/CI command, check prerequisites and choose the right scope. Use the existing selected tool rather than the example brand in this inventory.
5. Capture actual output and limits, then let the owning engineering responsibility interpret it. A tool failure, unavailable capability, skipped case and product failure have different meanings.
6. Evaluate before claiming a new integration works. Update review is scoped to changed assumptions and relevant gates; do not infer production confidence from downloads, stars, provider name or a recent push.

## 4. Gaps requiring project-owned intelligence

For every accepted candidate responsibility, the table names an existing composition that could reduce native work, then identifies the remaining decision that the inspected capability does not solve. These are justifications for ownership, not final skill names. Stage 9 selects the boundary; Stage 11 later decides packaging. A gap can be addressed by concise instructions/reference routing rather than new executable code.

| Capability | Existing alternative to writing it ourselves | Remaining project-owned intelligence and why composition alone is insufficient |
|---|---|---|
| C01 — Intent and actual authority | S05 specification workflow; existing issue/request; host interaction | Determine which outcome and action are already authorised, what is assumed and which clarification is material. Inspected upstream confirmation gates would stop fully authorised work. |
| C02 — Relevant system context | Host search/read, D15, S27 inventory and ecosystem references | Decide which runtime/config/data/consumer paths matter and when uncertainty is sufficient to proceed. Search returns matches, not an adequate system model. |
| C03 — Assessable obligations | Existing specification, S05/S08 schema/API patterns | Translate intended change plus preserved behaviour into observable criteria; reject unsupported targets. Schemas/style rules do not settle business meaning or quality budgets. |
| C04 — Architectural alternatives | S07 patterns and ecosystem agents | Compare current design, local repair and structural options against actual constraints/costs. A catalogue cannot establish that another layer/service is justified. |
| C05 — Structural and quality risk | S09 smell catalogue, D07 analysis, source/history | Relate structure to concrete failure/change mechanisms and separate dimensions. Fixed line counts, caller counts or pattern conformity are inadequate risk verdicts. |
| C06 — Feedback in weakly tested code | S02 adapted method, D03/D04/D06/D11 | Choose seams, characterization and preservation evidence without canonising the reported bug or destructively restarting. Existing tools execute checks but do not select trustworthy boundaries. |
| C07 — Oracles and verification boundaries | Runners, coverage/mutation/scanning, S06 | Choose a check sensitive to the relevant defect, know what a substitute omits and escalate for uncovered risk. A green suite or coverage count can miss the obligation entirely. |
| C08 — Coherent authorised change | Host editor, compiler/build, D15 worktrees, ecosystem references | Preserve valid work and unaffected obligations while implementing the smallest coherent approach. Editors and refactoring catalogues cannot determine legitimate scope. |
| C09 — Evidence-based diagnosis/repair | S01 adapted hypotheses; S29; profilers/log tools | Distinguish containment from causal repair, discriminate hypotheses, classify environment/oracle/product failure and choose bounded correction. No fixed number of failed edits proves an architectural cause. |
| C10 — API and persistent-state evolution | S08/S21/S27/S28 and existing schema/test tools | Check semantic compatibility, historical state, old/new participants and intermediate deployment states. Shape validation or a migration script does not establish a safe transition. |
| C11 — Concurrent invariants/progress | S15/S16/S19/S21 references; language/race/transaction checks | State invariant, scheduling/atomicity assumptions and progress/cancellation obligations across the actual boundary. Separate language, database and distributed guarantees; stress success is bounded evidence. |
| C12 — Faults and recovery | S11/S26/S29 plus diagnostics and runtime tools | Reason about unknown completion, duplicate effects, timeout/retry and external reconciliation. Short transactions and retries can make correctness worse without effect ownership. |
| C13 — Measured performance repair | S10/S19–S21, D09/D10 | Choose representative workload and comparable measurements, preserve correctness and assess tails/resource trade-offs. Generic speedup claims and hotspot lists are not an accepted outcome. |
| C14 — Dependency/configuration change | D05/D08/D14 and existing lock/install scripts | Determine effective resolution, supported environments, trust and runtime effects. A lockfile, install success or vulnerability report covers only part of the change. |
| C15 — Engineering review | S03 adapted review, S18/S25, static tools | Review actual obligations and trade-offs, distinguish blocking defects from preferences and invalidate stale conclusions. Another agent or generated report does not independently establish quality. |
| C16 — Migrations and releases | S11/S27 and repository CI/release tooling | Prepare candidate-specific transition, readiness, recovery and authorised action sequence. Passing CI does not imply deployed state, complete data migration or recoverable external effects. |
| C17 — Rationale and actionable handoff | Existing issue/ADR/release systems, tool reports | Preserve significant decisions with canonical source/status and identify what the receiver must do. Automatic report creation can duplicate or misstate truth. |
| C18 — Proportionate effort | Existing small-change/review methods, focused tool selection | Choose enough inspection, design, evidence and documentation for consequence/uncertainty. None of the inspected universal mandates establishes an appropriate cost/benefit threshold. |
| C19 — Security and supply-chain reasoning | S18/S25, D07/D08 and specialist handoff | Link actual assets/trust boundaries to controls, negative/positive checks, provenance and bounded remediation. Scanners and generic best practices neither accept residual risk nor prove security. |

This leaves a deliberately small type of native work: context-sensitive production decisions and the artifacts that carry their evidence. It does not justify writing a compiler, test runner, scanner, profiler, package manager, Git implementation, provider runtime or universal dependency graph. Existing skills remain useful scoped inputs where their assumptions fit; they do not own the whole project process.

## 5. Source challenge examples and limits

The source review changed candidate dispositions rather than merely collecting links:

- S01/S02 exposed a conflict between rigid root-cause/TDD mandates and accepted containment, preservation and proportionate evidence. Retain useful diagnostic/test sensitivity mechanisms only through a compatible adaptation.
- S08's broad POST/idempotency statement conflicts with the accepted caller-token API mechanism in Stage 4 S10. API style is not a substitute for operation semantics.
- S21's lock example moves a payment outside a transaction without supplying a duplicate/reconciliation protocol. Stage 3 DDIA and Stage 4 retry/transaction evidence make that omission material; no claim is made that the example itself was executed or that the entire skill lacks other guidance.
- S19 supplies a concrete request-state leak mechanism with bounded safe exceptions, whereas S20's universal short-list virtualisation goes beyond measured need. The same publisher is not one uniform quality verdict.
- S26 requires an extra confirmation even when requirements are fully specified, while S29 allows immediate restoration followed by deeper diagnosis. These are actual process differences to reconcile, not reasons to interrupt this authorised bootstrap.
- S23's explicit data/LWT/batch exclusions make it unsuitable as general Cassandra coverage. Targeted searches found S28/S29 instead; neither is claimed to have passed an execution benchmark here.

No generated-code quality, installation, cross-provider comparison, performance gain, scanner precision or production deployment has been measured in this stage. These are honest limits of a completed research task, not deferred mandatory Stage 8 work. Later stages must execute their own required gates before any stronger claim.

## 6. Conformance review and handoff

The governing Stage 8 section was re-read after producing the records. Verification checks the following substantive mappings and counts, not filenames alone.

| Requirement | Evidence | Verification | Result |
|---|---|---|---|
| Accepted inputs and sequential prerequisite | Section 1; exact Stage 7 input commit and linked accepted models | C01–C19 and WF1–WF6 preserve Stage 4/6/7 boundaries; no prior-stage rewrite | PASS |
| General Agent Skill research | Section 2.1; S01–S29 actual instruction scopes | All 13 named areas mapped; policy conflicts assessed | PASS |
| Major ecosystem research | Section 2.2; named primary sources and supporting rules | All 12 named examples covered; research categories not predefined packs | PASS |
| Repository-native deterministic tools | Section 2.3; D01–D15 | All 16 categories include discovery inputs and interpreted outputs | PASS |
| Current provider capabilities | Section 2.4; P01/P02; primary docs and actual host observations | All 9 areas assessed; documented/exposed/observed/unmeasured kept distinct | PASS |
| Every candidate's evaluation record | Companion records S01–S29, D01–D15, P01–P02 | 46 unique candidates × 13 required fields = 598 nonempty entries | PASS |
| Capability landscape | Sections 2.1–2.4 | Includes all four search categories and bounded source suitability | PASS |
| Candidate dependency map | Section 3 | Each WF responsibility maps optional references/executables and boundary information | PASS |
| Reuse decisions | Companion and section 3 | 16 USE, 5 ADAPT, 23 REFERENCE, 2 REJECT; installation/activation meaning explicit | PASS |
| Gaps requiring owned intelligence | Section 4 | All 19 accepted capability candidates have an existing alternative and residual justification | PASS |
| Exit: justify native capability against composition | Section 4 plus source challenges | Every proposed ownership is a decision the inspected tool/reference does not establish; no duplicate execution engine justified | PASS |
| Durable research record and truthful evidence | Both Stage 8 files and progress index | Revision/source/read-scope/maintenance/licence limits recorded; no supplied books or third-party code included | PASS |

**Handoff:** Stage 9 can choose the execution layer using these evaluated alternatives. No Stage 8 blocker requires user input. All remaining bootstrap stages remain authorised and execution continues after this stage's commit and remote verification.
