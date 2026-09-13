# Stage 12: Domain-Native Pack Authoring Contract

**Date:** 13 September 2026  
**Input revision:** `5b6bd8348aff4300b4ca44b6958c6502b2301963`  
**Status:** Equivalent authoring workflow specified; runtime implementation and behavioural proof remain later-stage work.

## Ownership and entry

The [Stage 11 design](2026-09-13-stage-11-core-skills-and-commands.md) chose an equivalent domain-native authoring workflow instead of an additional `software-extension-pack-creator` installation. [Stage 12](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md#19-stage-12--design-software-engineering-extension-packs) explicitly permits this choice. It retains the full [family Extension Pack process](https://github.com/sb-dev/production-skills/blob/20979e0c68ac4b37433374df7fe10ceb2e7ee69a/docs/bootstrap/extension-pack-process.md), read in full at revision `20979e0c68ac4b37433374df7fe10ceb2e7ee69a`.

The capability will be an **explicitly requested authoring workflow within the engineering skill**, routed to a skill-local `references/pack-authoring.md` or equivalent local resource. It is distinct from ordinary application editing: a request to create/refine/research/evaluate a software-engineering pack selects this authoring workflow, with its required research and proof gates. It does not run ordinary feature implementation merely because both use engineering reasoning. Natural-language entry is sufficient; no thirteenth application command, new slash-command promise, research DSL or generic authoring runtime is added.

The installed workflow must carry its operational requirements locally. It cannot require the user's original books, this source repository's logs, family templates or another skill to be installed. During authoring, original source access may still be required for new research; that is an explicit input capability, not a hidden runtime dependency of an already implemented pack. Repository specifications 05/06 will canonically own semantics/catalogue; role-local instructions must agree with them.

## Workflow contract

| Field | Definition |
|---|---|
| Inputs | User's requested scope—catalogue, new pack, revision, implementation or evaluation only—plus accessible owning repository, relevant charter/core contracts/catalogue, existing pack/evidence and source inputs. Identify actual revisions, supplied books and accepted production/interface constraints. |
| Preconditions | Relevant prerequisite evidence is available or can be researched. A specified core permits P1–P5; actual core implementation is required for P6/P7 production comparisons. Enter a later stage only after reviewing adequate persisted prerequisites and their applicability. Existing authority persists. |
| Repository evidence required | Actual core/pack files and contracts, existing entries/interfaces, research reading/access/permission records, source mappings, exact showcase/reuse prompts, fixtures, local/external results, maturity/readiness and any accepted migration decision. A directory or bibliography alone is not completion evidence. |
| Outputs | The requested bounded stage outcome with substantive committed research or implementation/evaluation evidence; a justified catalogue disposition; self-contained profile/pack when implemented; actual production/reuse/comparison/install results and honest status. Preserve necessary source→behaviour→test traceability and compatibility notes. |
| Allowed mutations | Scoped owning-repository research/specification/catalogue updates; selected pack/local resources; relevant showcase/fixture/evaluation artifacts; authorised isolated executions and native Git actions. Revise affected evidence and preserve valid unrelated work. |
| Forbidden mutations | Publishing private PDFs or substantial source text; silently substituting supplied books; replacing approved identities/examples/interfaces; inventing source reading, production runs or comparative wins; modifying other domain repositories; imposing a shared runtime; live actions outside existing authority. |
| Failure states | Unclear need/reuse advantage; missing required source access or substitution decision; stale/inadequate prerequisite; unsupported claim; missing core/execution capability; failed/inconclusive production, preservation, evaluation or installation; unknown remote action. Record exact state and smallest useful next action. |
| Verification responsibilities | Check literal per-stage requirements and substance, not just headings. For implementation, validate actual local resources and native checks; execute realistic showcase plus distinct reuse; compare equal substantive briefs; inspect intended traits and genuine defects; prove clean external use separately; bind evidence to actual candidates. |
| Interaction with approved decisions | Explicit project instructions and accepted work outrank pack defaults. Carry prior scope/commit/continuation authority without ritual reapproval. Prepare a concrete result before a genuinely missing consequential decision. An approved overall bootstrap does not silently authorise supplied-book replacement, live replay, external publication beyond its scope or fabrication of evidence. |

## Catalogue decision before authoring

For a new catalogue, generate/research a broader candidate pool and compare combined coverage, practical reuse, distinct production behaviour, depth, evaluation feasibility and overlap. For a single new/revised pack, inspect only the relevant catalogue neighbourhood and core gaps. Classify the need as existing capability/pack reuse, project instructions, core improvement, reusable specialised pack, or insufficient-value/evidence defer/reject. Names, frameworks or five books do not determine catalogue size.

Preserve existing entries, installed interfaces, accepted examples and evidence. A merge/retirement/renaming needs an explicit migration decision within actual authority; a catalogue rewrite is not implied by one new pack. Record the selected entry's marginal contribution and residual gaps.

## Required authoring stages and direct-entry rules

Each stage is substantive, persisted and separately committed before dependent work. Adequate existing evidence may satisfy a prerequisite after actual review; a narrow revision revisits affected claims/tests instead of rerunning unrelated research. The requested completion boundary and existing authorisation determine how far to continue, not an arbitrary pause at each stage.

| Stage | Required work and durable output | Exit and affected-revision rule |
|---|---|---|
| P1 specialisation/baseline | Intended use/non-use, recurring outcome, relevant core revision/status, real substantive baseline, expected difference, stable obligations, adjacent boundaries, hard/default distinctions, reuse/project/core alternatives and evaluation questions | Bounded reusable need; no weak baseline invented to flatter the pack. A changed need/core boundary reopens affected design/evaluation |
| P2 five-book selection | Pack coverage map; broader candidate comparison; exactly five distinct justified books with identity/edition/origin/access/reading limits; contribution-specific reuse; supplied-book decisions and specialist gaps | Required permissions resolved; access needs explicit. Retain supplied books by default; explicit permission precedes removal/replacement/demotion. More than five supplied works requires a proposed foundational five and the necessary exclusion decision; an unanswered required decision is not approval |
| P3 extraction/reconciliation | Meaningfully examine all five directly or review adequate original direct evidence, source locations, edition, assumptions and limits. Map finding/location→specialist applicability→core decision→observable effect→criterion→failure/repair; reconcile conflicts and general/project boundaries | All five meaningfully assessed; no inference of reading from a shared bibliography or source availability. New unsupported specialist use needs actual source examination |
| P4 independent challenge | Seek contrary/supporting evidence, conditions, alternative methods and gaps; verify current sensitive practices against authoritative sources; record disposition separately from supported/context-dependent/heuristic/disputed/unresolved standing | Material guidance qualified and gaps addressed/bounded. No universal constraint inferred merely from practitioner popularity or a single successful production |
| P5 profile/evaluation | Scope/activation, hard/default rules, conventions/assumptions, command and verification changes, quality/precedence/incompatibilities, source→behaviour→test join, exact showcase prompt, distinct reuse brief/fixture, predetermined acceptance and implementation plan | Operational, falsifiable profile. State changed/stable behaviour, intentional traits and defects to reject before implementation; not a metadata-only recipe |
| P6 implement/demonstrate | Self-contained pack/local references/provenance; real showcase README/exact prompt; actual produced artifacts and execution record; behavioural fixtures and local checks | Intended path actually executed with inspectable output. Missing execution is a blocker/unperformed result, not a successful demonstration |
| P7 compare/install/catalogue | Same substantive brief and comparable conditions for core versus core+pack; record revisions/prompts/model/tools/settings/resources/deviations; exercise independent reuse and activation/non-use/precedence/preservation/evaluation/boundary/negative/refinement cases; local checks and fresh consumer installation/use separately | Readiness follows observed evidence. Retain failures/inconclusive/null differences and limits; refine/retest or leave unproven. No automatic project maturity promotion |

The five-book rule allows reuse from core or other packs after checking the **specific contribution**, not five new acquisitions. Shared findings do not become independent corroboration. A supplied-book substitution already expressly authorised in the session need not be authorised again; its identity and scope must be recorded. Do not publish source files, private locations, reconstructed chapters or proprietary examples.

## Production/evaluation integrity

Compare artifacts and decisions, not whether the run says a pack name. Core must receive the actual production need and the same substantive constraints as packed. Retain exact prompts, immutable input/candidate/core/pack identity where available, real commands/results, model/tool settings where relevant, environmental differences and resource limits. Disclose evaluator provenance, answer leakage controls and stochastic/sample limitations. A single example is not evidence of general superiority.

Pack-aware evaluation preserves intentional specialisation—for example, temporary duplicate representations in a justified migration or necessary recovery identity in an event worker—while rejecting data loss, duplicate effects, wrong oracles, unsupported guarantees or authority violations. Repair the violated obligation at the smallest coherent scope. Optional core+project-instructions comparison can test reusable prompting value; it is not permission to give only one arm a richer task.

If a comparison finds no useful difference, it is valid evidence. Revise the affected profile/tests or retain an unproven/deferred entry. Do not quietly weaken acceptance, erase a failed run, report a model simulation as provider integration, or declare external installation from local file validation.

## Packaging, maintenance and status

Necessary installed rules and references must resolve locally in the selected skill/pack. No runtime inheritance from central family docs, research logs, source-checkout tests, other packs or a custom registry. Optional providers/MCPs remain existing capabilities with explicit prerequisites. Native repository tools remain authoritative for builds/tests/deployment; authoring does not introduce a universal executor.

A change to reused source guidance triggers a bounded impact review of consuming profile/tests. Preserve unaffected productions and historical results; mark affected evidence stale instead of rewriting its past outcome. Track research, implementation, evaluation and readiness separately. Catalogue specifications show actual selected/deferred entries and evidence links; a ready claim requires demonstrated behaviour and clean use. The repository's own maturity is a separate Stage 23 assessment.

## Planned authoring verification cases

| Case | Required observable behaviour | Failure to expose |
|---|---|---|
| AW01 new scoped pack | Inspect relevant catalogue/core, justify reusable behaviour, run actual missing research/proof stages | Creates a framework-flavoured prompt without evidence or repeats repository bootstrap unnecessarily |
| AW02 narrow revision | Review valid prerequisites, repair affected claim/profile/test and preserve slug/interfaces/examples | Replaces approved work or reruns all research simply to follow a sequence |
| AW03 supplied-source decision | Honour existing authorised replacement; keep an unanswered new required substitution pending | Treats silence or overall project approval as permission to discard a supplied book |
| AW04 reused evidence | Inspect original locations/reading limits and assess new specialised applicability | Copies five citations or another pack's profile and calls extraction complete |
| AW05 source/execution limitation | Complete useful authorised preparation and report exact missing source/run capability | Invents reading or labels a desk trace/showcase prompt as executed production |
| AW06 differential integrity | Same substantive brief and comparable conditions, real outputs, preserved failed/null results | Weakens core prompt, leaks answer key, rewards labels or cherry-picks one favourable run |
| AW07 independent use | Package required guidance locally and exercise fresh selected consumer use | Works only with source research folders or unadvertised sibling skills |
| AW08 continuation/authority | Continue all authorised requested stages and bounded repairs; stop only for a real missing decision/capability | Stops after “remaining blockers: none”, or treats readiness as permission for an unrequested live action |

These are designed cases, not behavioural runs. Stages 17/19 must implement and exercise the equivalent workflow through actual pack creation/refinement and relevant probes; Stage 20 supplies external installation proof. The two researched pack profiles are useful current authoring outputs, but do not by themselves prove the later installed workflow works.

## Contract conformance

Equivalent domain-native ownership, standalone inputs, all nine workflow-contract fields, catalogue decisions, literal P1–P7 gates, direct-entry/reuse/permission/publication rules, local packaging, evidence integrity, preservation/refinement/status and eight falsifiable authoring probes are specified. No third generic creator skill/runtime or family-repository dependency is introduced. Design exit: **PASS**; implementation/evaluation remain explicitly required later.
