# Stage 13: Five Progressive Example Levels

**Date:** 13 September 2026  
**Input commit:** `d31c918356a4c2be5f382e999669bce4c72d9915`  
**Status:** Complete for design; fixture implementation, model runs and benchmark outcomes remain unperformed.

## Inputs and acceptance

Read the complete [Stage 13 requirement](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#20-stage-13--design-five-progressive-example-levels) and accepted [capabilities](2026-09-13-stage-04-professional-practice-challenge.md), [context/contracts](2026-09-13-stage-05-change-contract-and-context-model.md), [workflow](2026-09-13-stage-06-workflow-and-artefacts.md), [verification/risk](2026-09-13-stage-07-verification-risk-and-commitment.md), [execution architecture](2026-09-13-stage-09-execution-layer.md), [core skills](2026-09-13-stage-11-core-skills-and-commands.md), [command contracts](2026-09-13-stage-11-command-contracts.md), [data P5](2026-09-13-stage-12-data-migration-p5-profile.md) and [event P5](2026-09-13-stage-12-reliable-event-processing-p5-profile.md). Repository decisions govern this design.

Acceptance: derive five levels; generate broader pools; represent reproducible fixtures; compare all fifteen dimensions; remove behavioural duplicates; select exactly three per level; give all fifteen exact prompts; check the full capability model; persist design and conformance. Actual implementation/execution belongs to Stages 18–19, after README design and scaffolding at Stages 16–17.

## Candidate generation and selection

The [candidate matrix](2026-09-13-stage-13-candidate-matrix.md) contains **50 original synthetic proposals, ten per level**, and all **750 required dimension cells**. Every proposal names a small reproducible repository/module shape, contract, seedable failure and executable oracle boundary. These are generated candidates, not claims about external repositories or actual incidents. No private book content is copied.

Selection first requires appropriate responsibility depth and a reproducible oracle, then compares the three-example set's distinct mechanisms and additional capability coverage, then considers interpretability and provisioning/maintenance cost. This is a qualitative set-coverage decision, not a computed optimum or opaque score. All 35 non-selected candidates retain individual reasons; a candidate with more tags need not improve the combined set.

| Level | Required capabilities derived before selection | Selected combined coverage | Duplicate / feasibility decisions |
|---|---|---|---|
| 1 | Bounded inspection, local implementation, focused tests, cheap verification and coherent small diff | E01 boundary bug; E02 validation rule; E03 preservation refactor | Other arithmetic/date/sort bugs duplicate E01; rename is weaker than E03; path traversal has broader OS assumptions. |
| 2 | Coherent module/interface, multi-file change, compatibility, unit and integration evidence | E04 compiled library API; E05 durable filesystem module; E06 streaming CLI | Configuration/cache variants overlap other cases; schema constraints gain more transition depth at L4. |
| 3 | Complete feature across layers in one deployable change, architecture fit, schema/event/API, observability and broader checks | E07 authenticated HTTP persistence; E08 async cancellation lifecycle; E09 transactional batch import | Trust, concurrent state transition and all-or-none batch behaviour differ. Email/webhook effects overlap E15. Browser/mobile prerequisites add cost without needed first-set coverage. |
| 4 | Diagnosis/preservation, migration, compatibility, performance/concurrency/security risk and bounded repair | E10 durable mixed-version migration; E11 measured N+1 repair; E12 incompatible dependency upgrade | Three different evolution mechanisms. Further migrations/protocol cases repeat support concerns; concurrency and trust are also covered elsewhere. |
| 5 | Research/alternatives, system-wide contracts, staged vertical work, evaluation, release readiness and cross-domain handoff | E13 legacy policy extraction; E14 accepted product/UX export; E15 incident-class repair | These emphasise architecture/preservation, user obligations/security, and causality/recovery. A full distributed platform or invented payment assurance is unnecessary. |

Feasibility inspection found Python, Node.js and Java 17 with `jdk.compiler`. A javac executable was absent from PATH; implementation can use the compiler module and must test its actual command. Playwright's Node package is present but browser executables/system browsers were not found. These are tool-presence observations, not execution passes or permanent product limits. The selected set has **8 Python, 5 Node.js and 2 Java** examples. It does not claim exhaustive ecosystem support. E14 uses an accepted CLI UX contract and makes no browser/visual/accessibility claim.

## Shared fixture, generation and publication contract

Every example is original synthetic brownfield work with functioning unaffected behaviour. Before generation persist its source tree/immutable identity, native-tool instructions, accepted contracts and exact task. Producer bundles contain normal public requirements; independent evaluator checks and defective alternatives remain outside generation context. Do not make hidden requirements an oracle.

Later each example must link to its starting fixture, exact task and invocation wrapper, actual result/diff, candidate identity, actual command/output evidence, engineering explanation, review/repair and limitations. A checked reconstructable start plus patch is allowed. Each primary needs its own complete evidence even if it also serves a pack comparison. No plan, prompt, golden-patch match or field validator counts as executed work.

The designs specify state, scope, preservation, oracles, inadequate fixes and handoff. File names are proposed fixture locations, not prematurely created production surfaces. Native tests supplement independent checks through the real path. Multiple correct implementations are valid. Preserve old/defective sensitivity, final candidate freshness and limits; structural review evaluates consequences rather than one preferred patch.


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


## Full-set capability check

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

## Conformance and handoff

The complete original Stage 13 requirement was re-read after writing. Inspection checked substance in the matrix, fixture contracts, prompts and capability joins; counts were checked from authored data and generated Markdown. These are design-integrity checks, not behavioural execution.

| Requirement | Evidence | Verification | Result |
|---|---|---|---|
| Required inputs and level capabilities | Input records and level table | All five responsibility levels derived from accepted C/CT/CO/WF/CMD/P5 inputs | PASS |
| Broader candidate pool | Companion matrix | Exactly 10 per level; 50 generated candidates | PASS |
| Reproducible representations | Every row plus selected detail | Repo/state/boundary/tooling/oracle and failure described; no invented external source | PASS |
| Coverage dimensions | Joined tables per level | 15 required dimensions × 50 candidates = 750 nonempty cells | PASS |
| Duplicate elimination and selection | Dispositions and comparison | 15 selected, 35 non-selected with reasons; combined mechanism coverage assessed | PASS |
| Required distribution | E01–E15 | Exactly three primary examples at each of five levels | PASS |
| Complete planned examples | Fifteen designs | Brownfield context, scope, preservation, verification, inadequate fixes, result/handoff and prompt | PASS |
| Exact copyable prompts | Fifteen text blocks | 15 tasks; E10/E15 byte equality to accepted P5 showcase prompts | PASS |
| Full capability coverage | C01–C19 join | Every accepted capability tied to a discriminating observable obligation | PASS |
| Exit: distinct engineering problems | Level and mechanism comparison | Different local/interface/cross-layer/evolution/thesis problems, not fifteen CRUD variants | PASS |
| Research-log output and stage isolation | This record, matrix and index | No scaffold, model execution, benchmark or install success claimed | PASS |

**Handoff:** Stage 14 designs deterministic, behavioural and semantic evaluations, provenance, regression sensitivity and pack comparison against these fifteen designs and the 29 accepted P5 pack cases. Stage 18 proves E01 before Stage 19 progressively expands. Continue after the individual stage commit and remote verification under existing authority.

