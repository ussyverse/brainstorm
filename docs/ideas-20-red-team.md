# Red-Team Product Ideas Beyond the Current Top Ten

**Date:** 2026-09-13
**Scope:** Eight new combinations challenging the ten proposals in `SOURCE_CHECKED_COMBINATIONS.md`. Every serious idea below uses at least two `ussyverse` repositories and none reuses a repository from the current top-ten combinations.
**Evidence status:** Source paths and symbols were inspected. The integrations, adapters, and product workflows are **Proposed**. No selected repository was installed, built, or runtime-tested during this pass.

## What This Challenges

The existing shortlist is strongest where it joins a symptom to a human follow-up: production planning, service improvement, CI diagnosis, archives, learning, household handoffs, civic asks, music sketching, dependency history, and returns. These alternatives test less-covered seams:

- business identity and capacity before a quote is made;
- release evidence across code, dependencies, and licenses;
- calibration of test evidence rather than a code-health score;
- documentation drift using both static and runtime evidence;
- pipeline handoff rehearsal without an orchestration platform;
- travel readiness rather than destination selection alone;
- preservation and weeding of mixed household collections;
- stewardship of shared assets rather than recruitment of volunteers.

Ranking favors a concrete local artifact, a natural shared entity, limited adapter work, and honest uncertainty. It is a product judgment, not a market estimate.

## Ranked Ideas

### 1. Quote-to-Capacity Desk

**Exact repositories:** `ussyverse/recapturaussy` + `ussyverse/bidussy` + `ussyverse/taktussy`

**User and recurring pain:** A small repair shop, alteration studio, or field-service owner receives leads from several places, quotes from incomplete demand information, and promises work without checking the actual service queue.

**Product promise:** “Turn messy lead exports into a deduplicated, capacity-aware quote queue, while showing which estimate is evidence and which is assumption.”

**Input -> processing -> output:** Two or more dated lead exports plus service definitions and weekly capacity -> Recaptura normalizes identities, merges aliases, estimates unseen overlap and reports warnings; Bidussy calculates demand probabilities and expected revenue; Taktussy models service capacity and historical demand -> a reviewable quote queue with duplicate groups, demand ranges, capacity warnings, unresolved records, and a follow-up list.

**Existing source to reuse:** **Exists:** [`recapturaussy/src/lib.zig`](https://github.com/ussyverse/recapturaussy/blob/HEAD/src/lib.zig) contains lead normalization, alias merging, deduplication, overlap matrices, capture-recapture estimates, warnings, and redacted hashes. [`bidussy/src/bid/demand.py`](https://github.com/ussyverse/bidussy/blob/HEAD/src/bid/demand.py) contains empirical demand points, logistic estimates, probabilities, and expected revenue. [`taktussy/src/lib.rs`](https://github.com/ussyverse/taktussy/blob/HEAD/src/lib.rs) models services, capacity, historical demand, and JSON persistence.

**Missing integration work:** Define a stable lead/service schema, make every merge reversible, map estimated demand to service IDs, and preserve source exports beside derived records. The quote editor and follow-up state are new.

**Maturity and feasibility caveats:** Recapture estimates require meaningfully independent captures and are not ground truth. Bidussy is a small historical model, not a market forecast. Taktussy's capacity assumptions need owner review. No CRM or payment integration is implied.

**Smallest useful demo:** Import two 20-row CSV exports for one repair service, merge three obvious aliases, add ten known historical jobs, and produce a queue showing an estimate range and one capacity conflict.

**Acceptance criteria:** No raw row disappears; every merged lead links to its source rows; estimated values are labeled; the owner can reject a merge; capacity warnings identify the input assumptions; the output is JSON plus a printable queue.

**Why better than separate tools:** The same lead identity and service ID connect acquisition, price confidence, and delivery capacity. Separate deduplication, pricing, and scheduling reports would not expose an overpromised quote.

**Rejected adjacent components:** `ussyverse/prospectaussy` was not added because cue scoring and intention design would add reminders without improving lead identity or capacity evidence.

### 2. Dependency Release Evidence Gate

**Exact repositories:** `ussyverse/mintussy` + `ussyverse/cambiumussy` + `ussyverse/portmoreussy`

**User and recurring pain:** A small package maintainer wants to release, but cannot answer in one pass whether the lockfile, public interface, provenance, and license obligations are consistent.

**Product promise:** “Generate a release dossier that distinguishes what changed, what is compatible, what is traceable, and what still needs a human decision.”

**Input -> processing -> output:** Source tree, lockfiles, package metadata, and selected license files -> Mintussy parses lockfiles and provenance/counterfeit findings; Cambiumussy extracts interfaces and compatibility drift; Portmore classifies licenses, origins, and dev/runtime obligations -> a release gate containing raw findings, public-interface diffs, dependency provenance, license obligations, and explicit unknowns.

**Existing source to reuse:** **Exists:** [`mintussy/mint/lockfile.py`](https://github.com/ussyverse/mintussy/blob/HEAD/mint/lockfile.py), [`counterfeit.py`](https://github.com/ussyverse/mintussy/blob/HEAD/mint/counterfeit.py), and [`provenance.py`](https://github.com/ussyverse/mintussy/blob/HEAD/mint/provenance.py) implement lockfile parsing, counterfeit findings, and provenance chains. [`cambiumussy/cambium/extractor.py`](https://github.com/ussyverse/cambiumussy/blob/HEAD/cambium/extractor.py), [`compatibility.py`](https://github.com/ussyverse/cambiumussy/blob/HEAD/cambium/compatibility.py), and [`scanner.py`](https://github.com/ussyverse/cambiumussy/blob/HEAD/cambium/scanner.py) implement AST interface extraction and compatibility scanning. [`portmoreussy/src/portmore/classifier.py`](https://github.com/ussyverse/portmoreussy/blob/HEAD/src/portmore/classifier.py), [`compatibility.py`](https://github.com/ussyverse/portmoreussy/blob/HEAD/src/portmore/compatibility.py), and [`origin.py`](https://github.com/ussyverse/portmoreussy/blob/HEAD/src/portmore/origin.py) cover license and origin analysis.

**Missing integration work:** Normalize package coordinates and file paths, choose the public API boundary, join findings by release ID, and add a human approval record. No automatic release publish should be part of the MVP.

**Maturity and feasibility caveats:** AST compatibility is language-specific and heuristic. License classification and provenance are evidence for review, not legal advice. Lockfile presence does not prove what was shipped. Source paths and package ecosystems need explicit adapters.

**Smallest useful demo:** Analyze one Python package with a deliberately changed function signature, one lockfile dependency, and one dependency whose license metadata is incomplete.

**Acceptance criteria:** A release report includes exact source paths, baseline/current identifiers, raw findings, unknown states, and no “safe to publish” claim unless a human records approval.

**Why better than separate tools:** A changed interface can be interpreted alongside the dependency and licensing context of the same release. Separate scanners leave the maintainer to reconstruct that join manually.

**Rejected adjacent components:** `ussyverse/hitchussy` and `ussyverse/churnmapussy` were omitted because cycle priority and historical co-change burden answer a refactoring question, not a release-evidence question.

### 3. Test Evidence Calibration Packet

**Exact repositories:** `ussyverse/acumenussy` + `ussyverse/calibreussy`

**User and recurring pain:** A maintainer must decide whether a failing or passing test suite is giving useful evidence, but usually has only an aggregate count and an intuition that the suite is flaky or too shallow.

**Product promise:** “Show which test evidence is repeatable, which is structurally weak, and which measurement should be run next.”

**Input -> processing -> output:** JUnit or pytest results, repeated run records, source/test inventory, and an explicit measurement question -> Acumen scans test structure, flake patterns, and estimated test quality; Calibre builds uncertainty budgets, repeatability/reproducibility and capability reports -> a calibration packet containing raw runs, test-to-module coverage gaps, uncertainty sources, repeatability findings, and a small next-experiment plan.

**Existing source to reuse:** **Exists:** [`acumenussy/src/acumen/testigram.py`](https://github.com/ussyverse/acumenussy/blob/HEAD/src/acumen/testigram.py), [`flakegram.py`](https://github.com/ussyverse/acumenussy/blob/HEAD/src/acumen/flakegram.py), [`scanner.py`](https://github.com/ussyverse/acumenussy/blob/HEAD/src/acumen/scanner.py), and [`storage.py`](https://github.com/ussyverse/acumenussy/blob/HEAD/src/acumen/storage.py) provide test diagnostics and persistence. [`calibreussy/src/calibre/budget.py`](https://github.com/ussyverse/calibreussy/blob/HEAD/src/calibre/budget.py), [`rr.py`](https://github.com/ussyverse/calibreussy/blob/HEAD/src/calibre/rr.py), and [`report.py`](https://github.com/ussyverse/calibreussy/blob/HEAD/src/calibre/report.py) provide uncertainty, R&R, drift, and traceability reporting.

**Missing integration work:** Define a shared run/test/module identity, ingest actual repeated results, map structural findings to measurement records, and render raw evidence beside conclusions.

**Maturity and feasibility caveats:** Acumen explicitly describes Testigram output as heuristic and says real mutation data would be needed for stronger evidence. Calibre requires scientific assumptions and `numpy`/`scipy`. Neither package establishes that a suite is “good” or that a proposed experiment caused an improvement.

**Smallest useful demo:** Run or import three repeated result files for a ten-test project, include one intentionally flaky test and one untested module, then show the proposed repeat/mutation/manual-review action.

**Acceptance criteria:** A report preserves every input run, separates observed from estimated fields, identifies missing denominators, and never collapses the packet to a single health score.

**Why better than separate tools:** Acumen can identify where evidence is structurally suspect while Calibre records how much confidence to place in repeated measurements. The joined artifact tells a maintainer what to measure next.

**Rejected adjacent components:** `ussyverse/levainussy` was omitted because its aggregate rise meter would encourage the universal code-health claim explicitly rejected in the existing analysis.

### 4. Documentation Drift Workbench

**Exact repositories:** `ussyverse/operonussy` + `ussyverse/rosettussy`

**User and recurring pain:** A Python maintainer updates public code and documentation separately, then discovers that examples, callable signatures, or runtime behavior no longer agree.

**Product promise:** “Turn documentation drift into a review packet with the exact callable, source text, doc text, and runtime check that disagree.”

**Input -> processing -> output:** Python package plus documentation files and an allowlist of safe callables -> Operon maps documentation clusters and trigger/deprecation signals; Rosetta compares AST/type/docstring information and optional runtime traces -> a drift packet listing stale or missing documentation, ambiguous ownership, and checks that require human review.

**Existing source to reuse:** **Exists:** [`operonussy/src/operon/mapper.py`](https://github.com/ussyverse/operonussy/blob/HEAD/src/operon/mapper.py), [`promoter.py`](https://github.com/ussyverse/operonussy/blob/HEAD/src/operon/promoter.py), and [`storage.py`](https://github.com/ussyverse/operonussy/blob/HEAD/src/operon/storage.py) provide clustering, trigger analysis, and local persistence. [`rosettussy/src/rosetta/inscription.py`](https://github.com/ussyverse/rosettussy/blob/HEAD/src/rosetta/inscription.py), [`scoring.py`](https://github.com/ussyverse/rosettussy/blob/HEAD/src/rosetta/scoring.py), and [`cli.py`](https://github.com/ussyverse/rosettussy/blob/HEAD/src/rosetta/cli.py) provide AST/type/docstring/runtime comparison and scoring.

**Missing integration work:** Map documentation sections to stable module/callable IDs, require an explicit safe-call fixture for runtime checks, and render source excerpts with the raw comparison evidence.

**Maturity and feasibility caveats:** Operon clustering is heuristic. Rosetta's runtime probe only works for a constrained callable set and may invoke code with side effects; a zero-argument call is not a general behavioral test. Scores are prioritization hints, not semantic truth.

**Smallest useful demo:** A three-function package with one changed parameter, one stale example, and one documented function that needs arguments. Produce a packet that marks the first two as observed drift and the third as unverified.

**Acceptance criteria:** No callable is executed without an explicit allowlist; every finding links to source and documentation locations; runtime-ineligible checks remain unverified; the user can accept or dismiss each finding.

**Why better than separate tools:** Static clustering supplies the likely documentation context, while Rosetta supplies a concrete code/document comparison. The result is an actionable review list rather than two unrelated scores.

**Rejected adjacent components:** `ussyverse/driftnetussy` was omitted because its checkout contains specifications and metadata but no implementation; adding it would make the proposed product depend on building the largest component first.

### 5. Pipeline Handoff Rehearsal

**Exact repositories:** `ussyverse/aquiferussy` + `ussyverse/cavityussy` + `ussyverse/telegraphaussy`

**User and recurring pain:** A data or operations team changes a multi-step local pipeline and wants to rehearse where pressure, queueing, deadlock, or handoff loss might appear before wiring production telemetry.

**Product promise:** “Use a small, inspectable scenario to find the next handoff to measure, without pretending a metaphorical score is an incident prediction.”

**Input -> processing -> output:** Service topology, observed throughput samples, queue/precedence rules, and known delay ranges -> Aquifer calculates flow and bottlenecks; Cavity analyzes impedance and standing-wave/deadlock patterns; Telegrapha evaluates route fidelity and precedence -> a rehearsal card with raw assumptions, bottleneck candidates, conservative scenarios, abort conditions, and next measurements.

**Existing source to reuse:** **Exists:** [`aquifer/topology.py`](https://github.com/ussyverse/aquiferussy/blob/HEAD/aquifer/topology.py) and [`aquifer/darcy.py`](https://github.com/ussyverse/aquiferussy/blob/HEAD/aquifer/darcy.py) model service topology, throughput, pressure, and bottlenecks. [`cavity/src/cavity/impedance.py`](https://github.com/ussyverse/cavityussy/blob/HEAD/src/cavity/impedance.py) and [`standing_wave.py`](https://github.com/ussyverse/cavityussy/blob/HEAD/src/cavity/standing_wave.py) implement pipeline impedance and STFT-style analysis. [`telegrapha/models.py`](https://github.com/ussyverse/telegraphaussy/blob/HEAD/telegrapha/models.py) and [`precedence.py`](https://github.com/ussyverse/telegraphaussy/blob/HEAD/telegrapha/precedence.py) model route fidelity/reliability and priority queues.

**Missing integration work:** Define one scenario schema with explicit units, adapt each model without silently converting semantics, retain input samples, and render a human review card. Production telemetry is out of scope for the demo.

**Maturity and feasibility caveats:** These models use different abstractions and are not validated as a combined operational predictor. Cavity's analysis needs numeric data and may be metaphorical for ordinary business pipelines. Any output must remain a hypothesis list, not an automated safety or capacity authority.

**Smallest useful demo:** A three-stage batch pipeline with ten observed runs, one queue priority rule, one injected delay, and a manually reviewed recommendation to instrument one boundary.

**Acceptance criteria:** Units and source observations are shown; each model can abstain when its inputs are missing; output names a measurement to collect; no incident probability or “healthy pipeline” verdict is emitted.

**Why better than separate tools:** Topology, delay behavior, and precedence are all views of the same handoff scenario. Their disagreement is itself visible and useful for deciding what to measure.

**Rejected adjacent components:** `mojomast/terrariumussy` and `ussyverse/fatigueussy` were not added because their aggregate observatory framing would repeat the unsupported universal-health pattern rejected in the existing report.

### 6. Departure Readiness Packet

**Exact repositories:** `ussyverse/modesaussy` + `ussyverse/migrationussy` + `ussyverse/portolanussy`

**User and recurring pain:** A small group can choose a destination but still misses a document, bag-access constraint, transfer reserve, or a deadline-specific check before leaving.

**Product promise:** “Convert a proposed group itinerary into a departure packet with failure controls, transfer reserves, and explicit source checks.”

**Input -> processing -> output:** Travelers, dates, destinations, budgets, constraints, luggage, and candidate transfer windows -> Migrationussy creates a group flyway, partial-traveler notes, budget status, and readiness warnings; Modesaussy scores failure modes into prevention/detection/contingency cards; Portolanussy computes conservative buffers, tide gates, fallback anchorages, and abort rules -> one dated departure packet and a post-trip learning log.

**Existing source to reuse:** **Exists:** [`modesaussy/src/lib.rs`](https://github.com/ussyverse/modesaussy/blob/HEAD/src/lib.rs) defines `Trip`, `FailureModeRow`, `analyze_trip`, action cards, and verification timelines. [`migrationussy/src/migration/planner.py`](https://github.com/ussyverse/migrationussy/blob/HEAD/src/migration/planner.py) provides destination scoring, availability windows, stop allocation, budget/readiness calculations, and Markdown export. [`portolanussy/src/lib.rs`](https://github.com/ussyverse/portolanussy/blob/HEAD/src/lib.rs) provides windows, reserves, shoals, buffers, safe-water scoring, pilotage cards, and abort modes.

**Missing integration work:** Join traveler, trip, leg, and item IDs; import authoritative document/opening data; keep manual estimates labeled; and produce one checklist with time zones and source links.

**Maturity and feasibility caveats:** Migration uses heuristic Borda/alignment and budget calculations. Modesa RPN is a prioritization method, not a probability. Portolan cannot know real travel times or opening hours without trusted inputs. This is planning assistance, not a safety guarantee.

**Smallest useful demo:** Two travelers, three destinations, one partial availability window, two documents, one transfer, and one candidate stop with a deliberately insufficient conservative buffer.

**Acceptance criteria:** The packet displays warnings and source timestamps, preserves partial participation, shows expected and conservative buffers separately, and lets a user override a recommendation with a reason.

**Why better than separate tools:** The group plan supplies the context for failure controls, while the transfer model supplies a concrete time boundary. A destination itinerary alone does not create a departure rehearsal.

**Rejected adjacent components:** `ussyverse/forageussy` was omitted because its routing contract uses Euclidean travel proxies and lacks the deadline and mandatory-stop semantics needed for this packet.

### 7. Memory Collection Lightbox

**Exact repositories:** `ussyverse/opticussy` + `ussyverse/taphonussy` + `ussyverse/mustiaussy`

**User and recurring pain:** Someone sorting a family photo folder and mixed paper/digital keepsakes cannot decide what is a duplicate, what carries unique context, what needs preservation, and what can safely leave the active collection.

**Product promise:** “Make a reversible keep/archive/review plan that preserves context instead of treating visual similarity as permission to delete.”

**Input -> processing -> output:** Photo directory plus CSV/JSON/TXT inventory and human collection purpose -> Opticussy scans byte signals, context tokens, clusters, and keeper candidates; Taphonussy parses inventory items, materials, condition, context, and risk pathways; Mustiaussy applies MUSTIE lanes and retention safety stops -> a lightbox-style review packet with candidate duplicates, preservation priorities, uncertain matches, and logged decisions.

**Existing source to reuse:** **Exists:** [`opticussy/src/lib.rs`](https://github.com/ussyverse/opticussy/blob/HEAD/src/lib.rs) provides `scan_photo_signals`, byte-derived signals, context grouping, clusters, and keeper recommendations. [`taphonussy/src/lib.rs`](https://github.com/ussyverse/taphonussy/blob/HEAD/src/lib.rs) discovers and parses inventory formats into `KeepsakeItem` and produces risk/pathway assessments. [`mustiaussy/src/mustia.ts`](https://github.com/ussyverse/mustiaussy/blob/HEAD/src/mustia.ts) provides `recommendDecision`, retention exceptions, collection analysis, policy, and CSV export.

**Missing integration work:** Map filenames and inventory IDs without assuming they are the same item, require human confirmation before destructive actions, copy or reference source files safely, and maintain an append-only decision log.

**Maturity and feasibility caveats:** Optic computes byte proxies and filename tokens; it does not decode image content or establish semantic duplicates. Taphon material extraction is heuristic. Mustia's decisions are policy aids, not legal advice, and a safety stop must block disposal.

**Smallest useful demo:** Ten photos, three inventory records, one near-duplicate-looking pair, one damaged paper item, and one sentimental/provenance exception. Export a review CSV without deleting anything.

**Acceptance criteria:** Every recommendation links to original paths and raw inventory; uncertain matches stay review-only; retention exceptions block discard; a human can record keep/archive/replace decisions; no source file changes occur.

**Why better than separate tools:** Photo grouping becomes useful only when joined to physical/context risk and retention decisions. The combined output protects meaning while reducing review volume.

**Rejected adjacent components:** `ussyverse/cartoucheussy` was omitted because transcription evidence is valuable for documents but would expand this MVP into an archival claim workflow already represented by the current shortlist.

### 8. Commons Rest-and-Revival Ledger

**Exact repositories:** `ussyverse/paddockussy` + `ussyverse/lichenoussy`

**User and recurring pain:** A community room, tool library, garden bed, or free shelf is repeatedly used, but caretakers notice wear and responsibility gaps only after the asset becomes difficult to use.

**Product promise:** “Schedule sustainable use and small restorative actions from the same evidence, without ranking people or declaring a civic space healthy.”

**Input -> processing -> output:** Asset capacity, bookings/usage events, rest requirements, condition observations, context notes, and nearby assets -> Paddockussy calculates pressure, capacity bands, rest debt, equivalent assets, and condition warnings; Lichenoussy weighs observations with recency/context dampeners, detects edge effects, recommends revival actions, and stores local observations -> a weekly stewardship ledger with rest windows, condition notes, named care loops, and a quiet-wins report.

**Existing source to reuse:** **Exists:** [`paddockussy/src/lib.rs`](https://github.com/ussyverse/paddockussy/blob/HEAD/src/lib.rs) defines assets, usage pressure, condition observations, stewardship plans, recovery capacity, and reports. [`lichenoussy/src/licheno/models.py`](https://github.com/ussyverse/lichenoussy/blob/HEAD/src/licheno/models.py), [`engine.py`](https://github.com/ussyverse/lichenoussy/blob/HEAD/src/licheno/engine.py), [`storage.py`](https://github.com/ussyverse/lichenoussy/blob/HEAD/src/licheno/storage.py), and [`export.py`](https://github.com/ussyverse/lichenoussy/blob/HEAD/src/licheno/export.py) implement place-based observations, context dampening, edge effects, SQLite/JSON storage, revival suggestions, and quiet-wins exports.

**Missing integration work:** Define a shared asset and local date schema, map Paddock condition indicators to Licheno indicators without merging unlike scores, add a booking/import surface, and make rest/action decisions explicitly reviewable.

**Maturity and feasibility caveats:** Paddock's pressure formula and Licheno's gradient bands are configurable heuristics, not ecological or social measurements. Owner ambiguity must not become a person score. There is no calendar, reservation, notification, or multi-user conflict handling in the inspected cores.

**Smallest useful demo:** One shared room, ten usage events, four condition observations, one weather/maintenance context, and one equivalent room. Produce a rest recommendation and a care-walk sheet.

**Acceptance criteria:** Raw usage and observation records remain visible; rest windows show their assumptions; context can soften but not erase a negative observation; no person leaderboard is emitted; the user can reject or annotate every suggested action.

**Why better than separate tools:** Paddock explains use pressure and recovery, while Licheno explains what a caretaker can observe and do next. Together they close the loop from booking load to restorative action without recruiting a volunteer network.

**Rejected adjacent components:** `ussyverse/commonsaussy` and `ussyverse/hoistussy` were omitted because their strongest existing combination is already current shortlist item #7 and focuses on bounded contribution asks, not asset recovery.

## Rejected New Directions

### R1. Universal Release Health Score

**Temptation:** Combine `mintussy`, `cambiumussy`, `portmoreussy`, `acumenussy`, `calibreussy`, and `cavityussy` into one red/yellow/green repository score.

**Reject:** These components observe different things with different units, baselines, and uncertainty. Averaging provenance findings, interface heuristics, license obligations, test evidence, measurement repeatability, and pipeline resonance would hide the raw evidence and invite an unsupported “safe” or “healthy” claim. Ideas 2 and 3 keep the user decisions separate and preserve unknowns.

### R2. Automatic Household Disposal and Preservation Agent

**Temptation:** Let `opticussy`, `taphonussy`, `mustiaussy`, and a general vision or OCR agent automatically delete duplicates and discard low-value keepsakes.

**Reject:** Optic's signals are byte and filename proxies, Taphon's material/context extraction is heuristic, and Mustia explicitly models legal, medical, sentimental, provenance, and stakeholder safety stops. Automatic deletion would turn prioritization aids into irreversible authority. Idea 7 remains review-only and emits a reversible CSV/log.

## Provenance

### Current shortlist used for exclusion

The ten source-checked proposals excluded from the repository selections above are: Kuleshov/Foleya/Chromascript production planning; Andonia/Shewharta/A3 service improvement; Triage/Petrichor CI evidence; Cartouche/Archivio family archive; Cladwise/Criterio learning lab; Racia/Transacta household handoff; Commonsa/Hoist volunteer desk; Tonal/Phyllotaxis/Shoedel music sketchbook; Hitch/ChurnMap dependency refactoring; and Retoura/Prospecta returns.

### Inspected revisions

The following short revisions were captured with `git -C <repo> rev-parse --short HEAD` on 2026-09-13:

| Repository | Revision |
|---|---|
| `ussyverse/recapturaussy` | `2640919` |
| `ussyverse/bidussy` | `4073119` |
| `ussyverse/taktussy` | `cf74d27` |
| `ussyverse/mintussy` | `ade5430` |
| `ussyverse/cambiumussy` | `5fe4d0d` |
| `ussyverse/portmoreussy` | `06cf815` |
| `ussyverse/acumenussy` | `403acf7` |
| `ussyverse/calibreussy` | `d9231bd` |
| `ussyverse/operonussy` | `c9c1cd4` |
| `ussyverse/rosettussy` | `59a8544` |
| `ussyverse/aquiferussy` | `375260b` |
| `ussyverse/cavityussy` | `10d6b4d` |
| `ussyverse/telegraphaussy` | `27fe051` |
| `ussyverse/modesaussy` | `e3db8f8` |
| `ussyverse/migrationussy` | `493a598` |
| `ussyverse/portolanussy` | `3973697` |
| `ussyverse/opticussy` | `7bd1350` |
| `ussyverse/taphonussy` | `432c97d` |
| `ussyverse/mustiaussy` | `122fc0a` |
| `ussyverse/paddockussy` | `b5fb590` |
| `ussyverse/lichenoussy` | `7633132` |

### Commands and verification limits

- Read `brainstorm/README.md`, `brainstorm/AGENTS.md`, `docs/SOURCE_CHECKED_COMBINATIONS.md`, and `docs/REPOSITORY_INDEX.md`.
- Listed the cloned `ussyverse` repositories with `ls /home/ubuntu/ussy/repos/ussyverse`.
- Read the source paths linked in the ideas and inspected manifests/READMEs for the selected repositories.
- Captured each revision listed above with `git -C ... rev-parse --short HEAD`.
- Did not install dependencies, build packages, run tests, run CLIs, connect external services, or modify any candidate repository.
- This file is a proposal and evidence handoff, not proof that any combined workflow currently runs.
