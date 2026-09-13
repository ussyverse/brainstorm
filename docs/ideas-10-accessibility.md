# Accessibility and Cognitive-Load Product Ideas

**Date:** 2026-09-13
**Focus:** accessibility, neurodivergence-friendly workflows, cognitive load, clear communication, and assistive interfaces.

These are new proposals, not replacements for the ten ideas in
`SOURCE_CHECKED_COMBINATIONS.md`. The existing shortlist includes a learning
confusion lab, household handoff rehearsal, return follow-through, and several
other overlapping domains. The ideas below instead emphasize reducing the
number of decisions a person must hold at once, making alternate modes visible,
and preserving a usable raw record beside any score or recommendation.

## Evidence and scope

I inspected the checked-out source and manifests for the repositories named
below, including core models, engines, entry points, and tests where present.
Repository revisions were recorded with `git rev-parse --short HEAD` on the
date above. No candidate repository was modified, built, installed, or runtime-
tested for this pass. Existing tests are evidence of intended contracts, not a
claim that the current checkouts pass or that a proposed product works.

Every statement marked **Exists** refers to inspected source. Every statement
marked **Proposed** is new integration or product work.

## 1. Control and Posture Redesign Cards

**Target user and pain.** A person configuring a phone, appliance, desk control,
or craft workstation may have to reach, tap, read, or hold a position at the
same time. Existing accessibility checklists often separate the target layout
from the task posture, leaving the user to reconcile two reports.

**Exact repositories.**

- [`ussyverse/fittsaussy`](https://github.com/ussyverse/fittsaussy)
- [`ussyverse/rulaiaussy`](https://github.com/ussyverse/rulaiaussy)

**Existing evidence.**

- **Exists:** Fittsa's [`TargetInput` and `analyze`](https://github.com/ussyverse/fittsaussy/blob/HEAD/src/lib.zig) accept target size, distance, neighboring controls, posture, input mode, urgency, and consequence. They return acquisition burden and redesign recommendations. Its [`main.zig`](https://github.com/ussyverse/fittsaussy/blob/HEAD/src/main.zig) exposes JSON analysis over a local HTTP endpoint.
- **Exists:** Rulaia's [`TaskCard` and `analyze_card`](https://github.com/ussyverse/rulaiaussy/blob/HEAD/src/lib.rs) accept task observations, duration, repetitions, input geometry, and reversible interventions. It has explicit safety-boundary output and a coarse self-observation disclaimer.

**Proposed handoff/data flow.** A user records one `controlId` plus one
`taskId`: location, target dimensions and distance, input mode, posture notes,
duration, and repeated-use context. A small coordinator sends the control
fields to Fittsa and task fields to Rulaia, then joins their raw JSON by the
stable IDs. It renders one card with separate sections: "make the target
easier to acquire" and "make the task easier to sustain," followed by a single
reversible change to try. It must not collapse both outputs into a medical or
universal accessibility grade.

**MVP.** A local form for three controls on one laptop or kitchen appliance;
export a plain-text card; let the user mark one change as tried and record
before/after misses or hesitation. Acceptance means every recommendation links
back to its input observation and the export remains usable without the web UI.

**Value of combination.** Fittsa catches small, distant, confusing targets;
Rulaia catches the posture and exposure around using them. Together they reduce
the need to translate an abstract layout issue into a separate task-body issue.

**Risks and maturity.** Both engines are deterministic heuristics, not
compliance certification, diagnosis, or proof that a person will find a change
comfortable. Fittsa's score uses fixed modifiers and Rulaia's text matching is
coarse. The adapter must preserve unknown fields, avoid using "low vision,"
"tremor," or similar input labels as diagnoses, and provide a text-only path.
Fittsa is a small Zig web app; Rulaia is a Rust CLI/library. Cross-language
serialization and an accessible editor are new work.

## 2. Hybrid Meeting Clarity Packet

**Target user and pain.** A meeting facilitator has remote, quiet, mobile, or
communication-preference-sensitive participants, while the room itself causes
echo or speech blur. Moving seats and buying acoustic treatment are usually
separate decisions, and neither produces a concise run-of-meeting packet.

**Exact repositories.**

- [`ussyverse/proxemaussy`](https://github.com/ussyverse/proxemaussy)
- [`ussyverse/reverbaussy`](https://github.com/ussyverse/reverbaussy)

**Existing evidence.**

- **Exists:** Proxema's [`Scenario`, `Participant`, and `OptimizeSeating`](https://github.com/ussyverse/proxemaussy/blob/HEAD/pkg/proxema/model.go) model accessible seats, remote attendance, desired presence, conflicts, affinities, and a deterministic seating assignment. Its analysis recommends an in-room remote advocate, early remote turns, and round-robin check-in.
- **Exists:** Reverba's [`RoomInput`, `analyze_room`, and treatment cards](https://github.com/ussyverse/reverbaussy/blob/HEAD/src/reverba/engine.py) model room surfaces, activity targets including calls and studying, speech-blur symptoms, background noise, reflection paths, and renter-safe reversible changes. The [`pyproject.toml`](https://github.com/ussyverse/reverbaussy/blob/HEAD/pyproject.toml) declares a local FastAPI/CLI package.

**Proposed handoff/data flow.** The meeting record contains a stable `meetingId`,
participant preferences, seat map, activity, room dimensions, surfaces, and
plain-language communication agreements. Proxema produces assignment and
turn-taking warnings. Reverba produces room-path and placement cards. The
joined packet shows: seat, remote advocate, first speaking round, microphone
placement, and one fallback such as chat or written notes. No participant
attribute should be inferred from their name or from the scores.

**MVP.** Import one JSON meeting scenario and room profile, generate a
one-page pre-meeting card, and simulate one remote participant plus one noisy
room. Acceptance means a facilitator can see each participant's requested
accommodation, every room recommendation names its input evidence, and the
packet includes a no-audio alternative.

**Value of combination.** Proxema addresses who can be seen, heard, and
included in the room protocol. Reverba addresses whether the room makes that
protocol harder to follow. The deliverable is a meeting preparation artifact,
not two unrelated dashboards.

**Risks and maturity.** Proxema's presence and power measures are spatial
heuristics, not a measure of actual participation. Reverba uses qualitative
surface coefficients and does not measure a room or hearing access. Neither
repo supplies calendar integration, live captions, or real-time audio
measurement. Keep the packet editable, use explicit participant-provided
preferences, and retain a text fallback.

## 3. Low-Decision Outing Exit Card

**Target user and pain.** A family, school group, or friend group attending an
event or taking a short urban walk may need to leave early, avoid dense streams,
or regroup without making new route decisions while tired or overloaded.

**Exact repositories.**

- [`ussyverse/egressaussy`](https://github.com/ussyverse/egressaussy)
- [`ussyverse/controlaussy`](https://github.com/ussyverse/controlaussy)

**Existing evidence.**

- **Exists:** Egressa's [`EventPlan` models](https://github.com/ussyverse/egressaussy/blob/HEAD/src/egressa/models.py) include group-entered communication needs, meeting points, accessibility notes, quiet edges, observations, phone battery, and sensory-load observations. [`analyze_plan`](https://github.com/ussyverse/egressaussy/blob/HEAD/src/egressa/engine.py) returns bottlenecks, departure waves, accepted low-flow meeting points, buddy protocols, lost-link steps, and a printable event card.
- **Exists:** Controla's [`WalkPlan`, `classifyLeg`, and `makeLeg`](https://github.com/ussyverse/controlaussy/blob/HEAD/src/controla.nim) accept manually entered controls, attack points, handrails, catching features, bailouts, ambiguous turns, time boxes, and `accessibleMode`. Its [`htmlReport`](https://github.com/ussyverse/controlaussy/blob/HEAD/src/controla.nim) renders printable leg cards.

**Proposed handoff/data flow.** A planner enters only verified venue features and
short route legs, with a source note for each. Egressa selects a departure
window, primary/backup regroup point, and lost-link protocol. Controla turns
the chosen route into a sequence of small leg cards with one clue, one
relocation trigger, and one bailout. The final card labels all values as
planning inputs and keeps venue staff, posted signs, and emergency responders
as the authority.

**MVP.** One event with three manually authored legs, two regroup points, a
phone-battery choice, and an early-exit preference. Acceptance means the user
can print a card containing no more than three immediate actions, a backup
point, a bailout, and a "do not use this for emergencies" notice.

**Value of combination.** Egressa reduces crowd-flow and regrouping choices;
Controla reduces navigation ambiguity. One small card is easier to consult than
reconstructing a route from a map and a separate event plan.

**Risks and maturity.** Egressa explicitly disclaims emergency evacuation and
real-time crowd prediction. Controla uses manually entered landmarks and does
not query maps, access audits, opening hours, lifts, or current closures. The
combination cannot certify a route as physically accessible. Its strongest
early use is a known venue or familiar neighborhood with a human-verified
route. The venue feature editor and source/provenance fields are new work.

## 4. Notes-to-Quiet-Study Card

**Target user and pain.** A learner who is overwhelmed by dense notes needs a
small, predictable next session, not another large dashboard. A teacher also
needs a way to vary guidance without treating a score as a statement about the
learner.

**Exact repositories.**

- [`ussyverse/dualiaussy`](https://github.com/ussyverse/dualiaussy)
- [`ussyverse/chunkussy`](https://github.com/ussyverse/chunkussy)
- [`ussyverse/exemplaussy`](https://github.com/ussyverse/exemplaussy)

**Existing evidence.**

- **Exists:** Dualia's [`StudyMaterial` types](https://github.com/ussyverse/dualiaussy/blob/HEAD/src/domain/types.ts) represent text, visuals, captions, audio, accessibility preferences, and structure. [`analyzeMaterial`](https://github.com/ussyverse/dualiaussy/blob/HEAD/src/domain/analyzer.ts) emits segmenting, coherence, signaling, redundancy, cognitive-load, retrieval, and accessibility notes.
- **Exists:** Chunk's [`chunk_analyze_text`, `build_chunks`, and render functions](https://github.com/ussyverse/chunkussy/blob/HEAD/chunk.c) split sentences, classify definitions/causes/lists/comparisons, greedily build three-to-five-item chunks, generate reconstruction prompts, and produce a text tree and interleaved schedule. The [`Makefile`](https://github.com/ussyverse/chunkussy/blob/HEAD/Makefile) declares a C11 build and unit-test target.
- **Exists:** Exempla's [`classifyLearner`](https://github.com/ussyverse/exemplaussy/blob/HEAD/src/learner.ts) and [`prescribeFading`](https://github.com/ussyverse/exemplaussy/blob/HEAD/src/fading.ts) choose worked examples, completion problems, independent practice, or transfer probes from user-entered metrics and deck steps.

**Proposed handoff/data flow.** Import a note as plain text plus optional
visual/caption metadata. Dualia identifies excess elements and missing access
supports; Chunk creates a bounded map and retrieval prompts; Exempla receives
the chosen topic's explicit steps and a teacher/learner-selected guidance
level. The output is a session card with one chunk, one prompt, one optional
hint, and a later revisit field. Raw text and all warnings stay available.

**MVP.** A local browser wrapper around one 1,000-word note, with a "short
session" button and exported Markdown card. Acceptance means the user can
choose text-first or visual-plus-text presentation, see unresolved structure,
and complete a prompt without being forced through a fixed schedule.

**Value of combination.** Dualia repairs presentation load, Chunk bounds the
material, and Exempla controls how much help is visible. The user gets a
manageable next action rather than three independent analyses.

**Risks and maturity.** Chunk has fixed C buffer limits and simple punctuation
and keyword rules. Dualia's score is not an accessibility certification, and
Exempla's stage labels are heuristic; none establishes learning efficacy. The
adapter must handle Unicode and long documents before relying on Chunk, keep
captions/transcripts rather than deleting them, and make guidance user
adjustable. No cross-repository storage contract exists.

## 5. Accessible Course-Packet Shelf

**Target user and pain.** A student, caregiver, or small office worker has a
mixed folder of current PDFs, old instructions, scans, and dense handouts. The
hard part is deciding what must remain, what to read next, and what needs a
more accessible presentation without destroying provenance.

**Exact repositories.**

- [`ussyverse/mustiaussy`](https://github.com/ussyverse/mustiaussy)
- [`ussyverse/citewiseussy`](https://github.com/ussyverse/citewiseussy)
- [`ussyverse/dualiaussy`](https://github.com/ussyverse/dualiaussy)

**Existing evidence.**

- **Exists:** Mustia's [`ItemCard`, `recommendDecision`, and `analyzeCollection`](https://github.com/ussyverse/mustiaussy/blob/HEAD/src/mustia.ts) distinguish keep, replace, archive, ask-first, discard, and review-later lanes. Retention exceptions block casual disposal and the renderer emits a Markdown board and CSV log.
- **Exists:** Citewise's [`Backlog` model and `PlanQueue`](https://github.com/ussyverse/citewiseussy/blob/HEAD/pkg/citewise/types.go) and [`engine.go`](https://github.com/ussyverse/citewiseussy/blob/HEAD/pkg/citewise/engine.go) accept JSON/CSV items, topics, prerequisites, length, difficulty, energy, density, and source trust. It identifies duplicates, missing bridges, and a bounded read-next queue with rationales.
- **Exists:** Dualia's [`summarizeCardMarkdown`](https://github.com/ussyverse/dualiaussy/blob/HEAD/src/domain/analyzer.ts) exports visual/verbal channels, remove/rewrite actions, retrieval prompts, and accessibility notes such as not relying on color alone.

**Proposed handoff/data flow.** A manual importer creates one stable record per
document and preserves the file path/hash outside the analysis text. Mustia
decides whether the item can leave the active shelf. Citewise plans a short
read-next queue from retained items and explicit prerequisite edges. Dualia
checks only the selected handout or note for density, captions, labels, and
non-color cues. The product offers three visible lanes: keep, read next, and
redesign; it never silently deletes or rewrites the source.

**MVP.** Five local handouts: one current, one duplicate, one protected record,
one dense diagram, and one stale item with a known replacement. Acceptance
means every decision has a reason and safety-stop field, the queue fits a
user-entered time budget, and the redesigned output links to the original.

**Value of combination.** Mustia reduces unsafe document decisions, Citewise
reduces reading-order decisions, and Dualia reduces presentation decisions.
This directly targets cognitive load while preserving control over source
material.

**Risks and maturity.** All three depend on manually supplied metadata; there
is no general PDF/OCR/import adapter. Mustia's export limitations documented in
the source-checked report still apply. Citewise's scores and prerequisite
conventions are heuristics, and Dualia does not create accessible media by
itself. The first release should be local-only and use explicit "unknown" and
"needs human review" states.

## 6. Task Launch Runway

**Target user and pain.** A person with variable energy or a busy transition
between activities may know what needs doing but fail to start because the
choice, setup, and cue are all separate. The product should help launch one
task without implying a diagnosis or demanding a streak.

**Exact repositories.**

- [`ussyverse/formicaussy`](https://github.com/ussyverse/formicaussy)
- [`ussyverse/ritualaussy`](https://github.com/ussyverse/ritualaussy)
- [`ussyverse/prospectaussy`](https://github.com/ussyverse/prospectaussy)

**Existing evidence.**

- **Exists:** Formica's [`Task`, `chooseTasks`, `matchesEnergy`, and `staleWarnings`](https://github.com/ussyverse/formicaussy/blob/HEAD/src/formica.nim) store estimated minutes, energy cost, cues, related tasks, decay, and status, then choose a bounded shortlist for current energy and available minutes.
- **Exists:** Rituala's [`Ritual`, `BuildRitualFromDesign`, and `AnalyzeRitual`](https://github.com/ussyverse/ritualaussy/blob/HEAD/main.go) create short transition sequences, log whether cues were noticed/completed, and include opt-out, pressure, ambiguity, and consent checks.
- **Exists:** Prospecta's [`DesignPlan`, `ClassifyMiss`, and `RecommendAids`](https://github.com/ussyverse/prospectaussy/blob/HEAD/prospecta.go) turn an intention into an if-then cue card, external-aid list, delayed-execution rule, and post-miss taxonomy.

**Proposed handoff/data flow.** A task record has stable ID, kind, estimated
minutes, user-entered energy cost, and a preferred context. Formica returns at
most three launch candidates. For the chosen task, Rituala supplies a
two-to-five-step transition with an explicit skip or pause path. Prospecta
binds the first step to a place, object, event, or routine and prints a cue
card. Completion, deliberate skip, and blocked start are recorded separately.

**MVP.** A local JSON/TUI prototype with ten tasks and three transition
templates: arriving home, opening work, and leaving for an errand. Acceptance
means a low-energy input produces a small list, the user can replace or reject
the suggestion, and no task is marked failed merely because it was deliberately
skipped.

**Value of combination.** Formica narrows the choice; Rituala makes the change
of context legible; Prospecta puts the next action in the environment. The
combination is a launch workflow, not a larger task score.

**Risks and maturity.** Formica's pheromone and "colony health" values are
metaphorical heuristics and should not be presented as a personal capacity
measurement. Rituala currently analyzes user-submitted logs and sample data;
Prospecta suggests aids but sends no notifications. A user-data editor,
timezone-aware persistence, and accessible non-TUI interface are new work.

## 7. Voice-Sparing Communication Day

**Target user and pain.** A teacher, facilitator, call-heavy worker, or person
choosing to limit speaking needs a plan that shifts some communication to room
setup and text. They need alternatives, not pressure to disclose a medical
reason.

**Exact repositories.**

- [`ussyverse/phonaraussy`](https://github.com/ussyverse/phonaraussy)
- [`ussyverse/reverbaussy`](https://github.com/ussyverse/reverbaussy)
- [`mojomast/Tchaikovskussy`](https://github.com/mojomast/Tchaikovskussy)

**Existing evidence.**

- **Exists:** Phonara's [`VoiceBaseline`, `TalkBlock`, and `analyze_day`](https://github.com/ussyverse/phonaraussy/blob/HEAD/src/phonara/models.py) and [`engine.py`](https://github.com/ussyverse/phonaraussy/blob/HEAD/src/phonara/engine.py) accept self-entered talk blocks, loudness, noise, audience, amplification, and recovery time. Its intervention ladder explicitly includes written directions, turn-taking, chat/visual cues, and rest blocks.
- **Exists:** Reverba supplies room activity targets, noise-vs-echo warnings, microphone placement suggestions, and reversible treatment cards in [`engine.py`](https://github.com/ussyverse/reverbaussy/blob/HEAD/src/reverba/engine.py).
- **Exists:** Tchaikovskussy's [`UserPreferences` and `transform_message`](https://github.com/mojomast/Tchaikovskussy/blob/HEAD/backend/models.py) support per-recipient target languages, while [`Chat.tsx`](https://github.com/mojomast/Tchaikovskussy/blob/HEAD/frontend/src/components/Chat.tsx) provides a text chat surface. Translation is LLM-backed and can pass through unchanged when no key or service is available.

**Proposed handoff/data flow.** The user enters a day schedule, room profile,
and communication choices such as "written fallback available" or "no
translation." Phonara suggests which blocks can be shortened or moved to text;
Reverba suggests microphone/placement changes; Tchaikovskussy is an optional
text bridge for named participants. The output is a schedule with explicit
voice, text, pause, and fallback blocks. It must show original text and
translation status separately.

**MVP.** Three talk blocks in one room, one written activity, and an optional
two-language text thread. Acceptance means the user can disable translation,
export the schedule without an account, and see a failure/pass-through state
when the language service is unavailable.

**Value of combination.** Phonara changes the communication mix, Reverba makes
speech easier to hear without requiring louder speech, and Tchaikovskussy
provides a text route when users choose it. This is a practical accommodation
planner rather than a voice-health or translation authority.

**Risks and maturity.** Phonara contains health-adjacent labels and fixed
thresholds; it must remain self-observation and pacing documentation, not
diagnosis or clinical advice. Reverba does not measure vocal effort or hearing.
Tchaikovskussy sends message text to a configured model unless a local/custom
provider is used, and language detection is heuristic. Consent, privacy,
retention, and a reliable non-LLM text path are mandatory before wider use.

## 8. Text-First Vocabulary Bridge

**Target user and pain.** A language learner or peer tutor may understand a
translated sentence but still not know why a new word looks or sounds the way
it does. A text-first side panel can expose word structure and reading rhythm
without requiring a live spoken exchange.

**Exact repositories.**

- [`ussyverse/morphemaussy`](https://github.com/ussyverse/morphemaussy)
- [`ussyverse/scansionussy`](https://github.com/ussyverse/scansionussy)
- [`mojomast/Tchaikovskussy`](https://github.com/mojomast/Tchaikovskussy)

**Existing evidence.**

- **Exists:** Morphema's [`MorphemaEngine::segment`, `transfer_prompt`, and `study_sheet`](https://github.com/ussyverse/morphemaussy/blob/HEAD/src/lib.rs) segment words into roots and affixes, expose ambiguity and false-friend warnings, record transfer attempts, and emit printable sheets. Its manifest shows a small Rust CLI with tests.
- **Exists:** Scansion's [`analyze` and report renderers](https://github.com/ussyverse/scansionussy/blob/HEAD/src/lib.rs) emit tokens, heuristic syllable/stress estimates, breath groups, overload prompts, and text/Markdown/JSON reports.
- **Exists:** Tchaikovskussy's [`ChatMessage` schema](https://github.com/mojomast/Tchaikovskussy/blob/HEAD/backend/models.py) retains original text, rewritten text, source language, target language, and timestamps. [`build_transform_prompt`](https://github.com/mojomast/Tchaikovskussy/blob/HEAD/backend/llm.py) instructs the model to translate fully, preserve meaning, and return only transformed text.

**Proposed handoff/data flow.** A user selects a message or manually enters a
word and confirms its language. Tchaikovskussy produces a translation with
status metadata. Morphema analyzes only explicitly supported vocabulary tables,
and Scansion creates an optional reading/pause view. The card displays source,
translation, word parts, cautions, and a user-editable definition. It never
pretends that a guessed segmentation or stress pattern is authoritative.

**MVP.** Support English study text and two configured target languages, with a
manual "add this word" action and Markdown export. Acceptance means an
unavailable or refused translation leaves the original visible, unknown
morphemes are labeled, and a user can remove the generated explanation before
sharing.

**Value of combination.** Tchaikovskussy handles the communication boundary;
Morphema supplies reusable word structure; Scansion offers a non-audio pacing
view. The result is useful to someone who prefers reading and inspection over
rapid conversation.

**Risks and maturity.** Morphema's starter table and Scansion's stress rules
are English-oriented and heuristic. Tchaikovskussy requires careful model,
privacy, and language validation; its chat UI is not an accessibility-tested
learning interface. This is not an interpreter, pronunciation evaluator, or
language-acquisition claim. Begin with user-authored examples, visible source
text, and manual correction.

## 9. Calm Search and Return-Home Card

**Target user and pain.** In a shared household, searching for keys, glasses,
or a remote can become repetitive and blame-laden. A good search plan says what
to check next; a good shared-home plan says how the item will be returned to a
known place afterward.

**Exact repositories.**

- [`ussyverse/saccadaussy`](https://github.com/ussyverse/saccadaussy)
- [`ussyverse/raciaussy`](https://github.com/ussyverse/raciaussy)
- [`ussyverse/prospectaussy`](https://github.com/ussyverse/prospectaussy)

**Existing evidence.**

- **Exists:** Saccada's [`SaccadaPlanner::plan` and `SearchPlan`](https://github.com/ussyverse/saccadaussy/blob/HEAD/src/lib.rs) rank zones, create explainable next steps, prevent identical revisits, insert a calm reset after a panic loop/fatigue input, and generate neutral shared-space questions.
- **Exists:** Racia's [`analyzePlan` and `computeLoads`](https://github.com/ussyverse/raciaussy/blob/HEAD/src/engine.ts) detect missing or multiple accountable owners, missing access, over-broad responsibility, affected-only-informed members, and invisible coordination load. Its [`models.ts`](https://github.com/ussyverse/raciaussy/blob/HEAD/src/models.ts) supports stable task/member IDs and temporary assignments.
- **Exists:** Prospecta's object-placement, location-note, and visual-marker aids are selected by [`RecommendAids`](https://github.com/ussyverse/prospectaussy/blob/HEAD/prospecta.go), and `GenerateCueCard` emits printable if-then text.

**Proposed handoff/data flow.** A lost-item case has a stable item ID and
privacy-preserving zone labels. Saccada returns the next three moves and any
stopping/escalation notes. If another household member or shared surface is
involved, Racia creates one accountable return-home task and names who can
provide context. Prospecta binds that task to a shelf, bowl, bag, or doorway
cue. The card shows "search now" separately from "change the future storage
routine."

**MVP.** Keys, glasses, and remote scenarios with a shared entry surface. Test
one ordinary search, one repeated-search case, and one deliberate skip.
Acceptance means the card never instructs accusation, records the search method
so an identical revisit is avoided, and can be printed with no names if the
household chooses.

**Value of combination.** Saccada handles attention and search sequencing;
Racia handles ownership and context; Prospecta handles future retrieval cues.
It closes the loop without turning a lost item into a person-ranking system.

**Risks and maturity.** Saccada is not a locator and cannot see the home;
Racia's invisible-load index is a heuristic; Prospecta's cue quality is
human-rated. Do not use this workflow to infer theft or responsibility. The
shared privacy model, local storage, and card redaction are new work.

## 10. Consent-First Household Decision Packet

**Target user and pain.** Roommates or families making a recurring choice may
need a quick decision mechanism, but a close vote can hide a veto, a pressure
pattern, or a need to pause the conversation. The output should distinguish
"we chose an option" from "we need a safer or slower discussion."

**Exact repositories.**

- [`ussyverse/quorumussy`](https://github.com/ussyverse/quorumussy)
- [`ussyverse/circleraussy`](https://github.com/ussyverse/circleraussy)
- [`ussyverse/proxemaussy`](https://github.com/ussyverse/proxemaussy)

**Existing evidence.**

- **Exists:** Quorum's [`DecisionFile`, `Quorum`, `Polarization`, `VetoDiagnostics`, and `Suggest`](https://github.com/ussyverse/quorumussy/blob/HEAD/internal/quorum/model.go) store preferences, vetoes, tolerances, notes, and weights. They report whether a threshold was reached, close-option clustering, veto imbalance, and a suggested option.
- **Exists:** Circlera's [`SafetyScreen`, `validate_circle_ready`, `create_session`, and round rules](https://github.com/ussyverse/circleraussy/blob/HEAD/src/circlera/rules.py) block cases with coercion, threats, retaliation fear, abuse, legal constraints, or missing consent. They enforce harm -> needs -> accountability order and create commitments with due/review dates.
- **Exists:** Proxema's [`Participant` and `OptimizeSeating`](https://github.com/ussyverse/proxemaussy/blob/HEAD/pkg/proxema/model.go) support accessible seats, remote status, conflict separation, and round-robin recommendations.

**Proposed handoff/data flow.** A decision file stores options and each
participant's preferred communication mode without requiring weights. Quorum
reports threshold, veto, tolerance, and close-race facts. If the group opts to
continue, Circlera's safety/consent screen determines whether a repair-style
conversation is appropriate; it does not automatically start one. Proxema
creates a room or remote arrangement for the agreed conversation. The final
packet has three possible outcomes: decision reached, more information needed,
or pause and seek outside support.

**MVP.** A four-option household decision with two remote participants, one
veto, and one declined participant. Acceptance means declined consent blocks a
session, a veto remains visible beside the winner, and the export contains no
private statement unless explicitly selected.

**Value of combination.** Quorum makes preferences inspectable, Circlera
protects voluntary participation and turns needs into observable follow-up,
and Proxema makes the discussion setup less exclusionary. The product offers a
clear stop path instead of forcing consensus.

**Risks and maturity.** These are decision and conversation aids, not therapy,
mediation, abuse assessment, or authority over household safety. Quorum's
weights and polarization detection are heuristics. Circlera uses generated IDs,
local objects, and a safety screen that still requires human judgment. Proxema
does not model acoustics or actual power dynamics. Keep the first version
single-user/local, make safety blocks prominent, and do not add an LLM mediator.

## Rejected ideas

### R1. Universal accessibility score

**Rejected components:** `ussyverse/fittsaussy` + `ussyverse/proxemaussy` +
`ussyverse/egressaussy` + `ussyverse/reverbaussy`.

The repositories produce different kinds of evidence: target acquisition
burden, spatial participation heuristics, event-flow planning, and room-echo
estimates. Averaging them into one "accessibility score" would hide which
observation caused a warning, encourage false comparisons between people and
places, and imply validation that was not inspected. The accepted ideas above
keep the components' raw inputs and make a concrete card for one context.

### R2. Automatic spoken-language and voice-capacity coach

**Rejected components:** `mojomast/Tchaikovskussy` +
`ussyverse/phonaraussy` + `ussyverse/scansionussy`.

The combination sounds attractive, but the inspected code does not provide a
validated speech recognizer, pronunciation evaluator, or clinical voice
assessment. Tchaikovskussy transforms text through a configured LLM;
Phonara uses self-entered talk blocks and conservative thresholds; Scansion
estimates English stress and syllables from text. Presenting their output as a
spoken-language coach could overstate translation accuracy, language coverage,
or health meaning. Idea 7 uses the narrower, defensible version: optional text
communication and schedule changes with visible uncertainty.

## Revision record

Revisions observed with `git rev-parse --short HEAD`:

| Repository | Revision |
|---|---|
| `ussyverse/fittsaussy` | `67a892d` |
| `ussyverse/rulaiaussy` | `0b276b3` |
| `ussyverse/proxemaussy` | `1e5ffe8` |
| `ussyverse/reverbaussy` | `c914aab` |
| `ussyverse/egressaussy` | `df3811b` |
| `ussyverse/controlaussy` | `c3170f9` |
| `ussyverse/dualiaussy` | `706bd5f` |
| `ussyverse/chunkussy` | `eecbced` |
| `ussyverse/exemplaussy` | `9d38399` |
| `ussyverse/mustiaussy` | `122fc0a` |
| `ussyverse/citewiseussy` | `ea270ca` |
| `ussyverse/formicaussy` | `64ce987` |
| `ussyverse/ritualaussy` | `3feb8fe` |
| `ussyverse/prospectaussy` | `aeeeca6` |
| `ussyverse/phonaraussy` | `e18cd03` |
| `mojomast/Tchaikovskussy` | `ba91800` |
| `ussyverse/morphemaussy` | `09f8f56` |
| `ussyverse/scansionussy` | `6db8fc0` |
| `ussyverse/saccadaussy` | `25d1e86` |
| `ussyverse/raciaussy` | `f7d1bfe` |
| `ussyverse/quorumussy` | `397531d` |
| `ussyverse/circleraussy` | `dd19b24` |
