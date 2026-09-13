# Creator Product Ideas: Film, Video, Photography, Design, and Writing

**Research date:** 2026-09-13

**Scope:** New combinations for film/video makers, photographers, designers,
writers, podcasters, and other independent creators. These are proposals, not
existing integrations.

## Evidence Boundary

**Exists** below means the capability is implemented in source inspected in the
checked-out repository. **Proposed** means the adapter, shared data model, UI,
or product workflow still needs to be built. **Unverified** means a repository
description, fixture, or intended contract was not established as working
behavior here.

I inspected source, manifests, and selected tests in these revisions:

| Repository | Revision | Inspected evidence |
|---|---|---|
| `ussyverse/scansionussy` | `6db8fc0` | [`src/lib.rs`](https://github.com/ussyverse/scansionussy/blob/HEAD/src/lib.rs), [`src/main.rs`](https://github.com/ussyverse/scansionussy/blob/HEAD/src/main.rs), [`tests/cli.rs`](https://github.com/ussyverse/scansionussy/blob/HEAD/tests/cli.rs), `Cargo.toml` |
| `ussyverse/olfactoussy` | `496619f` | [`src/types.ts`](https://github.com/ussyverse/olfactoussy/blob/HEAD/src/types.ts), [`src/engine.ts`](https://github.com/ussyverse/olfactoussy/blob/HEAD/src/engine.ts), [`tests/engine.test.ts`](https://github.com/ussyverse/olfactoussy/blob/HEAD/tests/engine.test.ts), `package.json` |
| `ussyverse/phyllotaxisussy` | `d857c0e` | [`src/index.ts`](https://github.com/ussyverse/phyllotaxisussy/blob/HEAD/src/index.ts), [`tests/index.test.ts`](https://github.com/ussyverse/phyllotaxisussy/blob/HEAD/tests/index.test.ts), `package.json` |
| `ussyverse/obscuraussy` | `3c91b65` | [`obscura/generator.py`](https://github.com/ussyverse/obscuraussy/blob/HEAD/obscura/generator.py), [`obscura/config.py`](https://github.com/ussyverse/obscuraussy/blob/HEAD/obscura/config.py), [`obscura/reports.py`](https://github.com/ussyverse/obscuraussy/blob/HEAD/obscura/reports.py), [`tests/test_action.py`](https://github.com/ussyverse/obscuraussy/blob/HEAD/tests/test_action.py) |
| `ussyverse/opticussy` | `7bd1350` | [`src/lib.rs`](https://github.com/ussyverse/opticussy/blob/HEAD/src/lib.rs), [`src/main.rs`](https://github.com/ussyverse/opticussy/blob/HEAD/src/main.rs), [`tests/cli.rs`](https://github.com/ussyverse/opticussy/blob/HEAD/tests/cli.rs), `Cargo.toml` |
| `ussyverse/luminaraussy` | `9da0321` | [`src/luminara_core.h`](https://github.com/ussyverse/luminaraussy/blob/HEAD/src/luminara_core.h), [`src/luminara_core.c`](https://github.com/ussyverse/luminaraussy/blob/HEAD/src/luminara_core.c), [`src-ts/extensionCore.ts`](https://github.com/ussyverse/luminaraussy/blob/HEAD/src-ts/extensionCore.ts), `Makefile` |
| `ussyverse/reverbaussy` | `c914aab` | [`src/reverba/engine.py`](https://github.com/ussyverse/reverbaussy/blob/HEAD/src/reverba/engine.py), [`tests/test_engine.py`](https://github.com/ussyverse/reverbaussy/blob/HEAD/tests/test_engine.py), `pyproject.toml` |
| `ussyverse/decibellaussy` | `e4e7bff` | [`python/decibella/core.py`](https://github.com/ussyverse/decibellaussy/blob/HEAD/python/decibella/core.py), [`tests/test_core.py`](https://github.com/ussyverse/decibellaussy/blob/HEAD/tests/test_core.py), `package.json`, `pyproject.toml` |
| `ussyverse/phonaraussy` | `e18cd03` | [`src/phonara/engine.py`](https://github.com/ussyverse/phonaraussy/blob/HEAD/src/phonara/engine.py), [`tests/test_engine.py`](https://github.com/ussyverse/phonaraussy/blob/HEAD/tests/test_engine.py), `pyproject.toml` |
| `ussyverse/marangoniussy` | `82f5ebe` | [`src/marangoni/engine.py`](https://github.com/ussyverse/marangoniussy/blob/HEAD/src/marangoni/engine.py), [`src/marangoni/experiments.py`](https://github.com/ussyverse/marangoniussy/blob/HEAD/src/marangoni/experiments.py), [`src/marangoni/storage.py`](https://github.com/ussyverse/marangoniussy/blob/HEAD/src/marangoni/storage.py), `pyproject.toml` |
| `ussyverse/chromascriptussy` | `5940bde` | [`src/lib.rs`](https://github.com/ussyverse/chromascriptussy/blob/HEAD/src/lib.rs), [`src/main.rs`](https://github.com/ussyverse/chromascriptussy/blob/HEAD/src/main.rs), `Cargo.toml` |
| `ussyverse/kuleshovussy` | `72bdd0f` | [`src/models.ts`](https://github.com/ussyverse/kuleshovussy/blob/HEAD/src/models.ts), [`src/engine.ts`](https://github.com/ussyverse/kuleshovussy/blob/HEAD/src/engine.ts), [`src/main.ts`](https://github.com/ussyverse/kuleshovussy/blob/HEAD/src/main.ts), `package.json` |
| `ussyverse/foleyaussy` | `2f6ec0e` | [`foleya.go`](https://github.com/ussyverse/foleyaussy/blob/HEAD/foleya.go), [`foleya_test.go`](https://github.com/ussyverse/foleyaussy/blob/HEAD/foleya_test.go), `go.mod` |
| `mojomast/mediageckussy` | `14a9073` | [`src/core/types.ts`](https://github.com/mojomast/mediageckussy/blob/HEAD/src/core/types.ts), [`src/core/schema.ts`](https://github.com/mojomast/mediageckussy/blob/HEAD/src/core/schema.ts), [`src/core/generator.ts`](https://github.com/mojomast/mediageckussy/blob/HEAD/src/core/generator.ts), [`src/formats/film/pack.ts`](https://github.com/mojomast/mediageckussy/blob/HEAD/src/formats/film/pack.ts), [`src/formats/podcast/pack.ts`](https://github.com/mojomast/mediageckussy/blob/HEAD/src/formats/podcast/pack.ts), `package.json` |
| `mojomast/designussy` | `fc3a2af` | [`generators/base_generator.py`](https://github.com/mojomast/designussy/blob/HEAD/generators/base_generator.py), [`generators/factory.py`](https://github.com/mojomast/designussy/blob/HEAD/generators/factory.py), [`generators/type_batch_generator.py`](https://github.com/mojomast/designussy/blob/HEAD/generators/type_batch_generator.py), [`upgraded_asset_system/asset_dsl.py`](https://github.com/mojomast/designussy/blob/HEAD/upgraded_asset_system/asset_dsl.py), `pyproject.toml` |
| `mojomast/bananagen` | `4c9555f` | [`bananagen/core.py`](https://github.com/mojomast/bananagen/blob/HEAD/bananagen/core.py), [`bananagen/scanner.py`](https://github.com/mojomast/bananagen/blob/HEAD/bananagen/scanner.py), [`bananagen/batch_runner.py`](https://github.com/mojomast/bananagen/blob/HEAD/bananagen/batch_runner.py), [`tests/test_core.py`](https://github.com/mojomast/bananagen/blob/HEAD/tests/test_core.py), `pyproject.toml` |
| `mojomast/ArtistSiteussy` | `00f29f3` | [`lib/types.ts`](https://github.com/mojomast/ArtistSiteussy/blob/HEAD/lib/types.ts), [`lib/dataLoader.ts`](https://github.com/mojomast/ArtistSiteussy/blob/HEAD/lib/dataLoader.ts), [`pages/api/portfolio.ts`](https://github.com/mojomast/ArtistSiteussy/blob/HEAD/pages/api/portfolio.ts), [`app/api/admin/export/route.ts`](https://github.com/mojomast/ArtistSiteussy/blob/HEAD/app/api/admin/export/route.ts), `package.json` |
| `mojomast/arrhivescrape` | `afffec1` | [`archive_recovery/pipeline/inventory.py`](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/pipeline/inventory.py), [`archive_recovery/pipeline/selection.py`](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/pipeline/selection.py), [`archive_recovery/pipeline/normalization.py`](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/pipeline/normalization.py), [`archive_recovery/pipeline/validation.py`](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/pipeline/validation.py), `pyproject.toml` |
| `mojomast/shoedelussy` | `da80168` | [`ui/src/types/project.ts`](https://github.com/mojomast/shoedelussy/blob/HEAD/ui/src/types/project.ts), [`ui/src/stores/projectStore.ts`](https://github.com/mojomast/shoedelussy/blob/HEAD/ui/src/stores/projectStore.ts), [`ui/src/components/StrudelEditor.tsx`](https://github.com/mojomast/shoedelussy/blob/HEAD/ui/src/components/StrudelEditor.tsx), [`ui/src/components/RhythmGenerator.tsx`](https://github.com/mojomast/shoedelussy/blob/HEAD/ui/src/components/RhythmGenerator.tsx), `ui/package.json` |

The revision command actually run was `git -C <repo> rev-parse --short HEAD`
for the repositories above. No candidate repository was modified. No build, install, or runtime
test was run in this pass; repository test files are evidence of intended
contracts, not claims that those tests pass here.

## Existing Source Evidence

These are the concrete primitives available for reuse, separate from the
products proposed below.

- **Narrative rhythm:** `scansionussy` has `analyze`, stress/syllable tokens,
  breath groups, cadence data, caesura/enjambment candidates, sound-device
  detection, revision prompts, and text/Markdown/JSON rendering. Its CLI
  accepts text, files, or stdin.
- **Sensory writing:** `olfactoussy` validates top/middle/base note profiles and
  returns synesthetic prompt expansions, tone checks, persistence maps, fatigue
  warnings, and memory triggers. It uses an offline note database.
- **Photo composition practice:** `obscuraussy` generates seeded constraint
  decks, timeboxes, capture limits, walk plans, reflection grids, and printable
  HTML cards from a small YAML/JSON config.
- **Photo-folder curation:** `opticussy` scans image files and emits signals,
  context/date clusters, keeper candidates, aperture recommendations, and JSON
  or text reports. Its `byte_optics` values are proxies from file bytes, not
  decoded-image computer vision.
- **Composition patterns:** `phyllotaxisussy` generates deterministic point
  fields and exports SVG/JSON/Markdown. Its `photo` domain produces focal zones
  and instructions; it does not compose actual image pixels.
- **Small-room capture planning:** `luminaraussy` has a C input/plan model for
  capture type, subject, mood, consent, room sources, glare, color mixing,
  separation, and hard route-away gates, with Markdown/JSON output.
- **Room echo planning:** `reverbaussy` models room dimensions, surfaces,
  activities, symptoms, estimated RT60, reflection paths, noise-vs-echo
  warnings, and reversible treatment cards.
- **Noise exposure planning:** `decibellaussy` models supplied or preset dBA
  exposures, duration, protection fit/worn fraction, daily dose, impulse
  caution, symptom boundaries, and conservative recommendations. It explicitly
  is not a calibrated meter or medical device.
- **Voice-load pacing:** `phonaraussy` models timed talk blocks, phonation
  minutes, audience/noise/amplification factors, recovery gaps, pacing changes,
  and stop/escalate banners. It is not diagnosis or voice measurement.
- **Surface-effect experiments:** `marangoniussy` forecasts acrylic/resin/ink
  recipe behavior, stores recipes/forecasts in SQLite, and creates one-variable
  experiment cards for viscosity, surface tension, and thickness.
- **Visual beat analysis:** `chromascriptussy` analyzes supplied beat colors and
  visual intent, then emits warnings plus Markdown, CSV, SVG, and JSON. It does
  not extract a palette from a video or photograph.
- **Metadata edit planning:** `kuleshovussy` has clip cards and deterministic
  montage checks, missing-shot prompts, rhythm reporting, and CSV output. The
  checked UI is a demo-oriented surface and does not ingest video pixels.
- **Foley preparation:** `foleyaussy` has Go scene requests, action-to-cue
  planning, household-object substitutions, room tone, cue/checklist/take-log
  exports, and integer-second sync suggestions. It does not record or render
  audio.
- **Canon-first package generation:** `mediageckussy` has Zod-validated canon
  fields, stable film and podcast format packs, template generation, manifests,
  protected regions, validation reports, iteration history, asset-provider
  hooks, and export/share surfaces. The cross-repository adapters proposed here
  are not present in its source.
- **Procedural asset generation:** `designussy` has PIL/NumPy generators, a
  registry/factory, type-aware batch generation, variation seeds, and a JSON DSL
  with background, ring, splatter, spiral, and starfield primitives.
- **Provider-backed image replacement:** `bananagen` has placeholder generation,
  prompt extraction around `__placeholder__` markers, provider adapters, async
  batch jobs, rate limiting, and generated-file replacement behavior. It needs
  an external provider for non-placeholder image generation.
- **Artist site shell:** `ArtistSiteussy` defines bilingual portfolio, events,
  commissions, shop, and site metadata JSON shapes, static data loaders, an
  admin export ZIP, and a Next.js UI. Its portfolio POST route explicitly
  returns 501, so durable portfolio editing is not an existing capability.
- **Archive recovery:** `arrhivescrape` implements CDX inventory, capture
  selection/canonicalization, dependency recovery, URL rewriting, Wayback
  artifact removal, staging, manifests, and reference validation. It still
  depends on archive availability and careful rights review.
- **Live music surface:** `shoedelussy` has a typed project state with code,
  sections, versions, chat diffs, BPM/key, and lighting bindings. Its editor
  evaluates Strudel in the browser, exposes cycle/track callbacks, and its
  rhythm generator emits editable Euclidean drum code. This is not evidence of
  any proposed text-to-music or visual mapping.

## Proposed Products

### 1. Scripted Sensory Cutbook

**Target user and pain:** An indie fiction podcaster, audio-drama writer, or
short-film writer can draft scenes but has difficulty making spoken rhythm and
sensory motifs survive into the production handoff. Voice direction, smell
motifs, and revision notes live in separate documents.

**Product promise:** Turn a scene canon into a cited, revision-ready cutbook
that keeps performance rhythm and sensory motifs attached to the same scene.

**Exact repositories:** `mojomast/mediageckussy` + `ussyverse/scansionussy` +
`ussyverse/olfactoussy`.

**Existing evidence:** **Exists:** MediaGeck has stable film/podcast packs and
canon fields for episodes, scenes, characters, tone, themes, and locations;
Scansion has structured rhythm analysis and JSON rendering; Olfacto has
validated scene profiles and sensory expansions. **Proposed:** none of the
three currently joins a scene ID to the other reports.

**Proposed handoff/data flow:** Author a MediaGeck canon with explicit scene or
episode IDs and a sidecar `sceneId -> text, scentProfile`. Run Scansion on each
spoken-text field and Olfacto on each scent profile. Store raw reports beside
the sidecar, then render a new scene cutbook with breath/cadence notes, sensory
prompt lines, and unresolved confidence markers. Feed only approved, public
fields into MediaGeck's existing podcast or film templates.

**MVP:** Three scenes from a five-minute audio drama, with one deliberate
breath-overload revision and one recurring scent family. Export a Markdown
cutbook and a MediaGeck podcast package; no transcription or audio generation.

**Acceptance criteria:** Each scene in the export links to its source text,
preserves raw Scansion and Olfacto results, labels heuristic confidence, and
passes unchanged public fields into the package.

**Value of combination:** MediaGeck makes the result a reusable production
artifact, Scansion makes dialogue performable by ear, and Olfacto keeps sensory
motifs deliberate across scenes. Separate reports would not preserve the scene
identity or package state.

**Rejected adjacent components:** `ussyverse/phonaraussy` is deferred because
the first slice edits written scenes, not a performer's timed vocal workload.

**Risks and maturity:** Scansion syllable/stress estimation is heuristic and
Olfacto's tone and memory confidence are invented writing aids, not reader
research. The scene adapter, template, and stable-ID persistence are new work.
MediaGeck's AI hydration and image providers add optional external dependencies.

### 2. Walk, Select, Compose

**Target user and pain:** A photography educator, club, or deliberate amateur
photographer wants a constrained photo walk and a useful edit afterward, but
gets either too many near-duplicates or an unstructured pile of images.

**Product promise:** Turn a bounded photo walk into a provenance-preserving
selection and composition packet without deleting the original images.

**Exact repositories:** `ussyverse/obscuraussy` + `ussyverse/opticussy` +
`ussyverse/phyllotaxisussy`.

**Existing evidence:** **Exists:** Obscura emits seeded camera-obscura prompt
cards, quotas, timing, and reflection grids; Optic scans local image files and
reports clusters, keepers, and candidates; Phyllotaxis emits photo focal zones
and SVG/Markdown/JSON artifacts. **Proposed:** a capture-card tag and a real
contact-sheet compositor.

**Proposed handoff/data flow:** Create an Obscura session with card IDs. The
photographer records `cardId -> filename` in a small sidecar while walking.
After the walk, Optic scans the folder and retains its raw signals and keeper
recommendations. The product groups selected frames by prompt, calls
Phyllotaxis with the chosen count, and uses its zones as placement instructions
for a new HTML/SVG contact-sheet renderer. Never delete originals automatically.

**MVP:** One 30-minute walk, six prompt cards, 20 local JPEGs, manual card tags,
and a printable report showing prompt, keeper candidates, reflection answer,
and a generated focal-map contact sheet.

**Acceptance criteria:** Every selected frame links to its original filename and
prompt card, uncertain keeper signals remain review-only, and the report keeps
the raw scan alongside the proposed focal layout.

**Value of combination:** The walk limits capture before the folder becomes
unmanageable, Optic reduces selection burden, and Phyllotaxis turns a selected
set into an editable visual sequence instead of another flat list.

**Rejected adjacent components:** `mojomast/bananagen` is excluded because
provider-generated imagery would distract from the first slice's real-photo
selection and add rights and credential dependencies.

**Risks and maturity:** Optic uses filename/date/context tokens and byte-level
brightness/chroma/sharpness proxies; it is not image understanding, face
selection, or reliable photographic sharpness measurement. Phyllotaxis supplies
coordinates, not a compositor. The sidecar and human approval step are
mandatory.

### 3. Bedroom Studio Preflight

**Target user and pain:** A solo streamer, interviewer, teacher, or home
videographer repeatedly records muddy lighting and echo, then discovers that
long sessions or loud monitoring make the setup uncomfortable. They need a
reversible setup card, not a shopping list or a smart-home controller.

**Product promise:** Produce one reversible home-studio preflight card covering
visual setup, room echo, and planned noise exposure without claiming to measure
the room or diagnose the performer.

**Exact repositories:** `ussyverse/luminaraussy` + `ussyverse/reverbaussy` +
`ussyverse/decibellaussy`.

**Existing evidence:** **Exists:** Luminara has consent and power/heat/trip/eye
comfort gates plus key/fill/rim recommendations; Reverba has room/ surface
inputs, RT60 proxy, reflection paths, and renter-safe treatment cards;
Decibella has supplied-level dose arithmetic, protection derating, impulse
caution, and symptom boundaries. **Proposed:** one shared session schema and
combined preflight card.

**Proposed handoff/data flow:** Capture one JSON room/session record containing
subject consent, room dimensions/surfaces, intended activity, light sources,
and planned noise events. Run the three deterministic cores independently and
retain each raw report. Join by `sessionId`, not by numerical score, and render
three sections: safe lighting adjustments, room placement/treatment, and a
quiet-break/noise plan.

**MVP:** A 20-minute family interview in a bedroom or living room. The user
enters one room inventory and two planned noise events, then receives one
Markdown setup card and repeats the test shot/room placement manually.

**Acceptance criteria:** Missing measurements remain visible, each recommendation
links to its component report, safety gates can block the plan, and no combined
"studio quality" score is emitted.

**Value of combination:** It catches three common causes of a bad recording at
the planning boundary: visual shape, reverberant speech, and accumulated noise
exposure. Each component remains inspectable instead of becoming an opaque
"studio quality" score.

**Rejected adjacent components:** `ussyverse/phonaraussy` is left out because
voice-load pacing belongs after the room and exposure preflight, not inside its
initial physical setup decision.

**Risks and maturity:** None of the components measures camera image quality,
microphone frequency response, or actual sound level. Decibella is not medical
or occupational compliance advice; Luminara is not electrical advice; Reverba
uses qualitative absorption estimates. C and Python wrappers plus input
validation are integration work.

### 4. Palette-Locked Asset Board

**Target user and pain:** A zine designer, tabletop publisher, or small video
team needs a coherent set of covers, icons, and background assets, but AI image
iterations drift away from the chosen palette and visual arc.

**Product promise:** Let a creator prove a palette-locked asset set locally
before opting into provider-generated images, with every asset's seed and
approval state recorded.

**Exact repositories:** `mojomast/designussy` + `mojomast/bananagen` +
`ussyverse/phyllotaxisussy` + `ussyverse/chromascriptussy`.

**Existing evidence:** **Exists:** Designussy has reusable PIL generators,
palette application, seeded generators, a type factory, batch variation code,
and a JSON drawing DSL. Bananagen has placeholders, nearby prompt extraction,
provider adapters, rate-limited batch jobs, and caching-related code.
Phyllotaxis has deterministic color/photo patterns; ChromaScript validates
supplied beat palettes and exports SVG/CSV/JSON. **Proposed:** palette and
asset-manifest handoff.

**Proposed handoff/data flow:** Start with a `projectId`, ordered beat list,
approved palette, and asset roles. ChromaScript checks the beat palette;
Phyllotaxis generates focal/color placement hints; Designussy renders local
deterministic base assets from DSL specs; Bananagen optionally turns explicit
prompt-marked slots into provider images. Record role, prompt, seed, provider,
palette, and approval state in a new manifest.

**MVP:** A nine-panel zine or three-video thumbnail board using only
Designussy plus placeholders first, then one opt-in provider-generated asset.
Show a rejected palette jump and a manually approved replacement.

**Acceptance criteria:** The manifest records each asset role, palette, prompt,
seed, and approval state; a palette mismatch is reviewable; and provider
failure leaves the deterministic placeholder intact.

**Value of combination:** It separates deterministic art direction from optional
image generation. The designer can prove the layout and palette before paying
for or trusting a provider batch.

**Rejected adjacent components:** `mojomast/ArtistSiteussy` is deferred because
publishing portfolio metadata is a later delivery concern and would expand the
asset-board MVP beyond local review.

**Risks and maturity:** Designussy has a large, older Python/PIL/NumPy surface
and several generator paths; Bananagen requires provider credentials for real
images. ChromaScript checks stated colors, not audience response or extracted
image palettes. Existing placeholder replacement writes paths into source and
needs sandboxing, escaping, and an approval UI before production use.

### 5. Canon-to-Campaign Launch Pack

**Target user and pain:** A self-producing filmmaker or fiction podcast team
has a coherent project but spends launch week rewriting the logline, press
copy, website text, lookbook notes, and social image briefs inconsistently.

**Product promise:** Convert an approved film or podcast canon into a consistent,
reviewable launch folder with explicit visual-beat provenance.

**Exact repositories:** `mojomast/mediageckussy` + `ussyverse/chromascriptussy` +
`ussyverse/phyllotaxisussy`.

**Existing evidence:** **Exists:** MediaGeck's film and podcast packs generate
press, website, story, and administrative files from a fingerprinted canon;
ChromaScript creates beat-level visual arc reports and printable SVG strips;
Phyllotaxis creates photo collage focal zones and color-walk artifacts.
**Proposed:** a launch-specific mapper from canon entities to visual beats.

**Proposed handoff/data flow:** Take approved MediaGeck `CanonProject` fields,
episode/structure order, motifs, and supplied palette references. Generate the
ordinary MediaGeck package. In parallel, map each approved public beat to a
ChromaScript beat and a Phyllotaxis photo/cover request. Emit a launch folder
containing the press/site package, visual strip, image-placement briefs, and a
manifest showing which canon fields fed each artifact.

**MVP:** A three-episode podcast or short-film launch with six visual beats,
one supplied palette, and Markdown/HTML outputs only. No social-platform API
publishing.

**Acceptance criteria:** Every generated artifact links to the canon fields and
visual beat that produced it, private fields stay out of public outputs, and the
folder remains usable without a publishing API.

**Value of combination:** MediaGeck solves canon drift, ChromaScript exposes a
flat or premature visual arc, and Phyllotaxis gives a concrete composition
brief. The result is an outward-facing launch handoff rather than three
unconnected planning reports.

**Rejected adjacent components:** `mojomast/bananagen` is deferred because
provider-backed image generation is not needed to validate canon-to-brief
consistency and would add cost and rights review.

**Risks and maturity:** MediaGeck does not infer colors from canon and
Phyllotaxis does not place real image pixels. Public/private visibility must be
preserved when projecting canon fields. All mapping, asset review, and any
publisher connectors are proposed.

### 6. Spoken-Word Live Set

**Target user and pain:** A poet, spoken-word performer, or livestream host can
write a piece but struggles to turn its cadence into a repeatable backing
pattern and a sustainable performance plan.

**Product promise:** Turn a reviewed spoken-word script into an editable rhythm
audition and a paced set card, without pretending to evaluate vocal health.

**Exact repositories:** `ussyverse/scansionussy` + `ussyverse/phonaraussy` +
`ussyverse/phyllotaxisussy` + `mojomast/shoedelussy`.

**Existing evidence:** **Exists:** Scansion emits stress, breath, cadence, and
sound-device data; Phonara models timed voice blocks and recovery gaps;
Phyllotaxis maps requests to music rhythms and visual zones; Shoedel has a
browser Strudel editor, playback/evaluation callbacks, section markers,
versioning, and an editable rhythm generator. **Proposed:** mappings from text
analysis to code and a performance cue surface.

**Proposed handoff/data flow:** Analyze the poem or script with Scansion. The
performer reviews and assigns section labels and approximate pulse counts.
Generate a Phyllotaxis rhythm suggestion, convert it to a small, explicitly
voiced Strudel snippet, and inject it into Shoedel for audition. Separately,
enter the actual timed talk blocks into Phonara and attach its pacing notes to
the set list. Store text, code, source analysis, and accepted revisions under a
new set ID.

**MVP:** One five-minute piece with three sections, one generated drum pattern,
one manual edit in Shoedel, and a printable set card with planned pauses. Do
not auto-score the performer's voice or claim health improvement.

**Acceptance criteria:** The set preserves source analysis, generated and
accepted code versions, manual pulse assignments, and Phonara pacing notes; the
performer can reject a pattern without losing the prior version.

**Value of combination:** Scansion supplies a textual reason for rhythmic
changes, Phyllotaxis supplies an editable pattern seed, Shoedel makes the idea
audible, and Phonara turns performance pacing into an explicit plan.

**Rejected adjacent components:** `ussyverse/foleyaussy` is excluded because
Foley cue planning serves recorded scene effects, not the backing-pattern and
vocal-pacing decision in this live-set MVP.

**Risks and maturity:** Scansion is heuristic and Phyllotaxis rhythms are
mathematical patterns, not musical-quality judgments. Phonara is conservative
pacing guidance, not diagnosis. Shoedel has browser/audio/sample-pack
 dependencies. Chord voicing, pulse mapping, and runtime audio verification
 remain open.

### 7. Pour, Document, Sell

**Target user and pain:** An acrylic-pour, marbling, or resin artist wants to
repeat a successful surface effect and present the resulting work for sale,
but recipe notes, visual intent, experiments, and portfolio metadata diverge.

**Product promise:** Carry a tested surface recipe into a bilingual portfolio
and shop draft while preserving which observations were forecast versus made.

**Exact repositories:** `ussyverse/marangoniussy` + `ussyverse/chromascriptussy` +
`mojomast/ArtistSiteussy`.

**Existing evidence:** **Exists:** Marangoni forecasts cell/lacing, feathering,
mud, crack, crawling, and density risks, stores recipes/forecasts, and plans
one-variable test tiles. ChromaScript checks an explicitly supplied palette
arc. ArtistSite defines portfolio, collection, store, and bilingual metadata
shapes and exports its public folder. **Proposed:** a recipe/artwork record
and completion handoff.

**Proposed handoff/data flow:** Save a recipe and forecast under a stable
`artworkId`; derive a human-supplied ChromaScript beat list from intended
colors, not from the forecast. After the artist performs a control and one
variant, attach photos, actual observations, and the selected forecast to the
artwork record. Generate an import projection for `portfolio.json` and
`store.json`, with a human approval step before publication.

**MVP:** Three recipes, three experiment cards, one completed test tile, and a
single bilingual portfolio collection generated from manually entered artwork
metadata.

**Acceptance criteria:** Each public draft links to a recipe and completed tile,
forecast and observed values remain separate, and publication requires explicit
human approval.

**Value of combination:** Marangoni closes the experiment loop, ChromaScript
keeps the intended visual sequence explicit, and ArtistSite turns the finished
work into a public artifact and sales surface.

**Rejected adjacent components:** `ussyverse/olfactoussy` is omitted because
sensory description would enrich copy but does not improve recipe repeatability
or the first portfolio handoff.

**Risks and maturity:** Forecast confidence is a heuristic and the tool does
not inspect the finished image. ChromaScript cannot validate actual paint
color. ArtistSite's portfolio POST endpoint is explicitly TODO/501 and its
static JSON model needs an import adapter; no direct integration exists.

### 8. Dead Portfolio Recovery Desk

**Target user and pain:** An artist or photographer has an old portfolio that
vanished or partially broke, and wants to recover the evidence, choose what is
still worth showing, and relaunch without manually rebuilding every route.

**Product promise:** Recover a reviewable portfolio slice, show where each item
came from, and prepare a rights-aware relaunch without silently publishing it.

**Exact repositories:** `mojomast/arrhivescrape` + `ussyverse/opticussy` +
`ussyverse/phyllotaxisussy` + `mojomast/ArtistSiteussy`.

**Existing evidence:** **Exists:** ArrhiveScrape inventories Wayback captures,
selects/canonicalizes routes, recovers dependencies, rewrites first-party
links, builds a staged site, and validates missing references. Optic reports
photo clusters and keeper candidates. Phyllotaxis emits photo-collage zones.
ArtistSite has portfolio/collection/store JSON shapes and an export route.
**Proposed:** a rights-aware migration and review interface.

**Proposed handoff/data flow:** Run ArrhiveScrape for an explicitly scoped old
domain/path and retain raw capture URLs, hashes, and unresolved references.
Extract recovered image candidates into a review folder; run Optic without
deleting anything. A human selects keepers and supplies titles/years/mediums.
Use Phyllotaxis for a proposed collection landing layout, then write an
ArtistSite import projection and a migration report linking every public item
to its recovered source.

**MVP:** One recovered portfolio path with ten images, one duplicate cluster,
one missing asset, and a local ArtistSite preview. Include a manual rights and
privacy checklist before publishing.

**Acceptance criteria:** Every recovered item retains capture and source links,
duplicates and missing assets are visible, uncertain rights block publication,
and no original file is deleted or overwritten.

**Value of combination:** Recovery, curation, composition, and relaunch are
one real workflow. Each stage preserves provenance instead of silently turning
an archived file into a new portfolio fact.

**Rejected adjacent components:** `ussyverse/marangoniussy` is excluded because
surface-recipe experiments do not help recover portfolio evidence and would
confuse archival provenance with new artwork production.

**Risks and maturity:** CDX availability, archive capture quality, copyright,
privacy, and third-party asset rights are material blockers. ArrhiveScrape's
staged output still needs review; Optic's signals are file/name/byte proxies;
Phyllotaxis is only a placement brief. ArtistSite persistence is incomplete,
so direct automated publishing is not proposed for the MVP.

### 9. Foley Room Session Planner

**Target user and pain:** A home podcaster or small video team plans a Foley
session in a reflective room, underestimates setup noise, and loses track of
which takes and room-tone cues still need recording.

**Product promise:** Turn a scene and room inventory into an ordered Foley
session packet that protects room tone, take tracking, and quiet breaks.

**Exact repositories:** `ussyverse/foleyaussy` + `ussyverse/reverbaussy` +
`ussyverse/decibellaussy`.

**Existing evidence:** **Exists:** Foleya has scene requests, action cue
families, household substitutions, room tone, masking/density warnings,
checklists, and take-log exports. Reverba has reflection-path and placement
cards. Decibella has daily exposure arithmetic and impulse/symptom boundaries.
**Proposed:** a session scheduler that keeps each component's raw output.

**Proposed handoff/data flow:** Enter a scene list with actual action
descriptions and approximate local cue times, a room inventory, and planned
noise events. Run Foleya for cues/checklist/take log, Reverba for source and
listener placement, and Decibella for the day's supplied exposure estimates.
Join by `sessionId` and `cueId`, then render an ordered room setup, recording,
quiet-break, and take-confirmation card.

**MVP:** One two-minute scene with footsteps, cloth, a prop impact, room tone,
and two takes. Use manual timestamps and a user-entered noise preset; do not
record audio or control hardware.

**Acceptance criteria:** Every cue has a checklist and take-log destination,
room placement and noise assumptions are shown, manual timestamps round-trip,
and the packet never claims to record or meter audio.

**Value of combination:** Foleya answers what to record, Reverba answers where
to record it, and Decibella answers how to avoid stacking loud activities. A
Foley checklist alone does not reveal that the room or day plan undermines it.

**Rejected adjacent components:** `ussyverse/luminaraussy` is deferred because
lighting preflight is useful for filmed Foley but not necessary to validate the
first audio-session workflow.

**Risks and maturity:** Foleya's action classification cannot infer timing from
an object list and its sync values are integer-second suggestions. Reverba is a
qualitative room model, and Decibella is not a sound meter or medical tool.
Cross-language wrappers, cue IDs, and the scheduler are new work.

### 10. Transcript-to-Vertical Cut Board

**Target user and pain:** A short-form creator has a transcript and a phone
folder full of clips but spends too long deciding where a spoken hook should
land, what pickup shot is missing, and how to make a thumbnail that belongs to
the same story.

**Product promise:** Turn manually aligned transcript and clip metadata into a
reviewable vertical cut board with pacing, pickup, and thumbnail handoffs.

**Exact repositories:** `ussyverse/kuleshovussy` + `ussyverse/scansionussy` +
`ussyverse/phyllotaxisussy` + `mojomast/bananagen`.

**Existing evidence:** **Exists:** Kuleshov has clip-card metadata, montage
checks, rhythm reports, missing-shot checks, and CSV export. Scansion can mark
breath/cadence pressure and revision prompts from transcript text. Phyllotaxis
can generate photo focal zones and SVG/JSON/Markdown artifacts. Bananagen can
scan prompt-marked placeholders, create local placeholders, and run provider
or batch jobs. **Proposed:** transcript-to-clip alignment and thumbnail
handoff.

**Proposed handoff/data flow:** The creator enters clip IDs, manually supplied
start/end times, shot roles, and transcript segments. Run Scansion on each
segment and Kuleshov on the clip-card sequence. Preserve both reports and let
the creator accept a hook, pickup, or reaction-shot action. Send accepted
thumbnail roles to Phyllotaxis for focal zones and to Bananagen only for
explicitly prompted image slots. Export a CSV cut board, caption timing sheet,
and thumbnail review folder.

**MVP:** One 60-second tutorial with six manually described clips, one missing
reaction/detail shot, three caption segments, and two placeholder thumbnails.
The final edit remains manual in CapCut, iMovie, or another editor.

**Acceptance criteria:** All timecodes and clip roles are user-supplied and
editable, raw analysis remains attached, missing shots are explicit, and the
export contains a CSV cut board plus reviewable thumbnail placeholders.

**Value of combination:** Scansion connects words to pacing, Kuleshov connects
metadata to shot order, Phyllotaxis makes thumbnail composition concrete, and
Bananagen removes asset-placeholder friction. It produces a handoff a creator
can use immediately without pretending to be a video-understanding model.

**Rejected adjacent components:** `mojomast/mediageckussy` is excluded because
the first slice is a single short edit handoff, not a canon-managed film or
podcast release package.

**Risks and maturity:** Kuleshov does not ingest video pixels or automatically
align transcript timecodes; Scansion has low confidence for many words;
Phyllotaxis does not compose images; Bananagen's provider path needs credentials
and its source replacement behavior needs sandboxing. Manual timecodes and
human approval are part of the product, not temporary claims of automation.

## Rejected Ideas

### R1. Automatic Synesthetic Audience Optimizer

**Temptation:** Combine `ussyverse/opticussy`,
`ussyverse/chromascriptussy`, `ussyverse/tonalussy`, and
`mojomast/bananagen` to inspect a video/photo, infer its emotional color and
music response, then generate a better thumbnail or soundtrack.

**Why rejected:** Optic's image signals come from filenames and sampled bytes,
not semantic image or video understanding. ChromaScript checks colors supplied
by the author, and Tonal handles symbolic harmony rather than audience
response. Bananagen can generate provider images but supplies no validated
cross-modal objective. The combination would turn several creative heuristics
into an unsupported optimization claim. The ideas above keep inputs explicit
and outputs inspectable instead.

### R2. One-Click Autonomous Creator Studio

**Temptation:** Combine `mojomast/mediageckussy`, `mojomast/bananagen`,
`mojomast/designussy`, and `mojomast/shoedelussy` into an autonomous system
that writes a project, generates every image and soundtrack, publishes it, and
iterates from engagement.

**Why rejected:** This stacks canon generation, multiple provider-dependent
asset paths, procedural art, browser audio, and publication without a bounded
user task. It also has unresolved rights, consent, provider failure, and human
approval boundaries. The source evidence supports small deterministic handoffs
and optional generation, not an end-to-end autonomous studio or an engagement
learning loop. A narrow product such as the launch pack or transcript cut board
can test user value first.
