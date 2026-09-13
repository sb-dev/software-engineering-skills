# Stage 14: Independent Example Oracles and Reference Failures

**Date:** 13 September 2026. **Status:** predetermined evaluation design; no case below has been executed yet.

This companion to [the evaluation design](2026-09-13-stage-14-evaluation-and-benchmarks.md) consumes all fifteen accepted [Stage 13 examples](2026-09-13-stage-13-progressive-examples.md). FC01–FC15 are one-to-one with E01–E15, exactly three per level. These public fixture policies and inputs are fixed before generation and supplied equally to comparable producers. Independent evaluator implementations, seeds and expected repair answers stay outside generation bundles. Public requirements are not hidden tests.

Each case needs a known source/start commit, actual candidate/diff, native commands and outputs, applicable behaviour/quality results and limitations. Repository file names may be normalised at scaffolding; required behaviour cannot be dropped. Original synthetic state avoids private data and mutable external-project dependencies. Multiple correct implementations are accepted. Reference failures below are semantic counterexamples, not preferred source patches.

## FC01 / E01 — Page boundary

- **Visible contract/inputs:** ordered lists of 0, 1, 2, 3, 4, 5 and 6 unique IDs with page sizes 1, 2 and 3; include repeated values to check multiplicity. Empty input returns no pages. Invalid sizes 0 and negative retain the existing documented error. Input list is unchanged.
- **Independent oracle:** each nonempty page has at most the size, all except the last are full, and flattening preserves exact original sequence and multiplicity. For `[a,b,c,d]`, size 2 gives `[[a,b],[c,d]]`. Reach the actual `catalogue.pages` binding.
- **Required evidence:** native focused and full small-suite run; sensitive regression fails on the initial exact-multiple omission and passes on final candidate; unrelated file and public API unchanged; actual diff review.
- **Reference failures:** missing last page, unconditional empty extra page, size-specific special case, disconnected replacement helper, reversed ordering. This first benchmark must reject plausible incorrect code before the core vertical is accepted.

## FC02 / E02 — Port configuration

- **Visible contract/inputs:** absent→8080; numeric 1, 80, 65535 and digit strings `1`, `080`, `65535` accepted with integer values. Numeric 100 is valid regardless of source notation; a number does not retain whether it was written with an exponent. String `1e2` is invalid. Reject empty/whitespace strings, signs, decimal/exponent strings, fractional numbers, booleans, arrays, null when explicitly supplied, 0 and 65536. Absence and an explicitly invalid value differ.
- **Independent oracle:** public parser and startup configuration return the accepted number or existing error type/channel. Other defaults/options remain unchanged.
- **Required evidence:** real startup binding plus table tests; existing native tests pass; no dependency or unrelated configuration change. Report accepted syntax and actual errors.
- **Reference failures:** `parseInt` accepts `80junk`/`80.5`, `value || default` masks 0/empty, broad number coercion admits whitespace/booleans, validation helper unused by startup.

## FC03 / E03 — Report preservation refactor

- **Visible contract/inputs:** raw records with plain text, comma, quote, embedded newline, empty value and Unicode; accepted header/row order and newline convention. Existing output is valid; no behaviour correction is requested.
- **Independent oracle:** capture and retain baseline bytes, then compare actual CLI bytes and parse CSV fields against original records. Check input objects remain unchanged and previous invalid-input error behaviour survives.
- **Required evidence:** baseline characterisation before consequential refactor; final native tests and actual CLI; source/diff review of eliminated local duplication and remaining readability. Baseline and final should both pass preservation.
- **Reference failures:** naive comma join loses quoting; shared helper mutates record order; implicit newline conversion; a correct-output but needless registry creates a semantic simplicity/maintainability finding only when its concrete cost is established. Seed a real output regression to test preservation sensitivity rather than forcing correct baseline failure.

## FC04 / E04 — Java decimal compatibility

- **Visible contract/inputs:** exact `BigDecimal` values `1.005→1.00`, `1.015→1.02`, `-1.005→-1.00`, `-1.015→-1.02`, `0→0.00`, and `9007199254740993.125→9007199254740993.12`; scale must be two. Existing `round(double)` cases remain accepted. Null follows the fixture's existing documented argument-error type, recorded in the baseline contract before generation.
- **Independent oracle:** construct expected decimal values directly from strings, never from the candidate or binary floating point. Compile and run unchanged legacy and new client sources with actual Java 17 compiler/runtime.
- **Required evidence:** effective compiler/runtime version, both caller builds, decimal and legacy results, native full check; coherent API/tests/client documentation diff.
- **Reference failures:** BigDecimal→double→BigDecimal loses large-value/tie meaning; HALF_UP changes ties; replacing the old overload breaks source compatibility; correct numeric value with wrong scale violates the new contract.

## FC05 / E05 — Atomic file update

- **Visible contract/inputs:** prior `{"theme":"dark","locale":"en"}`, update theme only; successful new value and unrelated locale preserved. Inject serialisation/write/replace failure at distinct observable points. In the stated process/write-failure model readers see an entire valid old or new document, never truncated/mixed state.
- **Independent oracle:** actual destination file parsed after operation and in a fresh process; temporary-file inventory checked. Failure before replacement preserves old state; a fault reported after replacement may leave new complete state, so do not incorrectly require old state after every error. Error remains visible to CLI.
- **Required evidence:** real filesystem integration plus targeted fault injection; native checks, cleanup, public CLI preservation and explicit power-loss/platform/flush limits. No universal filesystem durability claim.
- **Reference failures:** truncate-before-write, helper never used, swallow error and report success, temporary-file leak, assert only that an exception was raised without inspecting actual state.

## FC06 / E06 — Streamed CLI

- **Visible contract/inputs:** records `{"category":"é","count":2}` and `{"category":"a","count":3}` plus repeat `é:-1` produce `{"a":3,"é":1}` with repository's final newline convention. Include empty stream, final line without newline, split UTF-8 byte sequence, split JSON tokens and malformed/invalid-shape final record. Fixtures use exact representable integer counts and sums; they do not establish arbitrary-precision aggregation.
- **Independent oracle:** actual subprocess stdout/stderr/exit and parsed object/key order; late invalid input yields no successful summary. Old echo/help output remains accepted. Drive fragmentation through the process pipe, not only a decoder helper.
- **Required evidence:** native tests plus subprocess boundary cases, preserved commands, explicit stream/error semantics. Memory is at least dependent on distinct categories; no unsupported constant-space claim.
- **Reference failures:** per-chunk JSON parsing, UTF-8 replacement corruption, premature partial summary, ignored final line, swallowed invalid record or mixing diagnostics into stdout.

## FC07 / E07 — Authenticated note feature

- **Visible fixture policy:** tenants alpha/beta, equal-looking project identifiers, fixture-only credentials, existing health/project API and supplied note rules. Materialise the agreed note rule before generation: non-whitespace text, maximum 200 Unicode code points, retained original accepted content. Audit records contain event/tenant/project/result identifiers without note body or credentials.
- **Independent oracle:** real loopback HTTP through authentication, domain and SQLite; create/list as rightful tenant; forbid unauthenticated and cross-tenant access even when body claims the other tenant; reject invalid notes; inspect durable rows and redacted audit. An injected repository failure produces no successful note or success event.
- **Required evidence:** focused rules and integration checks, old APIs, actual source/data path, architecture decision proportional to feature, API/schema/audit handoff with production limits.
- **Reference failures:** trusting body identity, global project lookup without owner scope, in-memory controller store that bypasses persistence, audit payload leak, controller tests mocked past the control.

## FC08 / E08 — Cancellation lifecycle

- **Visible fixture policy:** one local worker process, durable job state, controlled cooperative checkpoints; queued→cancelled, running→cancellation-requested→cancelled only after worker observation; completed stays completed and downloadable. Cancellation requested while running is not already-stopped evidence. Define and persist state/result/event meanings before generation.
- **Independent oracle:** actual API/store/worker with barriers for cancel before start, before completion decision, after committed completion and restart of pending cancellation. Check actual artifact cleanup/retention and status. Observe the selected schedule; no sleep-only race claim or proof of untested multi-process writer semantics.
- **Required evidence:** integrated native runs and state/error assertions, preserved completed downloads, operational explanation of pending versus terminal result and actual fault-model limits.
- **Reference failures:** unconditional cancelled overwrite of completed state, early terminal claim, no worker binding, stale state after restart, deleting a legitimate completed artifact.

## FC09 / E09 — Atomic inventory import

- **Visible fixture policy:** tenants alpha/beta with SKU A/B; CSV `sku,quantity`, nonempty unique known SKU, nonnegative integer quantity. Duplicate, unknown or invalid row rejects entire batch. Valid replacement quantities are approved business meaning; this is not additive increments. Dry-run does not write inventory or an applied audit event.
- **Independent oracle:** real CLI and SQLite post-state for valid import, empty valid file, duplicate SKU, negative/fractional quantity, invalid final row, wrong tenant and injected interruption within apply. Either whole approved apply or unchanged stock; unrelated tenant untouched. Validate audit count/result without raw sensitive payload.
- **Required evidence:** parser/domain units plus CLI/transaction/audit integration, dry-run/apply distinction, native checks, clear operator failure/reporting semantics and bounded design rationale.
- **Reference failures:** per-row commit, duplicate last-write-wins, cross-tenant lookup, dry-run mutates state, applied audit emitted before failed transaction.

## FC10 / E10 — Invoice transition

- **Visible fixture policy:** exact data P5 task, historical signed/zero/boundary integer USD amounts within accepted storage/API range, existing API and old writer; new representation is semantically equal. Old/new overlap and continuing writes are real supported conditions. Track actual SQLite/runtime version and dependent schema objects.
- **Independent oracle:** actual legacy and new adapter reads/writes before/during/after batches; compare semantic values, not only counts. Force interruption before/after data/progress boundary; repeat/resume; schedule old writer after a backfill read and verify latest accepted write survives. Check unsupported cleanup while old consumers, unmigrated rows or exceptions remain.
- **Required evidence:** candidate code/tests and transition/reconciliation/recovery instructions, actual real-engine runs, hypothesis/repair of seeded stale write and affected rerun. Exact P5 prompt/fixture in both DF01 arms. Full DMC set and subscription reuse additionally required.
- **Reference failures:** stale backfill overwrites latest write, checkpoint skips uncommitted work, wrong units with same row count, latest-reader-only success, destructive contraction justified by source search or count. Temporary duplicate columns can be valid; corruption cannot.

## FC11 / E11 — Measured catalogue repair

- **Visible fixture policy:** 20, 200 and 2,000 items with tenant/category/filter/order variations; baseline correct N+1 implementation. The bounded fixture budget is **at most three SELECT statements for the complete listing request**, independent of output count: sufficient room for a root read and bounded related metadata reads, with valid single-query/join alternatives allowed. Count all statements issued by the actual measured path. This is a fixture-specific mechanism budget, not universal database advice.
- **Independent oracle:** actual SQL trace plus identical returned values/order before and after; fresh mutation visible on subsequent request, other tenants excluded. Warm-up and repeated timing samples use the same workload/runtime and include all path work; keep raw samples, counts and summary method.
- **Required evidence:** baseline/candidate query counts at all three sizes; at least five measured post-warm-up repetitions per size/arm for a modest variability account; output equivalence and native tests. State sample size, environment and unmeasured production tails/resources. No required percentage speedup; a timing result may be noisy/inconclusive while query-budget result is decisive.
- **Reference failures:** remaining linear queries, omitted category data, duplicate rows from join, cross-tenant join, stale global cache, excluding construction/database work from timing. The independent query budget must fail the old N+1 path.

## FC12 / E12 — Dependency contract transition

- **Visible fixture policy:** original authored local provider-sdk v1/v2 source and explicit changelog, actual local package dependency and lock/config. V1 callback, V2 promise plus tenant-scoped options. Public app success/error contract, timeout classification, supported runtime and credential-redaction rule are fixed equally for producers.
- **Independent oracle:** perform real local package installation/resolution, inspect effective version and module binding, then drive actual adapter success, asynchronous rejection, timeout/unknown outcome and two tenants. Capture safe audit/log content with fake credentials; old app clients still work.
- **Required evidence:** dependency source/provenance and resolved version, actual install/native results, meaningful integration tests, supported environment and release/downgrade limitations. A synthetic SDK demonstrates the mechanism and does not establish any actual vendor's current semantics.
- **Reference failures:** manifest edited but lock/resolution still old, callback left unused under V2, rejection swallowed, timeout reported as definitely not applied, tenant credentials shared globally, logs contain fake secret token.

## FC13 / E13 — Legacy billing thesis

- **Visible fixture policy:** accepted architecture brief and legacy output/history, sparse working tests, Java 17 clients and real ledger. Fix date/discount/rounding/null/error/persistence semantics in normal project records before generation. Task authorises policy extraction and preservation; suspected existing bugs are identified separately from approved restructuring.
- **Independent oracle:** string-defined expected invoices and boundary dates, legacy and newly routed clients, real ledger effects and failure injection at declared boundaries. Compare accepted baseline/final results; ensure both live routes use the coherent policy rather than duplicated diverging copies. Review actual invocation and persistence path.
- **Required evidence:** source-grounded context research, alternatives including local repair and rewrite, characterisation before consequential extraction; inspectable vertical snapshots/diffs (feedback seam, one caller, completed bounded route); native checks at useful checkpoints and final; architecture/test-quality assessment; support, switch/recovery and receiving notes. The overall task is local preparation, not deployment.
- **Reference failures:** “clean” rewrite changes historical tie/date rules, duplicate ledger effect, correct extracted helper never called, old client break, broad unrelated rewrite. Valid old behaviour should pass preservation; use a known semantic seed for sensitivity.

## FC14 / E14 — Product/UX export thesis

- **Visible fixture policy:** accepted CLI UX/product brief fixes preview→confirm/cancel, documented noninteractive flag, authorised role/tenant, CSV columns/order, newline/quoting, and formula-leading-cell representation. For this original fixture, the explicit policy prefixes an apostrophe to export cells starting `=`, `+`, `-` or `@`; preserve raw service values. Treat this as agreed fixture behaviour, not proof of safety in every spreadsheet application. Audit excludes cell values and credentials.
- **Independent oracle:** real CLI→loopback HTTP→auth/reporting/export/audit chain; legitimate preview/confirm, cancel/no applied output, forbidden role/tenant, equal IDs in distinct tenants, formula-leading content, quotes/newlines, empty set, server failure and old read API. Inspect actual file/output and audit. Confirmation is a user-facing product contract, not another assistant permission request.
- **Required evidence:** accepted-handoff obligations and architecture/streaming-versus-buffering comparison; inspectable preview/export/negative-path verticals; native end-to-end checks, exact candidate, separate quality findings and product/security/operations receiving notes. No browser or visual-accessibility claim.
- **Reference failures:** accepting body tenant, bypassing server-side role check because CLI hides option, escaping CSV but ignoring agreed formula handling, cancelled flow records success, logging raw cell content, new product scope without accepted need.

## FC15 / E15 — Reservation incident thesis

- **Visible fixture policy:** exact event P5 prompt, synthetic incident observations, real SQLite stock, actual worker/consumer adapter and bounded delivery model. Tenant-scoped request identity, stable exact-repeat result and conflicting-content rejection; accepted stock invariant and poison/recovery policy established before generation. Two legitimate new request IDs with identical contents are distinct intents.
- **Independent oracle:** observe actual stock/effect/result and acknowledgement under sequential/concurrent duplicates, same identity/different content, two tenants, distinct IDs/same payload, process stop before effect, after commit before ack and durable restart. Invalid/permanent failure follows visible recovery policy and cannot silently hot-loop. Confirm injected schedule actually occurred.
- **Required evidence:** causal investigation tied to incident window and feasible alternatives, old-failing reproduction, bounded atomic/effect/result/ack repair, permanent regression; inspectable vertical checkpoints, actual native/fault runs, candidate review and containment/recovery/release handoff. Exact same substantive prompt/fixture for DF03; full EPC cases and separate carrier reuse remain required.
- **Reference failures:** identity lacks tenant, hash conflates new requests, dedup/effect commit separately, check-then-write race, ack before accepted completion, lost-response retry invents fresh identity, helper tests miss consumer binding. Necessary identity/recovery state is valid; actual duplicate/lost effects are not.

## Additional required pack reuse and boundary fixtures

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

## Integrity check

FC01–FC15 provide concrete inputs/accepted contracts, real oracle boundaries, required evidence and multiple plausible defects for every selected primary example. They join all five levels and preserve P5 showcase task equality. Baseline correctness versus missing-feature/known-defect sensitivity is explicitly distinguished. Supplemental reuse and boundary cases retain all P5 obligations without pretending every concern is exercised by the showcases. Native commands, exact start/candidate identities and actual results are filled only by real implementation/execution, not expected-output prose in this design.
