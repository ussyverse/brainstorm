# New Integration Ideas: Pass 18

**Research date:** 2026-09-13
**Scope:** eight new product proposals built from source-inspected repositories.
They are distinct from the ten combinations in
[`SOURCE_CHECKED_COMBINATIONS.md`](SOURCE_CHECKED_COMBINATIONS.md). No candidate
repository was modified and no end-to-end integration was found in the inspected
source.

## Evidence Boundary

**Exists** means the cited model, function, CLI, or export was present in source.
**Proposed** means a new adapter, shared record, UI, persistence layer, or
workflow is required. **Unverified** means the result was not runtime-tested or
its domain validity was not established. Scores remain explanatory heuristics,
not security, financial, medical, accessibility, or historical authority.

I ran `git rev-parse --short HEAD` in each cited checkout and inspected the
listed source files. I did not install, build, or run candidate test suites in
this pass.

| Repository | Revision | Source inspected |
|---|---:|---|
| `ussyverse/snapshotussy` | `8351c8e` | `snapshot/models.py`, `core.py`, `export.py`, `diff.py` |
| `ussyverse/codelineageussy` | `e9e4d77` | `src/codelineage/core.py`, `git_archaeology.py`, `ast_genomes.py` |
| `ussyverse/sentinelussy` | `1b86f9c` | `sentinel/profile.py`, `checker.py`, `extractor.py` |
| `ussyverse/stenographussy` | `876be3f` | scanner modules, SARIF formatter, CLI |
| `ussyverse/coronerussy` | `cec3308` | `coroner/models.py`, `custody.py`, `investigate.py` |
| `ussyverse/archivioussy` | `918d690` | `src/archivio/models.py`, `storage.py`, `export.py` |
| `mojomast/arrhivescrape` | `afffec1` | `archive_recovery/pipeline/inventory.py`, `normalization.py`, `validation.py` |
| `ussyverse/auscultussy` | `875b0c2` | `src/ausculta/models.py`, `engine.py` |
| `ussyverse/quorumussy` | `397531d` | `internal/quorum/model.go` |
| `ussyverse/condorcetussy` | `7f62d4c` | `src/condorcet/core.py`, `report.py` |
| `ussyverse/controlaussy` | `c3170f9` | `src/controla.nim` |
| `ussyverse/cloforaussy` | `3b967eb` | `src/lib.rs` |
| `ussyverse/koppenussy` | `1f539a4` | `koppen.c`, `koppen.h`, `main.c` |
| `ussyverse/coreussy` | `29fae02` | `src/core.nim` |
| `ussyverse/keelussy` | `3dc4aa2` | `src/lib.zig` |
| `ussyverse/bolusaussy` | `b77846b` | `bolusa.h`, `bolusa.c` |
| `ussyverse/kinshipussy` | `308bbb3` | `kinship/types.go`, `analysis.go` |

## New Proposals

### 1. Context-Aware Change Capsule

**Target user and pain.** A maintainer returns to a half-finished change after
an interruption or hands it to a colleague. A commit message rarely preserves
the open files, environment assumptions, historical context, or whether a new
pattern is normal for this repository.

**Exact repositories.** `ussyverse/snapshotussy` + `ussyverse/codelineageussy` +
`ussyverse/sentinelussy`.

**Product promise.** Export a redacted, inspectable handoff that says what was
being done, what state was captured, and which changed code differs from the
repository's learned baseline.

**Existing evidence.** **Exists:** Snapshot's `Snapshot` dataclass includes
terminals, editor files, processes, environment, and `MentalContext`, with JSON
round trips in [`snapshot/models.py`](https://github.com/ussyverse/snapshotussy/blob/8351c8e/snapshot/models.py).
**Exists:** CodeLineage's `analyze_repository` joins tracked Python functions,
git history, structural genomes, and detections in
[`src/codelineage/core.py`](https://github.com/ussyverse/codelineageussy/blob/e9e4d77/src/codelineage/core.py).
**Exists:** Sentinel's `build_profile` and `check_directory` create a codebase
self-profile and location-bearing anomaly reports in
[`sentinel/profile.py`](https://github.com/ussyverse/sentinelussy/blob/1b86f9c/sentinel/profile.py)
and [`checker.py`](https://github.com/ussyverse/sentinelussy/blob/1b86f9c/sentinel/checker.py).

**Proposed handoff and data flow.** `capsuleId` + commit + selected snapshot ->
CodeLineage adds changed-function ancestry -> Sentinel compares the changed
functions with a profile pinned to a profile revision -> a Markdown/JSON capsule
shows raw facts, open questions, findings, and commands to resume.

**MVP and acceptance.** Capture one interrupted Python task, redact environment
values by default, and render five changed files with one explicit open question.
Loading the capsule must recover the note and snapshot metadata; anomaly output
must link to file and line; no process should be restarted automatically.

**Why combine.** Snapshot preserves human and machine context, CodeLineage adds
evolution, and Sentinel adds repository-specific review prompts. Separate state
and static-analysis reports do not explain how to resume the work.

**Risks and maturity.** Snapshot content can contain secrets and stale PIDs.
CodeLineage only analyzes Python functions and can be noisy with shallow history.
Sentinel's baseline depends on the training corpus and its score is not a defect
probability. Redaction, profile versioning, and the capsule format are
**Proposed**; runtime behavior is **Unverified**.

**Rejected adjacent component.** Do not add a general repository-health
dashboard; it would turn a concrete handoff into another low-actionability score.

### 2. Invisible-Change Review Gate

**Target user and pain.** A reviewer needs to distinguish an invisible-source
finding that deserves immediate inspection from an unusual but intentional local
pattern. Raw scanner output and a generic lint result do not preserve the review
decision or the repository baseline.

**Exact repositories.** `ussyverse/stenographussy` + `ussyverse/sentinelussy`.

**Product promise.** Produce a changed-line review packet for invisible or
confusable source changes, with evidence and a human disposition rather than an
automatic accusation.

**Existing evidence.** **Exists:** Stenograph scans zero-width characters,
homoglyphs, bidi controls, whitespace entropy, and comment steganography, and
renders SARIF; the scanner and formatter are in
[`stenography/engine.py`](https://github.com/ussyverse/stenographussy/blob/876be3f/stenography/engine.py)
and [`stenography/formatters/sarif.py`](https://github.com/ussyverse/stenographussy/blob/876be3f/stenography/formatters/sarif.py).
**Exists:** Sentinel stores feature vectors in a `SelfProfile` and emits
`Detection` records with source file, line, detector, distance, and explanation
through [`sentinel/checker.py`](https://github.com/ussyverse/sentinelussy/blob/1b86f9c/sentinel/checker.py).

**Proposed handoff and data flow.** Pull-request diff -> Stenograph findings
keyed by stable file/line fingerprints -> Sentinel checks only affected files
against a profile trained from an explicitly selected base revision -> review
queue with raw snippet, scanner result, baseline context, reviewer disposition,
and accepted-risk expiry.

**MVP and acceptance.** Analyze a fixture containing one bidi control, one
confusable identifier, and one ordinary unusual function. Emit SARIF plus a
Markdown review table. A reviewer can mark inspect, accept with reason, or block;
the tool must never convert an anomaly into a claim of malicious intent.

**Why combine.** Stenograph detects the concrete representation hazard; Sentinel
answers whether the surrounding pattern is unusual for this codebase. The shared
finding identity creates a review artifact rather than a merged security score.

**Risks and maturity.** False positives are expected in generated code,
international text, and formatting-heavy files. Sentinel's Euclidean feature
distance is not calibrated risk. SARIF severity and Sentinel anomaly strength
must remain separate. Diff parsing, stable fingerprints, and disposition storage
are **Proposed**; the gate is **Unverified**.

**Rejected adjacent component.** Do not add automatic quarantine or merge
blocking until false-positive review, generated-file policy, and repository
owner rules have been tested.

### 3. CI Incident Casefile

**Target user and pain.** A maintainer can identify a failed build but loses the
operator context, exact artifacts, and evidence behind a later explanation. A
casefile should preserve what was observed without pretending that a heuristic
root cause is proven.

**Exact repositories.** `ussyverse/coronerussy` + `ussyverse/archivioussy` +
`ussyverse/snapshotussy`.

**Product promise.** Turn one failed pipeline and its investigation context into
a local, reviewable incident packet with provenance, claims, counterclaims, and
safe sharing boundaries.

**Existing evidence.** **Exists:** Coroner models `PipelineRun`, stages, trace
evidence, investigations, and cross-run custody comparisons in
[`coroner/models.py`](https://github.com/ussyverse/coronerussy/blob/cec3308/coroner/models.py).
`build_custody_chain` and `compare_custody_chains` preserve stage hashes and
classify input/process divergence in
[`coroner/custody.py`](https://github.com/ussyverse/coronerussy/blob/cec3308/coroner/custody.py).
**Exists:** Archivio stores artifacts, source notes, claims, evidence links,
counterclaims, verification tasks, and fixity in
[`src/archivio/storage.py`](https://github.com/ussyverse/archivioussy/blob/918d690/src/archivio/storage.py).
**Exists:** Snapshot serializes terminal, editor, environment, and mental
context state for the investigator.

**Proposed handoff and data flow.** CI run manifest and logs -> Coroner stages,
hash chain, and comparison -> Snapshot captures the local reproduction note and
selected command context -> Archivio accessions raw logs/artifacts, then links a
human-authored suspected-cause claim to exact evidence -> private casefile and
filtered reviewer packet.

**MVP and acceptance.** Use two saved runs: one with a changed environment value
and one with the same inputs but a different output. Export stage hashes, raw
paths, the reproduction note, one suspected claim, one counterclaim, and one
verification task. The public projection must exclude environment secrets and
local paths.

**Why combine.** Coroner reconstructs the pipeline, Snapshot preserves the
investigator's reproduction context, and Archivio separates observation from
claim. That relationship is more useful than a single incident confidence score.

**Risks and maturity.** Coroner's forensic metaphors and confidence values are
heuristics. Its custody action summary includes environment values, so collection
must redact before persistence. Archivio's JSON export currently needs a new
artifact-level privacy projection. Storage atomicity, importer idempotence, and
runtime CI collection are **Proposed** and **Unverified**.

**Rejected adjacent component.** Do not add an LLM root-cause narrator before
the raw run, evidence links, and human correction path are reliable.

### 4. Recoverable Mirror Release Capsule

**Target user and pain.** An archivist recovers a dead site more than once as new
captures or dependencies become available. Staging folders do not explain which
bytes were used, what was transformed, or which operator assumptions produced a
release.

**Exact repositories.** `mojomast/arrhivescrape` + `ussyverse/archivioussy` +
`ussyverse/snapshotussy`.

**Product promise.** Publish an authorized static mirror only through a release
capsule that preserves capture evidence, transformation state, and human
approval.

**Existing evidence.** **Exists:** Arrhivescrape inventories CDX captures,
downloads content-addressed objects, normalizes links, and validates missing
files and references through [`inventory.py`](https://github.com/mojomast/arrhivescrape/blob/afffec1/archive_recovery/pipeline/inventory.py),
[`normalization.py`](https://github.com/mojomast/arrhivescrape/blob/afffec1/archive_recovery/pipeline/normalization.py),
and [`validation.py`](https://github.com/mojomast/arrhivescrape/blob/afffec1/archive_recovery/pipeline/validation.py).
**Exists:** Archivio records artifacts, source notes, claims, sensitivity, and
fixity. **Exists:** Snapshot records the operator's selected run context and
serializes it for later inspection.

**Proposed handoff and data flow.** Authorized domain + capture selection ->
Arrhivescrape run manifest with raw/final hashes -> Archivio artifact and source
note records -> Snapshot records the local configuration, operator note, and
approval state -> release capsule containing approved files, unresolved links,
privacy checks, and a rollback pointer.

**MVP and acceptance.** Recover five pages from two capture dates, retain one
missing dependency, accession the pages locally, and export a capsule with raw
URLs, hashes, transformed paths, and an explicit approval checkbox. A simulated
re-run must identify unchanged versus newly recovered files.

**Why combine.** Arrhivescrape explains how a mirror was made, Archivio explains
what is being claimed from it, and Snapshot preserves the operator context that
is otherwise lost between runs.

**Risks and maturity.** Recovery is not authenticity. Archived material may
contain personal data, credentials, copyrighted work, or deleted content.
Archivio's existing export can expose artifact dictionaries and local paths, so
the release projection must be written and tested separately. Snapshot may retain
secrets unless explicitly redacted. Authorization, deletion, and public-release
review are **Proposed**; the combined workflow is **Unverified**.

**Rejected adjacent component.** Do not add automatic public publishing or a
claim that a matching hash proves ownership or historical truth.

### 5. Meeting Closure and Ballot Record

**Target user and pain.** A recurring team, club, or household meeting identifies
options but leaves unclear whether the decision was ready, whether a minority
constraint was ignored, or whether the same topic will be reopened next week.

**Exact repositories.** `ussyverse/auscultussy` + `ussyverse/quorumussy` +
`ussyverse/condorcetussy`.

**Product promise.** Produce a compact meeting record that separates meeting
quality observations from the transparent method used to choose an option.

**Existing evidence.** **Exists:** Auscultussy models dated meeting observations,
agenda beats, closure, assignments, murmurs, follow-up, and trend analysis in
[`src/ausculta/models.py`](https://github.com/ussyverse/auscultussy/blob/875b0c2/src/ausculta/models.py)
and [`engine.py`](https://github.com/ussyverse/auscultussy/blob/875b0c2/src/ausculta/engine.py).
**Exists:** Quorum stores weighted members, options, preferences, vetoes, and
tolerances and reports threshold, polarization, and veto diagnostics in
[`internal/quorum/model.go`](https://github.com/ussyverse/quorumussy/blob/397531d/internal/quorum/model.go).
**Exists:** Condorcet supports ranked ballots, pairwise matrices, cycle
detection, and method comparison in [`src/condorcet/core.py`](https://github.com/ussyverse/condorcetussy/blob/7f62d4c/src/condorcet/core.py).

**Proposed handoff and data flow.** Facilitator records agenda and closure facts
-> Auscultussy produces a meeting observation and next intervention -> eligible
options and constraints are exported to Quorum or ranked ballots to Condorcet ->
the packet shows the chosen method, raw ballots, vetoes, cycles, decision owner,
and review date.

**MVP and acceptance.** Record three meetings about one recurring decision with
four options and four participants. Demonstrate a closed decision, a vetoed
winner, and a Condorcet cycle. The output must say “no decision” when the chosen
rules do not establish one and must preserve the next meeting's owner/date.

**Why combine.** Auscultussy describes whether the meeting closed cleanly,
Quorum exposes constraints and tolerances, and Condorcet explains ranked-choice
tradeoffs. This creates a closure artifact instead of another group-health score.

**Risks and maturity.** All three use hand-entered observations or heuristic
classification. Voting methods answer different questions and must not be
silently averaged. Participant names, notes, and vetoes are sensitive; use local
storage and explicit visibility. The shared ballot schema and follow-up ledger
are **Proposed**; runtime behavior is **Unverified**.

**Rejected adjacent component.** Do not add a sentiment classifier or automatic
facilitator that infers agreement from transcripts.

### 6. Climate-to-Walk Packing Card

**Target user and pain.** A family or visitor plans a short city walk across
different climates, activity levels, and indoor transitions. Climate rankings,
route notes, and clothing choices are usually separate, so a route that fits the
clock can still produce an impractical carry plan.

**Exact repositories.** `ussyverse/koppenussy` + `ussyverse/cloforaussy` +
`ussyverse/controlaussy`.

**Product promise.** Turn user-maintained climate normals and a manually verified
city course into a time-boxed route card with clothing transitions and explicit
weather uncertainty.

**Existing evidence.** **Exists:** Koppen parses preference key/value files and
destination climate CSVs, classifies Koppen-like bands, and writes ranked reports
in [`koppen.c`](https://github.com/ussyverse/koppenussy/blob/1f539a4/koppen.c).
**Exists:** Clofora models garments, weather bands, activity segments, target clo,
comfort bands, carry limits, and transition warnings in
[`src/lib.rs`](https://github.com/ussyverse/cloforaussy/blob/3b967eb/src/lib.rs).
**Exists:** Controla's `WalkPlan`, `classifyLeg`, and `htmlReport` represent
manual controls, route clues, bailouts, time boxes, and child/night/accessible
modes in [`src/controla.nim`](https://github.com/ussyverse/controlaussy/blob/c3170f9/src/controla.nim).

**Proposed handoff and data flow.** Destination/month climate row -> Koppen
ranking and source note -> Clofora uses the chosen weather band and activity
segments to produce worn/carry layers -> Controla receives only human-verified
controls and legs -> one printable walk-and-packing card with forecast confidence,
bailouts, clothing triggers, and official-alert reminders.

**MVP and acceptance.** Compare two manually entered destinations, select one
three-leg walk, and model a cool exposed wait followed by an indoor stop. The
card must show route time separately from climate data, retain a low-confidence
forecast, and include a return/bailout for every leg.

**Why combine.** Koppen narrows the climate context, Clofora handles clothing
transitions, and Controla makes the human-verified route consultable. The shared
destination/month/walk identity joins planning tasks without claiming to predict
weather or certify accessibility.

**Risks and maturity.** Koppen's normals are only as current as the user data and
are not a forecast. Clofora is comfort planning, not medical, survival, or PPE
guidance. Controla does not query maps, closures, opening hours, or physical
access audits. Weather import, accessibility verification, and route provenance
are **Proposed**; runtime behavior is **Unverified**.

**Rejected adjacent component.** Do not add live route optimization or hazard
authority before current data, map licensing, and local accessibility review.

### 7. Cash Regime and Shock Review

**Target user and pain.** A household sees a long transaction history but cannot
tell whether a current change is seasonal, a new spending regime, or a shock that
will exhaust reserves. A single stability label hides both the history and the
assumptions behind a scenario.

**Exact repositories.** `ussyverse/coreussy` + `ussyverse/keelussy`.

**Product promise.** Build a dated personal review packet showing what changed in
the transaction record and how explicitly entered shocks alter the household's
budget model.

**Existing evidence.** **Exists:** Core parses transactions, classifies them with
transparent keyword rules, aggregates monthly strata, detects rolling z-score
transitions, and summarizes seasonal cycles in [`src/core.nim`](https://github.com/ussyverse/coreussy/blob/29fae02/src/core.nim).
**Exists:** Keel's `HouseholdInput`, `Shock`, `Analysis`, damage cases, reserve
metrics, and righting curve model entered income, costs, debt, reserves, and
scenario shocks in [`src/lib.zig`](https://github.com/ussyverse/keelussy/blob/3dc4aa2/src/lib.zig).

**Proposed handoff and data flow.** User CSV -> Core preserves raw rows and
identifies dated transitions -> user reviews category corrections and chooses a
baseline month -> adapter maps only confirmed totals into Keel -> packet compares
one-month job-loss, repair, or cost-increase scenarios while showing the original
rows and assumptions.

**MVP and acceptance.** Import 18 months of synthetic or user-owned CSV, correct
three classifications, and run two manually entered shocks. The report must
distinguish observed transition from modeled shock, preserve currency/date scope,
and allow the user to remove a transaction without changing the source file.

**Why combine.** Core supplies historical context; Keel supplies a bounded
scenario surface. Neither alone connects an observed regime change to a
reviewable “what if” packet.

**Risks and maturity.** Core's keyword classification can misclassify merchants
and sparse months. Keel's naval quantities are metaphorical heuristics, not a
financial plan, credit decision, or solvency forecast. No bank connector,
accounting reconciliation, tax handling, or legal advice exists. The mapping of
categories and shock units is **Proposed** and **Unverified**.

**Rejected adjacent component.** Do not add investment, debt-refinancing, or
automatic transfer actions; the input and model do not justify those decisions.

### 8. Consent-Based Mealtime Care Handoff

**Target user and pain.** A family coordinating meals for someone with documented
swallowing-related preferences needs a clear handoff between the person's plan,
the food observations, and caregiver availability. A generic care chart can hide
backup gaps, while a food rule can be mistaken for a diagnosis.

**Exact repositories.** `ussyverse/bolusaussy` + `ussyverse/kinshipussy`.

**Product promise.** Produce a consented meal-support card that preserves the
person's entered plan, records observed texture checks, identifies who can cover
the task, and routes incidents to qualified help.

**Existing evidence.** **Exists:** Bolusa defines `BolusaPlan`, `BolusaCheck`,
`BolusaIncident`, plan validation, texture checks, route-away flags, and a
handoff report in [`bolusa.h`](https://github.com/ussyverse/bolusaussy/blob/b77846b/bolusa.h)
and [`bolusa.c`](https://github.com/ussyverse/bolusaussy/blob/b77846b/bolusa.c).
**Exists:** Kinshipussy models care edges with hours, cognitive load, criticality,
reliability, consent, and explicitness, then reports care loads, backup-path gaps,
and caregiver unavailability in [`kinship/types.go`](https://github.com/ussyverse/kinshipussy/blob/308bbb3/kinship/types.go)
and [`analysis.go`](https://github.com/ussyverse/kinshipussy/blob/308bbb3/kinship/analysis.go).

**Proposed handoff and data flow.** A person or authorized clinician supplies the
current plan -> caregiver enters the meal item and observed texture flags ->
Bolusa produces a conservative check/handoff record -> Kinshipussy maps only the
consented meal-support task to primary and backup caregivers -> private card with
the plan source, observation, coverage gap, questions, and urgent route-away
instruction.

**MVP and acceptance.** Use synthetic data for one person, three meals, two
caregivers, one unavailable backup, and one incident with a route-away flag. The
card must preserve unknown values, require explicit consent before adding a care
edge, and never recommend changing diet or treatment.

**Why combine.** Bolusa handles the meal observation and clinical handoff
boundary; Kinshipussy handles labor, consent, and backup paths. Together they
address both “what was observed?” and “who can responsibly carry the task?”

**Risks and maturity.** Bolusa is not diagnosis, dysphagia assessment, or diet
authorization. Kinship scores are planning heuristics, not measures of duty or
care quality. Health-related data requires least-privilege access, short
retention, and professional review. The consent adapter, data protection, and
incident escalation integration are **Proposed** and **Unverified**.

**Rejected adjacent component.** Do not add automatic meal generation, nutrition
optimization, or caregiver quality ranking.

## Rejected Ideas

### R1. Universal Code Trust Score

**Candidate shape.** Combine `ussyverse/stenographussy`, `ussyverse/sentinelussy`,
`ussyverse/coronerussy`, and `ussyverse/codelineageussy` into one score that
blocks releases.

**Why rejected.** The components observe different things: source
representation, repository-pattern distance, pipeline evidence, and code
history. Their scales, baselines, and failure modes are not interchangeable. A
high anomaly score is not proof of malicious code; a matching custody chain is
not proof of correctness; and historical similarity is not safety evidence. The
accepted ideas keep findings, provenance, and human disposition separate.

### R2. Automatic Family Health and Finance Advisor

**Candidate shape.** Combine `ussyverse/bolusaussy`, `ussyverse/kinshipussy`,
`ussyverse/coreussy`, and `ussyverse/keelussy` into an authority that recommends
care schedules, spending cuts, or medical actions.

**Why rejected.** This would cross unrelated health, caregiving, and finance
boundaries and turn hand-entered heuristics into high-consequence advice. The
mealtime proposal is limited to documentation, consent, coverage, and qualified
handoff; the cash proposal is limited to historical review and user-entered
scenarios. No combined score or automatic action is justified.

## Selection Notes and Next Validation

These proposals use a natural shared entity: a change capsule, finding, CI run,
recovery release, meeting, walk, monthly cash record, or care task. Each can
produce a local artifact before authentication, hosting, scraping, payment, or
automated action is required.

1. Run each cited repository's own tests in isolated environments and record
   failures; this document does not claim any test passes.
2. For one selected idea, define stable IDs, timestamps, units, missingness,
   source revisions, privacy classes, and raw-output retention before building a
   dashboard.
3. Test contradictory and incomplete inputs. The expected result should be an
   explicit unknown, review, or inconclusive state rather than a stronger score.
4. Obtain domain review before using the walk, financial, security, or care
   proposals with real decisions.
