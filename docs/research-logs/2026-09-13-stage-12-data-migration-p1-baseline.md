# Data Migration Pack — P1: Specialisation and Core Baseline

**Date:** 13 September 2026  
**Pack:** `data-migration`  
**Input:** catalogue curation commit `b908644bba05382e2245bb287507d251c90f2951`  
**Status:** P1 complete; research selection, extraction, challenge and operational specification remain separate dependent stages.

## Prerequisites and acceptance

The [catalogue decision](2026-09-13-stage-12-pack-catalogue-curation.md) selected finite durable-state transitions after comparing all required dimensions and alternatives. The family P1 requirements and [Stage 12](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#19-stage-12--design-software-engineering-extension-packs) were reviewed against the [core contracts](2026-09-13-stage-11-command-contracts.md). Acceptance is a reusable bounded need, a substantive core baseline, all nine required specialisation fields, deliverable constraints/defaults, and provisional falsifiable evaluation questions. This is a specified baseline, not an execution result.

## Specialisation brief

| Required field | Decision |
|---|---|
| Intended use and non-use | Use when an authorised application change transforms persisted schema or data and must preserve declared readers, writers, historical meaning or resumability through a finite transition. Includes small local migrations and rolling deployments. Do not activate for every SQL query, a fresh empty schema, routine database administration, backup policy, analytics quality certification or a live migration merely because a plan exists. |
| Reusable production need | Migration success requires more than a valid final schema: existing rows, concurrently written rows, mixed application versions, interrupted work and cleanup must remain consistent with the declared support window. The repeated outcome is an executable or actionable transition with explicit invariants, measurable reconciliation and honest recovery limits. |
| Relevant core skills | Engineering CMD01 inspection, CMD02 migration design, CMD03 implementation, CMD04/05 verification, CMD06 diagnosis and CMD07 handoff; optional evaluator CMD08–10 and relevant security/performance modes. Core-alone engineering retains all these obligations. |
| Core revision / baseline status | Stage 11 `0ebb157cac31079d28cd89d4db373a522812fd6e` specifies the command baseline. No production skill is implemented yet. P6/P7 must replace this with actual core/pack revision identities and actual run evidence, without treating this desk design as a measured baseline. |
| Expected behavioural difference | Systematically enumerate supported old/new readers and writers, historical-data cases and transition states; choose a staged or justified one-shot path; make backfill restart-safe and concurrency-aware; distinguish mapping errors from pending work; gate cutover/contraction on actual reconciliation and consumer evidence. Observable additions are a bounded transition account, meaningful failure/intermediate-state tests and exact completion/recovery evidence. |
| What must remain stable | Approved public behaviour and intended deltas, data meaning/invariants, project conventions, accepted architecture, authorisation, source/evidence honesty and proportionate scope. Preserve valid existing work. The pack cannot invent retention, mapping, maintenance windows, rollback promises or permission to delete data. |
| Adjacent boundaries | Product/data owners decide meaning and support/retention policy; database/platform owners supply operational limits, access, backup and restore capabilities. The pack owns application transition reasoning and verification. General API evolution, ETL analytics, broker administration and continuous event processing are adjacent, not silently absorbed. |
| Why instructions or an existing pack are insufficient | Project instructions must supply actual schemas, mappings, windows and commands, but a reusable method for mixed versions, interrupted batches, reconciliation and irreversible cleanup transfers across projects. Stage 8 S21 covers PostgreSQL techniques, S23 a narrow Spring/Cosmos migration, and S27 Schema Registry/Terraform management; none was found to provide this complete vendor-neutral application-transition profile. Reuse them where applicable instead of copying vendor command recipes. The hypothesis that a pack reduces omissions still requires P7 comparison against substantive core work. |
| Provisional evaluation questions | Does guidance change a material transition decision or test? Can repeated/interrupted backfill preserve concurrent writes? Are unknown values surfaced rather than coerced? Does cleanup wait for the actual supported-consumer boundary? Can core+pack recognise a legitimate one-shot migration without demanding rolling deployment? Does it reject an impossible rollback promise and preserve standing authority? |

## Hard deliverable constraints and provisional soft defaults

Hard constraints come from the accepted task and actual contracts: preserve supported semantics/data, do not overclaim recovery or execution, obey stronger decisions, and bind evidence to the relevant candidate and transition state. They do not prescribe one database vendor, migration tool, batch size or rollout topology.

Soft defaults to research: prefer additive preparation before destructive contraction when mixed versions must coexist; use bounded resumable batches when data size/contention makes them useful; compare transformed records/invariants rather than using row count alone; retain mapping exceptions for resolution; state who verifies cutover and cleanup. A maintenance window with verified exclusive access may justify a simpler transactional one-shot change. Backup existence by itself does not prove an acceptable restore point or duration.

## Substantive baseline task

The later comparison uses the same repository fixture, task details and constraints for core and core+pack. Only pack activation/local guidance differs. Both runs receive the following real need, not an intentionally vague prompt:

> In the invoice service fixture, migrate persisted `total_cents` to `amount_minor` without changing the USD integer amount or the public API. Existing rows must survive. Old and new application versions can overlap, and writes continue while backfill runs. Implement a bounded resumable migration, exercise interruption and repeat execution, and show evidence for when old storage can be removed. Use this repository's tools. Prepare code, tests and migration instructions; do not operate a live database.

The fixture will include a documented legacy writer, a new reader/writer boundary, representative historical rows, an interrupted batch and a concurrent update. Preconditions such as supported rollback versions and maintenance authority are equally visible to both runs. Exact runnable fixture layout, prompt, acceptance cases and intentional failure seeds are P5 design work; no fixture is created prematurely in P1.

Valid core-only work can already discover and solve these problems. The pack must earn its value through relevant decision/test completeness or consistency, not by withholding requirements from the baseline, requiring extra documentation for its own sake, or penalising a core solution merely for not using pack terminology. If no useful difference is observed, later readiness must remain unproven or the profile must be refined.

## Reuse and scope checks

A distinct later reuse case should transform explicit subscription-plan labels to stable identifiers, preserving unmapped values as actionable exceptions and retaining the declared consumer window. This changes data mapping and failure cases rather than merely renaming the invoice table. It tests whether the profile transfers beyond additive numeric-column copying.

The boundary with `reliable-event-processing` is temporal and operational: this pack owns a finite transition and its completion; the event pack owns continuing effect/acknowledgement/replay behaviour. A backfill driven through a broker may need both, but either can remain inactive when its responsibility is absent. No common runtime or mandatory combined installation is implied.

## P1 conformance

All nine required fields are explicit; hard constraints and soft defaults are distinguished. The baseline contains the actual production obligations and identifies the specified core revision. Existing/project/core alternatives and adjacent boundaries are assessed, and a distinct reuse case is proposed. No vendor guarantee, measured advantage or installed pack is claimed. Exit: **PASS**. Next: P2 separately selects and justifies exactly five books against this migration-specific need.
