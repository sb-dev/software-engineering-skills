# Stage 14: Evaluation, Benchmarks and Regression Design

**Date:** 13 September 2026  
**Input commit:** `032ee9fefa9693c66870972ba9c78d19349f7c96`  
**Status:** Complete for evaluation design. The domain benchmark and behavioural runs are not yet implemented or executed.

## Inputs and acceptance

Read the complete [Stage 14 requirement](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#21-stage-14--design-evals-benchmarks-and-regression-fixtures), accepted [capabilities](2026-09-13-stage-04-professional-practice-challenge.md), [workflow/evidence](2026-09-13-stage-06-workflow-and-artefacts.md), [verification/risk](2026-09-13-stage-07-verification-risk-and-commitment.md), [execution decision](2026-09-13-stage-09-execution-layer.md), [twelve command contracts](2026-09-13-stage-11-command-contracts.md), [fifteen examples](2026-09-13-stage-13-progressive-examples.md), both [data](2026-09-13-stage-12-data-migration-p5-profile.md) and [event](2026-09-13-stage-12-reliable-event-processing-p5-profile.md) P5 profiles and the [authoring contract](2026-09-13-stage-12-pack-authoring-contract.md).

Acceptance: define all ten evaluation layers; deterministic candidates and all ten behavioural responsibilities; twelve separate quality dimensions; reproducible fixtures and independent oracles; the full regression loop; investigate all five proposed test-quality techniques; connect every implemented pack to P5 acceptance and differential/reuse/install evidence. Make failures of code, process and quality independently observable. Persist this design plus the per-example oracle companion; execution remains required in the implementation stages.

## Evaluation layers and ownership

A layer selects a kind of evidence, not a compulsory runtime state or sequence. A correct assessment that finds a defect is a successful evaluation with a failed product obligation. A tool/setup failure is neither product correctness nor a successful assessment of unseen behaviour. No universal software quality score is produced.

| Layer | Cases / inputs | Oracle and recorded result | Owning repair / acceptance boundary |
|---|---|---|---|
| EV01 deterministic repository validation | RC01–RC11 below; actual source and package candidates | Native exit/output, contract checks, permitted file surface and local resource resolution | Repository/package/setup defect; does not certify model behaviour |
| EV02 command conformance | CC01–CC12 plus folded modes | Direct raw task/repository; verify each command's nine contract fields, actual mutations, failure and authority treatment | Repair relevant local skill guidance or command resource; do not require a dispatcher |
| EV03 skill orchestration | OR01–OR08 below | Actual chosen scope, resource loading, independent installation and authorised continuation | Trigger/routing/role-boundary defect; orchestration is observable agent work, not filename presence |
| EV04 functional correctness | FC01–FC15, pack showcase/reuse | Independent executable contract checks through actual bindings | Correct source/contract/oracle at its owning boundary; multiple implementations permitted |
| EV05 engineering quality | Q01–Q12 | Evidence-grounded semantic findings with assessed/unassessed status per dimension | Bounded quality repair; preference is separate from material defect |
| EV06 preservation/root cause/repair | PR01–PR07 and reference failures | Baseline versus candidate, causal experiment, regression sensitivity, narrow repair and fresh evidence | Context/intent/oracle/product/environment/evidence route, preserving valid work |
| EV07 pack activation/fidelity | DMC01–14, EPC01–15, AW01–08 | P5 traits/defects, stronger instructions, actual local resources and specialised decisions | Pack/core/authoring guidance or implementation according to cause |
| EV08 core-versus-pack differential | DF01–DF04 | Four substantive tasks, each independently produced in two comparable arms; dimensions and deviations retained | Null/negative/inconclusive results remain visible; no forced win or threshold revision |
| EV09 end-to-end engineering | E01–E15; first vertical E01 | Installed skill inspects, edits, tests, reviews, repairs when needed, and hands off actual candidate evidence | Full requested outcome and preserved obligations; no description substituted for action |
| EV10 installation smoke | IN01–IN06 | Local/source gate and separate fresh GitHub consumer gate with actual coding-agent invocation | Package/install/provider prerequisite defect; local file parsing is not external use |

## Deterministic repository and fixture checks

Existing repository-native wrappers/configuration are authoritative for execution. The benchmark invokes the commands actually owned by each fixture; it does not become a cross-language build abstraction. Small repository-specific materialisation, evidence or validation helpers are justified only when repeated fixture/integrity work needs them. Discover actual commands and supported versions before running. Use temporary isolated state, stop owned services and remove only task-owned scratch artifacts.

| Case | Required decision / check | Concrete acceptance and limits |
|---|---|---|
| RC01 build | Inspect and execute the actual build/compiler command where present | Java clients compile and run; Node/Python fixtures execute their actual source. Absence of a compile stage is reported as not applicable, not a fabricated compiler pass. |
| RC02 typecheck | Use configured typechecker/compiler for the actual language and scope | Java compile errors are real failures. No TypeScript checker is implied for plain JavaScript, and no new checker is imposed solely to fill a result field. |
| RC03 formatter/linter | Run declared required formatting/lint commands, if any | Existing mandatory gates remain gates. A fixture without one records the reason; syntax/runtime checks are not renamed lint. |
| RC04 required tests | Execute actual selected and required native tests | Record cases/exit/skips. Collection/setup failure cannot pass; empty collection is not successful behavioural evidence. |
| RC05 fixture contract | Independent FC/P5 checks exercise actual caller, process, database or durable effect | Expected values derive from public accepted meaning. Tests of an unused helper, mocked transaction or implementation-shared wrong formula are insufficient. |
| RC06 allowed surface | Compare base/candidate manifests and actual diff, excluding declared generated/check state | Preserve a seeded unrelated user file and approved work; flag deleted/rewritten protected files and unexpected dependencies. An allowlist is a diagnostic, not proof that allowed changes are correct. |
| RC07 API compatibility | Compile/run supported clients; exercise status, defaults, errors and semantics | Cover the actual support matrix (E04/E06/E07/E12), not all imaginable consumers. An approved intentional break is assessed against its transition. |
| RC08 schema/state compatibility | Real SQLite/history and old/new reader/writer/intermediate-state checks | Values, progress and accepted clients survive; schema shape/row count alone fails the semantic requirement. Report engine/version boundary. |
| RC09 security evidence | Threat-driven allowed/forbidden path tests plus an applicable configured scanner if available | E07/E09/E12/E14/E15 check real identity/control paths. Record scanner name/version/rules/scope when actually used; none configured means scanner evidence unavailable/not applicable by stated need, never universal security assurance. Missing a required scanner remains a gate. |
| RC10 performance budget | E11 fixed datasets, actual statement counts, result equivalence and repeated timings | The accepted bounded-query criterion is deterministic; timing remains measured with variability. No universal wall-clock speed threshold or production gain. |
| RC11 installation integrity | Selective contents, frontmatter/description, relative references, no hidden source paths, prerequisites | Check every advertised skill and implemented pack. Static correctness supplements but cannot replace actual discovery and use in EV10. |

The initial fixtures intentionally use available native standard-library tooling and an authored local dependency for E12. Tool setup is part of recorded conditions. If a required capability is unavailable, obtain an authorised materially adequate execution path or report the genuine blocker; do not change the requirement to a weaker text check.

## Command conformance and orchestration

Each CC case is an actual later direct task with raw repository evidence, not a preceding command's serialized artifact. Check all nine fields from the accepted command contract: inputs, preconditions, repository evidence, outputs, allowed mutations, forbidden mutations, failure states, verification and approved decisions. A case includes a normal path and a relevant limiting/negative variant. Cases may reuse small fixtures while remaining separately assessed.

| Case / command | Direct task and normal evidence | Counterexample to detect |
|---|---|---|
| CC01 inspect-system | Explain E07's trusted tenant path; report source/consumer/config evidence without edits | Merely search filenames or change production while inspecting; bounded partial source must stay partial |
| CC02 design-change | Plan E10 transition only; compare existing/local and staged options, history, overlap, recovery | Execute migration or impose an unapproved support change; failed premise is surfaced |
| CC03 implement-change | E01 bounded fix; additionally tests-only and E03 refactor modes | Delete existing code to enforce test-first ritual; alter product in tests-only request; lose unrelated work |
| CC04 select-verification | Select checks for E02 versus E07 auth edit, explaining consequence and oracle | Treat line count as risk or report selected tests as executed |
| CC05 run-verification | Run a supplied actual native check, report candidate/configuration, failures and skips | Auto-fix source in check-only mode, ignore collection failure or report missing command passed |
| CC06 diagnose-failure | Diagnose E11/E15 supplied evidence without permanent repair when diagnosis-only | Guess root cause, broad rewrite or confuse containment with eliminated cause |
| CC07 prepare-handoff | Prepare actual evidence and perform an already-authorised local commit when requested | Renew permission unnecessarily, claim release from readiness, or erase failed run history |
| CC08 review-change | Standalone evaluator reviews raw E07/E15 candidate and reports sourced consequential findings | Require engineering skill/artifacts, edit production or invent findings to fill a quota |
| CC09 evaluate-test-quality | Assess a disconnected-helper/weak-assertion test and propose discriminating repair | Coverage percentage treated as correctness; mutate original tests in assessment-only mode |
| CC10 evaluate-compatibility | Assess old/new E04/E10/E12 clients/state plus an explicitly approved intentional delta | Reject all change as breakage or consider only latest/latest while support includes old clients |
| CC11 evaluate-security-risk | Assess scoped tenant/credential/export paths with legitimate and forbidden cases | Broad unrelated audit, secret dump or clean-scanner proof of safety |
| CC12 evaluate-performance-risk | Assess E11 samples and a noncomparable/missing-workload variant | Invent speedup, ignore changed outputs or impose a universal threshold |

The folded classify-change/assess-impact/identify-contracts modes receive separate bounded CC01 variants; add-or-update-tests/refactor are CC03 variants; plan-migration is CC02. Their responsibility is not lost because the name is not a separate entrypoint.

| Case | Actual orchestration scenario | Required outcome |
|---|---|---|
| OR01 | Engineering skill alone, ordinary E01 request | Full inspect/edit/test/self-review/repair/handoff without evaluator or pack dependency |
| OR02 | Evaluator alone, supplied raw human/agent patch | Useful assessment and local references without engineering installation |
| OR03 | Review and fix explicitly requested | Assess then carry repair authority; preserve evaluation versus mutation provenance |
| OR04 | Design-only or diagnosis-only | Complete that bounded outcome without unwanted production edits |
| OR05 | Unrelated query/async task with pack folders present | No implicit pack activation, migration, broker or required extra documents |
| OR06 | Explicit applicable pack, stronger project instructions | Load relevant local guidance; preserve valid accepted one-shot/compensation/best-effort choices |
| OR07 | Create/refine a pack explicitly | Select the domain authoring workflow; review adequate prior P evidence and do the requested bounded authoring work |
| OR08 | User authorises multiple stages, current stage passes | Continue the next authorised stage; stop only for a real unresolved required decision/capability |

Observe invocation/resource reads, task-visible actions, diffs and results. Do not infer routing success from a phrase in final prose. Do not demand hidden reasoning, a prescribed number of tool calls, a planner artifact, a native slash-command parser or subagents as runtime dependencies.

## Behavioural responsibilities

Each BE case has a transcript/action oracle plus artifact evidence. The evaluator states when missing action visibility makes a claim inconclusive. A model claiming it inspected or ran a check is weaker than the actual read/command record.

| Case | Required behaviour | Discriminating evidence / failure |
|---|---|---|
| BE01 | Inspect before relevant edits | E01 actual caller/tests and E07 auth binding read before consequential changes; filename-only inspection misses seeded alternate binding |
| BE02 | Correct scope | E01 local repair versus E13 justified multi-file vertical; protected user file remains unchanged |
| BE03 | Preserve unaffected behaviour | Baseline and final old-client/CLI/API/data checks; intentional delta distinguished from regression |
| BE04 | Meaningful regression evidence | Old defect or known valid fault seed is detected; tests observe actual obligation and do not share wrong oracle |
| BE05 | Repository-native tools | Inspected native command used with actual effective environment and output; absent tool is not renamed a pass |
| BE06 | Stop an approach disproved by evidence | Inject a relevant counterexample to chosen fix; agent revises hypothesis/owning scope instead of repeating the same ineffective patch |
| BE07 | Diagnose before broad repair | E11 query trace or E15 effect/ack reproduction distinguishes cause; no unsupported rewrite based on symptom |
| BE08 | Avoid unrelated cleanup | Compare protected baseline and full candidate diff; valid neighbouring code/formatting retained |
| BE09 | Respect accepted architecture/contracts | E13 brief and pack precedence variant preserved; implementation defects still repaired without silently rewriting policy |
| BE10 | Escalate verification by risk | E01 focused boundary evidence contrasts E10 real state/interleaving and E15 crash/recovery checks; existing required gates retained |

## Twelve distinct quality dimensions

Each dimension records `passed`, `failed`, `inconclusive`, `unavailable`, or `not applicable` with a reason, evidence and scope. A pass means the stated assessed obligations in this fixture, not universal excellence. A finding records candidate/source, violated obligation or quality mechanism, consequence, confidence, blocking versus recommendation/preference, bounded repair and recheck. Review provenance states self-review versus an independent producer/reviewer context. All dimensions are considered for applicability; unassessed ones are not silently green.

| ID / dimension | Assessment question | Observable adverse example / scope limit |
|---|---|---|
| Q01 correctness | Does actual behaviour satisfy accepted requirements at relevant boundaries? | E01 missing page or E14 wrong export value; finite cases do not prove all inputs |
| Q02 simplicity | Does structure add necessary concepts and state for this outcome? | E03 universal formatter registry for two local paths; needed E15 identity state is valid |
| Q03 maintainability | Are responsibilities and future changes local enough to reason about? | E13 duplicates policy in new and old live routes; no universal file/line ceiling |
| Q04 architecture fit | Does implementation respect accepted boundaries and justified decisions? | E07 bypasses repository/auth or E13 unapproved rewrite; valid alternative pattern allowed |
| Q05 readability | Can a maintainer trace significant names, conditions, effects and errors? | Obscure coupled state transitions with misleading naming; formatting taste is a preference |
| Q06 test quality | Are oracle, sensitivity, isolation and real-boundary fidelity adequate? | E04 tests only 1.25; E15 checks callbacks rather than durable effect/ack |
| Q07 compatibility | Do supported callers/data/states preserve their promised meaning? | E10 latest/latest only; approved new API alongside legacy overload remains valid |
| Q08 security | Are relevant trust, access, data and dependency obligations enforced? | E07 body identity, E12 leaked credentials, E14 unsafe export; no broad certification |
| Q09 performance | Are actual workload/resource results comparable and within accepted need? | E11 query count remains linear or faster result omits work; production tails unmeasured |
| Q10 reliability | Do accepted faults, concurrency and recovery preserve effect and progress? | E05 truncated file, E08 wrong terminal transition, E15 duplicate effect |
| Q11 operability | Can a receiver diagnose/recover with accurate useful signals and instructions? | E09 partial apply logged as success; E15 poison loops without recovery state |
| Q12 scope discipline | Does work fulfil the authorised delta while retaining valid work? | E01 unrelated cleanup, E14 invented product requirements, pack overriding stronger decision |

No weighted average can hide a failing hard obligation. Report a dimension vector and concrete findings, plus completion of the requested task. A style preference cannot fail functional correctness; conversely tidy code cannot offset data loss.

## Fixture and run evidence contract

Each fixture record contains: ID/level; immutable starting tree and known starting commit; explicit exact task/defect; visible accepted contracts/support; language/runtime/native commands; allowed change surface and protected files; initial data; expected risk; independent evaluator checks; reference failure mechanisms; candidate/result locations and evidence limitations. Store the source files, not just a generator whose output was never checked. A deterministic helper may materialise an isolated consumer from stored bytes and record the resulting Git commit/tree. That local starting commit is the declared execution baseline; record the GitHub source revision separately.

A run record must include:

- run ID/time, fixture ID/source revision and actual starting commit/tree;
- exact substantive prompt and full activation/installation wrapper; skill/core/pack revision and file hashes;
- producer/reviewer identity and relationship, target coding-agent host, model/version/settings when exposed, unavailable fields explicitly marked;
- actual tool/runtime versions, working directory role, prerequisites, permitted effects, resource limits/termination and deviations;
- candidate source tree/hash and actual resulting diff/artifacts; model actions or execution transcript sufficient to verify claimed behaviour;
- each actual command, relevant configuration, exit/completion, output artifact, passed/failed/partial/skipped state and result scope;
- independent oracle/behaviour/quality findings, seeds and outcomes, any repair identity and affected rerun;
- cleanup and remaining limitations, with no credentials or private books in evidence.

Model settings hidden by the host are recorded as not exposed, not guessed. Same inherited model/host defaults do not prove deterministic sampling. Fresh producer contexts get raw tasks/fixtures and selected installed guidance only; no expected patch, private oracle, prior-arm result or evaluator summary. Keep task acceptance equally visible to both arms. A reviewer who saw construction is labelled self-review. Independent contexts help limit leakage; they do not create statistical independence of all model errors.

The [oracle companion](2026-09-13-stage-14-example-oracles.md) gives FC01–FC15 with exact contract partitions, native boundary, plausible defective alternatives, preservation and result expectations. These checks judge output behaviour rather than a golden implementation. A fresh fixture with a seed and deterministic result is preferred to a downloaded project drifting underneath the benchmark. Explicitly authored synthetic SDK, broker and carrier models retain their limits.

## Preservation, diagnosis, bounded repair and regression retention

| Case | Required experiment / evidence | Owning repair |
|---|---|---|
| PR01 valid baseline | E03/E13 accepted behaviour passes before and after; old supported client and protected user file retained | Preservation failure returns to bounded source/context change; do not alter the oracle to match regression |
| PR02 known defect | E01/E05/E11/E15 reproducer fails relevant initial behaviour, then protects final repair | Diagnose mechanism, implement local correction, rerun relevant neighbouring obligations |
| PR03 weak oracle | E04 float conversion or E15 disconnected-helper seed passes weak tests but fails independent check | Repair missing assertion/binding/fidelity; retain valid product work |
| PR04 environment failure | Missing command/setup/collection failure deliberately represented in disposable fixture | Report unavailable/setup failure; do not guess product cause or claim pass |
| PR05 disproved approach | Expose concurrent writer/crash counterexample after a plausible first fix | Return to relevant context/state hypothesis, preserve useful work, add discriminating case |
| PR06 bounded refinement | Plant one stale-write/wrong-identity/ack-order defect in an otherwise valid pack candidate | Repair only the violated path, keep approved architecture and rerun affected checks |
| PR07 evidence freshness | Edit candidate after a green run and supply the old result | Detect mismatch and recheck affected scope; reject stale completion claim |

For every escaped defect: preserve the observation and baseline; diagnose its owning layer; isolate the smallest faithful reproducible fixture; add the independent benchmark/eval; **execute failure on old behaviour and protection on repaired behaviour**; retain permanently with source/case identity. A refactor's correct baseline is expected to pass preservation checks; sensitivity comes from a valid regression seed, not a forced failure of correct old behaviour. New-feature acceptance can fail on the missing feature while existing behaviour stays green. Failure caused only by a broken test harness is not successful sensitivity.

Keep initial failures, failed candidate attempts, setup errors and inconclusive measurements in append-only run history. A later repair may supersede readiness, not erase history. Stable accepted requirements govern correction; if the test oracle itself is wrong, document the reason and re-evaluate affected candidates rather than quietly weakening it.

## Investigation of test-quality techniques

The techniques below were compared against actual selected failure mechanisms and accepted CMD09 semantics. This is design investigation, not a claimed mutation run. Stage 18 must demonstrate sensitivity on E01; Stage 19 applies the relevant techniques to implemented cases. Existing mutation tools are optional, not a new runtime dependency or universal quota.

| Technique | Useful selected application | Why selected / limits and treatment |
|---|---|---|
| Mutation testing | E01 final-boundary inequality, E04 intermediate double conversion, E07 trusted-tenant omission | Small semantic mutants test a known obligation. Execute only in isolated copies. Classify killed, surviving, equivalent/invalid, timeout and setup-error separately. A survivor matters only after confirming it changes accepted behaviour; no universal mutation percentage. |
| Fault seeding | E05 failed replace, E08 finish/cancel interleaving, E10 interrupted/stale backfill, E15 crash before/after commit | Controlled failpoints/barriers expose the actual boundary without random sleeps. Verify the fault happened and observe durable state/ack, not only raised exceptions. Models cannot certify untested production faults. |
| Negative cases | E02 bad type/range, E06 malformed late line, E07/E14 forbidden role/tenant, E15 conflicting identity | Pairs of permitted and forbidden behaviour avoid a reject-everything solution. Include realistic adjacent valid inputs and expected error semantics. |
| Contract-break fixtures | E04 old client, E10 old writer/history, E12 actual resolved V2 SDK, parcel lost-response model | Exercise supported combinations and actual integration. An intentionally unsupported client is not a regression. Keep dependency/model version and public contract visible. |
| Assertion-quality review | E03 before/after oracle, E11 output+workload parity, E15 effect count/result/ack | Check expected values do not copy the implementation's mistake; identify ignored outputs, overmocked transactions or tests that never reach production. Coverage/green status alone is insufficient. |

Select the smallest technique that resolves the concrete confidence gap. Do not mutate every line or add redundant tests after adequate evidence and required gates already pass.

## Pack evaluation and comparison design

P5 owns the predetermined specialised obligations; all **DMC01–DMC14 and EPC01–EPC15 (29 total)** remain mandatory to assess for each implemented pack at their stated scopes. The full source→behaviour→test joins DMT01–16 and EPT01–16 are preserved in the linked P5 records. Do not replace them with generic “pack loaded” tests. Supplementary small premises are permitted where the substantive showcase does not exercise a particular boundary.

| Required concern | Data migration cases | Event processing cases | Actual later evidence |
|---|---|---|---|
| Activation | DMC01 | EPC01 | Explicit applicable selection changes relevant decisions/actions; record local guidance read |
| Non-activation | DMC01 query optimisation | EPC01 ordinary async parsing | No invented migration/broker/ledger in unrelated work |
| Specialised behaviour | DMC02–08/DMC10 | EPC02–09/EPC11 | Actual state/history/mixed writer or identity/effect/ack/fault observations, not terminology |
| Precedence and valid alternatives | DMC09 exclusive one-shot | EPC10 approved compensation/best-effort | Stronger valid project/architecture instructions preserved; no compulsory staged rollout or lossless ledger |
| Repository conventions and approved work | DMC03/09/12 | EPC03/10/13 | Existing native commands, real bindings and protected user work survive |
| Pack-aware verification | DMC02–08/10/11 | EPC02–09/11/12 | Necessary real boundary checks executed with substitute and version limits |
| Differential behaviour | DMC01–13 over DF01/02 | EPC01–14 over DF03/04 | Same substantive input; dimension-specific observable differences, retained null/negative outcomes |
| Negative/incompatible cases | DMC02/06/08/10/11 | EPC02/06–12 | Reject data loss, wrong mapping, duplicate effect or unsupported guarantee; do not penalise valid temporary representations/recovery state |
| Independent reuse | DMC13 subscription mapping | EPC14 separate carrier effect | Actually generate and run each distinct reuse in both arms; not renamed showcase tables |
| Refinement/freshness | DMC12 | EPC13 | Targeted planted-defect repair and affected candidate rerun |
| Local/external installation | DMC14 | EPC15 | Separately recorded integrity and clean consumer use |

Supplemental required premises include: conditional JSON precision where supported consumers need it (DMC02); actual engine/version/DDL boundary (DMC10); unknown mapping and cleanup blockers (subscription); approved one-shot migration (DMC09); per-entity order versus independent work (EPC08); poison replay/retention policy and bounded retry ownership (EPC07/09); valid compensated/best-effort alternatives (EPC10); conditional HTTP retry/result semantics (EPC06/11); and an evaluator that preserves justified duplication/identity state while identifying planted actual corruption/effect defects (DMC11/EPC12). These are separate observable tests or assessment tasks, not all falsely attributed to stock/invoice.

| Comparison | Identical substantive task/fixture | Only intended arm difference |
|---|---|---|
| DF01 | E10 invoice showcase, literal data P5 prompt | Same engineering core versus same core + explicitly selected data-migration |
| DF02 | Subscription label→ID reuse, literal data P5 reuse prompt, aliases/unknowns/legacy export/concurrent write | Same core versus same core + data-migration |
| DF03 | E15 reservation showcase, literal event P5 prompt | Same core versus same core + reliable-event-processing |
| DF04 | Parcel dispatch reuse, literal event P5 reuse prompt, separate durable carrier/status/lost response | Same core versus same core + reliable-event-processing |

This requires **eight substantive production runs** before any refinement/rerun or small probes: two arms for each of four tasks. Same fixture bytes, substantive prompt, visible accepted requirements, starting state, model/host/tool availability, authority and resource conditions. Record revisions, wrappers, model/settings exposed by the host, actual tools, limits and deviations. Producer contexts do not see the other candidate or private evaluator answers. Order/context effects and stochastic one-sample limits remain explicit; the initial design does not promise statistical superiority.

Evaluate generated artifacts and observable decisions against predetermined obligations and separate Q dimensions. More prose, pack vocabulary or a preferred pattern is not a win. A core solution can be fully correct. If useful specialised difference is absent or negative, keep that result, refine a real gap and retest comparable affected arms, or retain unproven readiness as the P5 rules allow. Do not manufacture a worse core baseline or change the task/rubric to force a pass. Record safety/compatibility regressions independently of any improvement. An optional third core+ordinary-project-instructions arm can study packaging/prompt burden; it cannot substitute for the required pair.

The installed authoring workflow must also be **actually used to create or revise a pack**, with AW01 new/reviewed-prerequisite creation, AW02 narrow revision, AW03 supplied-source authority, AW04 adequate reading reuse, AW05 missing-access/execution honesty, AW06 equal-comparison integrity, AW07 standalone local guidance and AW08 authorised continuation assessed. New source reading is not fabricated to satisfy a scenario. Source-unavailable probes use explicitly hypothetical missing inputs and must preserve the blocked status. Existing approved five-book evidence may be reused only after actual applicable review.

## End-to-end and installation gates

E01 first proves installed engineering alone in an external brownfield fixture: inspect → understand contracts → bounded edit → meaningful regression → native checks → semantic diff review → bounded correction if needed → actual final evidence. Benchmark must reject at least one plausible defective implementation. Stages 19 expands in level order to all fifteen, preserving individual starts/prompts/results/evidence. L5 records research/alternatives, inspectable implementation steps, system-wide tests, review and receiving/release evidence. No single polished fixture stands in for broad coverage.

| Case | Installation gate | Evidence required |
|---|---|---|
| IN01 | Local/source integrity | Every advertised folder/frontmatter/local reference/helper plus repository/native benchmark checks; no private books, source-log runtime dependencies or missing assets |
| IN02 | Local full install | Install all advertised skills and packs into disposable consumer layout, verify exact selected contents and local references |
| IN03 | Local selective install | Each engineering/evaluator skill alone and each pack selection; absence of siblings exposes hidden dependencies |
| IN04 | Fresh GitHub consumer core | Outside source checkout, acquire immutable committed GitHub contents, install selected engineering, invoke target coding agent, inspect/change/verify a bounded fixture |
| IN05 | Fresh GitHub consumer evaluator | Install evaluator alone, invoke actual target agent on raw candidate, resolve its local resources and deliver meaningful assessment without production mutation |
| IN06 | Fresh GitHub consumer packs | Each advertised implemented pack with selected core; actual applicable bounded use, required tools and local references; source checkout unavailable to the task |

Full installation, selective contents and skill discovery/use are different observations. Record source origin/revision/file hashes, fresh consumer path and start commit, installed selection, invocation, actual reference reads, deterministic outputs and benchmark evidence. A local copy, parser, hand-written simulated transcript or manual function call is not a target coding-agent run. Host-specific tested invocation spelling belongs in installation documentation; no untested native slash-command support is advertised. Pack P7 external evidence can be reused by Stage 20 only after candidate identity/freshness and all Stage 20 obligations are checked.

## Design discrimination review and release gates

The following counterexamples check that the designed layers distinguish kinds of failure. They are analytical checks of this design; actual execution is required later.

| Candidate | Functional outcome | Process/quality outcome | Detection path |
|---|---|---|---|
| E01 special-case fix still omits another exact-multiple page | Failed independent partition | Process may otherwise be adequate | FC01/RC05, then bounded PR02 repair |
| E01 correct paginator plus unrelated protected-file deletion | Function can pass | Failed preservation/scope and observed edit boundary | RC06/BE02/BE08/Q12; functional green cannot hide it |
| E03 exact output preserved via a needless universal registry with coupled state | Function can pass | Assessable simplicity/maintainability concern with concrete consequence; preference alone cannot fail | Q02/Q03/Q05 plus source/diff review |
| E15 tests pass only against a fake disconnected consumer | Claimed pass unsupported; actual effect oracle fails | Failed test fidelity and evidence claim | FC15/PR03/CC09/Q06 |
| Correct source but missing native runner | Unknown from that run | Setup unavailable, not a product assertion failure | RC04/CC05/PR04 |
| Valid exclusive migration under stronger instructions | Can pass | Pack must preserve valid specialisation and proportion | DMC09/OR06; no forced multi-release style rule |

Readiness is a conjunction of relevant hard obligations and required gates, not an average. A stage design pass is not benchmark implementation; an implemented benchmark is not all examples passing; passing local fixtures is not production assurance or clean installation. Advertised pack readiness requires P1–P7 evidence including intended behaviour and clean use. Source/evaluation/install/maturity states remain separate. All fifteen primary tasks need actual artifacts and evidence before the mature README can claim demonstrated coverage.

## Conformance

The complete original Stage 14 section was re-read and the actual design and oracle companion inspected. Counts establish completeness of the design; none is labelled an executed benchmark.

| Requirement | Evidence | Verification | Result |
|---|---|---|---|
| Accepted inputs and design before implementation | Inputs and status | C/WF/risk/CMD/P5/E01–15 preserved; no production framework invented | PASS |
| Ten evaluation layers | EV01–EV10 | All named layers have inputs, observable oracle, result and repair boundary | PASS |
| Deterministic checks | RC01–RC11 | Build/type/lint/tests/contract/surface/API/schema/security/performance/install candidates explicitly treated with applicability and failure semantics | PASS |
| Ten behavioural responsibilities | BE01–BE10 | Actual action/artifact evidence distinguishes every requested behaviour | PASS |
| Twelve quality dimensions | Q01–Q12 | Separate criteria, evidence/limits and findings; no opaque score | PASS |
| Reproducible fixture model | Fixture contract and FC01–FC15 companion | Known source/start commit, explicit tasks/contracts, independent checks, scope/risk/failures and multiple-valid-implementation policy | PASS |
| Regression loop | PR01–PR07 and retention policy | Old-failure/repaired protection required to execute; correct refactor baseline not forced to fail; history retained | PASS |
| Test-quality investigation | Five-technique comparison | Mutation, faults, negative cases, contract breaks and assertion review assessed for concrete value and limits | PASS |
| Extension Pack evaluation | P5 join, supplemental premises, DF01–04 | All nine concerns, all 29 P5 cases and eight required substantive runs; distinct reuse, authoring and separate clean installation retained | PASS |
| Exit: distinguish code/process/quality failures | Discrimination table | Independent functional, mutation/scope, semantic and setup outcomes cannot mask each other | PASS |
| Durable output / stage isolation | This record, oracle companion, index | Design complete; benchmark execution and installation remain unperformed | PASS |

**Handoff:** Stage 15 generates six complete canonical specifications from persisted research logs. It must carry these evaluation contracts, fifteen examples, P5 mappings and separate readiness states into implementable requirements. Continue under existing authorisation after this stage's individual commit and remote verification.
