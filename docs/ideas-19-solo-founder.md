# Solo Founder Ideas: Source-Checked Combinations

Date checked: 2026-09-13

This document proposes new products assembled from capabilities found in the
local clones. Existing repository behavior is labeled **Exists**. The product
wrapper, cross-repository handoff, and customer workflow are **Proposed**.
No integration below has been implemented or tested.

## Selection Criteria

- 1-3 weeks for one experienced developer.
- Local-first and useful without a hosted service.
- A narrow, demoable workflow with an obvious saved/exported artifact.
- At least two Ussyverse repositories per combination.
- No duplication of the current shortlist: audiovisual production, service
  improvement, CI evidence, archival claims, learning calibration, household
  handoffs, civic pledges, music sketching, dependency cycles, or returns.

## Proposed Ideas

### 1. Weatherproof Weekend Pack

**Product (Proposed):** A CLI/web form that turns a short trip plan into a
weather-aware packing and clothing risk card, including uncertainty and
"reconsider" conditions rather than pretending to be a forecast service.

**User / pain:** Day hikers and weekend travelers repeatedly decide what to
pack from scattered forecasts, clothing notes, and personal comfort memory.

**Repositories:**

- `ussyverse/acclimaussy` at `39b4fe9651a2cd8cfe7fbc1ae6d36402d43ce48a`.
- `ussyverse/beaufortaussy` at `36a9bd2e3d20b85a1183cd0a6852c34ce763b997`.
- `ussyverse/cloforaussy` at `3b967eb9e498625ea896058828bc3eda2957cf7b`.

**Evidence (Exists):** `repos/ussyverse/acclimaussy/src/acclima.ts`
exports `analyzeTrip`; `repos/ussyverse/beaufortaussy/internal/beauforta/model.go`
defines Beaufort bands; `repos/ussyverse/cloforaussy/src/lib.rs` models
garments and clothing attributes.

**Handoff (Proposed):** Trip conditions become normalized wind/comfort inputs;
the output is a Markdown/JSON pack list with garment reasons and missing-data
warnings. Weather retrieval, if added, is **Unverified** and should be an
explicit import boundary.

**Missing integration:** Define one adapter for units and condition names,
then render the three existing output shapes into one card. No live API is
needed for the first demo.

**MVP / effort:** Paste a small JSON trip file and export one printable card;
3-5 days.

**Acceptance:** Given the same input, the tool produces deterministic output,
lists every assumption, and never presents missing weather data as observed.

**Why this combination:** It gives a concrete artifact for a recurring,
high-friction decision without needing accounts, maps, or live weather APIs.

**Maturity / risk:** Source contracts are inspected but not run together.
Advice can be mistaken for a safety guarantee; keep it conservative and expose
the assumptions.

**Rejected adjacent component:** Live forecast and map retrieval is excluded
from the MVP because it adds unverified network behavior and a larger support
surface.

### 2. Pantry-to-Compost Triage

**Product (Proposed):** A household kitchen desk that records storage and
appearance observations, explains common quality changes in produce or sweets,
and routes questionable or unavoidable waste into a compost action card.

**User / pain:** Households repeatedly throw out food because they cannot
separate a harmless quality change from a discard boundary or record what
storage practice caused it.

**Repositories:**

- `ussyverse/ethylenoussy` at `0d2206edc20b19cd06989553e83007c00269ddb7`.
- `ussyverse/bloomaussy` at `ba787cb87e06c7c446117084c2415b824b287259`.
- `ussyverse/compostaussy` at `d27eaca5ed5987533c74e7c08e5e598e219ed8a1`.

**Evidence (Exists):** `repos/ussyverse/ethylenoussy/ethyleno.c` contains
ethylene/ripening logic; `repos/ussyverse/bloomaussy/src/blooma/engine.py`
provides `diagnose` with quality and discard boundaries; and
`repos/ussyverse/compostaussy/src/lib.rs` provides compost
classification/action structures.

**Handoff (Proposed):** Produce observations become ripeness/use-soon inputs;
the final record separates food-quality guidance from compost guidance. Food
safety judgments beyond the existing rule scope are **Unverified**.

**Missing integration:** Normalize food item IDs, dates, and condition flags;
keep the quality diagnosis and compost route as separate sections rather than
feeding a diagnosis directly into a disposal decision.

**MVP / effort:** A local form, three pantry states, and printable weekly
triage sheet; 5-7 days.

**Acceptance:** A normal quality change, an explicit safety flag, and an
unknown item each produce visibly different next actions and preserve the raw
observations.

**Why this combination:** The output saves money and reduces waste while
combining four small deterministic engines into one understandable routine.

**Maturity / risk:** The component rules are source-inspected but the food
category mapping is incomplete. Never infer edibility from ripeness alone;
include a stop/discard path and professional guidance.

**Rejected adjacent component:** `phenoaussy` is not used here; its inspected
contract is seasonal cue/task timing, not food-quality diagnosis.

### 3. Scope-to-Quote Desk

**Product (Proposed):** A freelancer's quote worksheet that converts a rough
request into measured scope, compares candidate quotes, and exposes capacity
or scheduling pressure before a price is sent.

**User / pain:** Independent consultants and tradespeople lose margin when
vague requests are quoted before effort, minimum rate, or current capacity are
made explicit.

**Repositories:**

- `ussyverse/bidussy` at `4073119cf248c470c6956b769d2ba2926fb69586`.
- `ussyverse/allomaussy` at `ce4487de633357c69037b7fee5877f9de257a0b5`.
- `ussyverse/metraussy` at `c4232e866cca7e3d624cff0d0e303a086d73e9d7`.

**Evidence (Exists):** `repos/ussyverse/bidussy/src/bid/analysis.py` exports
`analyze_quotes`; `repos/ussyverse/allomaussy/src/alloma/analyzer.py` exports
`analyze_business`; `repos/ussyverse/metraussy/metra_core/engine.py` exports
`analyze_card` for structured measurement cards.

**Handoff (Proposed):** A scope card supplies comparable line items to the bid
analyzer; the business analyzer adds workload/capacity context. Pricing,
currency, and market-rate recommendations are **Unverified**.

**Missing integration:** Map measurement-card fields to `Quote` and
`PricingContext`, then add a small report composer; do not silently invent
currency or market data.

**MVP / effort:** JSON intake, quote comparison, and a client-ready Markdown
brief; 4-6 days.

**Acceptance:** A quote with missing effort is flagged, a below-minimum-rate
case remains visible, and the report shows raw inputs beside every derived
recommendation.

**Why this combination:** It targets a paying solo-operator workflow and
keeps the product useful even when the user supplies all commercial inputs.

**Maturity / risk:** The three analyzers have inspectable contracts, but their
identifiers and units are not proven interoperable. Bad scope produces false
confidence; require explicit unknowns and make the user approve the final
quote.

**Rejected adjacent component:** Automated invoicing/payment collection is
excluded because it would turn a local quoting aid into a financial system.

### 4. Provenance-Aware Change Intake

**Product (Proposed):** A local intake tool for a small team receiving a new
package, dataset, or vendor artifact. It produces a change summary, a
compatibility checklist, and a provenance trail before adoption.

**User / pain:** Small engineering or data teams need a lightweight review
packet but cannot justify a full governance platform for every incoming file.

**Repositories:**

- `ussyverse/chromatoussy` at `d236ab75b1c77b58be1226e905dc7c1853d5a230`.
- `ussyverse/cambiumussy` at `5fe4d0d9030d9e1022c279a0992b15e3668f1274`.
- `ussyverse/mintussy` at `ade54309bb136c19b78c599400b33a15c37c96de`.

**Evidence (Exists):** `repos/ussyverse/chromatoussy/chromato/engine.py`
contains `run_scan`/`run_diff`; `repos/ussyverse/cambiumussy/cambium/compatibility.py`
and `models.py` define compatibility analysis; `repos/ussyverse/mintussy/mint/provenance.py`
and `counterfeit.py` provide provenance and authenticity checks.

**Handoff (Proposed):** Scan/diff output is attached to a compatibility case;
the case receives provenance evidence and a review status. Network registry
lookups and legal authenticity conclusions are **Unverified**.

**Missing integration:** Define a stable case envelope containing raw paths,
hashes, scan findings, compatibility inputs, and reviewer decisions. Preserve
each tool's native output instead of reducing it to one score.

**MVP / effort:** Directory intake plus deterministic Markdown report; 4-6
days.

**Acceptance:** A repeated scan of unchanged input is byte-stable, changed
input is shown as a diff, and every recommendation links to its source finding.

**Why this combination:** It is an evidence packet rather than another generic
dependency dashboard, and the artifact can be attached to an approval ticket.

**Maturity / risk:** Source behavior is inspected, but no cross-tool fixture or
runtime adapter has been validated. A clean local scan is not proof of safety
or provenance; state coverage and preserve raw inputs.

**Rejected adjacent component:** A hosted registry mirror is excluded because
it introduces credentials, network freshness, and an authority claim.

### 5. Reproducible Method Card

**Product (Proposed):** A local report for a small research or engineering
script that records its callable documentation, declared interface, runtime
witness, citations, and input provenance in one inspectable method card.

**User / pain:** A researcher can share a result without sharing enough
evidence for another person to understand what ran, what was declared, and
which sources informed the method.

**Repositories:**

- `ussyverse/rosettussy` at `59a85443b6d63f5d31b090333c9235e241c1e74c`.
- `ussyverse/citewiseussy` at `ea270ca6b2517a99393b89006ffa7997ba326963`.
- `ussyverse/mintussy` at `ade54309bb136c19b78c599400b33a15c37c96de`.

**Evidence (Exists):** `repos/ussyverse/rosettussy/src/rosetta/inscription.py`
defines `Inscription`, extracting docstrings/arguments and a runtime trace;
`repos/ussyverse/citewiseussy/pkg/citewise/engine.go` provides `Analyze` for
citation analysis; `repos/ussyverse/mintussy/mint/provenance.py` provides
provenance records.

**Handoff (Proposed):** A user-selected callable and source manifest become an
inscription; citations and provenance are attached by stable artifact ID; the
wrapper exports a method card with raw evidence, divergences, and runtime
witnesses. Scientific validity remains **Unverified**.

**Missing integration:** Define artifact IDs and a manifest format, add a
safe callable-selection boundary, and render the three outputs without
turning missing evidence into a pass.

**MVP / effort:** One Python module plus a citation/provenance JSON file in,
one Markdown report out; 4-6 days.

**Acceptance:** A missing docstring, a declared/runtime divergence, and a
missing citation each remain visible and traceable to the raw input.

**Why this combination:** It gives a small research team a reviewable artifact
without requiring a full experiment manager or hosted repository integration.

**Maturity / risk:** Rosetta's runtime witness intentionally catches callable
exceptions and is not a correctness proof; citation and provenance IDs need a
new adapter. Preserve raw code metadata and label inferred evidence.

**Rejected adjacent component:** Automatic peer-review or scientific-quality
scoring is excluded because these source contracts document evidence, not truth.

### 6. Small Library Preservation Queue

**Product (Proposed):** A personal or small-institution queue that prioritizes
books and paper objects for binding attention, catalogs condition, and creates
citation-ready preservation notes.

**User / pain:** Collectors and small libraries know which objects are
valuable, but not which repair or documentation task should happen first.

**Repositories:**

- `ussyverse/binderyussy` at `f12ab22e73b4743645dfca0d261d88ac80db75b3`.
- `ussyverse/curatorussy` at `ce516147688a634a6dd6c6498dcbbeeda1b3b47b`.
- `ussyverse/citewiseussy` at `ea270ca6b2517a99393b89006ffa7997ba326963`.

**Evidence (Exists):** `repos/ussyverse/binderyussy/src/lib.zig` defines
binding/condition structures; `repos/ussyverse/curatorussy/curator/catalog.py`
and `conservation.py` define catalog and conservation behavior;
`repos/ussyverse/citewiseussy/pkg/citewise/engine.go` provides `Analyze`.

**Handoff (Proposed):** Condition intake creates a preservation item;
catalog metadata and citation analysis are rendered into a prioritized work
list and an exportable note. Conservation treatment recommendations outside
the existing models are **Unverified**.

**Missing integration:** Map condition severity and object identity into a
shared queue record, retain the original catalog fields, and make citation
exports point back to the object record.

**MVP / effort:** CSV/JSON import, manual condition form, and static queue;
4-6 days.

**Acceptance:** A user can import three objects, change a condition field,
re-run prioritization, and export a note whose citations still identify the
source object.

**Why this combination:** It serves librarians, collectors, and family
archives with a bounded workflow rather than attempting a full catalog system.

**Maturity / risk:** Source behavior is inspected, but the priority formula
would be new. Prioritization is not professional conservation advice; include
confidence and escalation fields.

**Rejected adjacent component:** Automated treatment instructions are excluded
because they exceed the inspected catalog and condition contracts.

### 7. Walkable Errand Window

**Product (Proposed):** A local route planner for a short errand or evening
walk that combines a user's time window, route conditions, and a small set of
comfort/visibility checks into one offline route card.

**User / pain:** People repeating a local walk or errand want a consistent
departure checklist without handing route data to a hosted planner.

**Repositories:**

- `ussyverse/controlaussy` at `c3170f9b075cd871691c66a8c8727917eb6a0476`.
- `ussyverse/celestialussy` at `2fbe197a258d306871b2e3a3298d68271683b30d`.
- `ussyverse/portolanussy` at `39736975ed88da4fc6c87d5fc65e3f0b9b141d74`.

**Evidence (Exists):** `repos/ussyverse/controlaussy/src/controla.nim`
defines `WalkPlan`; `repos/ussyverse/celestialussy/src/index.ts` defines
route/time models; `repos/ussyverse/portolanussy/src/lib.rs` defines a
`Window` model.

**Handoff (Proposed):** A local route/time JSON record is converted into a
walk plan and windowed route card. Live routing, map tiles, and accessibility
accuracy are **Unverified** unless supplied by the user.

**Missing integration:** Agree on route segment, timestamp, and window units;
add an importer for a user-owned route and preserve the input alongside the
derived card.

**MVP / effort:** Import a GPX/CSV-like route, enter a time window, export a
checklist; 5-7 days.

**Acceptance:** The same route and window produce the same card, an invalid or
missing segment is reported, and no route is silently fabricated.

**Why this combination:** The deliverable is useful offline and can be sold
to clubs, guides, or people planning repeat local routes.

**Maturity / risk:** The route/time source contracts are inspected but not
proven interoperable. Never represent heuristic route checks as navigation or
emergency guidance; require a user-supplied route.

**Rejected adjacent component:** Turn-by-turn navigation is excluded because
it requires map freshness and safety-critical positioning behavior.

### 8. Fermentation Experiment Notebook

**Product (Proposed):** A local batch notebook that links ingredient/process
notes to viscosity observations and keeps comparable experiment cards across
recipes.

**User / pain:** Fermentation and confectionery hobbyists lose the context
needed to reproduce a good batch when observations live in separate notebooks.

**Repositories:**

- `ussyverse/fermentussy` at `4a23600bcf0b5972a3d0b801bc54aa05c6f19e5b`.
- `ussyverse/rheoussy` at `c5ee1e0bab84a720bd8eafa4f16b080d4f9027fa`.
- `ussyverse/marangoniussy` at `82f5ebeea54b42b42b177e0ca2f6df969da3843d`.

**Evidence (Exists):** `repos/ussyverse/fermentussy/src/lib.rs` defines
`Batch` and `LogEntry`; `repos/ussyverse/rheoussy/src/lib.rs` defines
rheology inputs/outputs; `repos/ussyverse/marangoniussy/src/marangoni/engine.py`
contains `forecast_recipe`, while `experiments.py` and `storage.py` define
experiment persistence concepts.

**Handoff (Proposed):** Batch logs become experiment observations; viscosity
measurements and recipe forecasts are combined into a versioned card. Food
safety, microbial identification, and shelf-life claims are **Unverified**.

**Missing integration:** Define a batch ID, timestamp, unit, and recipe
version; attach rheology observations without changing the underlying batch
log and keep forecast assumptions visible.

**MVP / effort:** Manual batch entry, measurement fields, and CSV/Markdown
export; 4-6 days.

**Acceptance:** Two batch cards can be compared by recipe version and process
change, and an incomplete measurement is shown as unknown rather than zero.

**Why this combination:** Serious hobbyists already collect these observations
but lack a compact way to compare process changes.

**Maturity / risk:** The three persistence/analysis surfaces are inspected but
not run through a shared fixture. Keep it explicitly experimental and route
questionable batches to discard/professional guidance rather than scoring them
safe.

**Rejected adjacent component:** A public recipe recommendation marketplace is
excluded because it would require moderation, identity, and food-safety claims.

### 9. Battery-and-Cord Station Check

**Product (Proposed):** A household charging-station audit that produces one
action card for battery condition and one route card for cable heat, strain,
trip, and inspection risks.

**User / pain:** Households see battery, charger, and cable problems together
but currently have to interpret separate safety checklists and do not retain a
repeatable station audit.

**Repositories:**

- `ussyverse/chargeguardussy` at `55b3ac93f6dfc4d4270d49d744123c9243229643`.
- `ussyverse/capstanussy` at `01cd17d212e2347b0cd1fb712ca58b234065ba10`.

**Evidence (Exists):** `repos/ussyverse/chargeguardussy/src/lib.rs` defines
`BatteryItem`, `Charger`, `Location`, and conservative status/action analysis;
`repos/ussyverse/capstanussy/main.go` is the CLI entry point, with
`AnalyzeStation`/`AnalyzeCord` in `pkg/capstan/scorer.go` and rendering in
`pkg/capstan/render.go`.

**Handoff (Proposed):** One station JSON file is split into battery and cord
observations; the wrapper joins the action cards and highlights conflicting
conditions. Electrical certification, fire response, and manufacturer-policy
claims are **Unverified** and out of scope.

**Missing integration:** Define station, battery, charger, and cord IDs plus a
shared location reference; keep the two reports separate and add a combined
summary only at the presentation layer.

**MVP / effort:** A guided JSON form and combined Markdown report; 3-5 days.

**Acceptance:** A damaged battery and a frayed cord each retain their own
stop-use boundary, while a routine station produces actionable improvements;
the report never advises repair or firefighting.

**Why this combination:** It is a narrow safety-adjacent household audit with
clear boundaries and a tangible before/after station improvement workflow.

**Maturity / risk:** Both core implementations are source-inspected, but the
shared station schema is new. Safety messaging must preserve both libraries'
conservative limits; never provide repair, wiring, or firefighting instructions.

**Rejected adjacent component:** Smart-plug telemetry is excluded because it
would add hardware, electrical claims, and an unverified device integration.

### 10. Wood Project Risk Card

**Product (Proposed):** A maker's pre-build worksheet that combines wood
movement, adhesive/substrate risk, and measured project inputs into a printable
"build or revise" card.

**User / pain:** Hobby woodworkers make irreversible cuts and glue-ups before
checking movement, humidity, attachment method, or removal consequences.

**Repositories:**

- `ussyverse/kerfwiseussy` at `3717259598682bdbb818446b38274331a46c678c`.
- `ussyverse/adheraussy` at `6848031387e7577869d88d3cd65eb1968b5ef37d`.
- `ussyverse/metraussy` at `c4232e866cca7e3d624cff0d0e303a086d73e9d7`.

**Evidence (Exists):** `repos/ussyverse/kerfwiseussy/README.md` documents
`AssessProject` and movement risk cards; `repos/ussyverse/adheraussy/src/adhera/rules.py`
implements deterministic adhesion rules; `repos/ussyverse/metraussy/metra_core/engine.py`
provides `analyze_card`.

**Handoff (Proposed):** Measurement cards feed project dimensions and
environment; material/joinery observations produce separate movement and
adhesion warnings in one build packet. Structural engineering and load
certification are **Unverified**.

**Missing integration:** Map measurement units and part IDs into Kerfwise's
project model, then use Adhera only for adhesive/substrate tasks; do not merge
their unrelated risk levels into one unexplained number.

**MVP / effort:** A project JSON schema, three fixture projects, and Markdown
export; 4-6 days.

**Acceptance:** A wide solid-wood tabletop and a removable cable clip produce
the correct separate cards, and missing species or substrate data remains
visible as uncertainty.

**Why this combination:** The customer gets prevention before an expensive
build, while each underlying rule engine remains independently understandable.

**Maturity / risk:** Kerfwise and Adhera have source-level rule engines;
Metra's adapter contract is still unverified. Limit examples to hobby projects
and make uncertainty visible for unknown species, substrates, or assemblies.

**Rejected adjacent component:** Structural load certification is excluded;
the inspected tools are planning aids, not engineering sign-off systems.

### 11. Solo Service Fallow Planner

**Product (Proposed):** An offline planner for a solo consultancy that rotates
service offers, monitors client concentration and capacity, and schedules
seasonal preparation/recovery tasks without claiming to predict revenue.

**User / pain:** A solo operator can overwork a high-revenue service or client
for months before seeing that capacity, concentration, and recovery have become
dangerous.

**Repositories:**

- `ussyverse/rotationussy` at `b483de0487bf4244720f5c81cbf5abe441f70a99`.
- `ussyverse/phenoaussy` at `388eddd162501436caa7a23511077f7df2722e33`.
- `ussyverse/allomaussy` at `ce4487de633357c69037b7fee5877f9de257a0b5`.

**Evidence (Exists):** `repos/ussyverse/rotationussy/src/model.ts` and
`agronomy.ts` define service, client, work-log, soil-recovery, and
`rotationPlan` behavior; `repos/ussyverse/phenoaussy/src/phenoa/engine.py`
provides cue-based `PhenoaEngine.recommend`; and
`repos/ussyverse/allomaussy/src/alloma/analyzer.py` provides
`analyze_business` with capacity, client-surface, and cashflow metrics.

**Handoff (Proposed):** Service/work history becomes rotation and recovery
inputs; business snapshots add concentration/capacity context; seasonal cues
open preparation or wind-down tasks. Revenue forecasts and burnout diagnoses
are **Unverified**.

**Missing integration:** Rename metaphorical field/service concepts only at the
UI boundary, map dates and capacity units explicitly, and preserve each raw
analysis beside the combined plan.

**MVP / effort:** Service CSV import, concentration/capacity warnings, and a
printable four-week plan; 5-7 days.

**Acceptance:** A dominant client or depleted service produces a visible
rotation/fallow warning, while an incomplete history produces an uncertainty
note rather than a confident plan.

**Why this combination:** It turns three otherwise separate views of a solo
business into one recurring planning ritual without becoming a generic CRM.

**Maturity / risk:** The source contracts are inspected, but the business use
of Phenoa's seasonal cues and Rotation's farm metaphor is an adapter, not an
existing integration. Avoid prescriptive financial or health claims.

**Rejected adjacent component:** Automatic lead generation is excluded because
it would undermine the planner's local-first, user-controlled scope.

## Rejected Ideas

### A. One-Click Battery Emergency Coach

Rejected despite `chargeguardussy` because combining it with emergency
instructions would violate its documented boundary: it explicitly does not
provide firefighting tactics, battery repair, or emergency-response
substitution. The safer station-audit proposal preserves the existing scope.

### B. Universal Live Hiking Safety Planner

Rejected despite the route/weather candidates because a product that fetches
live forecasts, maps, accessibility data, and emergency guidance would require
unverified external integrations and create safety-critical expectations. The
offline, user-supplied-route `Walkable Errand Window` is a smaller and more
defensible MVP.

## Source Ledger

The revisions above were recorded with `git rev-parse HEAD` from each local
clone. The source paths and symbols were read from the checked-out revisions;
the proposed cross-repository adapters were not implemented or executed.

Commands run during review included:

```text
ls /home/ubuntu/ussy/brainstorm
ls /home/ubuntu/ussy/brainstorm/docs
ls /home/ubuntu/ussy/repos/ussyverse
ls /home/ubuntu/ussy/repos/mojomast
git rev-parse HEAD
```

No project test command was run for this document. The only file intended to
be added by this task is this document.
