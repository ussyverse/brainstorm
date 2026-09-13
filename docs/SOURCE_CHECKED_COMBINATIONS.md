# Useful combinations: an independent, source-checked analysis

**Date:** 2026-09-13 · **Catalog screened:** all 459 entries (330 `ussyverse`, 129 `mojomast`).

## Recommendation in brief

**Build a small audiovisual production planner first:** `ussyverse/kuleshovussy` + `ussyverse/foleyaussy` + `ussyverse/chromascriptussy`. Give an independent creator one editable sequence that produces a missing-shot list, a recording checklist, and a color strip. Start with shot order and Foley, then add color. This has a clear user, useful outputs before sophisticated automation, and an immediately understandable demonstration.

For a business-first product, choose **service problems → measured improvement** with `ussyverse/andoniaussy`, `ussyverse/shewhartaussy`, and `ussyverse/a3viaussy`. For a developer-first product, choose **CI failure evidence packets** with `ussyverse/triageussy` and `ussyverse/petrichorussy`.

**All ten combinations below are proposals.** Existing component functions and data formats are distinguished from the adapters and product workflows still to build. I did not find an existing end-to-end integration for these particular combinations in the inspected files.

## 1. Methodology and coverage

### Full-catalog screening

I read the **entire [INDEX.md](REPOSITORY_INDEX.md), lines 1–3308**, including the prior combinations and every repository entry. Reading windows were 1–240, 241–540, 541–840, 841–1140, 1141–1440, 1441–1740, 1741–2040, 2041–2360, 2361–2680, 2681–3000, and 3001–3308. The owner sections cover `mojomast/365compromisesleuth` through `mojomast/ytkiosk`, then `ussyverse/a3viaussy` through `ussyverse/zooxussy`.

I also read [the previous combinations document](combos.md). The existing `parts/` batch analyses are background provenance for the index, not independent confirmation of its capability claims; I did not reread those twenty files. This analysis does not use previous integration suggestions as evidence that integrations exist.

Every catalog entry was screened for:

1. A concrete user with a recurring task, rather than a new dashboard seeking a purpose.
2. A useful artifact or decision the combined system can produce.
3. A handoff between complementary capabilities: what information crosses the boundary?
4. A plausible two-to-four-project scope, preferentially using org projects.
5. Whether the concept depends on unverified predictions, missing implementation, or substantial new infrastructure.

The resulting catalog-wide dispositions were:

| Catalog area screened | Decision and reasoning |
|---|---|
| Agent runtimes, coding-agent forks, build harness generations, planning tools, LLM routers | Mostly enabling infrastructure or competing products. Chaining several does not itself solve a new recurring task. No orchestration stack made the shortlist. |
| Hosting, Discord/IRC bots, M365/admin tools, backup, network tools | Several concrete applications, but forcing in two org projects usually added weak analytics or unrelated machinery. Existing infrastructure is not a mandatory dependency of a local prototype. |
| Games, emulators, MUDs, PS1 recompilation, Vesuvius research | Strong specialist work, but most convincing integrations are already within their own ecosystem or require substantial engine/content/research validation. No forced cross-engine merger. |
| Code analysis, CI diagnosis, configuration history, dependency graphs, documentation | Promoted evidence extraction and history joining. Demoted aggregate “health,” architecture predictions, and scientific labels unsupported by relevant measurements. See #3 and #9. |
| Creative writing, visual media, music, craft tools, production packages | Promoted explicit sequences and generative data with inspectable exports. See #1 and #8. Craft formulas and prose heuristics remain useful standalone possibilities, not automatic companions merely because both concern creativity. |
| Study, practice, concept maps, reminders | Promoted contrast repair plus confidence/outcome evidence. Avoided stacking multiple mastery models. See #5 and the cue component in #10. |
| Small-business metrics, service operations, pricing, demand, cash flow | Promoted capture → investigation → follow-up. Did not assume a ticket system exports the fields required by unrelated financial models. See #2. |
| Household coordination, organization, purchases, returns, travel | Promoted responsibility/knowledge handoffs and return follow-through. See #6 and #10. Travel optimizers require real opening hours, travel times, and deadlines before their outputs become actionable routes. |
| Civic participation, mutual aid, shared assets, neighborhood observations | Promoted bounded resource asks with a notice lifecycle. Avoided combining different social scores into a person-ranking system. See #7. |
| Health, emergency readiness, outdoor hazards, repairs, food safety, physiological/wellness metaphors | Screened, but not promoted into automated medical, safety, or financial authorities. A deterministic rule engine or a disclaimer does not establish predictive validity. Household shortlist items concern ordinary coordination and paperwork. |
| Meta-indexes, duplicates, old generations, empty/demo/spec-only repositories | Retained as catalog context; no implementation credit for empty repositories, documentation plans, mirrors counted as distinct capabilities, or “production-ready” labels alone. |

These are overlapping screening families, not invented per-category census counts. **459/459 is index-level screening coverage, not 459 source audits.**

### Source-check depth

I inspected actual source in **27 repositories: 25 from `ussyverse`, two from `mojomast`**. These comprise all 23 distinct shortlist components, plus `ussyverse/ebbinghausussy`, `ussyverse/levainussy`, `ussyverse/forageussy`, and `mojomast/terrariumussy`. I separately checked the directory contents of `ussyverse/driftnetussy`, confirming spec documents without implementation. READMEs were checked for these candidate tools, with manifests for every top-five component and selected existing tests examined where informative.

The source paths below identify the portions actually supporting each proposal. **Not every source file was read, and no cloned project was built, installed, runtime-tested, or modified.** Existing tests are evidence of intended contracts, not proof that tests currently pass or that the product works in deployment. Most inspected org packages are small prototypes; a complete domain function often sits behind a demo-only interface.

No applicable `AGENTS.md` was found for this new document or the candidate source trees inspected. Instructions present inside unrelated cloned projects did not apply to this work.

### Ranking approach

Ordering favors recurring usefulness, complementarity, concrete reuse, demonstrability, and limited missing work. It is a product judgment, not a measured market ranking. Estimates below assume one experienced developer and a local single-user prototype after basic dependency setup; they exclude production hosting and multi-user synchronization.

Do not infer package identity from repository spelling: several org Go modules still declare `github.com/mojomast/...`, and the music frontend repository is **`mojomast/shoedelussy`**, despite calling itself “strudelussy.” Use the checked-out code and its manifest when preparing a build.

## 2. Ranked shortlist

| Rank | Proposal | Exact repositories | Why the combination earns its complexity | Main implementation gap |
|---|---|---|---|---|
| **1** | **Shot-to-sound production planner** | `ussyverse/kuleshovussy` + `ussyverse/foleyaussy` + `ussyverse/chromascriptussy` | One sequence drives editorial, recording, and palette decisions; a changed shot updates the preparation packet. | Real editing/persistence UI, shared IDs/time mapping, Go wrapper and Rust CLI bridge. |
| **2** | **Service problems → measured improvement** | `ussyverse/andoniaussy` + `ussyverse/shewhartaussy` + `ussyverse/a3viaussy` | Connects individual problems to process evidence and a dated experiment, rather than collecting forgotten incident notes. | Event capture, time-window aggregation, case/metric links, CLI coordination. |
| **3** | **CI failure evidence packet** | `ussyverse/triageussy` + `ussyverse/petrichorussy` | Explains the error alongside the actual configuration difference from a comparable successful run. | Run identity, captured config, normalized paths, baseline selection, joined report. |
| **4** | **Family archive with inspectable readings** | `ussyverse/cartoucheussy` + `ussyverse/archivioussy` | Connects an uncertain transcription line to the historical claim someone is making from it. | Line-to-evidence references, duplicate/independence handling, safe export projection. |
| **5** | **“I keep confusing these” learning lab** | `ussyverse/cladwiseussy` + `ussyverse/criterioussy` | A wrong confident answer leads to a specific contrast exercise instead of another generic flashcard. | Stable prompt/concept IDs, actual-answer capture, timestamped attempts, shared UI/storage. |
| **6** | **Household handoff rehearsal** | `ussyverse/raciaussy` + `ussyverse/transactaussy` | Checks both “who owns this?” and “can that person find out how?” | Task/domain mapping, real data editor, absence simulation, export filtering. |
| **7** | **The last-three-volunteers desk** | `ussyverse/commonsaussy` + `ussyverse/hoistussy` | Turns a specific missing contribution into a bounded ask, then retires the ask when filled. | Durable pledge store, notice/pledge links, quantity-aware acknowledgments. |
| **8** | **Playable harmony-and-rhythm sketchbook** | `ussyverse/tonalussy` + `ussyverse/phyllotaxisussy` + `mojomast/shoedelussy` | Joins harmonic explanation and generated rhythm to an actual audition/edit surface. | Pitch voicing, pulse-to-cycle mapping, Strudel code generation. |
| **9** | **Which dependency cycle should we untangle?** | `ussyverse/hitchussy` + `ussyverse/churnmapussy` | Prioritizes structural cycles by observed change burden, rather than treating every cycle as equally urgent. | Scanner granularity, module/path normalization, reliable history and ranking. |
| **10** | **Finish the return, including the refund** | `ussyverse/retouraussy` + `ussyverse/prospectaussy` | Turns each return stage into an actionable cue and follows through after the parcel leaves the house. | Stage-to-intention mapping, Go wrapper, real reminders, date semantics. |

All ten use at least two org projects; nine are entirely org-based. Lower-ranked concepts remain attractive, but their data-entry or adapter costs are harder to justify before testing the top candidates.

## 3. Detailed top five

### #1 — Shot-to-sound production planner

**User and recurring pain.** A solo video maker, classroom film group, or small craft business making short tutorials, trip films, or product stories. They discover in the edit that there is no reaction shot, no usable room tone, or no consistent visual emphasis. The work gets planned in separate notes and then drifts whenever the sequence changes.

**Product promise.** “Arrange the story once; get the shots, sounds, and palette decisions you still need.”

**Flow:** manually described clips and planned action beats → montage checks and ordered timeline → Foley cue suggestions plus explicitly supplied palette beats → editable recording/shot checklist, CSV planning timeline, printable color strip, and project JSON.

#### Existing components to reuse

| Component evidence | What really exists |
|---|---|
| [Kuleshov models](https://github.com/ussyverse/kuleshovussy/blob/HEAD/src/models.ts), [engine](https://github.com/ussyverse/kuleshovussy/blob/HEAD/src/engine.ts) | `ClipCard` with ID, duration, shot role, mood, direction, people and objects; `analyzeSequence`, `missingChecklist`, `exportEditDecisionList`, `toCsv`. These operate on metadata, not video pixels. |
| [Foleya core](https://github.com/ussyverse/foleyaussy/blob/HEAD/foleya.go), especially `SceneRequest`, `PlanScene`, `SoundCue`, `ToCSV` | Real Go planning library with action classification, household-object substitutions, room tone, cue/checklist/take-log outputs. `SyncTime` is in integer seconds. |
| [Chromascript library](https://github.com/ussyverse/chromascriptussy/blob/HEAD/src/lib.rs), [CLI](https://github.com/ussyverse/chromascriptussy/blob/HEAD/src/main.rs), [manifest](https://github.com/ussyverse/chromascriptussy/blob/HEAD/Cargo.toml) | `Project`/`Beat`, `analyze_project`, typed warnings, and a `chromascript` CLI that writes Markdown, CSV, SVG and JSON. Supplied colors, emotional function and contrast/saturation/temperature ranks drive the checks and artifact generation. |
| [Kuleshov tests](https://github.com/ussyverse/kuleshovussy/blob/HEAD/test/engine.test.ts) | Tests exercise action-run warnings, establishing context, CSV output, and fixture sequences. They do not establish a working user-authored editing workflow. |

#### Missing integration

- A canonical `ProductionProject` with stable `sceneId`, `clipId`, order, duration, **local action offsets**, and optional palette data. Keep the raw component outputs beside the normalized result.
- Map clip metadata to Foley requests, but ask users for actual action descriptions and timings. An object list alone cannot tell the planner when the mug lands.
- Foleya **evenly spaces action beats** using `duration/(beats+1)` with a minimum step. Preserve those times as suggestions until the creator sets sync points. Namespace its per-scene `cue-001` IDs. Add scene-start offsets to local cue times.
- Add palette fields explicitly; Kuleshov does not extract colors, and its mood enum is not a palette. Chromascript's ordered beat indices need a sidecar mapping back to stable IDs.
- Wrap Foleya in a tiny JSON stdin/stdout executable; use Chromascript's existing local CLI. A thin local coordinator can serve the UI and run both. A browser-only build would need additional packaging work.

#### Maturity and feasibility

**Feasible core reuse, incomplete product UI.** [Kuleshov `main.ts`](https://github.com/ussyverse/kuleshovussy/blob/HEAD/src/main.ts) only offers demo selection, a role-sorting “better order” button, and CSV download. It does not implement the advertised manual sequence editor. [Storage helpers](https://github.com/ussyverse/kuleshovussy/blob/HEAD/src/storage.ts) exist but are not wired into that screen. Its template also interpolates text directly into HTML, so a real data editor needs proper escaping or DOM text rendering.

The CSV is a **planning list**, not an NLE interchange format with media paths and source in/out points. Foleya produces neither audio nor frame-accurate synchronization; its output timestamp uses the current clock. Chromascript scores stated intent with heuristic penalties, not audience response or universal color meaning. These limits are compatible with the proposed preparation tool.

**MVP/demo:** author a 60–90-second “making a small craft object” sequence, identify a missing detail/reaction shot, add two household Foley takes, move the reveal, and show updated cue offsets and color-strip order. Export a usable checklist and manually recreate the plan in a normal editor. Approximately **5–8 developer-days** for a coherent local prototype with all three components; see staged build below.

**Why combine?** These are different production jobs sharing the same temporal backbone. The payoff is synchronized preparation and revision. Three independent reports without shared IDs, order, and editable timings would not deliver the benefit.

### #2 — Service problems → measured improvement

**User and recurring pain.** A two-to-eight-person repair shop, alteration studio, or small fulfillment business. Staff repeatedly encounter the same missing information or packaging step. The owner alternates between reacting to individual bad days and writing checklists nobody checks for effectiveness.

**Product promise.** “Capture the problem once, investigate whether it is recurring, and remember to check whether the change helped.”

**Flow:** dated station events and a consistent metric series → Andonia event cards/recurrence groups → Shewharta baseline and signal report → A3 record with observations, proposed explanation, countermeasure, check date and decision → updated one-page standard work and follow-up series.

#### Existing components to reuse

| Component evidence | What really exists |
|---|---|
| [Andonia domain implementation](https://github.com/ussyverse/andoniaussy/blob/HEAD/internal/andonia/andonia.go) | `Board`, `AndonEvent`, `BuildReport`, `BuildCard`, JSON decode/export; timestamps, responder, containment, status and root-cause text. Recurrence keys combine abnormality and optional root cause. |
| [Shewharta engine](https://github.com/ussyverse/shewhartaussy/blob/HEAD/pkg/shewharta/engine.go), [CSV contract](https://github.com/ussyverse/shewhartaussy/blob/HEAD/README.md#csv-input-format) | `ComputeLimits`, `AnalyzeMetric`, `AnalyzePortfolio`; XmR limits, eight-point runs, six-point trends, process-change markers and intervention warnings. CSV requires `metric,date,value`. |
| [A3 models](https://github.com/ussyverse/a3viaussy/blob/HEAD/internal/a3/model.go), [store/workflow functions](https://github.com/ussyverse/a3viaussy/blob/HEAD/internal/a3/store.go), [validators](https://github.com/ussyverse/a3viaussy/blob/HEAD/internal/a3/validate.go) | Actual observation → why-chain → experiment → check → standardize sequence. Experiments require observations and a why-chain; standardization requires an adopted experiment. CLI and JSON persistence already exist. |

#### Missing integration

- Add persistent event entry/status updates; a sampled board is not an operational incident database.
- Define a measured event taxonomy and generate **complete calendar buckets**, including genuine zero-event periods. Missing data must not silently become zero. Keep business closures and workload changes visible.
- Store a join table: event IDs ↔ recurrence group ↔ metric ID ↔ A3 case/experiment ID. Andonia's English recurrence strings are not durable identifiers.
- Pin an owner-selected, comparable baseline. Supply count metrics first; rates require actual workload denominators. Retain process-change notes rather than attributing every change to the experiment.
- Use Andonia and A3's CLIs at first: their engines live under Go **`internal/`**, so another Go module cannot directly import them. Shewharta's `pkg/shewharta` is an ordinary importable package. A common language does not remove these boundaries.

#### Maturity and feasibility

The code supports a narrow local tool without a ticketing platform. But `BuildReport` counts **all supplied events**, without a weekly filter; the adapter must supply the right period. `BuildCard` can retain a stop-line flag for a resolved event based on its severity/wording, so preserve status and distinguish historical from active cards.

Shewharta defaults to eight baseline points and warns below twelve. This is not proof that those points are stable. A marked change within seven days takes precedence over other point classifications. Display baseline and annotations, not a single red/green business verdict. A3's root-cause quality checks are keyword rules; they validate process structure, not causal truth. File writes are single-file JSON without a multi-user transaction system.

**MVP/demo:** twenty historical daily counts of missing packing inserts, linked examples from a packing station, one preflight-check experiment and a later check decision. Show both an ordinary noisy series and a shifted series. A count can prompt investigation; it cannot prove the proposed cause. Approximately **4–7 developer-days** for capture/import and the joined workflow. Reuse manual CSV input before adding any `mojomast/ticket2` connector.

**Why combine?** Andonia explains individual events, Shewharta provides temporal context, and A3 preserves the follow-up obligation. None of the three alone closes that loop. This is more useful than attaching five independent analytics widgets to a service desk.

### #3 — CI failure evidence packet

**User and recurring pain.** Maintainers of Python/TypeScript projects and small CI fleets investigating “same code, different result.” They repeatedly hunt for the first useful error and then discover a changed config file, tool version, or runner setting in a different log.

**Product promise.** “Put the error and the relevant before/after environment evidence in one packet.”

**Flow:** captured build log + actual command exit status + commit/job identity + selected configuration/tool-version text → Triage extraction and pattern suggestions + Petrichor snapshots/diffs → joined report comparing a failing run with a comparable successful baseline, with explicit missing-evidence markers.

#### Existing components to reuse

| Component evidence | What really exists |
|---|---|
| [Triage extractor](https://github.com/ussyverse/triageussy/blob/HEAD/triage/extractor.py), [models](https://github.com/ussyverse/triageussy/blob/HEAD/triage/models.py) | `ErrorExtractor.extract_from_text`, deduplication, `IsolatedError` with log/source locations and context, and diagnostic models. Recognition is regex-based. |
| [Triage CLI](https://github.com/ussyverse/triageussy/blob/HEAD/triage/cli.py), [renderer](https://github.com/ussyverse/triageussy/blob/HEAD/triage/renderer.py) | Real extractor → pattern matcher/enricher → diagnostic renderer pipeline; saved-log analysis, project context and JSON output. |
| [Petrichor soil memory](https://github.com/ussyverse/petrichorussy/blob/HEAD/src/petrichor/soil.py) | `SoilMemory.snapshot`, `snapshot_text`, `get_drift_history`, hashes, diffs, actor/context and SQLite-backed layers. Text snapshots can represent captured version output as well as files. |
| [Petrichor groundwater](https://github.com/ussyverse/petrichorussy/blob/HEAD/src/petrichor/groundwater.py) | `analyze_with_effective(path, effective_text)` accepts real externally captured runtime text. Plain `analyze` does not obtain it. |

#### Missing integration

- A build wrapper/CI step that records `runId`, commit, branch, job matrix, tool versions, command exit code, timestamps and raw artifacts. Always retain the original build result independently of Triage's exit status.
- Canonical logical paths for identical files on different runners; Petrichor otherwise keys by absolute path. Persist its history outside ephemeral workspaces.
- Explicit baseline selection: same job/runtime family and a successful run, not simply “previous record.” Prefer direct comparison of stored contents over relying exclusively on a drift boolean.
- Preserve raw extracted locations alongside rendered diagnoses, and report “configuration changed near this failure,” not “configuration caused this failure.”
- Capture selected non-secret configuration fields before writing snapshots: the existing store retains **full text**, not merely hashes. This is a concrete collection requirement, not a capability already supplied by Petrichor.

#### Maturity and feasibility

Both are small Python packages with real entry points. There are important contract traps:

- Triage exits **1 when it finds errors**, and its “no errors” path prints prose even with `--json`. A failed command with an unrecognized error must remain failed/unknown. Importing the extractor and renderer may be cleaner than wrapping the CLI verbatim.
- Patterns such as `TypeError` overlap languages. First-match classification and fixed confidence bonuses are hints, not calibrated cause probabilities.
- Petrichor's default effective state is assigned from declared state in `groundwater.py:99–102`. A runtime collector is required before claiming a three-way runtime comparison.
- `snapshot_text` can mark any change from the previous layer as drift even when text returns to the desired value; `detect_drift` can fall back to stored contents when a file is missing. Record presence and compare explicit baseline/current values.
- “SHA-256 with zero false positives” means neither semantic configuration equivalence nor zero false incident hypotheses. Formatting-only changes can be real byte/text differences with no behavioral consequence.

**MVP/demo:** two run packets for one tiny project, with an intentionally changed non-secret module/search-path configuration and a corresponding import failure. Compare against a second failure whose config did not change. Output error locations, exact config diff, baseline identity and next checks. Approximately **3–5 developer-days** for a local packet generator; live CI collection comes after the saved-artifact workflow.

**Why combine?** Triage gives the symptom; Petrichor supplies longitudinal context outside the source diff. The valuable integration is the **run-to-evidence join**, not a new overall health score. This can be consumed by a human or one existing coding agent without introducing another orchestrator.

### #4 — Family archive with inspectable readings

**User and recurring pain.** The family historian digitizing letters, recipe cards, captions and notebooks over many weekends. A guessed name in a transcription becomes an unquestioned family story; later edits lose the original reading or the evidence behind it.

**Product promise.** “Every family-history claim can show exactly which source line supports it—and what remains uncertain.”

**Flow:** scan + manual transcription packet → Cartouche line/apparatus validation → Archivio artifact, source note, claim and evidence links → private finding aid with diplomatic/normalized text, claim-to-line references, unresolved questions and attachment fixity status.

#### Existing components to reuse

| Component evidence | What really exists |
|---|---|
| [Cartouche core](https://github.com/ussyverse/cartoucheussy/blob/HEAD/src/cartouche.ts) | `CartouchePacket`, documents/image URIs, line IDs, diplomatic versus normalized text, apparatus and letterform references; `validatePacket`, `compilePacket`, `compilePackets`, structured findings and Markdown. |
| [Archivio storage](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/storage.py) | `ArchiveStore.accession_artifact`, `create_claim`, `add_source_note`, `link_evidence`, `add_counterclaim`, local JSON persistence and `fixity_report`. |
| [Archivio confidence logic](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/logic.py), [exports](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/export.py) | Claim/evidence distinction, contested labels and export functions. Inspect these limits carefully; privacy and source independence need integration work. |
| [Cartouche tests](https://github.com/ussyverse/cartoucheussy/blob/HEAD/tests/cartouche.test.ts), [Archivio tests](https://github.com/ussyverse/archivioussy/blob/HEAD/tests/test_app.py) | Concrete intended behavior for uncertain readings, unresolved references, fixity changes, conflicting claims and private-claim filtering. Artifact-level public-export coverage is incomplete. |

#### Missing integration

- A sidecar joining `packetId/documentId/lineId` to an Archivio artifact and claim. Existing evidence links do not supply this complete line-level bridge.
- A wrapper around Cartouche's pure TypeScript API to emit structured results; the current CLI's primary report is Markdown.
- An explicit human action to turn a reading into a claim. A validated packet establishes documented editorial reasoning, not historical truth.
- Preserve the scan, diplomatic text and normalized text separately. `deriveNormalized` deliberately removes some uncertainty syntax and chooses a readable alternative; never promote that output alone into unqualified evidence.
- Treat scan, transcription and re-export as representations of **one underlying source**, not independent corroboration. Archivio counts distinct artifact/source identifiers when deriving independence.
- Produce a new export projection with artifact-level filtering and portable attachment references. Link and copy the chosen files deliberately; accession currently records an external filesystem path and hash rather than creating a managed copy.

#### Maturity and feasibility

**Strong archival concepts, an important export blocker.** `export_json` emits every artifact's full dictionary, including local paths and metadata, regardless of the filtering applied to claims. Markdown filters private artifacts but not all other sensitivity classes, and the fixity list can expose titles independently. Claim redaction also relies on listed names and string matching. These exports must not be described as automatically safe public packets.

`ArchiveStore.save` overwrites a JSON file and `add` appends records: importer idempotency, duplicate-ID checks and atomic update/backup behavior are new work. Cartouche's same-hand confidence is a fixed formula over observations/features; it is not handwriting authentication or OCR.

**MVP/demo:** two scans, a disputed place name, one recipe line containing an uncertain word, and two conflicting captions. Click from a claim to the exact diplomatic line and evidence note; alter a copied attachment to demonstrate changed fixity. Keep the initial archive local, then implement and test a filtered share packet. Approximately **4–7 developer-days**, including the necessary export work.

**Why combine?** Cartouche asks “what does this mark say, and why?” Archivio asks “what claim are we making from it, on what basis?” The join prevents editorial guesses from silently becoming family facts. Adding a general RAG stack before this relationship exists would make the evidence problem harder to see.

### #5 — “I keep confusing these” learning lab

**User and recurring pain.** A student, vocational tutor, or junior developer learning neighboring concepts: invoice/receipt/purchase order, process/thread/coroutine, or related grammar forms. They recognize definitions but confuse the concepts when choosing or explaining an answer.

**Product promise.** “Find the distinction behind your confident mistake, practice it, and check it again without the hints.”

**Flow:** a learner/teacher-authored concept-and-trait family → Cladwise contrast pairs and diagnostic questions → Criterio prediction/confidence and actual answer outcome → focused repair prompt for the mistaken pair → later uncued attempt and before/after report.

#### Existing components to reuse

| Component evidence | What really exists |
|---|---|
| [Cladwise core](https://github.com/ussyverse/cladwiseussy/blob/HEAD/src/cladwise.ts) | `ConceptFamily`, `pairwiseDistances`, `rankDiagnosticTraits`, contrast trees and dichotomous-key generation; exported types include pair recommendations and repair prompts. No VS Code dependency in this core. |
| [Criterio core](https://github.com/ussyverse/criterioussy/blob/HEAD/src/criterioCore.ts) | `StudyPrompt`, `AttemptRecord`, `classifyOutcome`, confidence bins, prompt checks, `buildReport`, Markdown rendering. Its “confusion matrix” compares predicted knowledge with correctness. |
| [Criterio extension](https://github.com/ussyverse/criterioussy/blob/HEAD/src/extension.ts), [manifest](https://github.com/ussyverse/criterioussy/blob/HEAD/package.json) | An actual command-driven prediction/confidence/self-grade loop, local Memento records, and dashboard. The manifest/tests use Node's test runner, contrary to the README's Mocha description. |
| [Cladwise manifest](https://github.com/ussyverse/cladwiseussy/blob/HEAD/package.json), [Criterio tests](https://github.com/ussyverse/criterioussy/blob/HEAD/src/test/suite/criterioCore.test.ts) | VS Code extension entry points and testable pure-core behavior; no shared cross-extension database/API is declared. |

#### Missing integration

- Use stable IDs scoped by family and revision. Criterio's import functions reset IDs to `p1`, `p2`, etc.; importing a new set can leave old records associated with reused IDs.
- Add **actual concept selected, expected concept, timestamp, prompt revision and rubric**. The extension currently collects self-grades, not the wrong answer itself. Criterio's matrix cannot identify invoice-versus-receipt confusion without this new data.
- Generate one prompt per useful contrast and preserve links to the relevant traits. A false alarm routes to that pair's repair prompt, rather than rewriting every note in a topic.
- Keep partial answers and skipped attempts distinct in the product. The current core treats `maybe` as a positive prediction and `skipped` as unsuccessful; that policy is not automatically suitable for a delayed assessment.
- Build a small shared local web UI or a single host extension around the pure cores. The two existing extensions' Memento stores do not communicate automatically.

#### Maturity and feasibility

These are genuinely reusable TypeScript engines. However, similarity in a manually authored trait matrix is only a candidate confusion, not observed learner confusion. Unknown trait values are skipped, and the contrast tree's grouping can omit unknown-valued concepts from a split; explicitly show unresolved branches. Four attempts trigger some Criterio labels, which is far too little to market a stable learner diagnosis. Keep counts and raw outcomes visible.

I inspected `ussyverse/ebbinghausussy` as a possible third component and **left it out of the MVP**. Its [core](https://github.com/ussyverse/ebbinghausussy/blob/HEAD/src/ebbinghaus/core.py) implements power-law scheduling, but `update_decay_rate` moves toward a score-derived target with fixed `alpha = 0.15`; it is not an empirical fit of elapsed-time/recall observations as the index suggests. A user-selected delayed revisit is sufficient for the first product.

**MVP/demo:** author four neighboring concepts and six discriminating traits. Record a confident wrong choice, expose a targeted contrast, then use a differently worded uncued question at a later session. Show the raw attempted answers and confidence/outcome change. Approximately **3–5 developer-days** for the two-core local prototype; learning effectiveness requires real repeated use, not a higher heuristic score.

**Why combine?** Cladwise supplies what to contrast; Criterio supplies evidence that the learner's confidence and retrieval disagree. One repairs the content distinction, the other checks the learner's judgment. This is much tighter than a six-engine “learning OS.”

## 4. Other strong options, with implementation boundaries

### #6 — Household handoff rehearsal

**Repositories:** `ussyverse/raciaussy` + `ussyverse/transactaussy`.

**User/task:** roommates or partners preparing for one member's travel or a move. Garbage collection, router administration, plant routines and ordinary household paperwork still need both an owner and usable instructions.

**Flow:** agreed task assignments + knowledge/source pointers + absence dates → Racia ownership/access findings and Transacta knowledge/backup findings → rehearsal checklist and temporary handoff packet. The key new finding is “the assigned doer is available, but the only knower is away.”

**Reuse:** [`raciaussy/src/engine.ts`](https://github.com/ussyverse/raciaussy/blob/HEAD/src/engine.ts) exposes `analyzePlan` and `computeLoads`. [`transactaussy/src/models.ts`](https://github.com/ussyverse/transactaussy/blob/HEAD/src/models.ts) defines separate primary/backup knowers, freshness and source pointers; [`engine.ts`](https://github.com/ussyverse/transactaussy/blob/HEAD/src/engine.ts) implements `analyzeHousehold` and `buildTransitionPack`.

**Adapter/MVP:** join task `domain` to knowledge `domainId`, maintain common member IDs, and add explicit availability plus a temporary assignment layer. Generate five handoff cards and have the receiving roommate actually find each source and explain the task. Approximately **3–5 days**.

**Caveats:** Transacta's [extension](https://github.com/ussyverse/transactaussy/blob/HEAD/src/extension.ts) only loads sample data and opens a board; an ordinary user-data editor/import is new work. Its scenario option is text matching, not an absence-aware graph simulation. Its `redactedFields` metadata is not sufficient redaction: `buildHandoffCard` still places `sourceArtifact` in text even when the domain is sealed. Use a deliberately filtered output view. Racia's weighted load is a heuristic, not an objective division of labor.

**Added value:** ownership and knowledge are different failure modes. Joining them reveals a gap neither independent report can establish.

### #7 — The last-three-volunteers desk

**Repositories:** `ussyverse/commonsaussy` + `ussyverse/hoistussy`.

**User/task:** a neighborhood group repeatedly organizing book swaps, event setup or community-room activities. “Can anyone help?” produces ambiguous replies, duplicated requests and stale pleas after the gap is filled.

**Flow:** required contributions and explicit pledges → per-role threshold deficit → a Hoist request with scope/expiry → recorded acknowledgment and separately confirmed quantity → recalculated deficit → filled/closed notice.

**Reuse:** [Commonsa models/engine](https://github.com/ussyverse/commonsaussy/blob/HEAD/src/commonsa/models.py) implement active/waiting conditional pledges, scarcest-role viability and bottlenecks. [Hoist engine](https://github.com/ussyverse/hoistussy/blob/HEAD/src/hoist/engine.py) implements composition and acknowledgment summaries; its [documented store/render surfaces](https://github.com/ussyverse/hoistussy/blob/HEAD/README.md#architecture) provide SQLite notice lifecycle and Markdown/HTML output.

**Adapter/MVP:** add project and contribution IDs, a persistent pledge ledger, expiry handling and a quantity-confirmation form. “Seen” must not become a pledge; “can help” still needs a contribution type and quantity. Demo one event requiring three setup helpers and two tables: show an ask for the actual remaining type, then retire it when filled. First distribution can be copy/paste into existing chat. Approximately **3–5 days**.

**Caveats:** Commonsa's [API route](https://github.com/ussyverse/commonsaussy/blob/HEAD/src/commonsa/main.py) currently uses `CommonsaEngine(sample_log())` even for submitted projects, and the routes do not implement durable project storage. Use the engine with real or explicitly empty history. Its fairness calculation sums quantities across types, which makes “one table” and “one volunteer hour” incomparable; omit that combined fairness score. Hoist acknowledgment metrics also distinguish response presence from some response meanings, so aggregate ack rate must not substitute for confirmed resources.

**Added value:** a resource bottleneck becomes a precise, finite communication request. This is ordinary event coordination, not emergency alerting or a volunteer-worthiness score.

### #8 — Playable harmony-and-rhythm sketchbook

**Repositories:** `ussyverse/tonalussy` + `ussyverse/phyllotaxisussy` + `mojomast/shoedelussy`.

**User/task:** a music learner or live coder who can describe a chord progression but spends too long turning it into a playable rhythmic sketch.

**Flow:** key + progression + rhythm request → Tonal analysis/transposition + Phyllotaxis binary pulse pattern → generated, editable Strudel template → playback and a theory annotation alongside the code.

**Reuse:** [Tonal HTTP handlers](https://github.com/ussyverse/tonalussy/blob/HEAD/src/main.rs) call real analysis/transposition/exercise functions in the [Rust library](https://github.com/ussyverse/tonalussy/blob/HEAD/src/lib.rs). [Phyllotaxis `adaptToDomain('music', ...)`](https://github.com/ussyverse/phyllotaxisussy/blob/HEAD/src/index.ts) yields `artifact.rhythm: number[]`. [Shoedel's `StrudelEditor.tsx`](https://github.com/mojomast/shoedelussy/blob/HEAD/ui/src/components/StrudelEditor.tsx) exposes code-setting/evaluation/play callbacks and instantiates Strudel's audio runtime.

**Adapter/MVP:** convert supported triads to explicitly voiced notes, define octave and chord length, map pulses to musical cycles, and emit a known-small Strudel template. Begin with C–G–Am–F, audition a generated rhythm, transpose to E-flat and hear the result while retaining Roman numeral explanation. Manual code paste is a credible first integration boundary. Approximately **5–8 days** for a joined UI and audition workflow.

**Caveats:** Tonal's frontend is theory/JSON-oriented and does not itself provide ear-training audio. The two org tools do not generate Strudel or MIDI. Phyllotaxis rhythm is an angle-quantization mapping and can become dense; “golden angle” does not mean musically superior. Tonal's mode model is major/natural minor; constrain the initial chord vocabulary. Shoedel has a larger browser/audio dependency surface, a global audio-connect interception and optional remote assets/backend features. Its demo lighting rig is explicitly fake. Browser audition and asset availability need runtime verification.

**Added value:** theory becomes something the learner can hear and revise. The rhythm generator earns its place through concrete pattern data, not botanical musical claims.

### #9 — Which dependency cycle should we untangle?

**Repositories:** `ussyverse/hitchussy` + `ussyverse/churnmapussy`.

**User/task:** a Python maintainer planning one refactoring session. A cycle detector finds several cycles; history suggests only some repeatedly force coordinated edits.

**Flow:** normalized import graph + actual commit/file changes → Hitch strongly connected components and candidate feedback edges + ChurnMap co-change evidence → ranked investigation list showing cycle members, co-edit counts, representative commits and proposed interface boundaries.

**Reuse:** [Hitch `DependencyGraph`](https://github.com/ussyverse/hitchussy/blob/HEAD/src/hitch/graph.py) supplies graph construction, SCCs and a greedy feedback-edge approximation. [ChurnMap parser](https://github.com/ussyverse/churnmapussy/blob/HEAD/churnmap/git_parser.py) reads real `git log --numstat`; [co-change implementation](https://github.com/ussyverse/churnmapussy/blob/HEAD/churnmap/cochange.py) aggregates territories and builds maps.

**Adapter/MVP:** first use a small top-level-module project with known cycles, map modules to repository-relative files, and derive file-pair counts from the parser's `Commit.files` rather than the default directory aggregation. Show raw counts beside a simple explicit priority rule. Demo a frequently edited cycle versus a dormant one, then compare after a manually reviewed refactor. Approximately **3–5 days** for the restricted case; general nested-package support is a separate scope increase.

**Caveats:** [Hitch's scanner](https://github.com/ussyverse/hitchussy/blob/HEAD/src/hitch/scanner.py) collapses import targets and edge sources to their first dotted component, which can erase useful intra-package structure. ChurnMap's depth logic groups **directories**, not individual file pairs as the index's depth description suggests; root files collapse into `_root`. A trustworthy finer-grained product needs an adapter/resolver feeding Hitch's graph and revised aggregation, not just a UI over existing CLI output. The greedy edge set is not guaranteed minimum; knot names are heuristic. Shallow clones, squash commits and renames limit co-change inference—the parser uses `--no-renames`. Show available history coverage, never infer architectural calm from missing history.

**Added value:** structural coupling plus actual maintenance burden helps choose work. This is narrower and more defensible than predicting “time to codebase failure.” Its scanner work explains the lower rank.

### #10 — Finish the return, including the refund

**Repositories:** `ussyverse/retouraussy` + `ussyverse/prospectaussy`.

**User/task:** someone managing several ordinary online returns. They remember “return parcel” but miss the label, handoff receipt, first scan or refund follow-up.

**Flow:** manually recorded return facts → Retoura next incomplete stage → a Prospecta intention tied to a real routine/context → cue card and optional reminder → updated return stage → next cue, ending with refund reconciliation.

**Reuse:** [Retoura `domain.ts`](https://github.com/ussyverse/retouraussy/blob/HEAD/src/domain.ts) supplies `ReturnItem`, `classifyReturnStage`, packaging checks, evidence completeness and refund analysis. [Prospecta](https://github.com/ussyverse/prospectaussy/blob/HEAD/prospecta.go) supplies JSON-tagged `Intention`, `Cue`, `CuePlan`, `ScoreCue`, `DesignPlan` and miss taxonomy.

**Adapter/MVP:** bind a stable return ID and stage to one active intention; regenerate/cancel it on stage changes. Use a small Go JSON wrapper and TypeScript host. Demo three returns: missing accessory, ready for drop-off, and refund pending. Print a preparation card and a dated follow-up list. Approximately **3–5 days**.

**Caveats:** Prospecta suggests aids but sends no notifications; calendar/OS reminder delivery is new work. Cue scores use human-rated inputs and fixed weights, not measured forgetting probabilities. Use a visible note or designated parcel shelf rather than the README's path-blocking example. Retoura evidence booleans do not authenticate receipts; no retailer/carrier integration exists. Its `hasUsableLabel` accepts authorization or an RMA alone, so separately verify actual label/QR readiness before producing a drop-off cue. Its date calculation assumes UTC day boundaries and can count today's deadline as a remaining day; deadline/timezone behavior needs correction in the adapter. Keep ordinary return documentation separate from shipping-eligibility decisions.

**Added value:** the next action is surfaced at a usable moment, and handoff does not falsely end the workflow. I checked `ussyverse/forageussy` as a routing companion but omitted it: its [route contract](https://github.com/ussyverse/forageussy/blob/HEAD/README.md) and [engine](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/engine.go) use Euclidean travel proxies and can drop stores under a maximum-store constraint, without the deadline/mandatory-stop semantics this workflow needs.

## 5. Tempting combinations rejected

### A. The universal code-health oracle

**Temptation:** `mojomast/terrariumussy` + `ussyverse/churnmapussy` + `ussyverse/levainussy` + `ussyverse/fatigueussy`, extending the earlier observatory idea.

**Why reject this product claim:** independent scales do not become a validated health measurement when averaged. In inspected source, Terrarium's [ChurnMap adapter](https://github.com/mojomast/terrariumussy/blob/HEAD/terrarium/adapters/churnmap.py) reads a configured JSON file; it does not execute or automatically wire the other project. Its expected `territory_id/modules/files` structure is not ChurnMap's native `TerritoryMap` construction. [Base availability](https://github.com/mojomast/terrariumussy/blob/HEAD/terrarium/adapters/base.py) can also be satisfied by stub mode or a configured path.

Levain's [rise meter](https://github.com/ussyverse/levainussy/blob/HEAD/levain/instruments/rise.py) assigns 10/100 to zero failures and rewards a 1–8% failure band. Passing tests are not thereby dead, and failures are not thereby evidence of useful discrimination. Its [JUnit parser](https://github.com/ussyverse/levainussy/blob/HEAD/levain/parser.py) assigns import time to results, rather than reconstructing run history. Reuse concrete extractors if needed; do not build merge gates or engineering predictions from the aggregate score. #3 and #9 retain specific evidence joins instead.

### B. The six-engine learning OS

**Temptation:** `ussyverse/synapseussy` + `ussyverse/latticeussy` + `ussyverse/ebbinghausussy` + `ussyverse/criterioussy`, with more schedulers added later.

**Why reject:** multiple invented mastery/plasticity models create competing states without a clear new learner action. Ebbinghaus's inspected fixed-alpha update does not support the earlier claim of empirically fitted personal forgetting curves. #5 uses two distinct capabilities and stores what actually happened. Scheduling can be added after real timestamped attempts exist.

### C. The household emergency/medical super-advisor

**Temptation:** `ussyverse/triagiaussy` + `ussyverse/wetbulbaussy` + `ussyverse/carboxaussy` + `ussyverse/sterilaussy`.

**Why reject at screening:** the earlier suggestion joins several independent risk models and implies a usable master response system. Index descriptions and “conservative” wording are not clinical, engineering or field validation, and a common printable-card format does not resolve conflicting escalation logic or missing observations. I did not source-audit these engines and make no claim to have established their adequacy. A household binder may be useful, but an integrated recommendation authority is not justified by this review. #6 focuses on ordinary knowledge/ownership handoffs.

### D. More agents and routers as the product

**Temptation:** `mojomast/swarmussy` + `ussyverse/parliamentussy` + `mojomast/agenttrafficcontrol` + `mojomast/kportussy`, or chaining three LLM routers beneath it.

**Why reject at screening:** multiple coordination layers add protocols and failure boundaries without identifying a new end-user deliverable. The catalog's own `agenttrafficcontrol` entry describes a **simulation**, while the previous combination presents it as a real swarm monitor. That mismatch requires an actual event connector and runtime validation. This was not a fresh source audit of those four tools; it is a rejection of the unsupported integration claim. Concrete existing pairings such as `ussycode`/`ussyrouter` can remain infrastructure without becoming the centerpiece of every idea.

### E. Production API-drift prediction built on a spec

**Temptation:** `ussyverse/driftnetussy` + `ussyverse/fatigueussy` + `ussyverse/reverseoracleussy`.

**Why reject:** [DriftNet's checkout](https://github.com/ussyverse/driftnetussy/tree/HEAD/) contains `PROMPT.md`, `SPEC.md`, metadata and Git files, but no implementation. A `.built` marker is not code evidence. The proposed product would first require implementing a major missing component, then validating the predictive relationship between semantic drift and failures. That is a research/build project, not a ready recombination MVP.

## 6. Recommended first build: staged audiovisual planner

**Working name:** “Shot / Sound / Color.” **Scope:** one local creator, one short project, editable planning metadata and exportable preparation artifacts.

The first build uses the same three exact repositories as #1. It starts with **`ussyverse/kuleshovussy` + `ussyverse/foleyaussy`** and adds **`ussyverse/chromascriptussy`** once editing and timing work. This is a concrete way to give three underused org engines a coherent product surface.

### Stage 0 — Verify the component contracts

**Approximately half a day to one day.** In a separate integration workspace, pin the source revisions and build the required packages. Use existing tests as the initial check, then exercise user-authored—not just bundled—data.

Confirm that Kuleshov accepts an authored clip sequence, the Go wrapper can serialize Foleya's cue sheet, and the Rust CLI emits its documented artifacts. Record tool/runtime requirements from the manifests. Component build failures may change the estimate; none of these commands was run during this analysis.

**Exit criterion:** three saved, inspectable outputs tied to a recorded input and source revision. No marketing claims based on the successful execution of toy data.

### Stage 1 — Deliver the two-project vertical slice

**Approximately two to three days.** Build a small local UI with:

- Add/edit clip cards and keyboard-accessible move-up/move-down controls.
- Project JSON import/export and wired persistence.
- Separate action description and **editable local sync offset** for each recording cue.
- Kuleshov's missing-shot/warning panel.
- Foleya's recording checklist, substitutions and take-log template.
- One joined printable “what to shoot/record next” packet.

Proposed integration data, not an existing schema:

```text
ProductionProject
  schemaVersion, projectId, title, revision
  scenes[]
    sceneId, title, order
    clips[]: clipId, title, durationSeconds, shotRole, mood, direction
    actions[]: actionId, clipId, description, localOffsetSeconds
    palette?: supplied colors and explicit story intent
  recordings[]: actionId/cueId, fileRef, takeNumber, creatorNotes
```

Retain fractional offsets in the product model; Foleya's integer-second defaults are starting suggestions. Do not round-trip editable data through Kuleshov's lossy CSV export.

**Demo:** a creator enters six to ten cards from a real short project, discovers one useful missing shot or sound, and exports a packet they would take to a recording session.

**Exit criterion:** one creator can complete this without editing source code or using the bundled fixtures as their project.

### Stage 2 — Make revisions trustworthy

**Approximately one to two days.** Add stable identity and explicit timing translation across scenes, clips, actions and cues. Track manual overrides separately from generated suggestions. Wire save/reload and imported-project validation.

Necessary integration checks for the future implementation:

1. Reordering a clip moves its derived absolute cue times but keeps attached take references.
2. Renaming duplicate-titled clips does not merge their IDs.
3. Inserting an earlier scene shifts later offsets without changing local offsets.
4. Shortening a clip exposes out-of-range cues rather than silently moving them.
5. Regeneration preserves creator-edited sync points and handles Foleya's wall-clock metadata separately.
6. Export/reimport retains project identity, order and edits; names containing markup render as text.

These are acceptance criteria for the proposed build, **not tests already executed here**.

### Stage 3 — Add color as a genuinely connected lane

**Approximately one to two days.** Collect two or more palette beats from the creator, convert them to Chromascript input, and render its SVG strip beside the same ordered scenes. Resolve warning beat indices back to stable scene IDs and make narrative intent editable.

**Demo:** reserve a distinct accent for the reveal; move the reveal and show the strip and warnings following the new order. A palette change is a creative planning choice, not an automatically computed correction to video footage.

**Exit criterion:** the color output changes with the same project revision as shot and cue exports. A disconnected third report is not sufficient.

### Stage 4 — Check whether people actually reuse it

Have two or three creators use the planner on a second project. Ask whether the packet prevented a missing pickup, reduced duplicate planning, or made a revision easier. Record concrete examples rather than treating “story coherence” or “arc score” as outcome measures.

The success condition is simple: **someone opens this again because it helps finish a video.** If entering metadata costs more than the saved preparation, reduce the fields and center the missing-shot/recording list before adding any media ingestion or AI layer.

## 7. Final judgment

The most reusable value in the org is often a small typed model, a deterministic transformation, and a useful report—not the entire application advertised around it. The productive combinations connect **sequence to preparation, events to follow-up, symptoms to captured state, readings to claims, and mistakes to practice**.

The common missing work is equally concrete: real data entry, stable IDs, trustworthy time handling, source references, and exports that preserve meaning. Building those bridges is a more credible next step than assembling a larger tower of orchestrators or a composite scientific-sounding score.
