# Science, Field Observation, and Lab Workflow Ideas

**Date:** 2026-09-13

This is a new pass focused on scientific computation, field observation,
environmental data, lab-like logs, and explainable decision support. These are
new combinations, not additions to the ten-item shortlist in
`SOURCE_CHECKED_COMBINATIONS.md`. A repository may recur when it is a useful
component, but the product boundary and handoff below are different.

## Evidence Boundary

**Exists** means the checked-out source contains the cited model or function.
**Proposed** means a new adapter, shared record, UI, persistence, or workflow
would be required. **Unverified** means I did not run the component or establish
domain validity. No end-to-end combination below was found in the inspected
source.

I inspected source, manifests, entry points, and selected tests in the
repositories listed below. The short revisions are the local `HEAD` values on
2026-09-13. I did not build or run their test suites during this pass.

| Repository | Revision | Source checked |
|---|---:|---|
| `ussyverse/capillaussy` | `be22c1f` | `src/lib.rs`, `Cargo.toml` |
| `ussyverse/tilthaussy` | `b586450` | `src/tiltha/models.py`, `engine.py`, `pyproject.toml` |
| `ussyverse/symbiosisussy` | `3bb7c01` | `src/symbiosis/models.py`, `ecology.py`, `pyproject.toml` |
| `ussyverse/compostaussy` | `d27eaca` | `src/lib.rs`, `Cargo.toml` |
| `ussyverse/fermentussy` | `4a23600` | `src/lib.rs`, `Cargo.toml` |
| `ussyverse/psychraussy` | `72b4a95` | `src/psychra/psychrometrics.py`, `pyproject.toml` |
| `ussyverse/terroirussy` | `21949a0` | `terroir.h` |
| `ussyverse/aquariaussy` | `58a9532` | `src/lib.rs`, `Cargo.toml` |
| `ussyverse/shewhartaussy` | `8955b86` | `pkg/shewharta/engine.go` |
| `ussyverse/adsorbaussy` | `52717fe` | `src/adsorba/models.py`, `engine.py` |
| `ussyverse/weberaussy` | `f084588` | `src/webera/models.py`, `engine.py` |
| `ussyverse/watershedussy` | `c5c7cb6` | `pkg/hydro/types.go`, `hydrograph.go` |
| `ussyverse/beaufortaussy` | `36a9bd2` | `internal/beauforta/model.go` |
| `ussyverse/gamutussy` | `7734066` | `gamut/models.py`, `analyzer.py` |
| `ussyverse/telegraphaussy` | `27fe051` | `telegrapha/models.py`, `attenuation.py`, `capacity.py` |
| `ussyverse/aquiferussy` | `375260b` | `aquifer/topology.py`, `darcy.py` |
| `ussyverse/vesselussy` | `346766d` | `src/index.ts`, `package.json` |
| `ussyverse/trialwiseussy` | `285ff7f` | `src/domain/model.ts`, `analyzer.ts` |
| `ussyverse/archivioussy` | `918d690` | `src/archivio/models.py`, `storage.py` |
| `ussyverse/validaraussy` | `26fda8b` | `validara.h`, `Makefile` |

## Proposed Ideas

### 1. Bed and Pot Water-Path Recovery Notebook

**Target user and pain.** A community gardener, plant caretaker, or teaching
garden has repeated watering and access problems but only scattered notes. A
plant may look dry at the surface while the lower root zone remains wet, and
people may compact the bed while trying to reach it. The user needs an
observation-led recovery record, not a plant-disease diagnosis.

**Exact repositories.** `ussyverse/capillaussy` and `ussyverse/tilthaussy`.

**Existing evidence.** Capilla has typed `PlantCard`, `PotSystem`,
`WateringEvent`, and `FollowupObservation` models plus `assess`, dryback-curve
estimation, hydraulic states, experiments, and a vacation handoff in
[`src/lib.rs`](https://github.com/ussyverse/capillaussy/blob/be22c1f/src/lib.rs).
Tiltha has `GardenZone`, `TrafficEvent`, `SoilObservation`, `RecoveryCheck`,
`PathLayout`, and `analyze_zone`/`compare_recovery` in
[`models.py`](https://github.com/ussyverse/tilthaussy/blob/b586450/src/tiltha/models.py)
and [`engine.py`](https://github.com/ussyverse/tilthaussy/blob/b586450/src/tiltha/engine.py).

**Handoff and data flow.** A dated observation session records pot/bed identity,
watering or rain, surface/core moisture, bottom heaviness, probe resistance,
puddle duration, and traffic events. The adapter sends container observations
to Capilla and bed access observations to Tiltha. A proposed stable
`observation_id` and `zone_id` retain raw observations beside each component
result. The output is a recovery timeline, one next observation, a path card,
and a handoff note.

**MVP.** One patio container cluster and one raised bed; enter three watering or
rain events, one wet-traffic event, and day-1/day-3/day-7 observations. Export a
single Markdown report showing the evidence, separate component findings, and
the before/after score change.

**Value of the combination.** Capilla explains water movement in a container;
Tiltha explains pore-space damage and repeated access in a bed. Together they
can distinguish “water is not reaching the core” from “the core should not be
worked yet,” which neither report establishes alone.

**Risks and maturity.** The code uses qualitative proxies, not measured bulk
density, root health, plant water potential, or disease testing. Capilla's
confidence is a heuristic based partly on observation count. Keep uncertainty
and the raw curve visible. Validate the input vocabulary and recommendations
with an experienced horticulturist across soil textures and container types;
do not present the result as agronomic, pesticide, or plant-health authority.

### 2. Compost-to-Plot Amendment Ledger

**Target user and pain.** A home or community gardener wants to know which
compost batch is merely cooling, which needs correction, and which plot could
receive it without losing the batch history. Current compost notes, soil access
notes, and planting plans are disconnected.

**Exact repositories.** `ussyverse/compostaussy`, `ussyverse/tilthaussy`, and
`ussyverse/symbiosisussy`.

**Existing evidence.** Composta's Rust library defines feedstock profiles,
`CompostBin`, `PileObservation`, C:N/moisture/structure metrics, phases, red
flags, interventions, and cure-readiness in
[`src/lib.rs`](https://github.com/ussyverse/compostaussy/blob/d27eaca/src/lib.rs).
Tiltha exposes observations, traffic history, path recommendations, recovery
windows, and explainable compaction mechanisms. Symbiosis has Pydantic plot
models and ecology functions for mutualism, allelopathy, succession, and
mycorrhizal network reports in
[`ecology.py`](https://github.com/ussyverse/symbiosisussy/blob/3bb7c01/src/symbiosis/ecology.py).

**Handoff and data flow.** Feedstock additions and pile observations are stored
under `batch_id`; Composta emits phase, evidence, red flags, and a cautious
`amendment_candidate` state. A human records the destination plot, Tiltha
converts plot observations and access history into a work/path plan, and
Symbiosis checks the existing plant context and proposed seasonal succession.
The proposed ledger must never silently turn “finished-ish” into “safe.”

**MVP.** One 120-liter batch, one raised bed, two observation dates, and three
candidate plantings. Show an amendment review packet with batch inputs,
unresolved red flags, plot condition, plant-compatibility notes, and a human
approval checkbox. No automatic spreading schedule is needed.

**Value of the combination.** It connects material provenance and maturity to
the physical condition of the receiving plot and its planting context. The
user gets a traceable “why this batch is not ready for this plot” explanation,
not three unrelated ecology dashboards.

**Risks and maturity.** Composta explicitly says its ratios are coarse and
does not certify pathogen kill; Symbiosis uses a small hand-authored plant
database and simplified adjacency/mycorrhizal rules; Tiltha is not a lab soil
test. Validate feedstock assumptions, compost handling, and crop-specific
constraints with local extension or compost professionals. Keep diseased plant,
pet-waste, contamination, and food-growing decisions routed to local guidance.

### 3. Fermentation Batch Lab Notebook

**Target user and pain.** A fermentation hobbyist, food-science student, or
small teaching kitchen needs reproducible batch records. Temperature, pH,
oxygen exposure, sensory notes, and room conditions are currently logged in
different places, making it hard to compare batches without pretending a
heuristic is a validated safety test.

**Exact repositories.** `ussyverse/fermentussy`, `ussyverse/psychraussy`, and
`ussyverse/terroirussy`.

**Existing evidence.** Ferment defines JSON-serializable `Batch` and `LogEntry`
records and implements entropy over taste notes, stage classification,
peak-ripeness heuristics, contamination scoring, and local batch persistence in
[`src/lib.rs`](https://github.com/ussyverse/fermentussy/blob/4a23600/src/lib.rs).
Psychra provides deterministic temperature/RH to dew point, vapor pressure,
absolute humidity, and humidity-ratio calculations in
[`psychrometrics.py`](https://github.com/ussyverse/psychraussy/blob/72b4a95/src/psychra/psychrometrics.py).
Terroir has a SQLite `Tasting` record with six sensory dimensions and commands
for fingerprints, evolution, and adaptation in
[`terroir.h`](https://github.com/ussyverse/terroirussy/blob/21949a0/terroir.h).

**Handoff and data flow.** A proposed `batch_id`/`log_id` joins fermentation
readings with room temperature/RH and a separate tasting record. Ferment emits
its current heuristic stage and raw pH/temperature; Psychra adds environmental
derivatives without changing the batch reading; Terroir produces a sensory
fingerprint and longitudinal comparison. The report shows measurements,
missingness, model outputs, and sensory observations in separate sections.

**MVP.** One sourdough or vegetable batch over 14 days, with at least five
manual temperature/pH entries, three room readings, and three blinded or
structured tastings. Export JSON plus a plain-text “next sample” checklist.

**Value of the combination.** The batch can be compared across both process
conditions and observed sensory outcome. This makes it a useful teaching and
repeatability notebook rather than a single ripeness number.

**Risks and maturity.** Ferment's peak and contamination functions are explicit
heuristics with fixed thresholds; Terroir measures subjective notes; Psychra's
Magnus approximation is not a food-process model. Validate sensors, pH-meter
calibration, temperature logging, recipes, and food-safety procedures against
authoritative local guidance. Never use this product to certify a ferment,
detect pathogens, or replace a food laboratory.

### 4. Aquarium Intervention Evidence Board

**Target user and pain.** An aquarium hobbyist has a sequence of ammonia,
nitrite, nitrate, pH, and temperature readings interspersed with water changes,
feeding changes, filter work, and stocking events. They need to tell a genuine
cycle change from ordinary variation and preserve the reason for an
intervention.

**Exact repositories.** `ussyverse/aquariaussy` and
`ussyverse/shewhartaussy`.

**Existing evidence.** Aquaria parses profile, test, and event CSV/JSON records;
classifies nitrogen-cycle state; emits warning cards, dilution estimates, a
confidence heuristic, and a store/vet conversation packet in
[`src/lib.rs`](https://github.com/ussyverse/aquariaussy/blob/58a9532/src/lib.rs).
Shewharta computes XmR limits, moving-range signals, runs, trends, process
change markers, and overcontrol warnings in
[`engine.go`](https://github.com/ussyverse/shewhartaussy/blob/8955b86/pkg/shewharta/engine.go).

**Handoff and data flow.** A parser converts Aquaria tests into a canonical
`metric_id`, UTC date, value, unit, method, and explicit missing-reading state.
Aquaria handles domain state and event context; Shewharta receives one selected
metric at a time with marked water changes or feeding/filter changes. The
proposed board links a signal to the exact raw readings and the human action
that followed.

**MVP.** Import a 30-row tank log, chart nitrate and ammonia separately, mark
three process changes, and produce a report that distinguishes insufficient
baseline, common-cause variation, and an investigation signal. Do not combine
the metrics into one health score.

**Value of the combination.** Aquaria explains the plausible nitrogen-cycle
state; Shewharta prevents reacting to every single test result. The shared
intervention ledger lets the keeper ask whether a change preceded a shift
without claiming causality.

**Risks and maturity.** Aquaria's dates are strings and its thresholds are
educational; Shewharta needs a stable baseline and its control limits do not
validate test-kit accuracy. A tank is a living system and animal distress needs
experienced aquarium or veterinary help. Validate units, test methods, sampling
frequency, and event timing with aquarists. This is a record and investigation
aid, not veterinary or animal-welfare authority.

### 5. Room Moisture and Odor Rebound Lab

**Target user and pain.** A renter or facilities volunteer sees recurring musty
or chemical-like odor and wants to test whether moisture, airflow, or a porous
reservoir is involved. They need a defensible observation packet before buying
more fragrance or escalating an unsupported diagnosis.

**Exact repositories.** `ussyverse/psychraussy`, `ussyverse/adsorbaussy`, and
`ussyverse/weberaussy`.

**Existing evidence.** Psychra calculates psychrometric states and surface
condensation helpers. Adsorba models an `OdorEvent`, source/reservoir clues,
airflow route, humidity influence, intervention ladder, rebound explanation,
hazard escalation, and one-variable next experiments in
[`engine.py`](https://github.com/ussyverse/adsorbaussy/blob/52717fe/src/adsorba/engine.py).
Webera stores room/modality variables and trials and estimates per-person JND,
comfort bands, contradictions, and adaptation checks in
[`engine.py`](https://github.com/ussyverse/weberaussy/blob/f084588/src/webera/engine.py).

**Handoff and data flow.** A timestamped room observation holds calibrated
temperature/RH, odor intensity and character, location, airflow state, and
intervention. Psychra derives dew point/absolute humidity; Adsorba proposes a
source-pathway experiment; Webera records whether a ventilation or setting
change was noticed or preferred. The output separates chemical/environmental
observations from perception and comfort.

**MVP.** Seven days of closet or basement observations, one humidity intervention
and one source-isolation intervention, plus two paired comfort trials. Export a
timeline with rebound events and a next-step card.

**Value of the combination.** It distinguishes “the odor returned when humidity
rose” from “occupants noticed a setting change,” preserving both physical and
perceptual evidence without collapsing them into a comfort score.

**Risks and maturity.** Adsorba is not a gas detector, mold assessment, or
exposure monitor; Psychra is not building-envelope certification; Webera's JND
estimate is a staircase heuristic. Calibrate the hygrometer, keep raw readings,
and route gas, smoke, chemical, electrical, visible extensive mold, or symptom
concerns to appropriate local professionals or emergency guidance. Validate
the observation protocol with indoor-environment specialists.

### 6. Trail Water and Wind Observation Card

**Target user and pain.** A hiker or field class planning a route must reconcile
seasonal water-source uncertainty with wind and return-leg observations. A
generic weather forecast does not explain which waypoint assumptions matter or
what was actually observed on site.

**Exact repositories.** `ussyverse/watershedussy` and
`ussyverse/beaufortaussy`.

**Existing evidence.** Watershed models route waypoints and water sources,
daily weather, snowmelt, baseflow, quickflow, evapotranspiration, hydrographs,
and carry calculations in
[`types.go`](https://github.com/ussyverse/watershedussy/blob/c5c7cb6/pkg/hydro/types.go),
[`hydrograph.go`](https://github.com/ussyverse/watershedussy/blob/c5c7cb6/pkg/hydro/hydrograph.go),
and `carry.go`. Beauforta accepts forecast wind, gusts, direction, fetch, and
field clues such as ripples/whitecaps/spray, then emits effective force, leg
risk, reasons, turn-around text, and a disclaimer in
[`model.go`](https://github.com/ussyverse/beaufortaussy/blob/36a9bd2/internal/beauforta/model.go).

**Handoff and data flow.** A route file supplies stable segment and waypoint
IDs. Manually entered weather and source observations feed Watershed; wind
forecast and observed clues feed Beauforta. A proposed coordinator joins both
by segment/date, carries units and provenance, and prints a field card with
water assumptions, observed-vs-forecast differences, and explicit abort or
verification prompts.

**MVP.** One route with four waypoints, seven daily weather rows, three water
source reliability observations, and two wind observations. Compare the plan
with the field notebook after the trip; do not automate live forecasts or GPS.

**Value of the combination.** Water availability and wind exposure are separate
constraints on the same route. Showing each calculation and its source makes a
field plan more inspectable than a single route score.

**Risks and maturity.** Watershed uses simplified degree-day, reservoir, and
evapotranspiration models and does not establish source potability. Beauforta's
recommendation is a conservative heuristic, not a rescue or marine authority.
Validate against local hydrology, seasonal route data, weather services, and
qualified instructors. Include local closures, warnings, lifeguard/park rules,
and a hard statement that the card cannot make a go/no-go decision for a real
high-consequence trip.

### 7. Sensor Pipeline Fidelity Bench

**Target user and pain.** An environmental-data engineer moves sensor records
through CSV, message queues, databases, and dashboards. Values can be clipped,
rounded, timezone-shifted, delayed, duplicated, or trapped behind a queue, but
ordinary pipeline monitoring often reports only throughput.

**Exact repositories.** `ussyverse/gamutussy`, `ussyverse/telegraphaussy`, and
`ussyverse/aquiferussy`.

**Existing evidence.** Gamut defines stage/field/type-gamut models, boundary
reports, clipping examples, rendering-intent labels, and runtime sample records
in [`models.py`](https://github.com/ussyverse/gamutussy/blob/7734066/gamut/models.py)
and field/pipeline analysis in
[`analyzer.py`](https://github.com/ussyverse/gamutussy/blob/7734066/gamut/analyzer.py).
Telegrapha defines hops/routes and computes cumulative fidelity, reliability,
capacity, precedence, and dead-letter metrics in
[`models.py`](https://github.com/ussyverse/telegraphaussy/blob/27fe051/telegrapha/models.py)
and [`attenuation.py`](https://github.com/ussyverse/telegraphaussy/blob/27fe051/telegrapha/attenuation.py).
Aquifer parses a service topology and computes queue-derived head, Darcy-like
flows, and bottlenecks in
[`topology.py`](https://github.com/ussyverse/aquiferussy/blob/375260b/aquifer/topology.py)
and [`darcy.py`](https://github.com/ussyverse/aquiferussy/blob/375260b/aquifer/darcy.py).

**Handoff and data flow.** A proposed `ObservationSchema` describes units,
range, precision, timezone, and nullable policy. A `PipelineRun` joins field
samples, hop names, queue snapshots, and timestamps. Gamut reports field-level
loss with concrete examples; Telegrapha reports transport attenuation and
capacity; Aquifer highlights queue pressure. The packet retains raw and
decoded values rather than emitting a universal health number.

**MVP.** A synthetic temperature-and-rain pipeline with three schema stages,
one timezone conversion, one numeric narrowing, and one queued hop. Inject known
errors and verify that the report points to the exact boundary and raw example.

**Value of the combination.** It connects semantic data loss, transport loss,
and queue pressure in one observation lineage. Each component answers a
different question and can be checked against a deliberately constructed
fixture.

**Risks and maturity.** The scientific names are analogies for data systems;
Aquifer is not a groundwater simulator in this use. Gamut's Delta-E analogue
and Telegrapha's Shannon/attenuation thresholds are product heuristics, not
validated reliability measures. Validate against known schema transformations,
recorded pipeline traces, and domain-specific error budgets. Do not turn the
output into regulatory environmental-data certification without an external
metrology and quality-system review.

### 8. Ceramic Firing Trial Notebook

**Target user and pain.** A pottery studio repeatedly sees cracks, warping, or
glaze fit problems but changes several firing variables at once. The studio
needs an explainable failure hypothesis and a small, reversible test plan tied
to actual results.

**Exact repositories.** `ussyverse/vesselussy`, `ussyverse/trialwiseussy`, and
`ussyverse/psychraussy`.

**Existing evidence.** Vessel has `ProjectInput`, clay-body constants, fired-size
calculation, thermal-shock score, quartz-inversion warnings, glaze-fit estimate,
defect inference, practice/outcome logs, and atmosphere insight in
[`src/index.ts`](https://github.com/ussyverse/vesselussy/blob/346766d/src/index.ts).
Trialwise defines reversible low-risk interventions, outcome metrics, crossover
periods, check-ins, confounds, precommitted decision rules, and analysis with
keep/reject/repeat/inconclusive outcomes in
[`model.ts`](https://github.com/ussyverse/trialwiseussy/blob/285ff7f/src/domain/model.ts)
and [`analyzer.ts`](https://github.com/ussyverse/trialwiseussy/blob/285ff7f/src/domain/analyzer.ts).
Psychra provides derived room moisture quantities that can be stored as ambient
context, not as a kiln-material model.

**Handoff and data flow.** One `project_id` links clay body, dimensions, drying
and firing schedule, ambient readings, actual outcome, and a test question.
Vessel generates a hypothesis such as thermal shock or glaze mismatch.
Trialwise schedules one-variable test tiles or preparation changes, records
adherence and confounds, and produces a decision memo. Psychra adds ambient
temperature/RH context when drying conditions are part of the hypothesis.

**MVP.** Import ten historical projects, select one repeated defect, design an
AB or ABAB test using test tiles, record two or more outcomes, and export a
memo that shows why the result is inconclusive when data are missing.

**Value of the combination.** Vessel gives a quick physics-informed hypothesis;
Trialwise forces reversible, precommitted comparison; the environment record
helps avoid attributing every failure to the kiln schedule. This is a learning
and process-improvement notebook, not a kiln controller.

**Risks and maturity.** Vessel's constants and defect probabilities are rough
heuristics and do not model a particular kiln, clay lot, glaze recipe, or
thermal profile. Trialwise was designed for personal routines, not ceramic
materials, so the studio adapter and safety review are new. Validate against
kiln manufacturer limits, test tiles, clay/glaze technical data, and a ceramic
technologist. Never recommend firing changes that bypass the studio's existing
kiln safety procedures.

### 9. Reproducible Watershed Observation Packet

**Target user and pain.** A volunteer stream-monitoring group collects photos,
water-source notes, weather, and route observations, then loses the provenance
of the claim made from each observation. They need a private, inspectable packet
that distinguishes a measured value, a model estimate, and an interpretation.

**Exact repositories.** `ussyverse/watershedussy`, `ussyverse/archivioussy`, and
`ussyverse/validaraussy`.

**Existing evidence.** Watershed has typed route/weather inputs and hydrograph
and carry computations. Archivio models artifacts, source notes, claims,
evidence links, counterclaims, verification tasks, sensitivity, and SHA-256
fixity through [`models.py`](https://github.com/ussyverse/archivioussy/blob/918d690/src/archivio/models.py)
and [`storage.py`](https://github.com/ussyverse/archivioussy/blob/918d690/src/archivio/storage.py).
Validara has a seven-criterion readiness model, required inputs/exclusions,
pilot runs, revision boundaries, and draft/pilot/validated states in
[`validara.h`](https://github.com/ussyverse/validaraussy/blob/26fda8b/validara.h).

**Handoff and data flow.** A field visit imports raw readings, photos, and a
method version. Validara is adapted from its current service-offer model to
check protocol completeness and pilot evidence; Watershed calculates a clearly
labeled estimate; Archivio accessions the raw artifacts and links each claim to
the observation or model run. A reviewer can mark a counterclaim or create a
verification task.

**MVP.** One route, two visits, five raw artifacts, one missing-data case, and
one disputed claim. Produce a private Markdown packet that links each claim to
the exact input rows and file hashes.

**Value of the combination.** It makes an environmental estimate auditable
without pretending that provenance equals truth. Method readiness and evidence
links are useful additions to the hydrograph, especially for volunteer groups
handing data to a scientist.

**Risks and maturity.** Validara currently evaluates service-offer readiness,
not field protocols, so the adapter is substantial and its criteria require
domain review. Archivio's existing export/storage behavior needs privacy,
idempotency, and atomic-write hardening before shared use. Validate the sampling
protocol, instruments, chain of custody, hydrologic assumptions, and any claim
with a qualified environmental scientist. No packet should be presented as a
regulatory measurement or flood/water-safety authority.

## Rejected Ideas

### R1. Universal Outdoor Hazard Oracle

**Temptation:** combine `ussyverse/watershedussy`, `ussyverse/beaufortaussy`,
`ussyverse/riptidaussy`, and `ussyverse/wetbulbaussy` into one go/no-go score
for every hike, paddle, swim, and hot-day task.

**Reject.** The components use different observations, thresholds, units,
population assumptions, and safety boundaries. A common card or maximum score
would imply that simplified hydrology, wind, current, and heat heuristics are
interoperable and validated as a single authority. They are not. Keep the
smaller, domain-bounded field card in idea 6, show each raw evidence path, and
route real decisions to local warnings, qualified leaders, and emergency
guidance. This is not an implementation recommendation.

### R2. One Garden Health Score

**Temptation:** combine `ussyverse/compostaussy`, `ussyverse/capillaussy`, and
`ussyverse/symbiosisussy` into a single 0-100 score that declares a garden
healthy, diseased, or ready for planting.

**Reject.** The inspected engines describe different objects: coarse compost
feedstock balance and curing observations, container water-path heuristics, and
a small rule-based plant relationship database. Their scores do not share a
validated unit, target, or outcome, and a single score would hide missing
observations and uncertainty. Ideas 1 and 2 preserve separate evidence and
produce bounded next observations instead of a plant-health or soil-certainty
authority. A real crop, soil, or disease decision would require local sampling,
extension guidance, and independent agronomic validation.

## Next Validation Steps

1. Pin the revisions above and run each component's own tests before building
   an adapter; this pass did not claim those tests pass.
2. For one selected idea, define a versioned shared record with units,
   timestamps, missingness, provenance, and raw component outputs before adding
   a dashboard.
3. Test with user-authored observations and deliberately contradictory or
   missing data. The expected result should be an explicit unknown or
   inconclusive state, not a stronger score.
4. Obtain domain review for the relevant garden, food, aquarium, indoor
   environment, hydrology, or ceramics workflow before making recommendations
   that affect real materials, animals, food, or field decisions.
