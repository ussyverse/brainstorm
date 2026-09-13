# What I would build from the Ussyverse
Date: 2026-09-13

Independent product assessment of `ussyverse/brainstorm` at `312ccf64b56a07f74711ddb11e564aad3d888247`.

## Decision

**Build Agent Fix Lab first:** a small, local tool that turns a failed coding-agent run and a human correction into a reproducible regression case with evidence showing what changed.

Start with **ussyverse/triageussy + ussyverse/petrichorussy + mojomast/hermes-correction-aware-learning**. Target Python projects and one agent workflow initially. A Hermes import adapter is proposed follow-on work. Defer AgentReplay as a dependency until its implementation is repaired and its chosen architecture is tested.

For a business-facing product, my strongest alternative is a **service-improvement desk for small repair/IT service teams**, using Andonia, Shewharta, and A3via. The **shot-to-sound planner** remains the strongest creative experiment.

This is a recommendation about where Kyle should spend the next focused development cycle. It is informed by his existing agent-tooling and IT-operations work, inspected component contracts, runtime checks, adoption burden, and current alternatives. It is not a market-demand measurement.

## Scope and evidence

I cloned the research notebook and 13 candidate repositories. I reviewed the two main synthesis reports, scanned the catalogue and selected underlying idea passes, inspected relevant source and manifests, and checked current primary-source product documentation.

The notebook contains 459 catalogue entries. I did not perform 459 source audits or reread every line of all 20 raw idea files. I ran four existing Python test suites and small direct runtime probes. No integrated product, live Hermes session, Go/Rust/Zig application, or customer study was tested.

Evidence labels in this assessment:

- **Exists:** present in the inspected source.
- **Runtime checked:** the specifically described command or probe succeeded or produced the recorded finding.
- **Proposed:** product behavior or integration still to build.
- **Unverified:** runtime behavior, user demand, or compatibility not established here.

The source notebook's strongest contribution is its distinction between small reusable engines and complete applications. Its conclusions should be read alongside its explicit static-review limitations. [Original synthesis](https://github.com/ussyverse/brainstorm/blob/312ccf64b56a07f74711ddb11e564aad3d888247/docs/COMPOUNDED_IDEAS.md).

## My ranking

The order weighs recurring pain, practical reuse, ability to reach early users, required data entry, differentiation, and remaining integration work. I have not assigned numerical market scores.

| Priority | Product | Components | Reason to build | Main uncertainty |
|---|---|---|---|---|
| 1 | Agent Fix Lab | Triage + Petrichor + correction-aware-learning | Fits an existing repeated workflow; useful artifacts can live beside the code; all three Python suites passed | Whether preparing a trustworthy case is materially faster than doing it by hand |
| 2 | Service-improvement desk | Andonia + Shewharta + A3via | Connects repeat service problems to owned changes and a scheduled effectiveness review | Whether a small team supplies usable observations and completes follow-up |
| 3 | Shot-to-sound capture planner | Kuleshov + Foleya; Chromascript later | Clear creative demonstration and an understandable production checklist | Whether creators adopt the extra planning step and save revision effort |
| 4 | Scope-and-capacity quote worksheet | Bid + Takt; Recaptura only for demonstrated duplicate-list needs | Helps expose unclear scope and workload before a commitment | Sparse quote history and the absence of a real scheduling model |

The CI evidence-packet idea is the first useful slice of Agent Fix Lab. I would develop it as part of that product, then add correction and regression linkage. I would not maintain two competing products around the same run artifacts.

## What I agree with, and what I would change

**Keep the shared-workflow principle.** A run, incident, or scene is a good integration boundary. Combining components is worthwhile when it removes repeated work or preserves context during a revision.

**Treat the report as an output, not the whole product.** The lasting value is that the next failure, revision, or review can reuse previous evidence. A static packet alone is easy to abandon after its first export.

**Weight adoption more heavily.** Several proposals require ordinary people to enter elaborate structured data before receiving a checklist. Input effort, recurring use, and an existing distribution channel deserve more weight than a polished demonstration.

**Relax repository quotas.** The notebook prefers two to four projects and, where practical, two Ussyverse organization repositories. That is a useful search constraint, but a working product may need one strong engine and a modest amount of ordinary application code. Do not introduce another runtime solely to increase reuse.

**Reduce reliance on scientific metaphors.** Useful functions and data models survive after the branding is removed. Tests can establish implementation behavior; they cannot establish that a heuristic predicts quality, demand, comfort, or causal improvement.

**Separate prototype estimates from product readiness.** The notebook's short effort estimates explicitly exclude production concerns. They should not become launch commitments. Import, validation, reliable persistence, meaningful errors, and installation are often most of the remaining product work.

## Runtime findings that affect the decision

| Component/check | Result | Consequence |
|---|---|---|
| Triage existing suite | **160 passed**, 0.45 s | Credible starting point for log extraction, within its parser coverage |
| Petrichor existing suite | **140 passed**, 0.35 s | Useful configuration-history core; baseline selection and secret filtering remain product work |
| Correction-aware-learning existing suite | **76 passed**, 1.64 s | Stronger practical starting point for correction records than adding a generic procedural heuristic |
| Bid existing suite | **28 passed**, 0.18 s | Pricing calculations execute as tested; this establishes no real-world pricing accuracy |
| Correction-aware-learning demo | All seven reported checks true; shadow-only and activation disabled | Lifecycle, retraction, idempotency, and privacy-canary behavior worked in its supplied demo |
| Kuleshov authored-input probe | Five new clips analyzed; fractional durations and sequence IDs survived save/load with an in-memory localStorage substitute | The core accepts authored data; this did not test a browser editor |
| Kuleshov invalid-input probe | A negative duration was accepted by the analysis function | A product needs validation at its input boundary |
| Triage + Petrichor joint smoke probe | Same Python command exited 0 with a flag off and 1 with it on; error extraction and the exact flag diff were produced | A narrow symptom-plus-environment join works on a controlled example |
| AgentReplay SQLite store inspection and Node export probe | Source imports `createHash` from `zlib`; Node reported that export as undefined | The specifically cited store requires repair before reuse |

**404 existing Python tests passed in total; 376 belong to the three recommended initial components.** These are component tests, not an integration certification.

Two additional boundaries matter:

- Triage returns success when its parser finds no recognized errors. An unfamiliar failed process must retain its actual nonzero exit status independently of parser output. My unfamiliar-log probe produced zero recognized errors. [Extractor](https://github.com/ussyverse/triageussy/blob/36a391039b286a5571c91574267efe644d8ec1fe/triage/extractor.py), [CLI](https://github.com/ussyverse/triageussy/blob/36a391039b286a5571c91574267efe644d8ec1fe/triage/cli.py).
- AgentReplay contains a Python/PostgreSQL application and a separate TypeScript/SQLite implementation. The notebook cites the latter. I did not establish interoperability or a working end-to-end replay system. Besides the wrong hash import, the store applies `promisify` to stream constructors; that use needs correction and testing. [Store](https://github.com/mojomast/clanker03/blob/e9f8608828c31077980f9e86224799c60c8f73e4/agentreplay/store.ts), [root application](https://github.com/mojomast/clanker03/blob/e9f8608828c31077980f9e86224799c60c8f73e4/README.md).

## 1. Agent Fix Lab

### User, recurring pain, and promise

Start with a maintainer using coding agents on Python repositories. They repeatedly explain a failure, locate the relevant output, correct the agent, and later discover that the same mistake has returned.

**Promise:** “Turn this failure into a case you can check after the next change.”

The first cases should involve concrete tool/test outcomes: an import failure, wrong configuration, failed verification, or an explicitly reviewed premature-completion claim. Broad natural-language behavioral evaluation belongs after this narrow workflow works.

### Exact reuse

| Repository | Existing capability | Intended contribution |
|---|---|---|
| `ussyverse/triageussy` | `ErrorExtractor.extract_from_text`, structured locations/context, diagnostic rendering | Extract a readable symptom from the original output |
| `ussyverse/petrichorussy` | `SoilMemory.snapshot_text`, stored text, hashes, diffs, history | Show selected configuration changes between comparable runs |
| `mojomast/hermes-correction-aware-learning` | Immutable outcome records, correction pairs, retractions, recurrence evaluation | Preserve the distinction between an observed failure, a human correction, and later verification |
| `mojomast/hermes-agent`, optional adapter | Deterministic task-router evaluation | Support routing-specific cases when that particular fork is the target |

Source: [Triage extractor](https://github.com/ussyverse/triageussy/blob/36a391039b286a5571c91574267efe644d8ec1fe/triage/extractor.py), [Petrichor store interface](https://github.com/ussyverse/petrichorussy/blob/76b19e47e1aa1800e16b02aa73a8462bacddcad6/src/petrichor/soil.py), [correction store](https://github.com/mojomast/hermes-correction-aware-learning/blob/84c8c8c7e27c820cbc1aa0a5fcf99f891f503f48/src/correction_aware_learning/store.py), [recurrence](https://github.com/mojomast/hermes-correction-aware-learning/blob/84c8c8c7e27c820cbc1aa0a5fcf99f891f503f48/src/correction_aware_learning/recurrence.py), [Hermes routing evaluator](https://github.com/mojomast/hermes-agent/blob/cd941c46745e09d475d75d7ac88d41bc5364a0ed/agent/task_router_eval.py).

### Proposed workflow

1. Import a saved failed run with command, actual exit status, working directory, commit, selected configuration, and retained output.
2. Select a comparable baseline. Display missing fields instead of inventing environment history.
3. Extract error evidence and display configuration differences.
4. Let the maintainer state the expected result, record the correction, and attach an existing regression test or author a small reproducer.
5. Execute the selected test against the relevant baseline and candidate. Retain the implementation identity, outputs, and verdict for each run.
6. Save a portable case manifest, an evidence report, and the runnable regression artifact beside the project. Link subsequent observations to the case.

**Smallest useful demo:** one real previously encountered failure, one maintained regression case, and a changed implementation that passes the case while the faulty implementation fails it. A second person should be able to run it from the saved instructions.

### Work that does not already exist

The case schema, importer, trusted process capture, comparison policy, regression-artifact editor, test invocation, and joined user interface are all **proposed**. A failure log cannot automatically become a correct runnable test without additional work and human review.

Correction-aware-learning deliberately stores constrained structural records and emits count-only public recurrence reports. Keep selected content in a separate case-artifact layer and link it through opaque IDs/digests. Do not relax the package's privacy boundary to make it act as a transcript database. Its source labels are caller assertions; the host must establish where a verification result came from. [Model](https://github.com/mojomast/hermes-correction-aware-learning/blob/84c8c8c7e27c820cbc1aa0a5fcf99f891f503f48/src/correction_aware_learning/model.py), [pytest capture](https://github.com/mojomast/hermes-correction-aware-learning/blob/84c8c8c7e27c820cbc1aa0a5fcf99f891f503f48/src/correction_aware_learning/pytest_capture.py), [public projection](https://github.com/mojomast/hermes-correction-aware-learning/blob/84c8c8c7e27c820cbc1aa0a5fcf99f891f503f48/src/correction_aware_learning/reports.py).

Acceptance requires:

- Actual process status survives unrecognized logs and parser failures.
- Repeated imports preserve case identity and do not double-count an incident.
- Failed, not-run, and inconclusive outcomes remain distinguishable.
- The regression executes the implementation being checked; cached transcript playback cannot establish that a change works.
- Human labels and deterministic observations remain distinct.
- Export includes only deliberately selected content; private-value canaries do not leak.
- A case round-trips through storage without losing its revision, command, expected outcome, or linked correction.

Hermes's inspected evaluator checks a deterministic router. It does not rerun arbitrary model reasoning or establish a complete agent's reliability. Any later model-dependent evaluation needs fresh executions and repeated trials appropriate to its variability.

### Differentiation and validation

Trace-to-dataset evaluation already exists in [Langfuse](https://langfuse.com/docs/evaluation/get-started/offline), and [Braintrust](https://www.braintrust.dev/docs/evaluation-quickstart) offers evaluation workflows. That rules out “we have traces and evals” as a sufficient product claim.

My proposed distinction is a particularly fast path from a coding-agent failure to a portable repository-level regression artifact, with explicit correction history and comparable configuration evidence. Whether that workflow is sufficiently better remains **unverified**.

Start as a small CLI plus a local case viewer. Use Kyle's own projects to obtain real cases; test with other maintainers before adding hosting or more harnesses. Paid team workflow, installation/support, and CI integration are possible business models to validate later.

Rejected first-stage components: Chainlet's general behavioral-chaining analysis does not add essential information to this particular case; Rosetta's runtime witness expands execution scope; AgentReplay adds repair and architecture-selection work; another orchestration layer adds no necessary output.

## 2. Service-improvement desk

**Exact repositories:** `ussyverse/andoniaussy`, `ussyverse/shewhartaussy`, `ussyverse/a3viaussy`.

**User:** a small repair shop or IT service team with repeated intake omissions, callbacks, handoff failures, or rework.

**Promise:** “Find the repeat problem, give one change an owner, and check whether the problem improved.”

**Flow:** imported service events and workload observations → recurrence review → a clearly defined metric/baseline → owned experiment with check date → review decision and revised checklist.

**Exists:** Andonia's event cards and recurrence groups; Shewharta's XmR limits/signals; A3via's problem, observation, experiment, check, and standard-work models. [Andonia](https://github.com/ussyverse/andoniaussy/blob/222a203f2d28b2b0c863e0a2e9f05dc99fc37a69/internal/andonia/andonia.go), [Shewharta](https://github.com/ussyverse/shewhartaussy/blob/8955b86966b31823cd2c514d01dee98f886bf46d/pkg/shewharta/engine.go), [A3via](https://github.com/ussyverse/a3viaussy/blob/839ce111cb54fab812ddc5e575ad8d38894fc60f/internal/a3/model.go).

**Proposed:** one capture/import surface, stable event-to-problem links, correct time buckets, workload denominators, reminders, and a joined report. Andonia and A3via use Go `internal/` packages; reuse needs their CLI boundary or an intentional package refactor.

**Maturity:** source-inspected; Go runtime not tested here. Andonia's recurrence grouping uses normalized text, so real issue classification is new work. Its report covers all supplied events, so the importer must select the period. Shewharta's marked-change rule takes precedence over other point classifications near the change date; preserve independent numeric facts in the product.

**Demo and acceptance:** import 20 days of observations with explicit closures, missing entries, and true zeros; connect one repeated issue to one checklist change; assign a check date; record the subsequent result. Rates require denominators. A changed chart alone does not establish causality.

**Why combine:** the joined product carries an operational problem through action and follow-up. The individual tools cover separate parts of that lifecycle.

**Positioning:** test one repair/IT-service niche using its existing records. A CSV export from `mojomast/ticket2` could be a later input; its compatibility was not checked. Avoid creating another ticketing system. Commercial value is plausible because repeat work consumes paid staff time, but willingness to pay remains untested.

Rejected adjacent components: generic pricing forecasts, a second task board, and live ticket-system integration before a manual import pilot succeeds.

## 3. Shot-to-sound capture planner

**Exact repositories:** `ussyverse/kuleshovussy` + `ussyverse/foleyaussy`; add `ussyverse/chromascriptussy` only after demonstrated need.

**User:** a solo creator or small film group planning a short practical sequence.

**Promise:** “Leave the shoot with the shots and sounds your sequence needs.”

**Flow:** creator-authored shots/action beats → editable shot order and Foley suggestions → checked capture/take list → updated preparation plan when the sequence changes.

**Exists:** Kuleshov analyzes metadata and exports planning rows; Foleya generates cue suggestions and recording checklists; Chromascript validates supplied palette beats and renders color strips. [Kuleshov engine](https://github.com/ussyverse/kuleshovussy/blob/72bdd0f2d6b0df3663f9e44847f03091371b58a4/src/engine.ts), [Foleya](https://github.com/ussyverse/foleyaussy/blob/2f6ec0e13a1a6e6c5ae11c7fb1667ece1cddceb2/foleya.go), [Chromascript](https://github.com/ussyverse/chromascriptussy/blob/5940bde5155a525d85d82927c6a2593c08b90ae9/src/lib.rs).

**Proposed:** a normal editor, stable scene/action/cue identities, accurate editable offsets, take attachment, persistence, and portable export. Foleya assigns integer-second suggestions and regenerates cue IDs from order; preserving edits needs a separate canonical model.

**Maturity:** Kuleshov's authored-data/storage probe worked, with missing duration validation. Foleya and Chromascript received static review only. None analyzes actual video content; Foleya does not generate or record audio.

**Demo and acceptance:** plan and shoot a 60–90 second sequence, add two sound takes, reorder a scene, save/reload, and confirm that edits remain attached to the right actions. Measure missing captures and revision time against the creator's existing checklist.

**Why combine:** shot revisions and sound preparation share timing and scene identity. That is a real integration benefit.

The notebook places this first partly because the demonstration is clear. I rank it third because adoption and differentiation are unproven. [StudioBinder](https://www.studiobinder.com/shot-list-storyboard/) already provides shot lists, sound fields, scheduling, checklists, and exports. The opportunity therefore needs to be the specific revision-and-capture workflow, ease of use, or a focused audience—not the mere presence of a shot list.

Rejected adjacent components: initial color scoring, automatic editing, asset generation, and a full production-management suite. Keep editorial warnings dismissible so an intentional creative choice does not become an error to “fix.”

## 4. Scope-and-capacity quote worksheet

**Exact repositories:** `ussyverse/bidussy` + `ussyverse/taktussy`; optionally `ussyverse/recapturaussy`.

**User:** an owner quoting repeatable repair or service jobs from incomplete requests.

**Promise:** “See missing scope and workload implications before making the commitment.”

**Flow:** explicitly scoped request, owner-entered effort and limits, comparable quote history → transparent quote scenarios and workload calculation → reviewable quotation worksheet.

**Exists:** Bid's historical-quote structures and empirical/logistic calculations; Takt's weekly capacity/demand model and persistence; Recaptura's normalization/alias and overlap functions. [Bid](https://github.com/ussyverse/bidussy/blob/4073119cf248c470c6956b769d2ba2926fb69586/src/bid/demand.py), [Takt](https://github.com/ussyverse/taktussy/blob/cf74d276436414570531f222066621b5cd410396/src/lib.rs), [Recaptura](https://github.com/ussyverse/recapturaussy/blob/26409192246c532b78cc51f9c75860b40259ec74/src/lib.zig).

**Proposed:** scoped line items, currency/unit policy, real committed jobs, due dates, capacity arithmetic, editable quotes, and outcome recording.

**Maturity:** Bid's 28 tests pass; the other two were not run. Takt stores historical demand as week/quantity and averages production times across service types. It does not provide job-level scheduling or a service-mix-aware booking calendar. The capacity-conflict deliverable therefore requires more new work than the combination's name suggests.

**Demo and acceptance:** use ten comparable historical jobs and one new request; expose missing effort, a workload conflict, and the assumptions behind a scenario. Preserve every input row and allow incorrect identity merges to be reversed.

**Why combine:** quote and workload decisions should use the same scoped job. Capture-recapture estimation is unnecessary unless actual source-list overlap is part of the customer's recurring problem.

[Jobber](https://www.getjobber.com/features/field-service-management-software/) already joins quoting, scheduling, follow-up, and reporting. I would test a sharply defined scoping problem before building a general service desk. Historical acceptance at different prices is not proof of a causal price-response curve.

Rejected adjacent components: unseen-demand estimation as the lead feature, automatic “optimal” prices, and CRM/payments infrastructure.

## What stays on the bench

- **Recoverable archive release:** a strong specialist service opportunity if an authorized site owner has a concrete recovery need. The notebook's Arrhivescrape/Archivio/Snapshot proposal deserves a pilot, but I did not freshly inspect or run those three in this pass. Use the notebook's export-filtering findings as a gate. [Archive proposal](https://github.com/ussyverse/brainstorm/blob/312ccf64b56a07f74711ddb11e564aad3d888247/docs/COMPOUNDED_IDEAS.md).
- **Test calibration:** retain individual repeat-run measurements and concrete diagnostics. The combined metrology framing needs stronger justification than a new score.
- **Game replay tooling:** useful within a chosen game engine and content pipeline. A cross-engine product creates substantial semantic mapping work.
- **Music tools:** worth pursuing as a creative direction, but the catalogue's harmony/pattern components do not establish real-time guitar listening or adaptive accompaniment.
- **Household, civic, health, and safety heuristics:** the notebook contains interesting utilities, but structured data entry, validation burden, and uncertain recurring use make them weaker first product bets for this decision.
- **Broad agent platforms and ecosystem dashboards:** select an existing host when needed. Concentrate new development on a completed user task.

## The next development cycle

Treat this as a **two-week validation budget**, not a promise of production readiness.

| Stage | Work | Evidence required to continue |
|---|---|---|
| Days 1–2 | Collect ten real failures from one existing workflow; define case fields and comparison rules | At least several cases have enough evidence for a runnable or directly checkable regression |
| Days 3–5 | Build saved-run import and the joined error/configuration report | Correct handling of missing evidence, unknown errors, duplicate import, and comparable baselines |
| Days 6–8 | Add correction links and a maintained regression command/artifact | Faulty baseline fails, corrected implementation passes, and an unrelated case remains checked |
| Days 9–10 | Have five maintainers create and rerun cases from their own work | Measure preparation time, follow-up effort, and whether they independently reuse the saved case |

Continue if at least three of five maintainers can turn a real failure into a useful rerunnable case materially faster than their existing method and use it again on a later change. This is a proposed decision threshold, not a statistically representative demand study.

Stop or narrow scope if every case needs bespoke expert reconstruction, users only want log search, exports lose essential context, or the workflow takes longer than maintaining a normal regression test. Add additional harnesses only after one importer works on real histories.

## Revisions and commands

The research clone was shallow, on `main`; GitHub showed no open issues at review time. Candidate source was not modified. This dated report adds an independent assessment without replacing the original synthesis.

| Repository | Inspected checkout revision |
|---|---|
| ussyverse/brainstorm | 312ccf64b56a07f74711ddb11e564aad3d888247 |
| ussyverse/triageussy | 36a391039b286a5571c91574267efe644d8ec1fe |
| ussyverse/petrichorussy | 76b19e47e1aa1800e16b02aa73a8462bacddcad6 |
| mojomast/hermes-correction-aware-learning | 84c8c8c7e27c820cbc1aa0a5fcf99f891f503f48 |
| mojomast/clanker03 | e9f8608828c31077980f9e86224799c60c8f73e4 |
| ussyverse/kuleshovussy | 72bdd0f2d6b0df3663f9e44847f03091371b58a4 |
| ussyverse/foleyaussy | 2f6ec0e13a1a6e6c5ae11c7fb1667ece1cddceb2 |
| ussyverse/chromascriptussy | 5940bde5155a525d85d82927c6a2593c08b90ae9 |
| ussyverse/bidussy | 4073119cf248c470c6956b769d2ba2926fb69586 |
| ussyverse/taktussy | cf74d276436414570531f222066621b5cd410396 |
| ussyverse/recapturaussy | 26409192246c532b78cc51f9c75860b40259ec74 |
| ussyverse/andoniaussy | 222a203f2d28b2b0c863e0a2e9f05dc99fc37a69 |
| ussyverse/shewhartaussy | 8955b86966b31823cd2c514d01dee98f886bf46d |
| ussyverse/a3viaussy | 839ce111cb54fab812ddc5e575ad8d38894fc60f |

Hermes's `agent/task_router_eval.py` was fetched through GitHub from `mojomast-main` at `cd941c46745e09d475d75d7ac88d41bc5364a0ed`; it was source-reviewed, not executed.

Commands run included:

- `git clone --depth 1 --branch main https://github.com/ussyverse/brainstorm.git` with the explicit workspace destination.
- Sequential shallow clones of the 13 candidates; `git rev-parse HEAD`; source searches/reads with `rg`, `sed`, `cat`, and Python.
- A fresh scratch Python 3.12.14 environment with pytest 9.1.1.
- From each of correction-aware-learning, Petrichor, and Bid: `PYTHONPATH=src /workspace/scratch/80c982501ebf/review-venv/bin/python -m pytest -q`.
- From Triage: `PYTHONPATH=. /workspace/scratch/80c982501ebf/review-venv/bin/python -m pytest -q`.
- Correction package: `PYTHONPATH=src python -m correction_aware_learning demo`.
- Node 24.19.0 direct imports of Kuleshov's TypeScript engine/storage for the described authored-input probe and inspection of `node:zlib` exports.
- A temporary Python subprocess fixture connecting actual command status to Triage extraction and Petrichor snapshots; an unfamiliar-log extraction probe.
- Read-only GitHub metadata/issues and current primary-source product documentation.

No Go, Rust, or Zig toolchain was present in this environment. Their absence is a verification limit, not evidence that those components fail. Kuleshov's full Vite/Vitest application build was not run. No code was committed or pushed, no external users were contacted, and no complete Agent Fix Lab was implemented.
