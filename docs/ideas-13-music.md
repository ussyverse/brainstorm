# Music, Live Coding, Ear Training, and Audiovisual Ideas

**Date:** 2026-09-13
**Scope:** New proposals from a music/audio/live-performance lens. These are
not additions to the current shortlist. In particular, the existing
`tonalussy` + `phyllotaxisussy` + `mojomast/shoedelussy` harmony-and-rhythm
sketchbook is treated as prior art; the ideas below use different user jobs or
different handoffs.

## Evidence and boundaries

I inspected the following checked-out repositories under
`/home/ubuntu/ussy/repos`, including the listed manifests and source files:

| Repository | Revision inspected | Relevant source evidence |
|---|---|---|
| `ussyverse/scansionussy` | `6db8fc0c60699715e579b87f4ff5614e9ec2f2e2` | [`src/lib.rs`](https://github.com/ussyverse/scansionussy/blob/HEAD/src/lib.rs), [`src/main.rs`](https://github.com/ussyverse/scansionussy/blob/HEAD/src/main.rs), `Cargo.toml`, `tests/cli.rs` |
| `ussyverse/tonalussy` | `227156f25019389d97dfbbddca9964f993e90de1` | [`src/lib.rs`](https://github.com/ussyverse/tonalussy/blob/HEAD/src/lib.rs), [`src/main.rs`](https://github.com/ussyverse/tonalussy/blob/HEAD/src/main.rs), `Cargo.toml` |
| `ussyverse/phyllotaxisussy` | `d857c0ee7c80ac0bc8d015ad4531431819b7fb35` | [`src/index.ts`](https://github.com/ussyverse/phyllotaxisussy/blob/HEAD/src/index.ts), `package.json`, tests |
| `ussyverse/foleyaussy` | `2f6ec0e13a1a6e6c5ae11c7fb1667ece1cddceb2` | [`foleya.go`](https://github.com/ussyverse/foleyaussy/blob/HEAD/foleya.go), `foleya_test.go`, `go.mod` |
| `ussyverse/chromascriptussy` | `5940bde5155a525d85d82927c6a2593c08b90ae9` | [`src/lib.rs`](https://github.com/ussyverse/chromascriptussy/blob/HEAD/src/lib.rs), `Cargo.toml` |
| `ussyverse/kuleshovussy` | `72bdd0f2d6b0df3663f9e44847f03091371b58a4` | [`src/models.ts`](https://github.com/ussyverse/kuleshovussy/blob/HEAD/src/models.ts), [`src/engine.ts`](https://github.com/ussyverse/kuleshovussy/blob/HEAD/src/engine.ts), `test/engine.test.ts`, `package.json` |
| `ussyverse/criterioussy` | `d394308b5e9db35b2b09730017a89c55799aebf3` | [`src/criterioCore.ts`](https://github.com/ussyverse/criterioussy/blob/HEAD/src/criterioCore.ts), [`src/extension.ts`](https://github.com/ussyverse/criterioussy/blob/HEAD/src/extension.ts), `package.json` |
| `mojomast/fruityboofs` | `822280f77966f2028102bc7cece24ff98104a762` | [`modules/sequencer.js`](https://github.com/mojomast/fruityboofs/blob/HEAD/modules/sequencer.js), [`modules/piano-roll.js`](https://github.com/mojomast/fruityboofs/blob/HEAD/modules/piano-roll.js), [`modules/transport.js`](https://github.com/mojomast/fruityboofs/blob/HEAD/modules/transport.js), `README.md` |
| `mojomast/shoedelussy` | `da8016812d69324bc4c39820fee1fd09b1933cc5` | [`ui/src/components/StrudelEditor.tsx`](https://github.com/mojomast/shoedelussy/blob/HEAD/ui/src/components/StrudelEditor.tsx), [`ui/src/components/RhythmGenerator.tsx`](https://github.com/mojomast/shoedelussy/blob/HEAD/ui/src/components/RhythmGenerator.tsx), [`ui/src/lib/sequencer/notation.ts`](https://github.com/mojomast/shoedelussy/blob/HEAD/ui/src/lib/sequencer/notation.ts), [`bridges/dmx-mcp/src/scenes.ts`](https://github.com/mojomast/shoedelussy/blob/HEAD/bridges/dmx-mcp/src/scenes.ts) |
| `mojomast/toaster` | `86100029185459e85bcf0b5166244767e230264d` | `README.md`, `ui/src/components/StrudelEditor.tsx`, `server/src/routes/generate.ts` |

**Existing** below means functionality present in inspected source. **Proposed**
means the adapter, UI, or workflow does not currently exist. I found no
end-to-end implementation of any combination below. No candidate was modified.
The attempted checks were `cargo test` in `scansionussy` and `tonalussy`, `go
test ./...` in `foleyaussy`, and `npm test` in `phyllotaxisussy`, `criterioussy`,
and `kuleshovussy`. Cargo and Go were unavailable; Node test dependencies or
TypeScript tools were absent, so no test result is being represented as a
passing result.

Generated rhythms, stress maps, color arcs, and scores are starting points for
human listening and revision. They are not evidence of musical superiority,
learner improvement, audience response, or universal emotional meaning.

## 1. Lyric-to-groove rehearsal strip

**Target user and pain.** A lyricist who live-codes or prototypes beats needs to
hear whether a line's spoken emphasis survives conversion into a loop. Today,
they manually count syllables and then hand-place accents in a sequencer.

**Exact repositories.** `ussyverse/scansionussy` + `ussyverse/phyllotaxisussy` +
`mojomast/shoedelussy`.

**Existing evidence.** Scansion's `analyze` returns tokens with syllables,
stress patterns, confidence, breath groups, cadence tails, and JSON output.
Phyllotaxis's `adaptToDomain('music', ...)` returns a binary `rhythm` array.
Shoedelussy's `StrudelEditor` exposes set-code/evaluate/play callbacks, while
`notation.ts` converts slot-based notes to Strudel mini-notation.

**Proposed handoff/data flow.** `LyricLine {id, text, intendedBars}` -> Scansion
JSON -> an adapter maps `S`/`u` and breath boundaries to an editable 16- or
32-slot accent lane -> optionally overlays the Phyllotaxis rhythm as a second
candidate -> emits a small `note()` or `s()` snippet into Shoedelussy. Preserve
line IDs, source stress confidence, and every manual override beside the code.

**MVP and acceptance.** Import eight lyric lines, show uncertain words instead
of hiding them, audition two accent patterns at one BPM, and export JSON plus
Strudel code. A user can change one accent without changing the source lyric,
and playback visibly identifies the current line/bar. This is a proposed local
adapter, not a claim that either pattern scans or grooves correctly.

**Why combine.** Scansion supplies a useful textual observation, Phyllotaxis
supplies a repeatable alternative, and Shoedelussy turns both into something
editable and audible. Separate reports would not expose the accent-to-loop
tradeoff.

**Risks, maturity, licensing.** Scansion uses a tiny heuristic dictionary and
vowel rules; its low-confidence estimates need review, especially for names
and sung pronunciation. Phyllotaxis is MIT, but its golden-angle rhythm is a
mathematical construction, not a validated groove generator. Shoedelussy is
AGPL-3.0; a networked derivative needs source/notice compliance. Strudel sample
loading and browser timing still need runtime verification. Scansion has no
license field in the inspected manifest, so redistribution needs clarification.

## 2. Stress-to-formant vocal accent board

**Target user and pain.** A sound designer or vocal performer wants to test
whether a spoken phrase's accents read as a synthetic vocal texture without
building a DAW session from scratch. They need a fast way to compare hard
attacks, held vowels, and rests.

**Exact repositories.** `ussyverse/scansionussy` + `ussyverse/chromascriptussy` +
`mojomast/fruityboofs`.

**Existing evidence.** Scansion exposes stress maps, breath-group overloads,
cadences, and non-generative revision prompts. Fruity Boofs is a static browser
DAW with Singer, Trio, and Vocal Chords WASM instruments; `sequencer.js` stores
step data and dispatches pitch/shape/automation, `piano-roll.js` supports
editable MIDI cells, and `transport.js` provides BPM/beat/bar callbacks.
Chromascript accepts ordered `Beat` records and emits typed warnings plus
Markdown/CSV/SVG/JSON artifacts.

**Proposed handoff/data flow.** Text plus performer-selected vowel and MIDI
range -> Scansion stress/breath JSON -> adapter creates gate/rest cells and
default Singer shape/aspiration lanes -> performer edits pitch and vowel-like
parameters in Fruity Boofs -> optional visual beat labels/colors are checked by
Chromascript. The adapter must not pretend it synthesizes the original words;
it only maps inspected stress observations to user-chosen vocal textures.

**MVP and acceptance.** A four-line phrase creates two editable vocal patterns,
with a visible breath rest and one intentional emphasis color. Export a Fruity
Boofs project plus a Chromascript report. The performer can mute one pattern,
change its pitch, and hear the difference on localhost.

**Why combine.** It joins textual rhythm, vocal timbre controls, and a visual
cue sheet around the same phrase without requiring speech synthesis.

**Risks, maturity, licensing.** Fruity Boofs has no visible repository license
file in the inspected checkout; its README says the WASM binaries came from
Paul Batchelor public demos and credits Sndkit-derived DSP. Permission,
provenance, and binary redistribution must be resolved before shipping.
Chromascript explicitly avoids universal color psychology and only checks
stated intent. Browser AudioWorklet requires HTTPS or localhost. The other
repositories' license fields are incomplete or absent; perform a legal review.

## 3. Cadence call-and-response room

**Target user and pain.** A harmony student or accompanist can name a cadence
on paper but cannot reliably identify it after a key change or unfamiliar
voicing. They need a repeatable predict-then-hear loop, not another static
theory explanation.

**Exact repositories.** `ussyverse/tonalussy` + `ussyverse/criterioussy` +
`mojomast/shoedelussy`.

**Existing evidence.** Tonal has `generate_exercise`, `grade_exercise`,
`analyze_progression`, Roman-numeral/function analysis, cadence detection, and
an Axum API. Criterio records a pre-answer judgment/confidence and a strict
grade, classifies hits/false alarms/misses, and persists local records through
the extension's `globalState`. Shoedelussy provides live Strudel playback and
project/version persistence.

**Proposed handoff/data flow.** Tonal exercise JSON `{key, progression, answer}`
-> UI asks the learner to predict cadence and confidence -> adapter renders the
progression as a deliberately small Strudel `note()` pattern -> learner hears
it, answers, and self-grades -> Criterio `AttemptRecord` stores prompt revision,
cue condition, confidence, and outcome. Keep the raw Tonal answer and the
learner's answer; do not reduce them to one mastery score.

**MVP and acceptance.** Four cadence types, two keys, and ten local attempts.
The report shows each prediction before playback, answer, confidence, and
later delayed probe. A learner can transpose one exercise and preserve its
Roman-numeral identity. Audio playback and note voicing are proposed adapters.

**Why combine.** Tonal explains the harmonic event, Shoedelussy makes it
audible, and Criterio records whether confidence predicted unaided recognition.
Any one tool alone misses one part of that loop.

**Risks, maturity, licensing.** Tonal implements only major/natural-minor
basics and fixed exercise families; its cadence detector is rule-based, not a
complete harmony model. Criterio is self-report plus self-grade, and its
statistics need at least four observations per topic; it is not a hearing test.
Shoedelussy is AGPL-3.0, and Strudel/sample availability needs a browser test.
Tonal and Criterio have no explicit license field in the inspected manifests.

## 4. Voicing contrast ear lab

**Target user and pain.** A beginner hears that two chords feel different but
cannot connect the sound to root, quality, or harmonic function. They need to
compare a small set of controlled voicings while recording uncertainty.

**Exact repositories.** `ussyverse/tonalussy` + `ussyverse/criterioussy` +
`mojomast/fruityboofs`.

**Existing evidence.** Tonal parses chord symbols, identifies diatonic,
secondary, and borrowed functions, and returns explanations. Fruity Boofs has a
four-voice Vocal Chords engine with 12 named voicings, a chord sequence piano
roll, base-note transposition, and saved project data. Criterio's core accepts
`performance` prompts and records confidence/outcome categories.

**Proposed handoff/data flow.** A Tonal progression and function label -> an
explicit adapter maps the supported subset to Fruity's named voicing/index and
MIDI base note -> browser plays A/B or progression examples -> learner chooses
function/quality before seeing the label -> Criterio stores the response and
confidence. Unsupported chord qualities must be surfaced as unsupported, not
silently approximated.

**MVP and acceptance.** Support C, Dm, G, and Am in two octaves, with tonic,
subdominant, and dominant comparisons. Show the source symbol, actual MIDI
voicing, learner answer, and raw result. After six probes, the user can replay
only misses and export a local report.

**Why combine.** Tonal supplies inspectable labels, Fruity supplies an existing
multi-voice audition surface, and Criterio distinguishes confident guesses from
successful recognition.

**Risks, maturity, licensing.** Fruity's chord list is narrower than Tonal's
parser and does not establish authentic instrument realism. Criterio does not
measure pitch accuracy or objective ear skill unless the product adds a rubric
or MIDI input. The fixed-alpha/statistical labels should remain descriptive.
Fruity's DSP provenance and missing explicit frontend license require clearance;
Tonal/Criterio licensing is likewise unresolved from manifests.

## 5. Pulse-to-light live set notebook

**Target user and pain.** A solo live coder wants a small, rehearsable lighting
cue language that follows sections and rhythmic emphasis without manually
reprogramming a light controller after every code edit.

**Exact repositories.** `ussyverse/phyllotaxisussy` +
`ussyverse/chromascriptussy` + `mojomast/shoedelussy`.

**Existing evidence.** Phyllotaxis produces music pulse arrays and SVG/JSON
artifacts. Chromascript models ordered beat colors, emphasis, continuity, and
arc warnings. Shoedelussy has `LightingProjectState` bindings from sections and
tracks to DMX groups; its DMX bridge supports simulator/OLA paths, arm/disarm,
blackout, scenes, and group writes.

**Proposed handoff/data flow.** A hand-authored set list with section IDs ->
Phyllotaxis creates a candidate pulse lane -> Chromascript validates the
creator's chosen colors and emphasis arc -> adapter binds section labels and
track names to Shoedelussy DMX groups, generating simulator-safe pulse events.
Every light action should retain section ID, group ID, color/intensity, hold,
fade, and armed/disarmed state.

**MVP and acceptance.** Three sections, one simulated universe, one pulse track,
and four hand-authored colors. A set can be played with DMX disarmed, then
armed deliberately; blackout always yields zero output. Export a cue table and
an SVG strip. Hardware is not required for the first demo.

**Why combine.** It turns abstract pattern and palette artifacts into an
auditionable, reversible stage rehearsal rather than another visual score.

**Risks, maturity, licensing.** Phyllotaxis rhythm and Chromascript arc scores
are generated planning aids, not evidence that a light pattern improves a
performance. DMX must fail safe, rate-limit, authenticate, and preserve a
manual blackout. Shoedelussy is AGPL-3.0 and its bridge scenes are compiled in,
not hot-reloaded. OLA and real fixtures require separate validation. Phyllotaxis
and Chromascript declare MIT; the adapter must retain their notices.

## 6. Spoken-word stage cue pack

**Target user and pain.** A small theater, poetry, or lecture performer needs
repeatable breath, silence, sound, and visual cues for rehearsal. Notes are often
written in separate scripts, audio lists, and lighting documents, so timing
drifts between rehearsals.

**Exact repositories.** `ussyverse/scansionussy` + `ussyverse/foleyaussy` +
`ussyverse/chromascriptussy`.

**Existing evidence.** Scansion returns breath groups, overload counts, cadence
closure, caesura/enjambment candidates, sound-device clusters, and JSON/Markdown
reports. Foleya's `MediumTheater` and `SceneRequest` support action beats,
intentional silence, live playback, cue layers, integer-second sync times,
recording notes, safety notes, cue cards, and CSV/JSON. Chromascript's `Project`
and `Beat` types support ordered visual functions and printable SVG output.

**Proposed handoff/data flow.** Script lines -> Scansion line/breath IDs ->
performer confirms cue-worthy breaths and pauses -> Foleya `SceneRequest` with
those confirmed action beats -> shared beat IDs map to Chromascript visual cues
-> one rehearsal packet with script annotations, sound cue cards, and color
strip. Do not turn Scansion's estimated stress into an automatic director's
instruction.

**MVP and acceptance.** A three-minute poem with five confirmed cue points, one
intentional silence, two safe household Foley substitutions, and four visual
beats. The performer can move one cue and regenerate all exports while keeping
the raw analysis and manual decision visible.

**Why combine.** The natural shared entity is a confirmed performance beat;
each component serves a distinct rehearsal role and produces an inspectable
artifact.

**Risks, maturity, licensing.** Foleya does not record or play audio and uses
integer seconds, so frame-accurate or live clock synchronization is new work.
Its substitutions include safety caveats that must remain visible. Scansion's
heuristics are approximate. Chromascript warns against universal color meaning.
Foleya and Scansion have no explicit license field observed; Chromascript is
MIT. Confirm rights before bundling.

## 7. Sound-postcard loop maker

**Target user and pain.** A soundwalk artist or classroom wants to turn a place
observation into a one-minute loop with intentional rests, but has no interest
in a full production suite. They need a compact cue plan and a playable sketch.

**Exact repositories.** `ussyverse/foleyaussy` + `ussyverse/phyllotaxisussy` +
`mojomast/shoedelussy`.

**Existing evidence.** Foleya explicitly defines `MediumSoundPostcard`, scene
layers, room-tone/keynote cues, material substitutions, silence budgets, and
cue cards. Phyllotaxis emits a deterministic music rhythm array and JSON/MD/SVG
artifacts. Shoedelussy has a Strudel editor, Euclidean rhythm UI, note/drum
sequencing, project persistence, and live playback.

**Proposed handoff/data flow.** Place, duration, observed materials, and a
recording note -> Foleya creates a sound-postcard cue sheet -> artist accepts or
edits three to five material beats and a silence budget -> Phyllotaxis provides
one optional pulse scaffold -> adapter generates a small Strudel loop with
named cue comments -> Shoedelussy auditions and saves the revision. Real field
recordings remain external file references; no fake audio import is implied.

**MVP and acceptance.** Create a 60-second kitchen, street, or classroom
postcard from manually entered observations. Export cue cards and one playable
loop with at least one rest. Reopening the project preserves cue labels, BPM,
code, and manual edits.

**Why combine.** Foleya protects the story of the place and recording task,
Phyllotaxis offers a reproducible timing sketch, and Shoedelussy makes revision
immediate.

**Risks, maturity, licensing.** Foleya's believability numbers are heuristics,
not perceptual measurements; it does not generate audio. The generated pulse is
not inherently more musical. Shoedelussy's AGPL-3.0 terms, remote Strudel
assets, and browser runtime need review. Foleya has a module-path mismatch in
its manifest (`github.com/mojomast/foleyaussy`) and no license field observed;
pin and audit before packaging.

## 8. Lyric-video rhythm storyboard

**Target user and pain.** An independent musician making a lyric video needs to
decide where words hold, cut, or breathe before editing footage. A lyric sheet,
video shot list, and palette plan otherwise become three incompatible timelines.

**Exact repositories.** `ussyverse/scansionussy` + `ussyverse/kuleshovussy` +
`ussyverse/chromascriptussy`.

**Existing evidence.** Scansion exposes line tokens, cadence tails, breath
groups, and line-level enjambment candidates. Kuleshov's `ClipCard` has role,
size, mood, duration, and motion fields; its engine returns rhythm bars,
continuity/montage warnings, missing roles, and CSV edit-decision rows.
Chromascript analyzes ordered visual beats and renders SVG/CSV/JSON/Markdown.

**Proposed handoff/data flow.** Lyric lines with confirmed sung durations ->
Scansion report plus human duration overrides -> one `ClipCard` per lyric phrase
or visual beat -> Kuleshov checks reaction/cutaway/closure and sequence rhythm ->
the same stable beat IDs populate Chromascript colors and emphasis -> export a
phrase timing sheet, EDL-like planning CSV, and palette strip. It does not edit
video pixels or infer a finished music video.

**MVP and acceptance.** Eight phrases and six manually described visual cards;
show one long-breath warning and one missing bridge, then resolve them by an
explicit user edit. Reordering a phrase updates all outputs without losing the
source text or manual color choice.

**Why combine.** This is a lyric-video-specific timeline join: Scansion finds
text pressure, Kuleshov checks visual sequencing, and Chromascript checks the
stated visual arc. It is distinct from the existing shot/Foley/color planner.

**Risks, maturity, licensing.** Scansion does not know sung melisma or actual
tempo, and Kuleshov operates on metadata rather than media. Kuleshov's current
screen lacks the advertised full editor, so the shared editor is proposed.
Chromascript's warnings and score are heuristics. Kuleshov and Chromascript
declare MIT; Scansion's license is not explicit in its inspected manifest.

## 9. Meter-and-harmony false-fluency drillbook

**Target user and pain.** A musician who can perform a memorized progression but
loses the pulse or harmonic function when asked to start in a new key needs
short, varied probes with confidence recorded before the answer.

**Exact repositories.** `ussyverse/tonalussy` + `ussyverse/scansionussy` +
`ussyverse/criterioussy`.

**Existing evidence.** Tonal generates seeded cadence/transposition exercises,
grades Roman-numeral answers, and transposes progressions. Scansion analyzes a
learner's written or spoken explanation for syllable/breath/cadence pressure,
with JSON output. Criterio supports `performance`, prediction/confidence,
actual answer fields, delayed cues, reports, and prompt-quality warnings.

**Proposed handoff/data flow.** Tonal exercise -> learner taps or types the
expected function/rhythm and states confidence -> an optional metronome or
instrument supplies the sound outside these three cores -> learner records the
actual result and a short explanation -> Scansion annotates the explanation's
rhythmic clarity while Criterio stores the learning attempt. The product must
label this as a practice journal, not a diagnosis of timing or musicianship.

**MVP and acceptance.** Generate 12 seeded exercises across C, Eb, and Am;
record prediction, confidence, answer, delay, and explanation; produce a report
that separates harmonic correctness from explanation rhythm. A user can inspect
the raw record and delete it locally.

**Why combine.** It joins harmonic transfer, verbalization, and confidence
calibration without stacking several incompatible forgetting models. The
explanation channel is useful even when the learner practices on a separate
instrument.

**Risks, maturity, licensing.** There is no audio engine in any of these three
repositories, so a metronome/instrument capture boundary is required. Tonal's
mode and chord vocabulary are limited. Scansion's stress estimates are not
prosodic truth. Criterio's labels become unstable with small samples and
self-grading. Tonal, Scansion, and Criterio have no clear license field in the
inspected manifests.

## 10. Vocal texture plus Foley performance kit

**Target user and pain.** A live sound artist wants a small performance piece
that combines human-scale object sounds with synthetic vocal texture, while
keeping a rehearsable cue list instead of improvising every transition.

**Exact repositories.** `ussyverse/foleyaussy` + `ussyverse/phyllotaxisussy` +
`mojomast/fruityboofs`.

**Existing evidence.** Foleya classifies action beats into footstep, cloth, prop,
ambience, and intentional-silence cues; it suggests safe household techniques,
layers, attack/decay intentions, live cue cards, and take-log templates.
Phyllotaxis supplies deterministic pulse arrays. Fruity Boofs supplies five
WASM vocal engines, dynamic tracks, piano rolls, automation lanes, mixer,
visualizer, MIDI input, and saved JSON projects.

**Proposed handoff/data flow.** A 60-second `SceneRequest` with object list and
live playback -> Foleya cue/take plan -> map confirmed cue times to an editable
Fruity pattern and use Phyllotaxis as a clearly labeled optional rest/attack
scaffold -> performer records or triggers real Foley separately while Fruity
handles synthetic vocal texture -> export cue cards and a project file. The
integration should never claim Foleya generated or analyzed the resulting
recording.

**MVP and acceptance.** One performer, three safe object cues, one room-tone
cue, one intentional silence, and two Fruity vocal tracks. A rehearsal mode
shows the next cue and keeps a take log; the artist can change BPM and save/load
without losing pattern data.

**Why combine.** Foleya provides physical action preparation, Fruity supplies a
playable synthetic counterpart, and Phyllotaxis gives an optional repeatable
clock idea. The result is a concrete rehearsal artifact rather than a blended
"sound quality" score.

**Risks, maturity, licensing.** The cues use integer seconds and are not
frame/sample accurate. Fruity Boofs' WASM provenance and unclear frontend
license are the largest distribution blocker; obtain Paul Batchelor/Sndkit
permissions and preserve attribution. Hardware recording, latency, and
monitoring are new work. Phyllotaxis is MIT; Foleya licensing remains unclear.

## Rejected ideas

### R1. Universal musicality score

**Temptation:** combine `ussyverse/scansionussy`, `ussyverse/kuleshovussy`,
`ussyverse/chromascriptussy`, and `ussyverse/criterioussy` into one score for a
song, video, or performance.

**Rejected because:** cadence-variety percentages, montage scores, color-arc
penalties, and Criterio d-prime measure different constructs with different
units and sample assumptions. Averaging them would conceal raw evidence and
invite an unsupported claim of musical or audience superiority. The components
remain useful as separate annotations, as in ideas 8 and 9, with no composite
verdict.

### R2. One-click AI songwriter from prompt to finished track

**Temptation:** combine `mojomast/toaster`, `ussyverse/tonalussy`, and
`ussyverse/scansionussy` so a natural-language prompt produces a complete song,
lyrics, harmony, and mix.

**Rejected because:** Toaster's inspected README describes LLM-generated
Strudel code, but that is not evidence of good composition, lyric prosody, or a
finished mix. Tonal's implemented vocabulary is a compact theory engine and
Scansion is a heuristic reviewer, not a generator. The proposed chain would
need a large unvalidated generation layer and would erase human authorship and
uncertainty. A constrained, reviewable handoff such as idea 1 is a credible
experiment; an autonomous songwriter is not.

## Practical selection

For the smallest source-backed experiment, start with **idea 1** if a live coder
can supply lyric lines, or **idea 6** if a performer can supply a short script.
Both have a natural human confirmation step and can demonstrate useful exports
without claiming that generated patterns are musically better. Before any
public distribution, resolve the absent license metadata for several
`ussyverse` components and the AGPL/DSP provenance obligations for the
`mojomast` components.
