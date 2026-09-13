# Software Engineering Skills: Testing and Benchmark Specification

**Version:** 1.0 · **Date:** 13 September 2026

**State:** canonical implementation specification; source/behaviour/installation readiness is reported separately.

**Owns:** evaluation layers, fixture model/suites, twelve qualities, fifteen examples, regression policy, pack evaluation, installation, release gates and measured evidence.

This specification is derived from the persisted bootstrap research accepted through Stage 14 (`9c84caf8d535aedf8f774a30dfc90a9038315d6a`). Normative operational requirements are stated here; linked research preserves provenance and limitations. A requirement is not evidence that it has been implemented or passed. User/project authority outranks defaults.

## Evaluation contract and current evidence state

The domain benchmark measures separate functional, observed behavioural and semantic engineering obligations. It accepts multiple correct implementations, retains failed/inconclusive runs and never turns a planned check into a pass. At Version 1.0 no actual core/example/pack production or installation benchmark has run. The following suites and case oracles are required implementation contracts, derived from Stage 14.
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

The [oracle companion](research-logs/2026-09-13-stage-14-example-oracles.md) gives FC01–FC15 with exact contract partitions, native boundary, plausible defective alternatives, preservation and result expectations. These checks judge output behaviour rather than a golden implementation. A fresh fixture with a seed and deterministic result is preferred to a downloaded project drifting underneath the benchmark. Explicitly authored synthetic SDK, broker and carrier models retain their limits.
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

## Progressive examples: exact distribution and generation contracts

Exactly E01–E15, three per level, remain required. The fifty-candidate/750-cell selection evidence is historical; these selected briefs are the implementation contract. Stage 13 prompts are copied verbatim, including P5 showcase equality.

### E01 — Repair a missing final page (L1C01)

**Fixture, contract and scope:** Python pagination.py, catalogue.py and an existing unittest suite. catalogue.pages reaches the defective paginator. Seed an exact-multiple omission while empty and remainder cases already work. Positive page sizes, stable order, input immutability and existing invalid-size errors are accepted. Allowed scope is the paginator and meaningful tests; change the caller only if actual binding evidence requires it.

**Verification, repair and result:** Independent empty/single/exact/remainder cases flatten to the original sequence with no duplicates. Reject a one-case patch or tests of an unused helper. The regression must fail on the initial defect, then focused and complete small-repository checks pass on the candidate. Inspect the actual diff and cause. This is the Stage 18 external core-only vertical.

**Exact generation prompt:**

```text
Fix the pagination defect in this repository: when the item count is an exact multiple of page_size, catalogue.pages omits the final full page. Preserve ordering, empty-input behaviour, invalid-size errors and the public API, and do not mutate the input. Inspect the existing caller and tests, make the bounded repair, add a regression that catches the defect, run the repository's native checks and review the resulting diff. Finish with the actual verification evidence.
```


### E02 — Validate a service port (L1C02)

**Fixture, contract and scope:** Node config.js, start.js, package.json with built-in tests. Existing default is 8080. A supplied port may be an integer number or nonempty decimal digit string representing 1–65535. Whitespace, signs, fractions, exponents, booleans and other types are invalid. Use the existing configuration-error channel. Startup must use the actual validated value.

**Verification, repair and result:** Exercise extrema, absence/default, valid string/number and wrong type/format/range through parser and startup configuration. Reject parseInt-only and truthiness-only fixes. Preserve other settings and avoid new dependencies or unrelated startup redesign. Report actual error and native-command evidence.

**Exact generation prompt:**

```text
Add the approved service-port validation to this repository. Keep the default 8080 when the port is absent. Accept integer numbers and nonempty decimal digit strings representing ports 1 through 65535; reject whitespace, signs, fractions, exponents, booleans and other values using the existing configuration-error channel. Ensure startup uses the validated value, preserve other configuration behaviour, add meaningful boundary tests and run the repository's native checks.
```


### E03 — Extract duplicated report formatting (L1C03)

**Fixture, contract and scope:** Python report.py has two duplicated formatting paths and an existing CLI. Accepted valid CSV output includes commas, quotes, embedded newlines, empty strings and Unicode; header/row order and newline convention are fixed. Provide raw input examples and executable CLI. This is a structural change with no new behaviour.

**Verification, repair and result:** Characterise exact accepted output and input immutability before extraction. Compare the actual CLI afterward using independent raw examples and CSV parsing, not the extracted helper as its own oracle. Preserve exceptions. Review whether local duplication is reduced without extra abstractions or whole-repository formatting.

**Exact generation prompt:**

```text
Refactor the duplicated row-formatting logic in report.py into one clear local implementation. Preserve all accepted CLI output bytes, CSV quoting, row and header order, newline behaviour, errors and input immutability. Establish useful characterisation evidence before changing the structure, keep the refactor local, run the native checks and explain the structural benefit with the actual preservation evidence. Do not add new report behaviour.
```


### E04 — Add an exact decimal library entrypoint (L2C01)

**Fixture, contract and scope:** Java 17 Money.java, legacy client, new client harness and check.sh using the actual compiler/runtime. Preserve public round(double) and its accepted behaviour. Add round(BigDecimal), scale 2, HALF_EVEN, without binary-float conversion. Null follows the documented argument-error convention. Both old and new clients must compile.

**Verification, repair and result:** Independent fixed decimal ties, negatives, large exact values and scale checks distinguish conversion through double. Compile-time checks catch replacement of a supported API; legacy numeric examples catch behavioural drift. Review a coherent library/test/client change and provide a concise consumer note.

**Exact generation prompt:**

```text
Extend the Money library with round(BigDecimal), returning a scale-two HALF_EVEN result without converting through double. Preserve the existing round(double) signature and its documented behaviour, and follow the repository's existing argument-error convention for null. Update meaningful tests and a new caller example, compile and run both legacy and new clients with the native check command, and report compatibility and numeric-boundary evidence.
```


### E05 — Make a preferences update durable and atomic (L2C02)

**Fixture, contract and scope:** Python preferences.py, cli.py, real JSON files and a faultable filesystem boundary. Existing update truncates before completing the write. Inject serialisation/write/replace failure. Accepted state is the prior complete document or complete new document, with errors exposed and unrelated keys retained. Process/write failure is in scope; cross-filesystem power-loss assurance is not implied.

**Verification, repair and result:** Use actual temporary-directory writes and fresh-process rereads after success/failure. Catch unused-helper repair, swallowed errors and leaked temporary files. Review flush/replacement/platform assumptions explicitly. No schema conversion or migration pack is selected. Retain the local file and CLI APIs.

**Exact generation prompt:**

```text
Repair preferences updates so a failed write cannot leave a truncated JSON preferences file. Preserve unrelated keys, the public module and CLI contracts, and meaningful error reporting. Use the actual filesystem path with targeted failure injection and a fresh read to prove that readers see the prior complete document or the complete new document. Clean up temporary work, run native checks and explain the durability and platform limits of the chosen approach.
```


### E06 — Add a streaming CLI summary command (L2C03)

**Fixture, contract and scope:** Node CLI dispatcher, incremental UTF-8 decoder and aggregation module. Existing echo/help work. Add summary for JSONL objects with string category and integer count; emit one summed object with sorted keys. Final line may omit newline. Malformed JSON/shape uses existing nonzero stderr convention and produces no successful partial output.

**Verification, repair and result:** Run actual subprocesses with input fragmented inside multibyte characters and between lines, late invalid input, empty input and final-line variants. Check prior commands. Catch per-chunk parsing, replacement-character corruption and partial success. Do not claim constant memory in the number of distinct categories.

**Exact generation prompt:**

```text
Add the summary CLI command described in this repository: read UTF-8 JSONL category/count records from stdin, sum integer counts per category, and emit one JSON object with sorted keys on stdout. Accept a final line without a newline. Invalid records must use the existing nonzero stderr error convention and must not produce a partial success summary. Preserve existing commands, test real subprocess input including split Unicode chunks and a late invalid record, and run the native checks.
```


### E07 — Add tenant-scoped project notes (L3C01)

**Fixture, contract and scope:** Python HTTP service with auth middleware, existing project ownership, domain layer, SQLite repository and redacted audit sink. Add create/list project notes for the authenticated tenant. Body-supplied tenant identity is not authoritative. Preserve health/project responses and existing errors. Use local fixture identities, never live credentials.

**Verification, repair and result:** Real loopback HTTP plus actual database: tenant A/B with equal-looking project IDs, unauthenticated request, invalid/empty note, legitimate create/list, repository failure and audit redaction. Catch controller-only in-memory implementation and cross-tenant lookup. Trace auth→route→domain→repository, justify architecture fit and report API/schema/observability changes and production evidence limits.

**Exact generation prompt:**

```text
Implement the accepted project-notes feature across this service's existing HTTP, domain and SQLite layers. Only the authenticated tenant may create or list notes for its projects; never trust a tenant identity supplied in the request body. Preserve the existing health/project APIs and error conventions, follow the supplied note-validation and audit-redaction policy, add focused and real HTTP/database checks including forbidden cross-tenant access, and prepare an evidence-based technical handoff. Run locally only.
```


### E08 — Add cooperative cancellation to an export worker (L3C02)

**Fixture, contract and scope:** Node HTTP job API, durable state module and actual local export worker. Baseline queued/running/completed export and download work. Queued work can cancel; running work checks defined checkpoints; completed work keeps its valid artifact. A cancel request is not already-stopped evidence. Supply controlled finish/cancel barriers and restartable state.

**Verification, repair and result:** Exercise API→store→worker for cancellation before start, during checkpoint, after completed commit and after restart. Preserve completed downloads and remove only abandoned artifacts. Reject unconditional terminal-state overwrite and false cancellation claims. Observe states/errors. No event pack or broker is selected merely because a worker is asynchronous.

**Exact generation prompt:**

```text
Add cooperative export-job cancellation using this repository's accepted state-transition policy. Connect the HTTP API, durable job store and worker: queued jobs can cancel, running jobs observe cancellation at checkpoints, and completed jobs retain their result. A request to cancel must not falsely report that a running job has already stopped. Preserve existing downloads and errors, exercise controlled finish/cancel races and restart behaviour through the actual worker, add useful state observability and run native checks.
```


### E09 — Add an inventory import with dry-run and atomic apply (L3C03)

**Fixture, contract and scope:** Python CLI/parser/domain/SQLite/audit layers, seeded tenant/SKU quantities. Approved CSV grammar is sku,quantity: nonempty unique SKU per file and nonnegative integer quantity. Duplicate/unknown/invalid rows reject the entire batch. Dry-run reports proposed changes with no stock mutation or applied audit event; apply is atomic and tenant scoped.

**Verification, repair and result:** Real CLI plus post-state/audit inspection for valid apply, invalid final row, duplicate SKU, other tenant, interrupted transaction and dry-run. Catch incremental commit, hidden partial import and misleading applied log. Explain transactional design/alternatives and operator failure semantics; no schema migration is implied by a business import.

**Exact generation prompt:**

```text
Implement the approved inventory CSV import across the existing CLI, validation, SQLite and audit layers. Support dry-run and atomic apply for the selected tenant. Follow the repository's SKU/quantity grammar; reject duplicate, unknown or invalid rows as a whole batch. Dry-run must not change inventory or record an applied event. Preserve other tenants and existing commands, test late failure and interrupted apply through the real CLI/database path, and report the actual verification and operator-facing behaviour.
```


### E10 — Migrate invoice storage during mixed-version writes (L4C01)

**Fixture, contract and scope:** Exact data-migration P5 showcase: Python invoice service and real SQLite, integer-USD API, historical values, legacy/new adapter paths, interruption and controlled concurrent-write points. Include old writers during backfill, not only new writers that cooperate with migration. Stable API, values and supported overlap remain hard obligations. This primary example and pack showcase have one shared identity.

**Verification, repair and result:** Exercise actual storage and both adapter bindings across history/intermediate states, interruption/resume, stale-read writer schedule, reconciliation and contraction conditions. Detect count-only success, skipped progress, stale overwrite and early cleanup. Same fixture/task for core-only and packed arms. All P5 DMC obligations and separate subscription reuse remain required. Produce code/tests/transition notes and actual candidate evidence, with SQLite limits.

**Exact generation prompt:**

```text
In the invoice service fixture, migrate persisted total_cents to amount_minor without changing the USD integer amount or the public API. Existing rows must survive. Old and new application versions can overlap, and writes continue while backfill runs. Implement a bounded resumable migration, exercise interruption and repeat execution, and show evidence for when old storage can be removed. Use this repository's tools. Prepare code, tests and migration instructions; do not operate a live database.
```


### E11 — Diagnose an N+1 catalogue regression (L4C02)

**Fixture, contract and scope:** Python catalogue HTTP/repository path and SQLite categories. Baseline returns correct filtered, ordered, tenant-scoped values but issues one related query per item. Fixed 20/200/2000-item workloads vary tenants and repeat categories. Accepted mechanism budget is bounded SELECT count independent of returned item count for this path. Record actual repeated latency separately; do not invent a universal timing threshold.

**Verification, repair and result:** Measure baseline and candidate with identical workload/runtime, compare outputs and fresh updates, count actual database statements and retain repeated timing samples. Reject changed-result join, stale global cache, tenant leak and benchmark excluding the work. Diagnose the real N+1 path and limit repair to owning query/assembly. Query counts do not prove production tail latency.

**Exact generation prompt:**

```text
Diagnose and repair the catalogue listing performance regression using this repository's supplied workloads and query-count budget. Measure the baseline, identify the actual bottleneck and make a bounded repair. Preserve filtering, tenant isolation, ordering, returned values and visibility of fresh updates. Run comparable before/after query counts and repeated timings for all supplied dataset sizes, retain correctness checks and report the measured results and their limits without claiming an unmeasured production speedup.
```


### E12 — Upgrade a local provider SDK contract (L4C03)

**Fixture, contract and scope:** Node application with a real local file: dependency on an original synthetic provider SDK. Include authored v1/v2 packages, contract/changelog, lock/config, app adapter and provider model. V1 callback changes to V2 promise plus tenant-scoped options. Public app API, timeout/result policy and credential redaction stay accepted. This is actual dependency resolution against synthetic packages, not a commercial SDK assurance claim.

**Verification, repair and result:** Install/resolve locally, inspect effective package version, exercise actual adapter success/rejection/timeout and two tenants, check no credential logging and old application clients. Catch manifest-only upgrade, retained callback, swallowed asynchronous failure and shared credentials. Record provenance, Node support, install/check results and release/recovery notes. No external download or live provider required.

**Exact generation prompt:**

```text
Upgrade this application from the supplied local provider-sdk v1 package to v2 using its checked-in contract and changelog. Update actual dependency resolution and the application adapter for the promise-based, tenant-scoped API. Preserve the public application contract, timeout/result classification and credential-redaction policy. Exercise success, rejection, timeout and two-tenant behaviour through the real adapter, run the native installation and verification commands, and prepare concise compatibility, provenance and release notes. Do not contact a live provider.
```


### E13 — Extract a legacy billing policy without rewriting service (L5C01)

**Fixture, contract and scope:** Java 17 legacy billing mixes dates, money, persistence and output; sparse tests, existing CLI/API callers and real local ledger. Seed accepted historical invoices, date boundaries, discounts/rounding and failure policy. Checked-in architecture brief authorises policy extraction while preserving the deployable service, public clients and stored meaning. A broad rewrite is not the accepted plan.

**Verification, repair and result:** Research actual bindings and compare local repair/extraction/rewrite. Characterise independent expected invoices before consequential restructuring. Preserve inspectable vertical checkpoints: feedback/seam, one real caller through extracted policy, remaining bounded route with ledger/compatibility checks. Exercise dates/money/errors and failure before/after persistence; preserve valid quirks and flag suspected bugs separately. Review architecture and assertion sensitivity. Handoff candidate/support/switch/recovery and production limits; no live release.

**Exact generation prompt:**

```text
Modernise the approved billing-policy slice of this legacy service without rewriting the service or changing accepted invoice behaviour. Reconstruct the real callers, date/money rules and ledger effects; compare feasible approaches against the checked-in architecture brief. Establish meaningful characterisation, then implement the policy extraction in inspectable vertical steps while preserving public clients and historical meaning. Exercise failure and compatibility paths, evaluate the resulting architecture and tests, and prepare candidate-specific release/recovery and maintainer handoff evidence. Work locally; do not deploy.
```


### E14 — Implement an approved audit-export product handoff (L5C02)

**Fixture, contract and scope:** Node CLI/HTTP reporting service with accepted product/UX brief, role/tenant model, existing read API, export module and redacted audit. Flow is preview then explicit confirmation; tests may use the documented noninteractive flag. This is product interaction, not an assistant permission gate. Cancel makes no export/applied audit. Only approved role may export its tenant. Brief fixes CSV columns/order and safe representation for cells starting =,+,-,@ while raw service values remain unchanged.

**Verification, repair and result:** Research accepted handoff and architecture; derive user/security/operability obligations and compare streaming/buffering for the actual small workload. Preserve inspectable verticals: authorised preview, confirmed export/audit, forbidden/cancel/error closure. Real CLI→HTTP checks cover roles/tenants, formula cells, quotes/newlines, empty output, server failure, old APIs and redacted audit. Review trust binding and UX wording. Give separate product/security/operations receiving evidence. Nonvisual UX only; no browser accessibility claim.

**Exact generation prompt:**

```text
Implement the audit-export feature from this repository's accepted product and CLI UX handoff. Preserve the approved preview/confirm/cancel flow, role and tenant boundaries, deterministic CSV contract, agreed spreadsheet-formula treatment and audit-redaction policy. Trace the existing CLI, HTTP, authentication and reporting paths; compare feasible implementation approaches and deliver the feature in inspectable vertical steps. Test the real end-to-end flow, forbidden access, cancellation, unsafe cell content and failures while preserving existing APIs. Evaluate the change against the handoff and prepare product, security and operational receiving evidence. Run locally only.
```


### E15 — Repair repeated stock reservations after an incident (L5C03)

**Fixture, contract and scope:** Exact event-processing P5 stock showcase, with equal synthetic incident evidence for both arms: stock decrement committed, process stops before ack, message redelivered, second decrement. Actual Python consumer/store, real SQLite, tenant identity and conflicting-payload policy, controlled duplicate/concurrent/crash schedules and invalid-message recovery. No actual customer incident or real broker is claimed.

**Verification, repair and result:** Distinguish causal hypotheses with effect/commit/ack evidence; compare feasible local atomicity/result and approved recovery choices. Retain vertical checkpoints: old-failing incident reproduction, bounded effect/identity/ack repair, durable restart/concurrency/poison regression protection. Check exact-repeat result, conflict, tenant, crash windows and actual effects. Review decisions/code/assertions separately; provide containment, recovery and release notes. No consensus/runtime project. P5 parcel reuse is additional, not a sixteenth primary example.

**Exact generation prompt:**

```text
Repair the stock-reservation consumer in this repository. Delivery is at least once. Reserve stock once for each accepted tenant-scoped reservation request, preserve the public result for an exact repeat, and reject reuse of the same request identity with different contents. A process can stop before or after the database commit and before acknowledgement. Implement the bounded repair with project-native checks, exercise duplicate/concurrent delivery and crash/retry cases, and explain recovery for invalid messages. Do not operate a live broker or inventory service.
```


## Capability coverage of the fifteen examples

These are design mappings, not measured coverage. Common core duties apply even when strongest discriminating examples are named.

| Capability | Primary evidence design | Missing-capability signal |
|---|---|---|
| C01 | E02/E09/E13/E14 | Invented acceptance/product scope or repeated approval for authorised local work |
| C02 | E01 caller, E07 auth, E12 resolution, E15 effect/ack | Correct unused helper while actual binding remains defective |
| C03 | E04 decimal ties, E08 states, E14 handoff | Only happy paths or invented obligations |
| C04 | E07–10/E13–15 alternatives | Default pattern without comparing bounded adequate choices |
| C05 | E05/E10/E12/E15 consequence analysis | Small diff treated as low risk despite durable effects |
| C06 | E03/E10/E13/E15 preservation feedback | Restructure before relevant evidence exists |
| C07 | All fifteen; E01/E04/E11/E15 discriminate different inadequate fixes | Green assertions mirror wrong code or miss actual binding |
| C08 | All fifteen; E03/E07/E13 scope | Unrelated cleanup or incomplete cross-layer route |
| C09 | E01/E05/E10–13/E15 diagnosis | Guess-and-rewrite or stale evidence after repair |
| C10 | E04/E06–07/E09–10/E12–15 | Supported clients/rows silently abandoned |
| C11 | E08 finish/cancel, E10 writer/backfill, E15 duplicates | Unsafe schedule hidden by sequential happy path |
| C12 | E05/E08–10/E12–15; additional parcel reuse | Timeout confused with non-application or recovery asserted |
| C13 | E11 same workload and results | Faster-looking source without comparable measurement |
| C14 | E02 config, E04 compiler, E12 actual resolution, E13–14 runtime | Manifest-only upgrade or unrecorded effective environment |
| C15 | All fifteen; focused evaluator cases E03/E04/E11/E14/E15 | Preference reported as defect or quality collapsed into correctness |
| C16 | E10/E12–15 transition/release | Tests pass while support/transition/recovery remains unsupported |
| C17 | E04–15, especially E13–15 receiving roles | No actionable receiver or planned action reported as executed |
| C18 | E01–03 compared with E10/E13–15 | Same ceremony despite different consequence or broad rewrite of local bug |
| C19 | E07 trust, E09 tenant import, E12 provenance/credentials, E14 export, E15 identity | Scanner-only assurance or untrusted payload supplies identity |


The fifteen mechanisms are bug repair, validation, local refactor, compiled library API, durable file update, streamed CLI, authenticated persistence, asynchronous lifecycle, batch transaction, data migration, measured optimisation, dependency transition, legacy architecture, accepted product handoff and incident prevention. They are substantially different problems. Packs specialise E10/E15 plus separate reuse/boundary cases; core-only cases show that SQL or async code does not automatically activate a pack.

## Independent functional oracles

### FC01 / E01 — Page boundary

- **Visible contract/inputs:** ordered lists of 0, 1, 2, 3, 4, 5 and 6 unique IDs with page sizes 1, 2 and 3; include repeated values to check multiplicity. Empty input returns no pages. Invalid sizes 0 and negative retain the existing documented error. Input list is unchanged.
- **Independent oracle:** each nonempty page has at most the size, all except the last are full, and flattening preserves exact original sequence and multiplicity. For `[a,b,c,d]`, size 2 gives `[[a,b],[c,d]]`. Reach the actual `catalogue.pages` binding.
- **Required evidence:** native focused and full small-suite run; sensitive regression fails on the initial exact-multiple omission and passes on final candidate; unrelated file and public API unchanged; actual diff review.
- **Reference failures:** missing last page, unconditional empty extra page, size-specific special case, disconnected replacement helper, reversed ordering. This first benchmark must reject plausible incorrect code before the core vertical is accepted.

### FC02 / E02 — Port configuration

- **Visible contract/inputs:** absent→8080; numeric 1, 80, 65535 and digit strings `1`, `080`, `65535` accepted with integer values. Numeric 100 is valid regardless of source notation; a number does not retain whether it was written with an exponent. String `1e2` is invalid. Reject empty/whitespace strings, signs, decimal/exponent strings, fractional numbers, booleans, arrays, null when explicitly supplied, 0 and 65536. Absence and an explicitly invalid value differ.
- **Independent oracle:** public parser and startup configuration return the accepted number or existing error type/channel. Other defaults/options remain unchanged.
- **Required evidence:** real startup binding plus table tests; existing native tests pass; no dependency or unrelated configuration change. Report accepted syntax and actual errors.
- **Reference failures:** `parseInt` accepts `80junk`/`80.5`, `value || default` masks 0/empty, broad number coercion admits whitespace/booleans, validation helper unused by startup.

### FC03 / E03 — Report preservation refactor

- **Visible contract/inputs:** raw records with plain text, comma, quote, embedded newline, empty value and Unicode; accepted header/row order and newline convention. Existing output is valid; no behaviour correction is requested.
- **Independent oracle:** capture and retain baseline bytes, then compare actual CLI bytes and parse CSV fields against original records. Check input objects remain unchanged and previous invalid-input error behaviour survives.
- **Required evidence:** baseline characterisation before consequential refactor; final native tests and actual CLI; source/diff review of eliminated local duplication and remaining readability. Baseline and final should both pass preservation.
- **Reference failures:** naive comma join loses quoting; shared helper mutates record order; implicit newline conversion; a correct-output but needless registry creates a semantic simplicity/maintainability finding only when its concrete cost is established. Seed a real output regression to test preservation sensitivity rather than forcing correct baseline failure.

### FC04 / E04 — Java decimal compatibility

- **Visible contract/inputs:** exact `BigDecimal` values `1.005→1.00`, `1.015→1.02`, `-1.005→-1.00`, `-1.015→-1.02`, `0→0.00`, and `9007199254740993.125→9007199254740993.12`; scale must be two. Existing `round(double)` cases remain accepted. Null follows the fixture's existing documented argument-error type, recorded in the baseline contract before generation.
- **Independent oracle:** construct expected decimal values directly from strings, never from the candidate or binary floating point. Compile and run unchanged legacy and new client sources with actual Java 17 compiler/runtime.
- **Required evidence:** effective compiler/runtime version, both caller builds, decimal and legacy results, native full check; coherent API/tests/client documentation diff.
- **Reference failures:** BigDecimal→double→BigDecimal loses large-value/tie meaning; HALF_UP changes ties; replacing the old overload breaks source compatibility; correct numeric value with wrong scale violates the new contract.

### FC05 / E05 — Atomic file update

- **Visible contract/inputs:** prior `{"theme":"dark","locale":"en"}`, update theme only; successful new value and unrelated locale preserved. Inject serialisation/write/replace failure at distinct observable points. In the stated process/write-failure model readers see an entire valid old or new document, never truncated/mixed state.
- **Independent oracle:** actual destination file parsed after operation and in a fresh process; temporary-file inventory checked. Failure before replacement preserves old state; a fault reported after replacement may leave new complete state, so do not incorrectly require old state after every error. Error remains visible to CLI.
- **Required evidence:** real filesystem integration plus targeted fault injection; native checks, cleanup, public CLI preservation and explicit power-loss/platform/flush limits. No universal filesystem durability claim.
- **Reference failures:** truncate-before-write, helper never used, swallow error and report success, temporary-file leak, assert only that an exception was raised without inspecting actual state.

### FC06 / E06 — Streamed CLI

- **Visible contract/inputs:** records `{"category":"é","count":2}` and `{"category":"a","count":3}` plus repeat `é:-1` produce `{"a":3,"é":1}` with repository's final newline convention. Include empty stream, final line without newline, split UTF-8 byte sequence, split JSON tokens and malformed/invalid-shape final record. Fixtures use exact representable integer counts and sums; they do not establish arbitrary-precision aggregation.
- **Independent oracle:** actual subprocess stdout/stderr/exit and parsed object/key order; late invalid input yields no successful summary. Old echo/help output remains accepted. Drive fragmentation through the process pipe, not only a decoder helper.
- **Required evidence:** native tests plus subprocess boundary cases, preserved commands, explicit stream/error semantics. Memory is at least dependent on distinct categories; no unsupported constant-space claim.
- **Reference failures:** per-chunk JSON parsing, UTF-8 replacement corruption, premature partial summary, ignored final line, swallowed invalid record or mixing diagnostics into stdout.

### FC07 / E07 — Authenticated note feature

- **Visible fixture policy:** tenants alpha/beta, equal-looking project identifiers, fixture-only credentials, existing health/project API and supplied note rules. Materialise the agreed note rule before generation: non-whitespace text, maximum 200 Unicode code points, retained original accepted content. Audit records contain event/tenant/project/result identifiers without note body or credentials.
- **Independent oracle:** real loopback HTTP through authentication, domain and SQLite; create/list as rightful tenant; forbid unauthenticated and cross-tenant access even when body claims the other tenant; reject invalid notes; inspect durable rows and redacted audit. An injected repository failure produces no successful note or success event.
- **Required evidence:** focused rules and integration checks, old APIs, actual source/data path, architecture decision proportional to feature, API/schema/audit handoff with production limits.
- **Reference failures:** trusting body identity, global project lookup without owner scope, in-memory controller store that bypasses persistence, audit payload leak, controller tests mocked past the control.

### FC08 / E08 — Cancellation lifecycle

- **Visible fixture policy:** one local worker process, durable job state, controlled cooperative checkpoints; queued→cancelled, running→cancellation-requested→cancelled only after worker observation; completed stays completed and downloadable. Cancellation requested while running is not already-stopped evidence. Define and persist state/result/event meanings before generation.
- **Independent oracle:** actual API/store/worker with barriers for cancel before start, before completion decision, after committed completion and restart of pending cancellation. Check actual artifact cleanup/retention and status. Observe the selected schedule; no sleep-only race claim or proof of untested multi-process writer semantics.
- **Required evidence:** integrated native runs and state/error assertions, preserved completed downloads, operational explanation of pending versus terminal result and actual fault-model limits.
- **Reference failures:** unconditional cancelled overwrite of completed state, early terminal claim, no worker binding, stale state after restart, deleting a legitimate completed artifact.

### FC09 / E09 — Atomic inventory import

- **Visible fixture policy:** tenants alpha/beta with SKU A/B; CSV `sku,quantity`, nonempty unique known SKU, nonnegative integer quantity. Duplicate, unknown or invalid row rejects entire batch. Valid replacement quantities are approved business meaning; this is not additive increments. Dry-run does not write inventory or an applied audit event.
- **Independent oracle:** real CLI and SQLite post-state for valid import, empty valid file, duplicate SKU, negative/fractional quantity, invalid final row, wrong tenant and injected interruption within apply. Either whole approved apply or unchanged stock; unrelated tenant untouched. Validate audit count/result without raw sensitive payload.
- **Required evidence:** parser/domain units plus CLI/transaction/audit integration, dry-run/apply distinction, native checks, clear operator failure/reporting semantics and bounded design rationale.
- **Reference failures:** per-row commit, duplicate last-write-wins, cross-tenant lookup, dry-run mutates state, applied audit emitted before failed transaction.

### FC10 / E10 — Invoice transition

- **Visible fixture policy:** exact data P5 task, historical signed/zero/boundary integer USD amounts within accepted storage/API range, existing API and old writer; new representation is semantically equal. Old/new overlap and continuing writes are real supported conditions. Track actual SQLite/runtime version and dependent schema objects.
- **Independent oracle:** actual legacy and new adapter reads/writes before/during/after batches; compare semantic values, not only counts. Force interruption before/after data/progress boundary; repeat/resume; schedule old writer after a backfill read and verify latest accepted write survives. Check unsupported cleanup while old consumers, unmigrated rows or exceptions remain.
- **Required evidence:** candidate code/tests and transition/reconciliation/recovery instructions, actual real-engine runs, hypothesis/repair of seeded stale write and affected rerun. Exact P5 prompt/fixture in both DF01 arms. Full DMC set and subscription reuse additionally required.
- **Reference failures:** stale backfill overwrites latest write, checkpoint skips uncommitted work, wrong units with same row count, latest-reader-only success, destructive contraction justified by source search or count. Temporary duplicate columns can be valid; corruption cannot.

### FC11 / E11 — Measured catalogue repair

- **Visible fixture policy:** 20, 200 and 2,000 items with tenant/category/filter/order variations; baseline correct N+1 implementation. The bounded fixture budget is **at most three SELECT statements for the complete listing request**, independent of output count: sufficient room for a root read and bounded related metadata reads, with valid single-query/join alternatives allowed. Count all statements issued by the actual measured path. This is a fixture-specific mechanism budget, not universal database advice.
- **Independent oracle:** actual SQL trace plus identical returned values/order before and after; fresh mutation visible on subsequent request, other tenants excluded. Warm-up and repeated timing samples use the same workload/runtime and include all path work; keep raw samples, counts and summary method.
- **Required evidence:** baseline/candidate query counts at all three sizes; at least five measured post-warm-up repetitions per size/arm for a modest variability account; output equivalence and native tests. State sample size, environment and unmeasured production tails/resources. No required percentage speedup; a timing result may be noisy/inconclusive while query-budget result is decisive.
- **Reference failures:** remaining linear queries, omitted category data, duplicate rows from join, cross-tenant join, stale global cache, excluding construction/database work from timing. The independent query budget must fail the old N+1 path.

### FC12 / E12 — Dependency contract transition

- **Visible fixture policy:** original authored local provider-sdk v1/v2 source and explicit changelog, actual local package dependency and lock/config. V1 callback, V2 promise plus tenant-scoped options. Public app success/error contract, timeout classification, supported runtime and credential-redaction rule are fixed equally for producers.
- **Independent oracle:** perform real local package installation/resolution, inspect effective version and module binding, then drive actual adapter success, asynchronous rejection, timeout/unknown outcome and two tenants. Capture safe audit/log content with fake credentials; old app clients still work.
- **Required evidence:** dependency source/provenance and resolved version, actual install/native results, meaningful integration tests, supported environment and release/downgrade limitations. A synthetic SDK demonstrates the mechanism and does not establish any actual vendor's current semantics.
- **Reference failures:** manifest edited but lock/resolution still old, callback left unused under V2, rejection swallowed, timeout reported as definitely not applied, tenant credentials shared globally, logs contain fake secret token.

### FC13 / E13 — Legacy billing thesis

- **Visible fixture policy:** accepted architecture brief and legacy output/history, sparse working tests, Java 17 clients and real ledger. Fix date/discount/rounding/null/error/persistence semantics in normal project records before generation. Task authorises policy extraction and preservation; suspected existing bugs are identified separately from approved restructuring.
- **Independent oracle:** string-defined expected invoices and boundary dates, legacy and newly routed clients, real ledger effects and failure injection at declared boundaries. Compare accepted baseline/final results; ensure both live routes use the coherent policy rather than duplicated diverging copies. Review actual invocation and persistence path.
- **Required evidence:** source-grounded context research, alternatives including local repair and rewrite, characterisation before consequential extraction; inspectable vertical snapshots/diffs (feedback seam, one caller, completed bounded route); native checks at useful checkpoints and final; architecture/test-quality assessment; support, switch/recovery and receiving notes. The overall task is local preparation, not deployment.
- **Reference failures:** “clean” rewrite changes historical tie/date rules, duplicate ledger effect, correct extracted helper never called, old client break, broad unrelated rewrite. Valid old behaviour should pass preservation; use a known semantic seed for sensitivity.

### FC14 / E14 — Product/UX export thesis

- **Visible fixture policy:** accepted CLI UX/product brief fixes preview→confirm/cancel, documented noninteractive flag, authorised role/tenant, CSV columns/order, newline/quoting, and formula-leading-cell representation. For this original fixture, the explicit policy prefixes an apostrophe to export cells starting `=`, `+`, `-` or `@`; preserve raw service values. Treat this as agreed fixture behaviour, not proof of safety in every spreadsheet application. Audit excludes cell values and credentials.
- **Independent oracle:** real CLI→loopback HTTP→auth/reporting/export/audit chain; legitimate preview/confirm, cancel/no applied output, forbidden role/tenant, equal IDs in distinct tenants, formula-leading content, quotes/newlines, empty set, server failure and old read API. Inspect actual file/output and audit. Confirmation is a user-facing product contract, not another assistant permission request.
- **Required evidence:** accepted-handoff obligations and architecture/streaming-versus-buffering comparison; inspectable preview/export/negative-path verticals; native end-to-end checks, exact candidate, separate quality findings and product/security/operations receiving notes. No browser or visual-accessibility claim.
- **Reference failures:** accepting body tenant, bypassing server-side role check because CLI hides option, escaping CSV but ignoring agreed formula handling, cancelled flow records success, logging raw cell content, new product scope without accepted need.

### FC15 / E15 — Reservation incident thesis

- **Visible fixture policy:** exact event P5 prompt, synthetic incident observations, real SQLite stock, actual worker/consumer adapter and bounded delivery model. Tenant-scoped request identity, stable exact-repeat result and conflicting-content rejection; accepted stock invariant and poison/recovery policy established before generation. Two legitimate new request IDs with identical contents are distinct intents.
- **Independent oracle:** observe actual stock/effect/result and acknowledgement under sequential/concurrent duplicates, same identity/different content, two tenants, distinct IDs/same payload, process stop before effect, after commit before ack and durable restart. Invalid/permanent failure follows visible recovery policy and cannot silently hot-loop. Confirm injected schedule actually occurred.
- **Required evidence:** causal investigation tied to incident window and feasible alternatives, old-failing reproduction, bounded atomic/effect/result/ack repair, permanent regression; inspectable vertical checkpoints, actual native/fault runs, candidate review and containment/recovery/release handoff. Exact same substantive prompt/fixture for DF03; full EPC cases and separate carrier reuse remain required.
- **Reference failures:** identity lacks tenant, hash conflates new requests, dedup/effect commit separately, check-then-write race, ack before accepted completion, lost-response retry invents fresh identity, helper tests miss consumer binding. Necessary identity/recovery state is valid; actual duplicate/lost effects are not.

### Additional required pack reuse and boundary fixtures

These are supplemental to the fifteen primary examples and do not change the 5×3 distribution.

| Fixture | Public premise and independent oracle | Comparison / scope |
|---|---|---|
| Subscription plan migration | Literal data P5 reuse task; approved aliases map to same ID, unknown label remains an explicit exception, legacy export and entitlement preserved, actual writer/backfill interruption/concurrent update exercised. Unknown must not silently become a default; contraction remains ineligible while exception/support obligations remain. | DF02 two arms; real SQLite mapping/history semantics, distinct from integer column rename |
| Parcel dispatch | Literal event P5 reuse task; carrier has its own durable store and documented identity/status, can commit then drop response; worker local transaction cannot include carrier. Reuse stable tenant/request identity, reconcile pending after restart, reject mismatch and preserve legitimate distinct requests with same payload. | DF04 two arms; actual separate local stores/model interaction, not real carrier certification |
| Exclusive migration precedence | Stronger valid project contract establishes maintenance/exclusive access and bounded one-shot transaction; preserve semantics and honest recovery without mandatory multi-release ceremony. | DMC09 actual plan/implementation or evaluation probe, same core/pack policy boundary |
| Conditional JSON precision | Supported JSON consumer and accepted numeric range/representation made explicit; exercise actual decoding boundary; reject silent rounding without inventing a new type/range. | DMC02 supplemental; avoid claiming all JSON consumers have one precision model |
| Event ordering/replay/retry | Small explicit per-entity-version state, independent commutative work, poison retention/replay and existing retry-owner policy. Exercise stale event, valid independent event and permanent failure against that policy. | EPC07–09; bounded model, no global FIFO or throughput guarantee |
| Valid best-effort/compensation | Stronger accepted telemetry-loss or compensated-business contract; evaluator respects it while detecting real violation of that actual contract. | EPC10; no universal lossless ledger/outbox mandate |
| Pack-aware review and refinement | Pair valid necessary migration duplication/recovery identity with a planted corrupt mapping/wrong identity/ack defect; assessment must preserve valid trait and find actual defect. Then requested repair preserves unrelated source and refreshes affected results. | DMC11/12, EPC12/13; observed evaluator/repair actions, not phrase matching |


## Measured evidence and release acceptance

Before a result is called measured, record actual start/candidate/core/pack identity, prompt/wrapper, host/model fields exposed, runtime/tool versions, conditions/limits, native command/output and evaluator provenance. Unknown fields remain unknown. The initial state for all fifteen examples, DF01–DF04 and IN01–IN06 is **not run**. Design-integrity counts are not success rates.

The first vertical must show a plausible defective candidate failing independent checks and the actual installed-core result passing relevant gates. Progressive coverage requires all fifteen actual changes and meaningful evidence; refactor baselines can validly pass preservation before/after. Each pack needs showcase plus distinct reuse in both arms and all relevant P5/authoring/boundary/installation cases. Stage 20 rechecks exact current package identities separately for local and clean external gates. Public maturity/README claims follow observed evidence; no aggregate score, single favourable sample or source-folder existence can waive a required gate.


## Provenance and specification ownership

[S01 charter](research-logs/2026-09-12-stage-01-project-goal-and-domain-boundary.md), [source-qualified C/S/W models](research-logs/2026-09-13-stage-04-professional-practice-challenge.md), [CT/CO/SI context](research-logs/2026-09-13-stage-05-change-contract-and-context-model.md), [WF/A/RR semantics](research-logs/2026-09-13-stage-06-workflow-and-artefacts.md), [VL/RF/CP policy](research-logs/2026-09-13-stage-07-verification-risk-and-commitment.md), [D/S/P capability inventory](research-logs/2026-09-13-stage-08-candidate-evaluations.md), [execution architecture](research-logs/2026-09-13-stage-09-execution-layer.md), [core design](research-logs/2026-09-13-stage-11-core-skills-and-commands.md), [pack research](research-logs/2026-09-13-stage-12-extension-packs-completion.md), [example selection](research-logs/2026-09-13-stage-13-progressive-examples.md) and [evaluation design](research-logs/2026-09-13-stage-14-evaluation-and-benchmarks.md) preserve the decision/source register and research limitations. These links are maintainer provenance, not installed runtime dependencies.

The six specifications divide canonical responsibilities: [01 system](01-software-engineering-skills-system-spec.md), [02 workflows/artefacts](02-software-engineering-skills-workflows-and-artifacts-spec.md), [03 repository/contracts](03-software-engineering-skills-repository-and-contracts-spec.md), [04 testing/benchmark](04-testing-and-benchmark-spec.md), [05 packs](05-software-engineering-extension-packs-spec.md), [06 catalogue](06-software-engineering-extension-pack-catalogue.md). Operational details copied into role-local installed guidance must preserve the owning specification's meaning and be checked for drift; no shared runtime is implied.

---

Version 1.0 — 13 September 2026. Initial canonical specification from accepted research.
