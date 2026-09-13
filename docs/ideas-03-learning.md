# Learning, Studying, and Teaching Ideas: Pass 03

**Date:** 2026-09-13
**Focus:** education, studying, tutoring, skill practice, knowledge management, and teacher tools
**Status:** new proposals; none is an existing end-to-end integration

## Scope and evidence

I read `README.md`, `AGENTS.md`, `docs/SOURCE_CHECKED_COMBINATIONS.md`, and
`docs/REPOSITORY_INDEX.md` before selecting candidates. I inspected source and
manifests in the checked-out repositories under `/home/ubuntu/ussy/repos`.
The revisions below came from `git -C <repo> rev-parse --short HEAD`:

| Repository | Revision |
|---|---|
| `ussyverse/bloomussy` | `ece5f35` |
| `ussyverse/exemplaussy` | `9d38399` |
| `ussyverse/scaffoldussy` | `71691e0` |
| `ussyverse/chunkussy` | `eecbced` |
| `ussyverse/morphemaussy` | `09f8f56` |
| `ussyverse/dualiaussy` | `706bd5f` |
| `ussyverse/chainletussy` | `eaa6a01` |
| `ussyverse/entrainussy` | `117449c` |
| `ussyverse/driftlineussy` | `fe62970` |
| `ussyverse/clavisussy` | `0675ec9` |
| `ussyverse/tellussy` | `82a4f73` |
| `ussyverse/citewiseussy` | `ea270ca` |
| `mojomast/coderc` | `7768684` |

No component was installed, built, runtime-tested, or modified during this
pass. Existing tests and README examples are evidence of intended contracts,
not evidence that the current checkouts pass or that an integration works.
"Exists" below means implemented in inspected source. "Proposed" means product
or adapter work still required. "Unverified" means a claim not established by
the inspected source or runtime.

## New product ideas

### 1. Notes to Recall Atlas

**Target user and pain:** A student with dense Markdown lecture notes can read
and highlight them, but needs a compact structure and concrete prompts for a
short review session. A tutor needs an editable packet rather than another
opaque summary.

**Exact repositories:** `ussyverse/chunkussy` + `ussyverse/dualiaussy` +
`ussyverse/bloomussy`.

**Existing evidence (Exists):** Chunk has `ChunkDocument`, sentence
classification, bounded 3-5 item chunking, `chunk_generate_prompt`, an
interleaved schedule, and confidence/correctness calibration in
[`chunk.c`](https://github.com/ussyverse/chunkussy/blob/HEAD/chunk.c) and
[`chunk.h`](https://github.com/ussyverse/chunkussy/blob/HEAD/chunk.h). Dualia
parses Markdown into `StudyMaterial` in
[`parser.ts`](https://github.com/ussyverse/dualiaussy/blob/HEAD/src/domain/parser.ts)
and emits visual/verbal actions, accessibility notes, and reconstructive
prompts from `analyzeMaterial` in
[`analyzer.ts`](https://github.com/ussyverse/dualiaussy/blob/HEAD/src/domain/analyzer.ts).
Bloom defines six levels and stores level-specific `Evidence` in
[`models.py`](https://github.com/ussyverse/bloomussy/blob/HEAD/src/bloom/models.py),
while `BloomEngine.generate_task` creates level-oriented tasks in
[`engine.py`](https://github.com/ussyverse/bloomussy/blob/HEAD/src/bloom/engine.py).

**Proposed handoff/data flow:** Markdown notes -> Dualia parses structure and
accessibility concerns -> Chunk produces chunk headings and retrieval prompts
-> a coordinator assigns each prompt a Bloom task level -> learner records the
raw answer, confidence, and review date -> Markdown/JSON recall packet. The
shared entity is a note revision plus stable chunk ID; source spans and raw
outputs must be retained because Chunk currently exposes array positions rather
than durable note IDs.

**MVP:** Import one 1,500-word biology chapter, let a teacher edit six chunks,
export a one-page visual/verbal recall sheet with four reconstruction prompts,
and record one later uncued attempt. Do not generate answers automatically.

**Why combine:** Chunk makes a long note navigable, Dualia repairs how the
material is represented, and Bloom supplies a progression of task verbs. The
learner receives one review artifact instead of three disconnected reports.

**Missing work and acceptance:** Add source-span/chunk IDs, a JSON bridge, a
review UI, and answer/confidence timestamps. A demo passes if re-importing the
same note preserves edited chunk IDs and the packet contains both raw note
text and prompts. This is not a claim that the packet improves retention.

**Risks and maturity:** Chunk truncates sentences at fixed limits and uses
keyword overlap; Dualia's Markdown parser is regex-based; Bloom's threshold is
rule-based and partly self-reported. These are useful authoring hints, not
validated diagnoses. Reject automatic grading or a single "learning score."

### 2. Tutor Fading Board

**Target user and pain:** A tutor plans worked examples and completion problems
but later cannot tell whether a learner needed that support, outgrew it, or
failed because the task was mismatched.

**Exact repositories:** `ussyverse/exemplaussy` + `ussyverse/scaffoldussy` +
`ussyverse/bloomussy`.

**Existing evidence (Exists):** Exempla's typed plan includes learner stage,
guidance rung, revealed/masked steps, warnings, teacher card, and next-session
recommendation in [`types.ts`](https://github.com/ussyverse/exemplaussy/blob/HEAD/src/types.ts)
and [`session.ts`](https://github.com/ussyverse/exemplaussy/blob/HEAD/src/session.ts).
Its deterministic fading and warning rules are in
[`fading.ts`](https://github.com/ussyverse/exemplaussy/blob/HEAD/src/fading.ts).
Scaffold loads skills, tasks, and sessions from JSON/CSV in
[`models/__init__.py`](https://github.com/ussyverse/scaffoldussy/blob/HEAD/src/scaffold/models/__init__.py)
and [`io.py`](https://github.com/ussyverse/scaffoldussy/blob/HEAD/src/scaffold/io.py),
then calculates fit, trend, and support advice in
[`analysis.py`](https://github.com/ussyverse/scaffoldussy/blob/HEAD/src/scaffold/analysis.py).
Bloom supplies topic evidence and next-level task text in
[`engine.py`](https://github.com/ussyverse/bloomussy/blob/HEAD/src/bloom/engine.py).

**Proposed handoff/data flow:** Tutor authors a step-labeled deck and recent
metrics -> Exempla creates the planned fading rung -> the adapter maps each
item to a Scaffold task with an explicit support level -> the tutor records
success, support used, confidence, and notes -> Scaffold reports task fit and
trend -> Bloom labels the intended cognitive demand and stores teacher-reviewed
evidence. Exempla should own visibility decisions; Scaffold should own session
trend; Bloom should remain a task-language/reporting layer rather than a fourth
mastery state.

**MVP:** One algebra deck with six steps, three sessions, and a teacher card
showing planned versus observed support. Export the raw attempts beside the
derived report.

**Why combine:** Exempla answers "how much should I show now?", Scaffold answers
"what happened across attempts?", and Bloom makes the intended task demand
explicit. The handoff closes the planning-to-observation loop without claiming
that any rung is universally optimal.

**Missing work and acceptance:** Define mappings between the two support
vocabularies, preserve prompt revisions, and add stable deck/item IDs. A demo
passes if an attempt with a hint is not silently recorded as independent and a
teacher can override a generated recommendation with a reason.

**Risks and maturity:** Exempla accepts manually supplied aggregate metrics and
does not grade solutions; Scaffold's levels are numeric heuristics; Bloom's
"evidence" is not an assessment validity claim. Small local prototype is
plausible, but classroom value and learning outcomes are **Unverified**.

### 3. Morpheme Transfer Workbook

**Target user and pain:** A language learner or test-prep tutor sees long words
as arbitrary strings and needs practice inferring an unfamiliar word while
being warned when a tempting split is misleading.

**Exact repositories:** `ussyverse/morphemaussy` + `ussyverse/dualiaussy` +
`ussyverse/scaffoldussy`.

**Existing evidence (Exists):** Morphema models morphemes, variants, glosses,
cautions, vocabulary words, transfer prompts, word families, and attempts in
[`lib.rs`](https://github.com/ussyverse/morphemaussy/blob/HEAD/src/lib.rs).
`MorphemaEngine` implements segmentation, false-friend warnings, family
listing, transfer-attempt recording, high-yield suggestions, and printable
study sheets. The CLI accepts comma-separated word/definition entries in
[`main.rs`](https://github.com/ussyverse/morphemaussy/blob/HEAD/src/main.rs).
Dualia's `StudyMaterial` supports vocabulary structure and reconstructive
prompts in [`types.ts`](https://github.com/ussyverse/dualiaussy/blob/HEAD/src/domain/types.ts).
Scaffold supplies task/session loading and support trends as above.

**Proposed handoff/data flow:** Teacher imports a word list -> Morphema
segments each word and marks unknown pieces/false splits -> the adapter creates
an editable vocabulary card with literal construction and a word-family visual
sidecar for Dualia -> learner predicts a new word's meaning and confidence ->
the adapter records a Scaffold task/session and preserves the Morphema
`TransferAttempt` -> workbook export includes the correction and caution.

**MVP:** Twenty English terms, teacher approval of every segmentation, three
transfer prompts, and a CSV/Markdown session record. Keep the generated family
diagram optional and editable.

**Why combine:** Morphema supplies domain content and trap handling, Dualia
turns that content into a reconstructive card, and Scaffold gives a tutor a
small history of support and outcomes. A learner can move from "see the root"
to "use it on a new word" in one artifact.

**Missing work and acceptance:** Add stable word/prompt IDs, a mapping from
Morphema attempts to Scaffold sessions, and a human correction screen. The demo
passes if a false split such as `inflammable` remains visibly flagged and a
corrected segmentation is retained on export.

**Risks and maturity:** Segmentation is greedy and starter data is English-only;
unknown pieces explicitly reduce confidence. Productivity ranks and Scaffold
support advice are heuristics. The product must never present a literal
morpheme construction as a guaranteed definition or claim vocabulary gains.

### 4. Procedure Rehearsal Notebook

**Target user and pain:** A special-education teacher, vocational tutor, or
lab instructor needs to see which step in a multi-step routine breaks, whether
support is fading, and whether performance survives a changed setting.

**Exact repositories:** `ussyverse/chainletussy` + `ussyverse/scaffoldussy`.

**Existing evidence (Exists):** Chainlet defines ordered `Procedure`/`ChainLink`
and `PracticeAttempt` records in
[`models.py`](https://github.com/ussyverse/chainletussy/blob/HEAD/src/chainletussy/models.py).
`analyze_procedure` calculates per-link statistics, chain breaks, prompt plans,
generalization dimensions, and guardrails in
[`analyzer.py`](https://github.com/ussyverse/chainletussy/blob/HEAD/src/chainletussy/analyzer.py).
Its JSON/CSV loader preserves prompt, latency, context, correction, and
timestamp fields in [`io.py`](https://github.com/ussyverse/chainletussy/blob/HEAD/src/chainletussy/io.py).
Scaffold's `Task`, `Session`, `trend_for_skill`, and `recommend_support` are
implemented in [`analysis.py`](https://github.com/ussyverse/scaffoldussy/blob/HEAD/src/scaffold/analysis.py)
and its model module.

**Proposed handoff/data flow:** Procedure links and attempts -> Chainlet finds
the weak link, prompt dependence, and context variants -> adapter creates one
Scaffold skill/task per link or carefully chosen link cluster -> instructor
records the next attempt -> combined report shows step-level evidence beside
whole-task fit. Preserve `prompted`, `corrected`, and `skipped` separately;
they are not interchangeable success values.

**MVP:** A low-stakes routine with five links, two locations, and ten manually
entered attempts. Produce one weak-link card and a generalization checklist.

**Why combine:** Chainlet is fine-grained and procedural; Scaffold is useful for
task difficulty and session trend. The combination answers both "where does the
sequence fail?" and "what support should the next task expose?"

**Missing work and acceptance:** Define link-to-skill IDs, support vocabulary
mapping, consent/privacy handling, and a report that retains raw attempts. A
demo passes if three independent low-latency successes cause only a proposed
prompt fade, while two corrected attempts cause a proposed escalation.

**Risks and maturity:** Chainlet's generalization result requires observed
variation and its thresholds are hand-coded; Scaffold's ZPD classification is
not an individual diagnosis. For safety-critical routines, use qualified
instruction and treat the report as documentation only.

### 5. Chronobiology Puzzle Debrief

**Target user and pain:** A science teacher has a playable circadian-rhythm
simulation, but a final game score alone does not show whether a student can
explain phase shifts, budgets, and trade-offs.

**Exact repositories:** `ussyverse/entrainussy` + `ussyverse/bloomussy` +
`ussyverse/scaffoldussy`.

**Existing evidence (Exists):** Entrain models oscillators, phase-response
curves, bounded zeitgeber use, coupling, simulation history, and end-of-level
score in [`engine.py`](https://github.com/ussyverse/entrainussy/blob/HEAD/entrain/engine.py).
Hand-authored scenarios such as jet lag, shift work, DST, and a space mission
are defined in [`levels.py`](https://github.com/ussyverse/entrainussy/blob/HEAD/entrain/levels.py).
Progress persistence exists in [`storage.py`](https://github.com/ussyverse/entrainussy/blob/HEAD/entrain/storage.py).
Bloom can generate explain/compare/design tasks and store teacher-entered
evidence; Scaffold can represent the scenario as a task and the debrief as a
session.

**Proposed handoff/data flow:** Teacher selects a level -> learner actions and
phase changes are captured as a replay/debrief packet -> adapter asks the
learner to explain a chosen action, compare an alternative, and identify model
assumptions -> Bloom records the intended response level -> Scaffold records
task difficulty, support, success, and reflection -> teacher sees replay,
written explanation, and raw score side by side.

**MVP:** Use only the `jetlag` level, add an event-log export that includes
every action, and generate three teacher-authored debrief prompts. A learner
must be able to inspect the result without receiving personal sleep advice.

**Why combine:** Entrain provides an interactive model; Bloom supplies a
structured explanation/debrief vocabulary; Scaffold preserves repeated classroom
attempts. The educational artifact is the reasoning record, not the game score.

**Missing work and acceptance:** Add replay identity, action-log export, a
teacher rubric, and an explicit model-assumptions field. A demo passes if two
different action sequences can be replayed and the report distinguishes final
phase score from the learner's explanation.

**Risks and maturity:** PRCs are hard-coded model parameters and the source
does not establish scientific or instructional validity. `SimulationState.to_dict`
does not include its full `history`, so telemetry export is **Proposed**, not
existing. Keep this a classroom simulation, not health or sleep guidance.

### 6. Evolution Decision Field Lab

**Target user and pain:** An ecology instructor wants students to reason about
adaptation, colonization, population limits, and extinction, but a game result
does not preserve the student's hypotheses or distinguish luck from reasoning.

**Exact repositories:** `ussyverse/driftlineussy` + `ussyverse/bloomussy` +
`ussyverse/scaffoldussy`.

**Existing evidence (Exists):** Driftline's `Game` creates a seeded archipelago,
advances generations, simulates populations and random events, permits mutation
allocation and colonization, and serializes game state in
[`game.py`](https://github.com/ussyverse/driftlineussy/blob/HEAD/src/driftline/game.py).
Its score has a visible breakdown for living species, capacity, island
diversity, and convergence in
[`scoring.py`](https://github.com/ussyverse/driftlineussy/blob/HEAD/src/driftline/scoring.py).
JSON save/load is implemented in
[`save_load.py`](https://github.com/ussyverse/driftlineussy/blob/HEAD/src/driftline/save_load.py).
Bloom and Scaffold provide the prompt/evidence and task/session boundaries.

**Proposed handoff/data flow:** Seeded run -> capture each learner choice,
generation state, random event, and observation -> learner writes a prediction
before the next generation -> Bloom labels prediction, comparison, or design
task -> Scaffold records task difficulty/support and session outcome -> export
run trace plus student explanation and score breakdown.

**MVP:** A teacher-provided seed, six islands, five generations, and one
counterfactual replay with a changed colonization choice. Require the student
to explain one population change using the visible state, without grading the
explanation automatically.

**Why combine:** Driftline creates an inspectable scenario, while Bloom and
Scaffold turn play into a repeatable reflection and teaching workflow. This is
more useful than putting a leaderboard around the game.

**Missing work and acceptance:** Add action/replay logs, student and run IDs,
teacher-authored rubrics, and a way to label random events. A demo passes if a
teacher can compare two same-seed runs and see choices, state, and explanations
without conflating the game score with understanding.

**Risks and maturity:** Random events and simplified population rules can
confound interpretation; Driftline's score is a game objective, not a biology
assessment. `messages` and full decision history are not included in the main
serialized `Game.to_dict`, so the proposed telemetry layer is new. No claim of
learning efficacy is justified.

### 7. 8-bit Assembly Apprenticeship

**Target user and pain:** An introductory computer-architecture class needs
small executable exercises with deterministic feedback and a way to discuss
why a submission failed, rather than only showing accepted/rejected.

**Exact repositories:** `mojomast/coderc` + `ussyverse/scaffoldussy` +
`ussyverse/bloomussy`.

**Existing evidence (Exists):** CoderColossusussy's `Assembler` produces
bytecode, symbols, and a source line map in
[`Assembler.ts`](https://github.com/mojomast/coderc/blob/HEAD/packages/simulator/src/assembler/Assembler.ts).
`Simulator` supports step/run, CPU and memory state, snapshots, and reset in
[`Simulator.ts`](https://github.com/mojomast/coderc/blob/HEAD/packages/simulator/src/Simulator.ts).
`ChallengeGrader` runs supplied test cases with register/memory/flag/output
expectations and returns per-test results, cycles, memory, and errors in
[`ChallengeGrader.ts`](https://github.com/mojomast/coderc/blob/HEAD/apps/backend/src/services/ChallengeGrader.ts).
The repository also has explicit challenge/submission/session schema in
[`schema.prisma`](https://github.com/mojomast/coderc/blob/HEAD/apps/backend/prisma/schema.prisma).
Scaffold can ingest a manually normalized skill/task/session record; Bloom can
generate explain, apply, analyze, and create prompts.

**Proposed handoff/data flow:** Teacher-authored assembly challenge and rubric
-> learner submits code -> grader returns tests and resource observations ->
teacher or learner labels the observed error (register, control flow, memory,
or syntax) -> adapter records a Scaffold session and generates a Bloom-level
explanation prompt -> export code, test inputs, expected output, raw result,
and reflection. Do not infer a misconception solely from a failed test.

**MVP:** A local ADD/CMP/branch challenge set with three test cases, a replay
button, one line-mapped inspection view, and a Markdown reflection report.
Avoid auth, Discord, tournaments, and a persistent server in the first slice.

**Why combine:** Coder supplies executable evidence; Scaffold records the
support and task progression; Bloom makes students explain or modify the
program rather than chase a score. The common entity is a submission/test run.

**Missing work and acceptance:** Decouple or wrap the grader's Prisma enum
dependency, add stable challenge/run IDs, capture source-line observations, and
define a teacher rubric. A demo passes if a failed test preserves the exact
input/expected/actual evidence and produces a reflection task without claiming
the cause.

**Risks and maturity:** The source was inspected but not built or run here.
Coder has a broad web/database surface; the grader uses a performance formula
and its integration contract needs verification. Scaffold/Bloom outputs are
not validated assessments, and leaderboard ranking should be excluded from the
MVP.

### 8. Decision-Key Reasoning Dojo

**Target user and pain:** A junior support engineer or science student can
reach an answer by intuition but cannot explain which discriminating observation
changed the classification. A teacher needs to review the path, not just the
terminal label.

**Exact repositories:** `ussyverse/clavisussy` + `ussyverse/scaffoldussy` +
`ussyverse/bloomussy`.

**Existing evidence (Exists):** Clavis loads JSON dichotomous keys, traverses
binary questions, and returns a terminal plus full answer path in
[`engine.py`](https://github.com/ussyverse/clavisussy/blob/HEAD/clavis/engine.py).
It validates key coverage/determinism in
[`validation.py`](https://github.com/ussyverse/clavisussy/blob/HEAD/clavis/validation.py),
and `AdaptiveLearner.analyze_misclassification` compares original and correct
paths to identify a divergence point in
[`adaptive.py`](https://github.com/ussyverse/clavisussy/blob/HEAD/clavis/adaptive.py).
SQLite storage records keys, classification history, validation metrics, and
adaptive events in [`storage.py`](https://github.com/ussyverse/clavisussy/blob/HEAD/clavis/storage.py).
Scaffold models task/session evidence; Bloom supplies compare, justify, and
design prompts.

**Proposed handoff/data flow:** Teacher authors a domain-specific key and
specimens -> Clavis validates it -> learner answers one branch at a time ->
the teacher supplies the correct path when needed -> Clavis stores the path and
divergence -> adapter records a Scaffold session -> Bloom asks the learner to
justify the decisive observation or revise a question -> teacher reviews raw
paths and revised key versions.

**MVP:** A custom eight-terminal key for low-stakes software troubleshooting
or specimen identification, ten synthetic cases, and a report of the first
divergence per case. Do not reuse production severity/SLA fields as automatic
operational advice.

**Why combine:** Clavis makes reasoning steps inspectable, Scaffold tracks
practice context/support, and Bloom turns a classification into explanation or
key-design work. The output is a reviewable reasoning trace rather than a
personality or competence score.

**Missing work and acceptance:** Add learner IDs, case revisions, confidence
and time fields, explicit teacher answer keys, and education-specific terminal
metadata. A demo passes if a wrong branch can be replayed, compared with the
correct branch, and exported without overwriting the original path.

**Risks and maturity:** Clavis's built-in domain is bug/vulnerability triage;
custom classroom keys and terminal semantics are new. Its adaptive analysis
requires a supplied correct path and does not prove why a learner erred.
Scaffold and Bloom remain heuristic documentation aids.

### 9. Ruin to Reasoning Lab

**Target user and pain:** A history or archaeology teacher wants students to
reason from layered evidence and write an interpretation, not simply finish a
game or receive a narrative generated from hidden state.

**Exact repositories:** `ussyverse/tellussy` + `ussyverse/dualiaussy` +
`ussyverse/bloomussy`.

**Existing evidence (Exists):** Tell has a builder-to-excavator phase transition,
layered excavation, artifact registration, journal entries, feature flags, and
save/load in [`game.py`](https://github.com/ussyverse/tellussy/blob/HEAD/src/tell/game.py)
and [`excavator.py`](https://github.com/ussyverse/tellussy/blob/HEAD/src/tell/excavator.py).
`FieldJournal` preserves text, coordinates, depth, interpretation, and
confidence in [`journal.py`](https://github.com/ussyverse/tellussy/blob/HEAD/src/tell/journal.py).
The game computes separate chronology, feature-identification, narrative, and
care components in [`interpreter.py`](https://github.com/ussyverse/tellussy/blob/HEAD/src/tell/interpreter.py).
Dualia can analyze timeline/system/process material and generate reorder,
label, and teach-back prompts; Bloom stores a teacher-reviewed progression of
explanation, analysis, evaluation, and creation tasks.

**Proposed handoff/data flow:** Saved Tell run plus journal -> adapter builds a
timeline/layer diagram and evidence table -> Dualia checks label placement,
segmentation, and retrieval prompts -> learner writes a claim with cited
coordinates/depths -> Bloom records the intended reasoning task and teacher
feedback -> export run state, journal, visual reconstruction, and claim/evidence
packet.

**MVP:** One seeded run, five journal entries, two competing interpretations,
and a student-created timeline. Keep the game score visible but separate from
the teacher's rubric.

**Why combine:** Tell creates the observation problem, Dualia makes the spatial
and chronological structure reconstructable, and Bloom provides an explicit
reflection target. The resulting artifact can be reviewed after the session.

**Missing work and acceptance:** Add stable run/entry IDs, an evidence-reference
format, a lossless state exporter, and teacher rubric fields. A demo passes if a
student can click from a claim to the exact depth/coordinate and rebuild the
timeline without the adapter inventing evidence.

**Risks and maturity:** Tell's artifact generation and events are game
mechanics, not archaeological evidence. Dualia's analysis is input-metadata
driven and will not understand arbitrary game output without the proposed
adapter. Tell's scoring should not be marketed as historical reasoning
measurement.

### 10. Reading Seminar Pack

**Target user and pain:** A graduate student, independent learner, or seminar
leader has a large reading backlog with prerequisites and duplicates, then
needs a manageable agenda and a way to prepare a discussion from the selected
material.

**Exact repositories:** `ussyverse/citewiseussy` + `ussyverse/dualiaussy` +
`ussyverse/scaffoldussy`.

**Existing evidence (Exists):** Citewise accepts structured items, topics,
edges, goals, difficulty, length, energy, and trust in
[`types.go`](https://github.com/ussyverse/citewiseussy/blob/HEAD/pkg/citewise/types.go).
`Analyze` classifies roles and computes explainable scores; `PlanQueue` applies a
time budget; `Hygiene` identifies duplicates, orphans, stale items, and missing
bridges in [`engine.go`](https://github.com/ussyverse/citewiseussy/blob/HEAD/pkg/citewise/engine.go).
Dualia parses a selected Markdown reading note and emits retrieval/accessibility
actions. Scaffold records a task/session history and produces a practice plan.

**Proposed handoff/data flow:** CSV/JSON bibliography plus manually curated
prerequisite/citation edges -> Citewise produces a bounded read-next queue and
flags missing bridges -> leader attaches a Markdown note for one selected item
-> Dualia produces a visual/verbal discussion card and prompts -> Scaffold
records preparation, discussion, support, and follow-up tasks -> export agenda,
source links, raw rationale, and unresolved questions.

**MVP:** Twelve papers, one 90-minute budget, manually entered prerequisite
edges, and one prepared seminar note with four discussion prompts. Let the
leader accept or reject every queue choice.

**Why combine:** Citewise solves selection and backlog hygiene, Dualia solves
the shape of the preparation artifact, and Scaffold records whether the task
was completed and what support was used. This joins reading management to a
concrete seminar deliverable without pretending to assess comprehension.

**Missing work and acceptance:** Add stable reading/note/task IDs, a source
link and revision field, queue-to-card provenance, and manual outcome entry. A
demo passes if a selected paper's prerequisite warning remains visible in the
agenda and the exported card links back to the same source item.

**Risks and maturity:** Citewise scoring depends on metadata and manually
entered edges; it is not a bibliographic truth engine. Dualia's Markdown
inference is shallow, and Scaffold does not grade discussion quality. Preserve
the leader's overrides and do not claim that queue order improves scholarship.

## Rejected adjacent ideas

### R1. The Personal Mastery and Forgetting OS

**Exact repositories considered:** `ussyverse/synapseussy` +
`ussyverse/ebbinghausussy` + `ussyverse/bloomussy` +
`ussyverse/scaffoldussy`.

**Existing evidence:** Synapse stores topic/prerequisite graphs and study
sessions in [`engine.ts`](https://github.com/ussyverse/synapseussy/blob/HEAD/src/engine.ts).
Ebbinghaus is listed in the index as a power-law scheduler, while Bloom and
Scaffold provide separate level/support histories.

**Why rejected:** This is the same failure mode as the already rejected broad
learning-OS direction: several state machines would compete to decide what
"mastery" means, while the learner still lacks one clearly bounded next action.
The inspected Synapse rules include arbitrary fatigue, consolidation, and
"myelinated" thresholds; they do not validate a personal neuroscience model.
Ebbinghaus was not source-audited in this pass, so its index description is
**Unverified** here. Use a single concrete workflow such as ideas 2, 4, or 10
after collecting actual attempts instead.

### R2. Universal Gamified Tutor Arcade

**Exact repositories considered:** `mojomast/coderc` +
`ussyverse/entrainussy` + `ussyverse/driftlineussy`.

**Existing evidence:** Coder has an executable 8-bit simulator and challenge
grader; Entrain and Driftline have deterministic seeded science-game cores and
save/score surfaces.

**Why rejected:** A shared game shell would be an orchestration/UI project, not
a natural handoff between the three domains. Their entities, action spaces,
and scoring semantics do not share a meaningful learning record without first
building three separate curricula, telemetry systems, and rubrics. Combining
them because all three are playable would add novelty but no defensible user
outcome. Keep the science ideas as separate debrief products and the assembly
idea as a focused apprenticeship.

## Overall judgment

The strongest low-risk experiments are **Notes to Recall Atlas**, **Tutor
Fading Board**, **Procedure Rehearsal Notebook**, and **Reading Seminar Pack**:
they have small local inputs, explicit human review points, and useful exports
without requiring a validated prediction model. The science-game and assembly
ideas are attractive teaching prototypes but need better event capture and
teacher-authored rubrics before their run data can support any educational
interpretation.
