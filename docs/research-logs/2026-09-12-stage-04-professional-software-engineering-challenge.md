# Stage 4 — Professional Software-Engineering Challenge

**Project:** `software-engineering-skills`  
**Bootstrap stage:** 4 — Challenge: Broader Professional Software-Engineering Research  
**Status:** Complete  
**Date:** 12 September 2026  
**Input corpus revision:** `software-engineering-corpus-r2`  
**Domain-model revision:** `software-engineering-domain-model-r1`

## 1. Stage purpose

This stage challenges the five-book model from Stage 3 against broader professional software-engineering evidence.

The objective is not to prove the books right. It is to determine which book-derived ideas survive contact with current standards, empirical research, protocol specifications and strong operating practice, which require qualification, and which should not become reusable core rules.

The research flow is:

```text
Stage 1 domain boundary
+ Stage 3 provisional capability model
+ Stage 3 challenge backlog
        ↓
current standards and bodies of knowledge
+ empirical software-engineering research
+ authoritative operational practice
+ current protocol / platform guidance
        ↓
support / challenge / qualify / reject
        ↓
evidence-qualified software-engineering model
        ↓
inputs for Stage 5 change + contract modelling
```

No coding-agent capability, LLM provider API or current agent product defines the discipline in this stage.

---

## 2. Inputs reviewed

### Repository evidence

- [`2026-09-12-stage-01-project-goal-and-domain-boundary.md`](2026-09-12-stage-01-project-goal-and-domain-boundary.md)
- [`2026-09-12-stage-02-knowledge-coverage-and-five-book-corpus.md`](2026-09-12-stage-02-knowledge-coverage-and-five-book-corpus.md)
- [`2026-09-12-stage-03-five-book-extraction-and-reconciliation.md`](2026-09-12-stage-03-five-book-extraction-and-reconciliation.md)
- [`2026-09-07-software-engineering-skills-new-project-bootstrap-process.md`](2026-09-07-software-engineering-skills-new-project-bootstrap-process.md)
- [`production-skills/docs/bootstrap/domain-research-process.md`](https://github.com/sb-dev/production-skills/blob/main/docs/bootstrap/domain-research-process.md)

### Stage 3 hypothesis under challenge

Stage 3 proposed fourteen capabilities around:

```text
intent + acceptance
system understanding
impact + contracts
architecture scope
safe feedback
incremental implementation
layered verification
review
contract / schema / dependency evolution
failure containment
diagnosis
releasability
commitment authority
sustainable maintenance
```

Stage 3 also identified five high-priority evidence gaps:

1. security engineering integration;
2. debugging and root-cause diagnosis;
3. API / event / schema evolution;
4. observability and operability;
5. performance and concurrency.

Those gaps receive explicit treatment below.

---

# 3. Evidence qualification model

This stage keeps **evidential standing** separate from the eventual disposition of a practice.

A standard can define a required professional concept without proving one implementation technique. An empirical study can challenge a popular heuristic without becoming a universal process. A strong practitioner source may encode a useful method that remains context-dependent.

## 3.1 Source classes

| Source class | Use in this stage | Important limitation |
| --- | --- | --- |
| Current international / national standards and formal specifications | Establish current terminology, lifecycle responsibilities, quality/security obligations and protocol constraints | Usually do not prescribe the best implementation method for a particular project |
| Current authoritative project / platform documentation | Establish actual semantics and operational constraints of protocols, delivery systems and observability mechanisms | May be ecosystem-specific |
| Peer-reviewed empirical research | Test assumptions about review, testing, evolution, technical debt and performance | Results have populations, contexts and threats to validity; do not generalise automatically |
| Mature specialist practitioner material | Provide workflows, heuristics and failure-repair patterns grounded in substantial production experience | Practice may depend on organisation, platform or architecture |
| Five-book corpus | Provides the Stage 3 hypotheses to challenge and useful durable craft knowledge | Corpus is deliberately incomplete and not independent professional validation |

No numeric authority score is assigned. A standard, experiment and practitioner report answer different questions.

## 3.2 Finding states

Every material idea is placed in one of these states:

```text
SUPPORTED
→ strong enough to inform the reusable domain model

QUALIFIED
→ useful under stated conditions; must not become an unconditional rule

HEURISTIC
→ practical decision aid with insufficient basis for mandatory behaviour

DISPUTED
→ credible evidence or current practice materially conflicts

UNRESOLVED
→ evidence is insufficient or scope belongs to later specialist research

REJECTED AS CORE RULE
→ may still be useful locally, but must not be encoded as general software-engineering doctrine
```

## 3.3 Conflict rules

When evidence conflicts:

1. verify whether the sources answer the same question;
2. prefer current specifications for change-sensitive protocol/security semantics;
3. preserve empirical limitations instead of promoting correlations to universal laws;
4. preserve context-specific alternatives when both can be correct;
5. treat organisation-specific thresholds as examples, not defaults;
6. leave genuinely unresolved claims unresolved;
7. do not replace a project-specific risk policy with generic research.

---

# 4. Current professional baseline

## 4.1 SWEBOK V4.0a — domain map

The IEEE Computer Society identifies SWEBOK V4 as the current Software Engineering Body of Knowledge and explicitly describes software engineering as an evolving discipline whose accepted practice changes as technology, security needs and professional responsibilities change.

Source:

- https://www.computer.org/education/bodies-of-knowledge/software-engineering
- https://www.computer.org/education/bodies-of-knowledge/software-engineering/v4

**Finding:** Stage 1 was correct not to reduce Software Engineering to code generation. Requirements, architecture/design, construction, testing, maintenance, configuration, quality, process and related engineering responsibilities form a coherent professional landscape.

**Disposition:** `SUPPORTED`.

## 4.2 ISO/IEC/IEEE 12207:2026 — lifecycle without a mandatory methodology

The new 2026 edition establishes a common software-lifecycle process framework spanning conception, development, operations, support, maintenance and retirement. It explicitly permits concurrent, iterative, recursive and incremental application and does not mandate a lifecycle model, methodology or implementation technique.

Source:

- https://www.iso.org/standard/90219.html

**Challenge to Stage 3:** the Stage 3 evidence-to-behaviour sequence is credible as a change model, but it must not become a compulsory waterfall-like lifecycle. Real work loops, omits irrelevant artefacts, and revisits earlier decisions when evidence changes.

**Disposition:** `SUPPORTED WITH QUALIFICATION` — retain a change lifecycle, not a ceremony sequence.

## 4.3 Requirements and acceptance — ISO/IEC/IEEE 29148:2018

ISO/IEC/IEEE 29148 remains the current requirements-engineering standard as of this stage, although ISO has started its revision. It treats requirements engineering as lifecycle work and defines requirements processes and information items rather than assuming a one-time requirements phase.

Source:

- https://www.iso.org/standard/72089.html

**Challenge to the book corpus:** Wiegers/Hokanson’s iterative requirements framing is consistent with the standard. The book’s specific artefacts, decision rules and baselining practices remain optional methods rather than universal outputs.

**Disposition:**

- problem / outcome / constraint clarification: `SUPPORTED`;
- testable acceptance conditions: `SUPPORTED`;
- heavyweight baselines or a fixed change-control board: `REJECTED AS CORE RULE`;
- a lightweight explicit current agreement that can change: `SUPPORTED`.

## 4.4 Architecture — ISO/IEC/IEEE 42010:2022

ISO/IEC/IEEE 42010 distinguishes an architecture from its architecture description and standardises the concepts used to express architecture descriptions, viewpoints and model kinds. It explicitly does **not** prescribe an architecting process, method, notation or tool.

Source:

- https://www.iso.org/standard/74393.html

**Challenge to the corpus:** Richards/Ford’s contextual trade-off framing is compatible with professional architecture practice, but their named styles, ratings, architecture laws and fitness-function techniques are practitioner methods, not normative truths.

**Disposition:**

- architecture is contextual and concern-driven: `SUPPORTED`;
- retain decision rationale for material structural choices: `SUPPORTED`;
- use viewpoints/models only when they answer stakeholder concerns: `SUPPORTED`;
- universal style rankings: `REJECTED AS CORE RULE`;
- fitness functions: `QUALIFIED HEURISTIC` when an important characteristic can be meaningfully and economically observed.

## 4.5 Product quality — ISO/IEC 25010:2023

ISO/IEC 25010:2023 defines a product-quality model with nine characteristics and positions the model as a reference for requirements, design objectives, testing objectives, acceptance criteria and quality evaluation.

Source:

- https://www.iso.org/standard/78176.html

**Challenge to the corpus:** Stage 1 and Stage 3 correctly separated quality dimensions. No one metric, passing test suite or code-review approval proves general software quality.

**Disposition:** `SUPPORTED`.

Core implication:

```text
claim
→ name the quality property
→ define applicable evidence
→ avoid substituting a different quality signal
```

## 4.6 Testing — ISO/IEC/IEEE 29119 + empirical testing evidence

ISO/IEC/IEEE 29119 provides general testing concepts, processes, documentation relationships and test-design techniques without requiring one universal unit/integration/system ratio.

Sources:

- https://www.iso.org/standard/81291.html
- https://committee.iso.org/sites/jtc1sc7/home/projects/flagship-standards/isoiecieee-29119-series.html

Empirical testing evidence also challenges simplistic proxies. Research has found that raw coverage is not a strong standalone proxy for test effectiveness, while mutation-based evidence can help reveal weaknesses but is itself an imperfect proxy for real fault detection.

Sources:

- Inozemtseva & Holmes, *Coverage is not strongly correlated with test suite effectiveness*, ICSE 2014, DOI `10.1145/2568225.2568271`
- Chekam et al., *An Empirical Study on Mutation, Statement and Branch Coverage Fault Revelation*, ICSE 2017: https://discovery.ucl.ac.uk/id/eprint/10058915/
- Papadakis et al., *Are Mutation Scores Correlated with Real Fault Detection?*, ICSE 2018, DOI `10.1145/3180155.3180183`

**Challenge to Feathers / Google:**

- fast local tests are valuable for change feedback;
- high-level tests are required for integration and emergent behaviour;
- isolation can improve speed and localisation but can also remove realistic failure modes;
- test doubles are a technique, not a default architecture;
- code coverage is useful diagnostic information, not sufficient acceptance evidence;
- mutation testing is a possible test-quality probe, not a universal gate.

**Disposition:** risk-based layered verification is `SUPPORTED`; fixed test pyramids/ratios are `REJECTED AS CORE RULE`.

## 4.7 Code review — empirical and practitioner evidence

Google’s ICSE case study used interviews, a survey and logs from roughly nine million reviewed changes to examine modern code review in a large industrial environment. Current Google guidance evaluates design, functionality, complexity, tests, readability, documentation and context rather than defect finding alone.

Sources:

- https://research.google/pubs/modern-code-review-a-case-study-at-google/
- https://google.github.io/eng-practices/review/
- https://google.github.io/eng-practices/review/reviewer/looking-for.html

Google also recommends small, self-contained changes but explicitly says there is no hard universal line-count rule.

Source:

- https://google.github.io/eng-practices/review/developer/small-cls.html

**Challenge to Stage 3:** small coherent changes survive the challenge; exact limits such as `200 LOC` do not.

**Disposition:**

- independent review as a correctness/comprehension/health control: `SUPPORTED` where the project uses review;
- small coherent review units: `SUPPORTED HEURISTIC`;
- fixed line-count threshold: `REJECTED AS CORE RULE`;
- specialist review for security/concurrency/privacy/etc. when ordinary reviewer expertise is insufficient: `SUPPORTED`.

## 4.8 Maintenance and evolution

ISO/IEC/IEEE 12207:2026 explicitly includes maintenance and retirement across the lifecycle. Google’s sustainability framing and software-evolution research support treating long-lived software as continually changing rather than as a finished artefact.

Sources:

- https://www.iso.org/standard/90219.html
- Lehman & Ramil, *Software evolution—Background, theory, practice*, DOI `10.1016/S0020-0190(03)00382-X`

**Challenge to Stage 3:** sustainable change capability is well supported, but specific organisation-level policies such as a monorepo or one-version rule cannot be promoted to general doctrine.

**Disposition:** `SUPPORTED` for sustainable evolution; Google-specific implementation policies remain `QUALIFIED`.

## 4.9 Configuration management and software configuration

Current professional practice treats code, configuration, build/release definitions and dependency state as part of the controlled software system. DORA recommends version control for production artefacts including application and system configuration. ISO/IEC/IEEE 12207 provides the lifecycle framework within which configuration/change control is applied.

Sources:

- https://dora.dev/capabilities/continuous-delivery/
- https://www.iso.org/standard/90219.html

**Challenge to Stage 3:** configuration is not a late deployment detail. A configuration-only change can be a software change with the same need for review, verification and rollback evidence as code.

**Disposition:** `SUPPORTED`.

## 4.10 Engineering process and change size — DORA

DORA’s current research model retains continuous delivery, CI, small batches, version control, database change management, observability, reliability, pervasive security and test automation as repeatedly supported capabilities.

Sources:

- https://dora.dev/research/
- https://dora.dev/capabilities/continuous-integration/
- https://dora.dev/capabilities/working-in-small-batches/
- https://dora.dev/capabilities/continuous-delivery/

DORA’s 2026 material now exposes five delivery metrics in the Quick Check, including deployment rework rate, whereas some conservative Core-model surfaces still show the older four-metric formulation. The important bootstrap lesson is not the current count; it is that delivery measurement itself evolves.

Sources:

- https://dora.dev/guides/dora-metrics/
- https://dora.dev/insights/dora-metrics-history/

**Disposition:**

- small batches and fast feedback: `SUPPORTED`;
- mandatory continuous deployment: `REJECTED AS CORE RULE`;
- continuous **delivery** / deployability as a quality for releasable software: `SUPPORTED`;
- hard-coding current DORA benchmark bands or metric counts into a reusable skill: `REJECTED`.

## 4.11 Secure software development — NIST SSDF, OWASP ASVS and OpenSSF

NIST SP 800-218 SSDF v1.1 remains the current **final** SSDF. NIST published SSDF v1.2 as SP 800-218 Rev. 1 in December 2025, but it remains a draft at this stage. The final framework expects secure practices to be integrated into the SDLC rather than performed only as a final scan.

Sources:

- https://csrc.nist.gov/pubs/sp/800/218/final
- https://csrc.nist.gov/projects/ssdf/publications

OWASP ASVS 5.0.0 is the current stable application-security verification standard and provides testable application-security requirements.

Source:

- https://owasp.org/www-project-application-security-verification-standard/

Software supply-chain risk also requires evidence beyond source-code scanning. SLSA v1.2 defines provenance as verifiable information about where, when and how software artefacts were produced. OpenSSF guidance recommends evaluating dependencies before adoption and treating dependency provenance, maintenance and security posture as engineering inputs.

Sources:

- https://slsa.dev/spec/v1.2/provenance
- https://best.openssf.org/Concise-Guide-for-Evaluating-Open-Source-Software.html

**Challenge to Stage 3:** security cannot remain merely a quality-attribute row inside generic verification. It needs an explicit reusable capability that knows when to invoke specialist security authority.

**Disposition:** add an explicit secure-development and supply-chain capability.

## 4.12 CI and continuous delivery

DORA distinguishes continuous delivery from continuous deployment. Continuous delivery means keeping changes releasable on demand and applies to services, firmware, mobile applications, schema changes, mainframes and other software forms.

Source:

- https://dora.dev/capabilities/continuous-delivery/

**Challenge to Stage 3:** `preserve releasability` is broader and more portable than `deploy every change`.

**Disposition:** `SUPPORTED`.

## 4.13 Observability and operability

OpenTelemetry’s current signal model includes traces, metrics, logs and profiles, with context propagation linking relevant telemetry. It describes signal semantics, not an obligation to instrument everything.

Source:

- https://opentelemetry.io/docs/concepts/signals/

Google SRE troubleshooting treats diagnosis as a learnable hypothesis-driven process. Runtime telemetry is useful only when it can discriminate hypotheses and reveal meaningful system state.

Source:

- https://sre.google/sre-book/effective-troubleshooting/

**Challenge to Stage 3:** observability deserves an explicit capability, but no fixed vendor, mandatory signal set or telemetry volume belongs in core knowledge.

**Disposition:** add proportional diagnosability/operability capability.

## 4.14 Performance

Dean and Barroso’s *The Tail at Scale* demonstrates why latency distributions, especially tail behaviour, matter in large interactive systems and why averages can conceal material user-visible degradation.

Source:

- https://research.google/pubs/the-tail-at-scale/

Google SRE recommends load testing to establish actual capacity and failure behaviour rather than inheriting historic capacity assumptions.

Source:

- https://sre.google/sre-book/service-best-practices/

**Challenge to Stage 3:** `measure before optimisation` survives, but “performance” needs change-specific workload, percentile/distribution and resource evidence. Universal benchmark thresholds do not.

**Disposition:** add explicit performance/concurrency evidence capability.

## 4.15 Reliability and resilience

Google SRE and AWS production guidance independently support several `Release It!` concepts: timeouts, bounded retries, exponential backoff with jitter, overload protection, load shedding, finite queues, isolation and controlled degradation.

Sources:

- https://sre.google/sre-book/addressing-cascading-failures/
- https://sre.google/sre-book/service-best-practices/
- https://aws.amazon.com/builders-library/
- https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/

Important qualifications:

- retries at multiple layers can multiply load catastrophically;
- side-effecting operations need idempotency or an equivalent duplicate-control strategy before automatic retry is safe;
- circuit breakers introduce modal behaviour and are not automatically preferable to retry budgets/token buckets;
- queues can move a failure from immediate overload to stale backlog if arrival rate exceeds processing capacity;
- managed runtimes, service meshes and SDKs may own some mechanism implementation, but the application still owns the required semantics and must avoid duplicate controls across layers.

**Disposition:** resilience concepts are `SUPPORTED`; particular pattern selection is context-dependent.

## 4.16 Debugging and incident-driven repair

Google SRE describes troubleshooting as hypothesis generation and testing from observations. It explicitly separates urgent mitigation from later root-cause work: during severe impact, first stop the damage while preserving evidence where possible.

Source:

- https://sre.google/sre-book/effective-troubleshooting/

Git provides a deterministic bisection mechanism for regressions when a reliable good/bad test exists.

Source:

- https://git-scm.com/docs/git-bisect

**Challenge to Stage 3:** “root cause before repair” is too absolute for active incidents. Correct rule:

```text
if harm is ongoing
→ mitigate / contain first
→ preserve diagnostic evidence
→ then isolate causal mechanism
→ apply durable repair + regression evidence

if harm is not ongoing
→ reproduce / localise before changing broad scope
```

**Disposition:** Stage 3 C11 is revised accordingly.

## 4.17 Concurrency

Concurrency defects are often timing-sensitive and can disappear under ordinary reproduction. Dynamic race detection is therefore a specialised cheap-to-medium-cost check when the language/runtime supports it. Clang ThreadSanitizer, for example, instruments programs to detect data races but carries substantial runtime and memory overhead.

Source:

- https://clang.llvm.org/docs/ThreadSanitizer.html

**Challenge to Stage 3:** concurrency cannot be reduced to normal unit-test success. Review the synchronization model and invariants; use deterministic tests where possible, race/deadlock detectors where available, and representative stress/soak evidence when risk warrants it.

**Disposition:** explicit performance/concurrency capability added.

## 4.18 Technical debt and refactoring

Empirical technical-debt research shows that teams use multiple strategies and that prioritisation remains strongly contextual. Systematic reviews have not established a universal metric that determines when debt should outrank feature or defect work.

Sources:

- *How do software development teams manage technical debt?*, Journal of Systems and Software 120 (2016), DOI `10.1016/j.jss.2016.05.018`
- Lenarduzzi et al., *Technical Debt Prioritization: State of the Art*, systematic review: https://arxiv.org/abs/1904.12538

**Challenge to Stage 3:** “technical debt reduction” must require an evidenced payoff or risk reduction. Code smells, static-analysis counts or debt scores alone are not authority for speculative refactoring.

**Disposition:** `SUPPORTED WITH QUALIFICATION`.

---

# 5. Book-claim challenge register

| Book-derived claim / method | Broader evidence | Disposition | Core implication |
| --- | --- | --- | --- |
| Clarify problem before solution | ISO 29148 lifecycle requirements + professional requirements practice | **SUPPORTED** | Do not implement an ambiguous externally visible policy without clarifying the intended outcome/authority |
| Make quality attributes measurable | ISO 25010 + architecture/requirements standards | **SUPPORTED** | Express material quality claims in observable terms appropriate to context |
| Requirements baseline as shared agreement | ISO 29148 supports managed requirements; 12207 supports iterative lifecycle | **QUALIFIED** | Preserve an explicit current contract; do not require heavyweight baseline ceremony |
| Choose prototype fidelity by uncertainty | Compatible with iterative lifecycle and cheap-learning practice | **SUPPORTED HEURISTIC** | Define what must be learned and whether prototype is throwaway or evolutionary |
| Architecture decisions are trade-offs | ISO 42010 supports concern/viewpoint-based description; no universal architecting method | **SUPPORTED** | Compare material alternatives in context; retain rationale |
| Architecture fitness functions | Strong practitioner practice; not mandated by 42010 | **QUALIFIED HEURISTIC** | Use when a characteristic is testable/observable and the check has acceptable cost |
| Default to synchronous communication | Reliability evidence shows sync chains can amplify runtime coupling; async adds its own failure/consistency/backlog costs | **REJECTED AS UNIVERSAL DEFAULT** | Choose interaction mode from semantic, latency, consistency, failure and operability constraints |
| “Legacy code is code without tests” | Useful Feathers framing but not a professional definition of legacy systems | **REJECTED AS DEFINITION** | Lack of trustworthy feedback is a change-risk signal, regardless of system age |
| Characterisation tests preserve behaviour | Testing practice supports behaviour capture; risk exists of freezing accidental behaviour | **QUALIFIED** | Use when current behaviour is the best available oracle; distinguish required contract from incidental behaviour |
| Fast isolated unit tests are the core safety net | Testing standards and modern practice require multiple test scopes; larger tests catch integration/emergent failures | **QUALIFIED** | Prefer fastest evidence that can detect the target risk; layer broader tests for residual risks |
| Use seams/dependency breaking to gain testability | Still useful and language-independent at concept level | **SUPPORTED HEURISTIC** | Introduce the smallest testability boundary needed; do not distort production design gratuitously |
| Small changes are safer/easier to review | Google empirical/practice evidence + DORA small-batch research | **SUPPORTED** | Prefer small coherent reversible batches; no universal LOC threshold |
| Prefer state testing over interaction testing | Implementation-coupled mocks can be brittle; protocol/side-effect behaviour sometimes requires interaction assertions | **QUALIFIED** | Test externally meaningful outcomes by default; test interactions only when interaction itself is contractual/risky |
| Observable behaviour can become a de facto contract (Hyrum’s Law) | API evolution evidence and protocol history strongly support hidden-consumer risk | **SUPPORTED AS PRACTICAL LAW, NOT FORMAL GUARANTEE** | Inspect consumers and observed behaviour before compatibility-sensitive changes |
| One-version / monorepo policies | Google-specific solution to Google-scale evolution | **REJECTED AS CORE RULE** | Core owns compatibility and dependency reasoning, not one repository/versioning model |
| Timeouts, backoff, jitter, load shedding, isolation | Google SRE + AWS current guidance | **SUPPORTED** | Select and test failure controls from actual failure modes; avoid layered retry amplification |
| Circuit breaker as default remote-call protection | AWS documents trade-offs and modal recovery problems | **QUALIFIED** | One possible control; compare with retry budgets, fail-fast, isolation and platform-native controls |
| Liberal acceptance / Postel’s Law for API evolution | IETF RFC 9413 documents protocol decay and ecosystem harm from over-broad tolerance | **DISPUTED / REJECTED AS UNIVERSAL RULE** | Be explicit about accepted contracts; tolerate deviations deliberately and temporarily when required for interoperability |
| Observability = logs/metrics/traces | Current OpenTelemetry also includes profiles; needs are problem-specific | **QUALIFIED** | Instrument what is needed to answer operational questions; no fixed signal/vendor checklist |
| Refactor whenever code smells appear | Technical-debt research lacks a universal prioritisation metric | **REJECTED** | Refactor when change cost, risk, quality or explicit objective justifies it |

---

# 6. Modern API, event and schema evolution

Stage 3 correctly identified contract evolution as a first-class capability but needed stronger current evidence.

## 6.1 Parallel / expand-migrate-contract change

For published interfaces and persistent schemas, a breaking change can often be made safer by separating compatibility phases:

```text
expand
→ introduce new representation/capability compatibly

migrate
→ move consumers/data while old + new coexist

contract
→ remove old representation only after evidence shows it is no longer needed
```

Source:

- https://martinfowler.com/bliki/ParallelChange.html
- https://martinfowler.com/articles/evodb.html

**Standing:** `SUPPORTED PRACTICE`, not mandatory when all consumers can truly move atomically.

## 6.2 Wire/schema compatibility is representation-specific

Protocol Buffers documents concrete wire-safe and wire-unsafe evolution rules and warns that clients and servers are not updated at exactly the same time; rollback also creates mixed-version periods.

Sources:

- https://protobuf.dev/best-practices/dos-donts/
- https://protobuf.dev/programming-guides/proto2/

**Core implication:** “backward compatible” is meaningless without naming the contract form:

```text
source compatibility
binary compatibility
wire compatibility
semantic compatibility
stored-data compatibility
operational compatibility
```

Stage 5 must model these separately.

## 6.3 Versioning is not a substitute for compatibility reasoning

Google’s API guidance gates breaking/deprecated behaviour through explicit API versions, but versioning still requires lifecycle policy and migration.

Source:

- https://google.aip.dev/185

**Standing:** `QUALIFIED` — use explicit versions when the public contract requires it; do not version every internal change by default.

## 6.4 Postel’s Law needs active-maintenance qualification

RFC 9413 documents how silently accepting malformed or divergent behaviour can entrench quirks and create protocol decay. It advocates active maintenance rather than permanent tolerance where implementations/specifications can be updated.

Source:

- https://datatracker.ietf.org/doc/rfc9413/

**Core rule candidate:**

> Be deliberately compatible, not accidentally permissive.

---

# 7. Security, dependency and software-supply-chain model

Stage 3 did not give security sufficient independent structure.

## 7.1 Secure-development loop

A generic software-engineering change should ask:

```text
Does this change alter a trust boundary, identity/auth decision,
secret, parser/input surface, dependency, privilege, persistence,
network exposure, sensitive data path or security control?
```

If no, ordinary secure coding and dependency hygiene still apply.

If yes, stronger evidence may be required:

```text
security requirement
→ threat / abuse-case analysis at suitable depth
→ secure design / implementation
→ targeted verification
→ specialist review when risk exceeds general engineering competence
→ release evidence
```

NIST SSDF provides the lifecycle anchor; ASVS supplies concrete verification requirements for applicable web/application controls.

## 7.2 Dependency changes are trust decisions

Before introducing or upgrading a dependency, engineering should consider:

- whether the dependency is necessary;
- authentic source and maintenance health;
- direct and transitive compatibility;
- known vulnerabilities and update path;
- licence/project constraints owned elsewhere when applicable;
- build/release integrity;
- blast radius if compromised;
- provenance/attestation when the project requires it.

OpenSSF and SLSA provide current source/provenance guidance.

## 7.3 Vulnerability repair differs from ordinary feature work

A security fix may require restricted disclosure and coordination, but the engineering mechanics remain evidence-driven:

```text
vulnerability evidence
→ assess affected versions/surfaces
→ contain exploitation if active
→ smallest correct repair
→ negative + regression security tests
→ dependency/provenance update if relevant
→ coordinated release / disclosure handoff
→ recurrence/root-cause prevention where justified
```

The repository should not own organisation-specific disclosure policy.

---

# 8. Debugging and repair model

The book corpus overemphasised “root cause before repair” as one sequence. Professional incident practice requires two modes.

## 8.1 Non-urgent defect diagnosis

```text
reproduce or establish observable failure
→ reduce/minimise when useful
→ establish expected vs actual behaviour
→ collect discriminating evidence
→ form hypotheses
→ test cheapest/high-information hypothesis
→ bisect/history analysis when applicable
→ localise owning layer
→ repair smallest sufficient cause
→ add regression evidence
→ verify no broader contract damage
```

## 8.2 Active incident / ongoing damage

```text
assess severity + blast radius
→ stop bleeding / contain / rollback / disable / shed load
→ preserve evidence where feasible
→ restore acceptable service or data safety
→ investigate causal chain
→ durable repair
→ regression / load / fault evidence
→ follow-up on recurrence mechanisms
```

This avoids the dangerous rule that an engineer must understand the full root cause while data is being corrupted or an outage is expanding.

## 8.3 Causality discipline

Operational correlation is not automatically causation. A useful diagnosis should identify evidence that discriminates competing explanations. Useful tools may include:

- minimal reproducers;
- targeted logs/traces/metrics/profiles;
- change-history comparison;
- `git bisect` with an executable good/bad oracle;
- controlled fault or load experiments;
- race/deadlock detectors;
- data invariant checks;
- dependency health evidence.

The core should teach selection of evidence, not a fixed debugging toolchain.

---

# 9. Performance and concurrency model

## 9.1 Performance repair

Performance work should begin with a falsifiable performance problem, not an intuition that code “looks slow”.

```text
performance requirement / regression
→ define representative workload + environment
→ capture baseline distribution + resource profile
→ identify bottleneck / critical path
→ change smallest responsible component
→ rerun equivalent measurement
→ inspect downstream trade-offs
→ retain regression benchmark only if it can detect the material failure economically
```

Evidence may include:

- latency distribution / percentiles rather than average alone;
- throughput at a stated concurrency/load;
- CPU, memory, allocation, I/O, network and storage profiles;
- queue age/depth;
- target-device/runtime measurements;
- capacity and overload breakpoints.

## 9.2 Concurrency repair

Concurrency work should identify the invariant being violated:

```text
lost update
race
atomicity violation
ordering violation
deadlock / livelock
starvation
unsafe publication
duplicate execution
unbounded concurrency
```

Candidate evidence:

- deterministic reproduction when possible;
- race detector / sanitizer;
- model/invariant tests for critical algorithms;
- stress and schedule variation;
- timeout/deadlock diagnostics;
- thread/task dumps;
- review by someone competent in the concurrency model.

A concurrency change that merely “stops failing in this run” is not adequate evidence.

---

# 10. Role and responsibility map

Roles vary by organisation; responsibilities matter more than job titles.

| Responsibility | Software Engineering owns | Typical adjacent authority / handoff |
| --- | --- | --- |
| Product / requirement intent | technical clarification, feasibility, acceptance implications | Product/BA/business authority owns product priority and policy |
| Architecture | software structural decisions necessary to realise qualities safely | Enterprise/platform architecture where scope exceeds the software/product boundary |
| Construction | implementation, local design, refactoring, code health | specialist domain implementation when the domain requires separate expertise |
| Verification | developer-owned tests and change-specific evidence | QA/testing specialists for independent/broader integrated assurance |
| Security | secure implementation, dependency hygiene, change-level threat awareness, targeted verification | security engineering for high-risk threat modelling, penetration/adversarial assurance, policy/control authority |
| Reliability | software failure semantics, resilience implementation, diagnostic hooks | SRE/operations for production SLO governance, incident command, capacity/operational policy |
| Platform / infrastructure | application-facing contracts, packaging/config needs | platform engineering owns shared platform capability and infrastructure product |
| Data/schema | application-owned transactional schema/contract evolution | data engineering/DB specialist when shared analytical/platform data responsibility dominates |
| Release readiness | build/package/config/migration/rollback evidence | release/operations authority owns production rollout policy when separately governed |
| Technical documentation | correctness of software/API/change rationale | technical-writing discipline owns broader documentation-product structure/editorial quality |

The reusable core should trigger a handoff when the required assurance exceeds general software-engineering competence, not because a particular job title exists.

---

# 11. Real software-change workflow study

The table below captures **workflow candidates**, not mandatory universal sequences. Stage 5 will turn these into the change/contract taxonomy and Stage 6 will design the final engineering workflow.

| Change class | Inputs + working artefacts | Main uncertainty + cheap checks | Commitment / review points | Expensive / representative checks | Common failure + smallest repair | Handoff / quality target |
| --- | --- | --- | --- | --- | --- | --- |
| **Small feature change** | requirement/issue, acceptance criteria, affected code/tests, local contracts | Is requested behaviour clear? What existing behaviour can it affect? Inspect call/data flow; focused tests/type/static checks | product ambiguity; external contract change; code review | affected integration/E2E; target runtime if behaviour is environment-sensitive | scope creep, wrong assumption, hidden regression → revert to intent/impact and patch only responsible slice | product for policy; QA for independent acceptance; correct + compatible + maintainable |
| **Bug fix** | defect report, reproducer, telemetry/logs, suspected code, prior behaviour | Is failure reproducible? Which layer owns it? Reproducer, targeted logging, history/bisect, focused test | user-visible semantic decision; broad workaround; risky rollback | integration/system regression; production-like reproduction where environment-sensitive | symptom patch, flaky reproducer, unrelated rewrite → isolate causal condition and add regression oracle | SRE if active incident; product if expected behaviour ambiguous; defect no longer reproducible and regression is detectable |
| **Refactor** | change objective, affected module, existing tests/contracts, debt/risk evidence | Can behaviour be held invariant? Focused tests, compile/type/static checks | broad structural change or externally visible change; code/architecture review | broader regression/performance when structure affects runtime properties | “cleanup” changes behaviour or expands scope → split/refine and restore invariant | architecture review only when structural consequence warrants it; lower future change cost without contract drift |
| **API/interface change** | published contract, consumers, usage telemetry/search, deprecation policy, version constraints | Which source/binary/wire/semantic behaviours are depended upon? Consumer search and compatibility tests | breaking semantic change; version/deprecation decision; owner approval | mixed-version integration, consumer contract suites, rollout/rollback | hidden consumer break, version explosion, permissive parser lock-in → expand/migrate/contract or restore compatibility | consumer owners/product/API governance; explicit compatibility and migration evidence |
| **Database/schema change** | schema/data invariants, migrations, application versions, data volume, rollback/recovery plan | Will old/new app versions coexist? Is change locking/destructive? Dry-run migration, schema lint, local representative data | destructive/lossy change; long lock; irreversible migration | production-scale migration timing, restore/recovery rehearsal, mixed-version deployment | coordinated deploy requirement, data loss, long lock → additive migration, backfill, dual-read/write only when justified, delayed removal | DB/platform specialist for high-risk operations; integrity + availability + recoverability |
| **Dependency/platform upgrade** | dependency graph, changelog/advisory, compatibility/support policy, provenance | Direct/transitive breakage? Security urgency? Build/test affected dependents; static/API compatibility checks | major/breaking upgrade; unsupported platform; new supply-chain trust | broad integration, platform matrix, performance/security regression | diamond/version conflict, hidden behaviour change, stale transitive dependency → incremental upgrade, adapters or selected replacement | security for vulnerable dependency; platform owner for runtime change; supported and maintainable dependency state |
| **Security fix** | advisory/report, affected versions/surfaces, threat/control, exploit evidence if authorised | Is exposure real and active? Which trust boundary/control failed? Reproduce safely, targeted security test/scanner | secret disclosure, auth/crypto/trust boundary, risk acceptance | penetration/adversarial test, dependency/provenance verification, production-like control validation | superficial patch, bypass remains, regression elsewhere → repair control/root cause and add abuse-case regression | security engineering/disclosure authority; vulnerability removed without weakening adjacent controls |
| **Performance repair** | target SLO/budget/requirement, workload, baseline, profile | Is regression real and representative? Profile/benchmark under controlled workload | material architectural trade-off, extra cost, quality compromise | load/capacity test, tail-latency analysis, target hardware/device | optimize non-bottleneck, benchmark bias, average hides tail → restore representative baseline and profile causal hotspot | SRE/capacity/product if trade-off affects cost/experience; measurable improvement without correctness regression |
| **Concurrency repair** | failing invariant, thread/task model, traces/dumps, reproducer | Race/order/deadlock? race detector, deterministic test, schedule stress | synchronization architecture or consistency semantics | high-concurrency stress/soak, fault/time tests | timing-sensitive “fix” only masks symptom → state invariant explicitly and verify under varied scheduling | concurrency/runtime expert when needed; invariant preserved without new deadlock/starvation |
| **Legacy-system change** | observed behaviour, available docs/tests, callers, build/release constraints | What is actually contractual? Can code be put under feedback safely? characterization/contract tests, effect analysis | broad rewrite, unsupported runtime, unclear business behaviour | representative regression and environment/build tests | freezing accidental behaviour or unsafe dependency break → target relevant behaviour, introduce smallest seam/adapter | product/domain owners for undocumented semantics; safe incremental improvement and preserved required behaviour |
| **Cross-service change** | API/event contracts, topology, ownership, SLOs, retry/timeout semantics, traces | Which services/versions coexist? Failure propagation? contract checks, trace path, local simulations | cross-team contract break; retry ownership; consistency semantics | integration/fault/load testing across representative topology | retry amplification, partial rollout mismatch, event/schema incompatibility → compatibility phase, single retry responsibility, bounded failure | service owners/SRE/platform; end-to-end semantic compatibility + bounded failure |
| **Release preparation** | immutable artefact, source revision, config, dependency/provenance, migrations, test evidence, release notes | Is exact candidate releasable? Build/package/signature/config verification, smoke test | release authority, known waived failure, irreversible rollout | staged/canary/target-platform validation, rollback/recovery check | rebuilt artefact differs, config skew, untested migration → promote same artefact, fix config/migration, regenerate evidence | release/SRE/app-store/regulatory authority as applicable; reproducible releasability, not merely local success |

---

# 12. Failure and repair taxonomy candidates

These categories are candidates for Stage 6/7 workflow and evaluation design.

| Failure class | Diagnostic question | Typical evidence | Smallest sufficient repair target |
| --- | --- | --- | --- |
| Intent / requirement mismatch | Did we build the wrong behaviour? | acceptance conflict, stakeholder decision, requirement trace | intent/acceptance contract before implementation rewrite |
| Local implementation defect | Does implementation violate an agreed behaviour? | focused reproducer, failing test, static/runtime evidence | responsible code path |
| Test defect / weak oracle | Is the test wrong or unable to detect the claimed failure? | mutation/reproduction comparison, test inspection | test/oracle or test fixture |
| Compatibility / contract break | Which consumer or persisted/wire contract changed? | consumer tests/search, schema/protocol diff, mixed-version run | compatibility layer/migration/version boundary |
| Architecture mismatch | Is a required quality structurally impossible or being eroded? | characteristic evidence, dependency/coupling/topology analysis | smallest affected architecture boundary |
| Data / migration failure | Are invariants, availability or recoverability at risk? | migration rehearsal, invariant checks, restore evidence | migration sequence/data transformation |
| Dependency / supply-chain failure | Is external software incompatible, vulnerable or untrusted? | dependency graph, advisory, provenance, verification | dependency/version/source/build step |
| Security-control failure | Which trust boundary/control assumption failed? | threat/abuse case, security test, audit evidence | security control + causal design/implementation weakness |
| Performance/resource regression | Which resource/critical path causes the material regression? | profiles, distributions, load/capacity measurements | measured hotspot/bottleneck |
| Concurrency/ordering defect | Which invariant fails under interleaving? | race detector, trace, deterministic schedule/stress | synchronization/state-transition boundary |
| Reliability/overload propagation | Why does one failure amplify? | retry/queue/resource metrics, fault test, call graph | retry/load/isolation/backpressure boundary |
| Configuration/release mismatch | Does deployed candidate differ from tested assumptions? | config/version/artefact diff, build provenance | configuration/promotion/release definition |
| Observability gap | Can we distinguish plausible causes? | missing correlation/telemetry/context | smallest diagnostic signal needed, not instrumentation sprawl |
| Process/authority failure | Was a consequential decision made without the owning authority/evidence? | decision history, change description, approval policy | decision path/guardrail rather than code regeneration |

A single incident can contain several classes. Repair should follow causality rather than whichever symptom appeared first.

---

# 13. Evidence-qualified capability model

Stage 4 retains the structure of the Stage 3 model but revises and expands it from 14 to **17 provisional capabilities**.

This is still a capability model, **not** the final skill list.

## C1 — Clarify engineering intent, boundaries and acceptance

Determine what observable change is required, which policy decisions are external to Software Engineering, and what evidence will show success.

**Standing:** `SUPPORTED`.

## C2 — Inspect the real software system before editing

Discover executable architecture, conventions, dependencies, configuration, tests, build/release path and relevant runtime evidence instead of inferring from filenames or assumptions.

**Standing:** `SUPPORTED`.

## C3 — Map change impact and effective contracts

Trace affected callers/consumers, data, interfaces, configuration, runtime assumptions and implicit observable behaviour. Distinguish contract forms rather than using “compatibility” generically.

**Standing:** `SUPPORTED`, strengthened by API/protocol evidence.

## C4 — Decide local design versus architectural change

Escalate design depth according to consequence, reversibility, blast radius and quality impact. Preserve the smallest coherent structural scope.

**Standing:** `SUPPORTED`.

## C5 — Establish an adequate feedback boundary

Create or locate the cheapest feedback mechanism capable of detecting the relevant regression: existing unit/contract/integration test, characterization test, seam, simulator, static analysis, reproducible script or other oracle.

**Standing:** `SUPPORTED WITH CONTEXT`; characterization/unit testing is not mandatory for every risk.

## C6 — Implement and refactor in coherent reversible increments

Prefer small single-purpose changes, preserve unrelated behaviour, separate mechanical refactoring from semantic change where it improves reviewability, and keep each intermediate state valid when practical.

**Standing:** `SUPPORTED`; no universal LOC limit.

## C7 — Select verification according to residual risk

Use a cheap-first ladder, but choose test/check scope by the defect class it can actually detect. Coverage, mutation score or test count are supporting diagnostics rather than proof of correctness.

**Standing:** `SUPPORTED`, materially refined.

## C8 — Review correctness, comprehension and software health

Review design, functionality, complexity, tests, compatibility, concurrency/security implications and relevant architecture characteristics separately. Route specialist risks to competent reviewers.

**Standing:** `SUPPORTED`.

## C9 — Evolve interfaces, persisted data, dependencies and configuration safely

Identify compatibility type, plan coexistence/migration, preserve rollback/recovery constraints, control deprecation/removal and verify configuration/dependency state as software artefacts.

**Standing:** `SUPPORTED`, materially strengthened.

## C10 — Design and verify bounded failure behaviour

Analyse integration points, overload, queues, retries and resource exhaustion. Select timeouts, bounded retries, jitter, idempotency, isolation, backpressure, load shedding, degradation or platform-native equivalents from the actual failure model.

**Standing:** `SUPPORTED WITH CONTEXT`.

## C11 — Troubleshoot, contain and repair from evidence

In active harm, contain first while preserving evidence; otherwise reproduce/localise before broad changes. Use hypothesis-driven evidence, history/bisection and runtime diagnostics to identify the owning layer, then produce durable regression evidence.

**Standing:** `SUPPORTED`, revised from Stage 3.

## C12 — Preserve releasability and promotion integrity

Keep releasable software buildable/packageable with compatible configuration, migrations and dependencies; preserve the relationship between tested and released artefacts; make rollback/recovery constraints explicit.

**Standing:** `SUPPORTED`.

## C13 — Govern consequential engineering commitments

Stop or escalate for destructive data change, external contract break, material security-control change, known quality waiver, high-switching-cost architecture change or scope expansion beyond standing authority.

**Standing:** `SUPPORTED`; exact organisational approval mechanism remains local.

## C14 — Maintain, migrate, deprecate and remove sustainably

Treat maintenance/removal as first-class work. Justify technical-debt work through evidenced change cost, risk or quality payoff; automate repetitive migration when economical; complete cleanup rather than leaving permanent dual paths.

**Standing:** `SUPPORTED WITH QUALIFICATION`.

## C15 — Integrate secure development and software-supply-chain evidence

Recognise security-sensitive changes, apply appropriate secure-development controls throughout the change, verify applicable security requirements, evaluate dependency/provenance risk, and invoke specialist security authority when general engineering evidence is insufficient.

**Standing:** `SUPPORTED` — **new explicit capability**.

## C16 — Engineer proportional diagnosability and operability

Ensure changed runtime behaviour can be understood at the required level using appropriate logs, metrics, traces, profiles, correlation or domain diagnostics. Add signals to answer operational questions, not to satisfy a fixed telemetry checklist.

**Standing:** `SUPPORTED` — **new explicit capability**.

## C17 — Measure and repair performance and concurrency behaviour

Define representative workloads/invariants, capture baselines, profile or detect races at the appropriate layer, make the smallest causal change, and retain regression evidence for material performance/concurrency risk.

**Standing:** `SUPPORTED` — **new explicit capability**.

---

# 14. Revised evidence-to-behaviour hypothesis

The broader research supports this **conditional** production model:

```text
change intent / defect / maintenance need
        ↓
clarify required outcome + authority
        ↓
inspect actual system + effective contracts
        ↓
map affected behaviour / data / dependency / runtime risk
        ↓
choose smallest coherent design scope
        ↓
choose adequate feedback / diagnostic boundary
        ↓
implement in reviewable increments
        ↓
run cheapest checks that can falsify the change
        ↓
escalate verification for residual
functional / compatibility / security /
performance / concurrency / reliability risk
        ↓
review change + rationale + specialist risks
        ↓
preserve releasability / migration / rollback evidence
```

When a failure occurs:

```text
ongoing harm?
├─ YES → contain / mitigate → preserve evidence → diagnose → durable repair
└─ NO  → reproduce / localise → diagnose → smallest repair

then
→ targeted regression evidence
→ broader checks only where residual risk requires them
```

This is not a mandatory document workflow. Steps collapse or repeat according to change class and risk.

---

# 15. Remaining bounded questions

Stage 4 resolves the main domain gaps sufficiently to continue, but the following questions remain intentionally open:

1. **High-assurance domains:** aviation, medical, automotive, nuclear, formal-cryptographic and other regulated/safety-critical work may require domain standards, formal evidence and specialist Extension Packs. Generic core automation must not claim adequacy.
2. **Security escalation threshold:** core can recognise high-risk surfaces, but exact mandatory specialist-review triggers depend on project threat model, regulation and organisational policy.
3. **Independent QA:** the precise contract between developer-owned change verification and independent integrated QA belongs to later workflow/evaluation design.
4. **Consumer discovery:** no universal method exists for proving all API/event consumers are known. Stage 5 must model evidence strength and unknown-consumer risk.
5. **Mutation testing:** useful in some contexts, but cost/effectiveness varies. It should remain an optional verification technique unless later benchmark evidence justifies a narrower requirement.
6. **Formal architecture fitness functions:** retain as an optional automated guardrail, not a universal architecture artefact.
7. **Non-service release readiness:** the evidence shape differs for libraries, mobile/desktop apps, firmware and services even though the underlying releasability principle is portable.
8. **AI-generated changes:** no separate universal review doctrine is established here. Provider/tool-specific provenance and evaluation belong primarily to Stage 8 and later benchmark research; high-consequence changes retain the same evidence/authority requirements regardless of author.
9. **Technical-debt prioritisation:** research does not support a universal debt score. Later planning should preserve project-specific cost/risk judgement.
10. **Performance budgets:** portable method, non-portable thresholds. Budgets remain consuming-project facts.

None blocks Stage 5.

---

# 16. Decisions made

Stage 4 establishes the following evidence-qualified decisions:

1. The domain model can be justified independently from the five-book corpus.
2. Software Engineering remains brownfield-first and greenfield-capable; maintenance/evolution are first-class lifecycle work.
3. The core must remain methodology-independent. Iterative/recursive change is expected; no mandatory ceremony sequence is justified.
4. Requirements/acceptance work is in scope only to the depth needed to make engineering behaviour clear and verifiable; Product authority remains distinct.
5. Architecture is consequence- and concern-driven. No style, architecture rating or synchronous/asynchronous default belongs in the core.
6. Tests are selected by risk and failure-detection ability. Unit tests, characterization tests, contract tests, integration tests, load tests and other checks are complementary.
7. Code coverage, mutation scores, line counts, debt scores and similar proxies must not become standalone quality gates without project-specific justification.
8. Small coherent batches are strongly supported, but fixed LOC thresholds are not.
9. Compatibility must name its contract form. Parallel/expand-migrate-contract evolution is a preferred pattern when consumers cannot change atomically.
10. Permanent Postel-style permissiveness is not a safe general API/protocol evolution rule; active maintenance and explicit compatibility are preferred where possible.
11. Security needs an explicit core capability covering secure development, dependency risk and supply-chain evidence, with specialist escalation.
12. Observability/diagnosability needs an explicit core capability without prescribing a telemetry vendor or universal signal checklist.
13. Performance and concurrency need explicit evidence methods rather than being hidden inside general testing.
14. Reliability patterns remain durable, but their mechanism may be provided by application code, SDK, runtime, service mesh or managed platform. The system must avoid duplicated/conflicting controls.
15. “Root cause before repair” is revised: stop ongoing harm first; then diagnose and repair durably.
16. Continuous delivery/releasability is portable; continuous deployment is not mandatory.
17. Technical-debt/refactoring work requires an evidenced reason; speculative cleanup is not a reusable production rule.
18. The provisional capability model expands from 14 to 17 capabilities. This expansion does **not** imply 17 final skills.

---

# 17. Source register

## Standards and bodies of knowledge

- IEEE Computer Society — SWEBOK Guide V4.0 / V4.0a: https://www.computer.org/education/bodies-of-knowledge/software-engineering
- ISO/IEC/IEEE 12207:2026 — Software life cycle processes: https://www.iso.org/standard/90219.html
- ISO/IEC/IEEE 29148:2018 — Requirements engineering: https://www.iso.org/standard/72089.html
- ISO/IEC/IEEE 42010:2022 — Architecture description: https://www.iso.org/standard/74393.html
- ISO/IEC 25010:2023 — Product quality model: https://www.iso.org/standard/78176.html
- ISO/IEC/IEEE 29119-1:2022 — Software testing concepts: https://www.iso.org/standard/81291.html
- NIST SP 800-218 SSDF v1.1 (final): https://csrc.nist.gov/pubs/sp/800/218/final
- NIST SSDF publications/status: https://csrc.nist.gov/projects/ssdf/publications
- OWASP ASVS 5.0.0: https://owasp.org/www-project-application-security-verification-standard/
- IETF RFC 9413 — Maintaining Robust Protocols: https://datatracker.ietf.org/doc/rfc9413/

## Authoritative operational / protocol practice

- DORA research model: https://dora.dev/research/
- DORA Continuous Integration: https://dora.dev/capabilities/continuous-integration/
- DORA Continuous Delivery: https://dora.dev/capabilities/continuous-delivery/
- DORA Working in Small Batches: https://dora.dev/capabilities/working-in-small-batches/
- DORA delivery metrics guide/history: https://dora.dev/guides/dora-metrics/ and https://dora.dev/insights/dora-metrics-history/
- Google Engineering Practices — Code Review: https://google.github.io/eng-practices/review/
- Google SRE — Effective Troubleshooting: https://sre.google/sre-book/effective-troubleshooting/
- Google SRE — Addressing Cascading Failures: https://sre.google/sre-book/addressing-cascading-failures/
- Google SRE — Production Services Best Practices: https://sre.google/sre-book/service-best-practices/
- OpenTelemetry Signals: https://opentelemetry.io/docs/concepts/signals/
- AWS Builders’ Library: https://aws.amazon.com/builders-library/
- AWS — Making retries safe with idempotent APIs: https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/
- Protocol Buffers best practices: https://protobuf.dev/best-practices/dos-donts/
- Google API versioning AIP-185: https://google.aip.dev/185
- SLSA v1.2 provenance: https://slsa.dev/spec/v1.2/provenance
- OpenSSF OSS dependency evaluation: https://best.openssf.org/Concise-Guide-for-Evaluating-Open-Source-Software.html
- Git bisect: https://git-scm.com/docs/git-bisect
- Clang ThreadSanitizer: https://clang.llvm.org/docs/ThreadSanitizer.html
- Evolutionary Database Design: https://martinfowler.com/articles/evodb.html
- Parallel Change: https://martinfowler.com/bliki/ParallelChange.html

## Empirical / research challenge sources

- Sadowski et al. — *Modern Code Review: A Case Study at Google*: https://research.google/pubs/modern-code-review-a-case-study-at-google/
- Dean & Barroso — *The Tail at Scale*: https://research.google/pubs/the-tail-at-scale/
- Inozemtseva & Holmes — *Coverage is not strongly correlated with test suite effectiveness*, ICSE 2014, DOI `10.1145/2568225.2568271`
- Chekam et al. — mutation/coverage fault revelation study: https://discovery.ucl.ac.uk/id/eprint/10058915/
- Papadakis et al. — *Are Mutation Scores Correlated with Real Fault Detection?*, ICSE 2018, DOI `10.1145/3180155.3180183`
- Li et al. — *How do software development teams manage technical debt?*, DOI `10.1016/j.jss.2016.05.018`
- Lenarduzzi et al. — technical-debt prioritisation systematic review: https://arxiv.org/abs/1904.12538
- Lehman & Ramil — *Software evolution—Background, theory, practice*, DOI `10.1016/S0020-0190(03)00382-X`

---

# 18. Stage 4 exit-criteria verification

| Exit criterion | Evidence | Status |
| --- | --- | --- |
| Material book findings assessed | Section 5 challenges the major Stage 3 claims and methods | PASS |
| Both research questions answered | Sections 4–6 identify defensible claims, limitations and missing responsibilities | PASS |
| Required research areas covered | Sections 4.1–4.18 cover requirements, architecture, construction/review, testing, maintenance, configuration/process, quality, security, CI/CD, observability, performance, reliability, debugging and technical debt | PASS |
| Real workflows studied | Section 11 covers all required change classes and records inputs, evidence, commitment, expensive checks, failures, repairs, handoffs and quality targets | PASS |
| Supporting and contrary evidence recorded | Section 5 explicitly supports, qualifies, disputes and rejects claims | PASS |
| Role/responsibility map exists | Section 10 | PASS |
| Gap analysis against Stage 1 exists | Security, observability and performance/concurrency become explicit; remaining bounded questions in Section 15 | PASS |
| Software change lifecycle candidates exist | Sections 11 and 14 | PASS |
| Failure/repair taxonomy candidates exist | Section 12 | PASS |
| Evidence-quality model exists | Section 3 | PASS |
| Evidence-qualified capability model exists | Section 13, `software-engineering-domain-model-r1` | PASS |
| Unresolved claims remain explicit | Section 15 | PASS |
| Model does not depend on a book or coding agent | Standards, empirical and operational evidence independently support the model; no provider capability defines it | PASS |

## Completion decision

Stage 4 is complete.

The Stage 3 corpus remains valuable, but it is no longer the authority for the project model. The evidence-qualified model now has independent support from current lifecycle, requirements, architecture, quality, testing and security standards; empirical software-engineering research; and current operational/protocol practice.

Stage 5 may now model software change types, contracts and system context using `software-engineering-domain-model-r1` as its evidence-qualified input.
