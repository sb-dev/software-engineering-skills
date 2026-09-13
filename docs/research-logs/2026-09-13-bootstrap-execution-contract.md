# Software Engineering Skills — Bootstrap Execution Contract

Execute the bootstrap exactly as defined here:

https://github.com/sb-dev/software-engineering-skills/blob/main/docs/research-logs/2026-09-07-software-engineering-skills-new-project-bootstrap-process.md

**Repository:** `sb-dev/software-engineering-skills`  
**Working branch:** `feat/bootstrap-2`  
**Starting point:** `21c608bade12791ce892ff7ab4d9d6bb083d5dee`  
**Accepted state:** Stage 1 and Stage 2 are complete. Stage 3 is next.  
**Authorised work:** Stage 3 through Stage 23, strictly in order.

The bootstrap specification is the authority. This execution contract only defines how to execute it; it must never weaken, summarise or replace bootstrap requirements.

## One stage = one complete task

Treat the current stage exactly as if it were the only task the user asked you to do.

For every stage:

```text
read the complete stage in the bootstrap specification
→ read all accepted prior-stage inputs it depends on
→ extract every requirement and exit criterion
→ perform the full research / design / implementation / evaluation required
→ create every required output
→ verify the actual repository against every requirement
→ repair every failure
→ commit only that stage
→ verify the remote commit
→ only then start the next stage
```

Do not optimise for reaching Stage 23. Do not batch stages.

A stage is complete only when all of its requirements and exit criteria actually pass.

## Follow exact requirements literally

Do not replace required work with a representative subset, summary, plan or future target.

Examples:

- Stage 3 direct-source extraction means meaningfully examining all five selected books; access checks, summaries or model memory are not enough.
- `5 levels × 3 examples` means exactly 15 complete examples with the required distribution.
- `six specifications` means six complete specification files.
- required execution means executing it, not merely writing a script or describing the expected result.
- required benchmark, installation or pack comparison means recording actual evidence.

The accepted Stage 2 corpus is `SE-CORPUS-002`. All five current books are user-supplied and available for direct reading. Follow the bootstrap's supplied-book permission rules; never silently replace, demote or remove one.

Never invent source findings, repository behaviour, benchmark results, command executions, installation results, test passes or empirical evidence. Synthetic fixtures must remain explicitly synthetic.

## Before each stage

State the stage and a concise acceptance checklist covering:

- required inputs and prerequisites;
- required research or activities;
- required outputs;
- exact counts, structure or distribution;
- required tests / execution / evaluation;
- research-log output;
- exit criteria.

Then do only that stage.

## Questions and blockers

If ANY question requires user input, STOP THE PROCESS AND ASK THE USER.

Do not guess or continue to another stage.

This includes:

- ambiguous or conflicting requirements;
- missing required source material;
- required permission or approval;
- a proposed substitution, deferral, exception or scope reduction;
- an unavailable capability that prevents satisfying the stage;
- a contradiction with accepted earlier work that would require changing it.

## Verification gate

Before declaring a stage complete, re-read its original bootstrap section and inspect the actual outputs.

Record a conformance table:

| Requirement | Evidence | Verification | Result |
|---|---|---|---|
| ... | ... | ... | PASS / FAIL / BLOCKED |

Check substance, not filenames alone. Count exact requirements explicitly. Run required tests or tools and inspect their real results.

If anything is `FAIL`, repair it and verify again.

If anything is `BLOCKED` and needs user input, stop and ask.

Do not weaken the acceptance criterion or validator to make incomplete work pass.

## Commit gate

Only after every mandatory requirement is `PASS`:

1. persist the complete stage outputs and conformance evidence;
2. update the durable progress/index record accurately;
3. commit only that stage to `feat/bootstrap-2`;
4. verify the remote branch points to the commit;
5. verify the intended files at that commit.

Then report:

```text
Stage: <stage>
Status: COMPLETE
Commit: <full SHA>
Verification: PASS
Remaining blockers: none
```

Only then begin the next stage.

Do not rewrite accepted Stage 1–2 work unless a genuine contradiction requires it. If so, stop and ask the user first.

## Context rule

The repository is authoritative. At every new stage reconstruct context from:

```text
governing bootstrap specification
+
accepted prior-stage outputs on feat/bootstrap-2
```

Do not rely on conversation memory.

If the work becomes too large, stop at the last fully verified stage boundary. Never reduce the quality of the current stage just to continue farther.

## Final audit

After Stage 23 has individually passed and been committed, re-read the full bootstrap specification and audit the final repository against every required output, stage exit criterion and global acceptance gate.

If any mandatory requirement fails, the bootstrap is not complete. Repair the owning stage and re-check affected downstream work.

Do not raise or mark a PR ready, merge, publish, promote maturity or claim benchmark/install success until the specification's corresponding evidence actually exists and the action is authorised.

# Most important rule

**COMPLETE EACH STAGE AS IF IT WERE THE ONLY TASK THE USER ASKED YOU TO DO.**

The bootstrap specification is more important than this prompt. Follow it literally.
