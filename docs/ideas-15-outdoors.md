# Outdoors Product Combinations

**Date:** 2026-09-13
**Scope:** New product concepts for travel, hiking, gardening, weather,
conservation, and outdoor stewardship.
**Status:** Research proposals, not implemented integrations.

## How to Read This

- **Exists** means the capability is present in source inspected for this pass.
- **Proposed** means an adapter, product workflow, or shared data model still
  needs to be built.
- **Unverified** means the claim was not established by runtime testing or by
  inspecting the relevant implementation.
- Safety and environmental outputs below are planning aids only. They must not
  replace official weather, flood, fire, medical, land-manager, or emergency
  guidance.

The ideas are ranked by recurring user need, complementarity, concrete reuse,
local demonstrability, and limited missing work. Every serious candidate uses
at least two `ussyverse` repositories. I found no end-to-end implementation of
these particular combinations in the inspected files.

## 1. Trail Water and Heat Card

**Exact repositories:** `ussyverse/watershedussy` + `ussyverse/wetbulbaussy` +
`ussyverse/plantaussy`

**User and recurring pain.** A day hiker or hiking-group leader repeatedly
decides how much water to carry and when to schedule breaks while also trying to
avoid hot-weather exposure and foot problems. These decisions are currently
split between a route note, a weather app, and personal experience.

**Product promise.** “Turn a route and weather scenario into a conservative,
editable water, rest, and foot-care plan.”

**Flow:** route waypoints, water sources, expected inflow/usage assumptions,
weather readings, terrain, and footwear/exposure observations -> calculate
carry legs, heat/work-rest flags, and foot-zone risk -> printable trail card
with water checkpoints, suggested pauses, assumptions, and route-away prompts.

**Existing source to reuse.**

- **Exists:** `watershedussy` defines `WaterSource`, `Waypoint`, `Route`, and
  weather structures in [`pkg/hydro/types.go`](https://github.com/ussyverse/watershedussy/blob/HEAD/pkg/hydro/types.go),
  plus `CalculateCarryLegs` in [`pkg/hydro/carry.go`](https://github.com/ussyverse/watershedussy/blob/HEAD/pkg/hydro/carry.go).
- **Exists:** `wetbulbaussy` has exposure readings, task plans, heat-index /
  WBGT-like calculations, and safety flags in [`src/wetbulba/models.py`](https://github.com/ussyverse/wetbulbaussy/blob/HEAD/src/wetbulba/models.py)
  and [`src/wetbulba/engine.py`](https://github.com/ussyverse/wetbulbaussy/blob/HEAD/src/wetbulba/engine.py).
- **Exists:** `plantaussy` models footwear, terrain, exposure, and foot-zone
  risk in [`src/core/mechanics.ts`](https://github.com/ussyverse/plantaussy/blob/HEAD/src/core/mechanics.ts).

**Missing integration work.** Define one route-segment schema; normalize
liters/gallons, minutes, temperature units, and local timestamps; keep user
water assumptions separate from measured sources; and show each component's
raw result next to the combined recommendation. The adapter must not infer a
trail's water availability from a route name.

**Maturity and feasibility.** **Proposed** output is deterministic planning,
not a hydration or heat-safety predictor. **Unverified:** the component
contracts have not been built or run together, and the source models do not
establish reliable field measurements or official route data.

**Smallest useful demo.** Enter a five-waypoint loop with two manually entered
water sources, two weather scenarios, and one footwear observation. Export a
one-page card and change the heat scenario to show which assumptions and pauses
changed.

**Acceptance criteria.** Every output cites its input and unit; missing water
data is shown as unknown; no route is marked safe; changing one waypoint only
changes affected carry legs; and the export contains a clear official-guidance
disclaimer.

**Why combine?** The route is the shared entity. Water logistics, heat pacing,
and foot care become one pre-hike packet instead of three unrelated scores.

**Rejected adjacent components.** `ussyverse/solaraussy` was not included in
the MVP because UV exposure adds another independent hazard layer before the
route-segment contract is proven; it is a possible later input, not evidence of
an existing integration.

## 2. Constraint-First Outdoor Trip Window Planner

**Exact repositories:** `ussyverse/migrationussy` + `ussyverse/koppenussy` +
`ussyverse/portolanussy` + `ussyverse/celestialussy`

**User and recurring pain.** A traveler planning a multi-day trek or nature
trip must reconcile group constraints, climate preferences, usable travel
windows, and daylight. A destination shortlist alone does not produce a
bookable or hikeable itinerary.

**Product promise.** “Show which destinations and departure windows satisfy the
group’s constraints before you spend time assembling a route.”

**Flow:** traveler constraints, date range, destination climate data, leg
durations, reserves, and waypoint sequence -> rank climate-compatible
destinations, calculate usable window minutes, and identify daylight-aware
route legs -> produce a shortlist with rejected constraints, timing assumptions,
and an editable itinerary skeleton.

**Existing source to reuse.**

- **Exists:** `migrationussy` defines traveler constraints, date windows,
  budgets, interests, and destination scoring in [`src/migration/models.py`](https://github.com/ussyverse/migrationussy/blob/HEAD/src/migration/models.py)
  and [`src/migration/planner.py`](https://github.com/ussyverse/migrationussy/blob/HEAD/src/migration/planner.py).
- **Exists:** `koppenussy` provides climate classification and monthly
  temperature/precipitation/humidity preference ranking in [`koppen.h`](https://github.com/ussyverse/koppenussy/blob/HEAD/koppen.h)
  and [`koppen.c`](https://github.com/ussyverse/koppenussy/blob/HEAD/koppen.c).
- **Exists:** `portolanussy` models `Window`, reserve multipliers, and usable
  minutes in [`src/lib.rs`](https://github.com/ussyverse/portolanussy/blob/HEAD/src/lib.rs).
- **Exists:** `celestialussy` defines typed waypoints, route legs/plans,
  travel style, and recovery data in [`src/index.ts`](https://github.com/ussyverse/celestialussy/blob/HEAD/src/index.ts).

**Missing integration work.** Add a destination-to-waypoint mapping, explicit
opening-hours and travel-time inputs, date/time-zone normalization, and a
constraint provenance table. Climate averages must remain distinct from a
forecast, and a celestial calculation must not be treated as permission to
travel after dark.

**Maturity and feasibility.** **Exists** components are mostly local planners
and ranking functions. **Unverified:** destination datasets, current closures,
transport schedules, and real daylight calculations were not validated in this
pass. The product should show “not enough data” rather than silently rank a
missing field.

**Smallest useful demo.** Compare three manually entered trailhead regions for
one group, one date range, and one reserve policy. Show why each destination
passed or failed and export a draft route with daylight and buffer fields.

**Acceptance criteria.** Each ranking factor is inspectable; a missing opening
time prevents a “bookable” claim; every time has a stated timezone; reserves
are visible; and official land-manager information is linked as a required
human check.

**Why combine?** Migration describes the group, Koppen narrows climate fit,
Portolan checks usable time, and Celestial gives the route a temporal shape.
The shared entity is a constrained destination/window pair.

**Rejected adjacent components.** `ussyverse/acclimaussy` was held out because
altitude acclimatization is a separate itinerary policy and would make the
first MVP imply medical suitability. It is a candidate extension after
altitude inputs and professional review rules are defined.

## 3. Altitude Arrival and Recovery Planner

**Exact repositories:** `ussyverse/acclimaussy` + `ussyverse/migrationussy` +
`ussyverse/currentussy`

**User and recurring pain.** A traveler repeatedly arrives at higher elevation
with an overpacked first day, no planned recovery, and no record of what pacing
worked on prior trips.

**Product promise.** “Turn an elevation-changing itinerary into an editable
arrival pacing plan, without pretending to diagnose altitude illness.”

**Flow:** destination elevations, travel dates, trip purpose, planned activity,
personal baseline, and past-trip notes -> produce acclimatization day cards,
travel-energy/current forecasts, and rest prompts -> export an itinerary with
assumptions, symptom escalation reminders, and professional-help boundaries.

**Existing source to reuse.**

- **Exists:** `acclimaussy` contains altitude trip points, traveler profiles,
  symptom checks, day cards, and actions in [`src/acclima.ts`](https://github.com/ussyverse/acclimaussy/blob/HEAD/src/acclima.ts).
- **Exists:** `migrationussy` supplies trip constraints and destination/date
  planning in [`src/migration/models.py`](https://github.com/ussyverse/migrationussy/blob/HEAD/src/migration/models.py)
  and [`src/migration/planner.py`](https://github.com/ussyverse/migrationussy/blob/HEAD/src/migration/planner.py).
- **Exists:** `currentussy` models personal baselines, destination profiles,
  daily choices, adaptation, recovery, and rest recommendations in [`src/current/models.py`](https://github.com/ussyverse/currentussy/blob/HEAD/src/current/models.py)
  and [`src/current/engine.py`](https://github.com/ussyverse/currentussy/blob/HEAD/src/current/engine.py).

**Missing integration work.** Establish an explicit altitude/elevation unit and
source field; map a trip day to one canonical plan ID; separate subjective
energy notes from altitude symptoms; and define a hard escalation copy block
for concerning symptoms. Never use a computed label as a medical clearance.

**Maturity and feasibility.** **Exists** is limited to deterministic models and
recommendation strings. **Unverified:** clinical validity, geographic elevation
data, and whether the two planning vocabularies can be joined without losing
meaning. The first version should be a journaling and pacing aid.

**Smallest useful demo.** Enter a four-day itinerary with a low-elevation start,
two elevation changes, one rest day, and two past-trip notes. Export day cards
and demonstrate that a changed recovery preference changes prompts but not
source facts.

**Acceptance criteria.** Source altitude and user-entered symptoms remain
separate; symptoms trigger “seek authoritative help” copy rather than a score;
past trips are never presented as clinical evidence; and the plan can be
edited without rewriting its input history.

**Why combine?** Acclima handles the altitude-shaped day plan, Migration gives
it a real trip constraint envelope, and Current adds a transparent personal
recovery journal. The shared entity is an itinerary day.

**Rejected adjacent components.** `ussyverse/wetbulbaussy` was rejected from
this concept because heat exposure would complicate attribution between
altitude, weather, exertion, and symptoms. It belongs in a separate outdoor
hazard card with stronger measurement boundaries.

## 4. Layer, Wind, and UV Packing Planner

**Exact repositories:** `ussyverse/cloforaussy` + `ussyverse/beaufortaussy` +
`ussyverse/solaraussy`

**User and recurring pain.** A commuter cyclist, paddler, or day hiker packs
layers based on temperature alone and then discovers that wind, rain,
breathability, altitude, or sun exposure makes the chosen kit uncomfortable.

**Product promise.** “Make the assumptions behind a clothing and sun-protection
packing list visible before the outing.”

**Flow:** activity, garment properties, wind/rain conditions, exposure,
altitude, reflection, and planned timing -> evaluate clothing comfort factors,
wind bands, UV exposure windows, and route-away conditions -> produce a packing
list and time-of-day checklist with raw inputs and uncertainty.

**Existing source to reuse.**

- **Exists:** `cloforaussy` models garments, clo, wind, rain, breathability,
  and packability in [`src/lib.rs`](https://github.com/ussyverse/cloforaussy/blob/HEAD/src/lib.rs).
- **Exists:** `beaufortaussy` provides wind bands and land/sea/paddling notes in
  [`internal/beauforta/model.go`](https://github.com/ussyverse/beaufortaussy/blob/HEAD/internal/beauforta/model.go).
- **Exists:** `solaraussy` models UV exposure, reflection, altitude, sunscreen,
  timing, and route-away rules in [`src/solara/models.py`](https://github.com/ussyverse/solaraussy/blob/HEAD/src/solara/models.py)
  and [`src/solara/planner.py`](https://github.com/ussyverse/solaraussy/blob/HEAD/src/solara/planner.py).

**Missing integration work.** Define a shared weather snapshot and time zone;
map Beaufort bands to clothing inputs without inventing a wind-chill law;
preserve garment-user assumptions; and make sun guidance conditional on
authoritative forecast and local conditions.

**Maturity and feasibility.** **Exists** are small rule engines with different
units and confidence semantics. **Unverified:** comfort thresholds, forecast
freshness, and cross-engine equivalence. This should be a packing assistant,
not a guarantee of protection or thermal safety.

**Smallest useful demo.** Compare one coastal paddle and one dry trail using the
same garment inventory. Export the changed layers, wind notes, and sun timing.

**Acceptance criteria.** The report distinguishes comfort from hazard; missing
wind or UV observations remain unknown; no garment is declared protective
without its user-supplied properties; and the user can override any suggested
layer with a recorded reason.

**Why combine?** Clofora describes the kit, Beauforta describes wind in an
activity-aware vocabulary, and Solara adds a separate exposure checklist. The
combined value is an auditable packing decision, not a larger opaque score.

**Rejected adjacent components.** `ussyverse/fulguraussy` was not included in
the packing MVP because lightning shelter timing is an event-safety workflow,
not a garment attribute. It should be a separate route-away gate.

## 5. Garden Workday and Soil Recovery Planner

**Exact repositories:** `ussyverse/tilthaussy` + `ussyverse/wetbulbaussy` +
`ussyverse/solaraussy` + `ussyverse/compostaussy`

**User and recurring pain.** A home gardener plans watering, turning, weeding,
or bed preparation around a calendar rather than actual soil state and exposure
conditions, resulting in rushed hot-weather work or repeated compaction.

**Product promise.** “Choose the next garden task from observed zone conditions,
weather exposure, and compost readiness.”

**Flow:** garden zones, soil observations, traffic events, compost batch state,
weather/exposure readings, and planned tasks -> analyze zone condition, heat/UV
work pacing, and compost stability -> produce a zone-by-zone work card with rest
windows, access limits, and amendment/turning questions.

**Existing source to reuse.**

- **Exists:** `tilthaussy` defines garden zones, soil observations, traffic
  events, and qualitative compaction plans in [`src/tiltha/models.py`](https://github.com/ussyverse/tilthaussy/blob/HEAD/src/tiltha/models.py)
  and [`src/tiltha/engine.py`](https://github.com/ussyverse/tilthaussy/blob/HEAD/src/tiltha/engine.py).
- **Exists:** `wetbulbaussy` defines exposure readings and task plans in
  [`src/wetbulba/models.py`](https://github.com/ussyverse/wetbulbaussy/blob/HEAD/src/wetbulba/models.py)
  and safety flags in [`src/wetbulba/engine.py`](https://github.com/ussyverse/wetbulbaussy/blob/HEAD/src/wetbulba/engine.py).
- **Exists:** `solaraussy` has timing, reflection, altitude, and sunscreen
  inputs in [`src/solara/planner.py`](https://github.com/ussyverse/solaraussy/blob/HEAD/src/solara/planner.py).
- **Exists:** `compostaussy` models coarse carbon/nitrogen, moisture,
  structure, phase, safety, and rescue planning in [`src/lib.rs`](https://github.com/ussyverse/compostaussy/blob/HEAD/src/lib.rs).

**Missing integration work.** Link a task to a zone and optional compost batch;
define whether a weather reading applies to a whole site or one microclimate;
avoid turning qualitative soil labels into agronomic prescriptions; and keep
worker safety gates ahead of productivity suggestions.

**Maturity and feasibility.** **Exists** components support a local notebook
well. **Unverified:** crop-specific recommendations, sensor accuracy, and
whether source thresholds suit a particular garden. Compost safety and heat
guidance require conservative unknown handling.

**Smallest useful demo.** Record two zones, one compacted path, one compost
batch, and a hot afternoon reading. Generate a morning work card and compare it
with a cooler-day scenario.

**Acceptance criteria.** Zone observations are preserved verbatim; the planner
can defer a task; compost actions expose their input assumptions; heat or UV
flags never become a “safe to work” assertion; and the card names when to stop
and consult local guidance.

**Why combine?** Tiltha supplies the garden state, Wetbulba and Solara bound
the work window, and Composta makes an otherwise separate batch part of the
same recurring maintenance loop.

**Rejected adjacent components.** `ussyverse/ethylenoussy` was held out because
produce storage is post-harvest and would distract from proving a zone/task
workflow. It is a better fit for the separate harvest notebook below.

## 6. Harvest-to-Storage Notebook

**Exact repositories:** `ussyverse/ethylenoussy` + `ussyverse/tilthaussy` +
`ussyverse/compostaussy`

**User and recurring pain.** A small grower harvests mixed produce over several
weeks but loses track of ripeness, storage separation, and which bed or batch
produced it.

**Product promise.** “Keep a traceable harvest note that explains storage
recommendations without pretending to know more than the observations show.”

**Flow:** bed/zone record, harvest item, observed ripeness, produce quantity,
storage location, and optional compost return -> apply ethylene compatibility
and storage-zone rules, retain garden provenance, and record compost disposition
-> printable harvest label, storage map, and follow-up checklist.

**Existing source to reuse.**

- **Exists:** `ethylenoussy` defines produce ripeness, storage zones, ethylene
  interactions, and recommendations in [`ethyleno.h`](https://github.com/ussyverse/ethylenoussy/blob/HEAD/ethyleno.h)
  and [`ethyleno.c`](https://github.com/ussyverse/ethylenoussy/blob/HEAD/ethyleno.c).
- **Exists:** `tilthaussy` has garden zones and observations in [`src/tiltha/models.py`](https://github.com/ussyverse/tilthaussy/blob/HEAD/src/tiltha/models.py).
- **Exists:** `compostaussy` has batch phases and rescue/safety outputs in
  [`src/lib.rs`](https://github.com/ussyverse/compostaussy/blob/HEAD/src/lib.rs).

**Missing integration work.** Create stable `bedId`, `harvestId`, and
`batchId` values; distinguish edible storage from compost disposal; capture
actual temperature/humidity as optional observations; and avoid treating a
coarse compatibility rule as a food-safety guarantee.

**Maturity and feasibility.** **Exists** is a rule-based storage model and
small garden/compost data model. **Unverified:** cultivar-specific behavior,
actual storage conditions, and shelf-life predictions. The MVP should provide
labels and reminders, not expiration promises.

**Smallest useful demo.** Log tomatoes, apples, and leafy greens from two beds,
apply a storage layout, and mark one item as composted with a linked reason.

**Acceptance criteria.** Every recommendation shows the observed inputs; an
unknown ripeness or storage condition is explicit; food-safety claims are not
made; and provenance survives CSV/JSON export.

**Why combine?** Ethyleno answers “which items should be separated?”, Tiltha
answers “where did this come from?”, and Composta closes the loop on what is
not stored or eaten. The shared entity is a harvest record.

**Rejected adjacent components.** `ussyverse/plantaussy` was rejected because
the inspected implementation is focused on footwear and foot-zone exposure,
not plant identity or crop yield. Similar naming is not evidence of a useful
plant-care handoff.

## 7. Community Garden Coverage Board

**Exact repositories:** `ussyverse/apicolaussy` + `ussyverse/commonsaussy` +
`ussyverse/tilthaussy`

**User and recurring pain.** A volunteer garden coordinator knows that beds
need watering, harvest, or repair but cannot match bounded tasks to available
helpers without exposing more personal information than necessary.

**Product promise.** “Turn observed garden needs into private, time-bounded
asks and retire each ask when covered.”

**Flow:** zone observations and tasks -> Apicola skill/availability/trust
matching -> Commonsa pledge, threshold, and privacy projection -> coordinator
board with task owner, expiry, status, and unresolved coverage gaps.

**Existing source to reuse.**

- **Exists:** `apicolaussy` models gardening skills, availability, trust, needs,
  and a community ledger in [`src/lib/apicola.ts`](https://github.com/ussyverse/apicolaussy/blob/HEAD/src/lib/apicola.ts).
- **Exists:** `commonsaussy` models residents, pledges, contribution
  thresholds, and privacy levels in [`src/commonsa/models.py`](https://github.com/ussyverse/commonsaussy/blob/HEAD/src/commonsa/models.py).
- **Exists:** `tilthaussy` models zones, soil observations, and traffic/task
  context in [`src/tiltha/models.py`](https://github.com/ussyverse/tilthaussy/blob/HEAD/src/tiltha/models.py).

**Missing integration work.** Define a garden task taxonomy and stable task
IDs; allow a coordinator to publish only the minimum location/detail; add
expiry and cancellation semantics; and ensure trust is not converted into a
general person ranking. A volunteer must be able to decline without penalty.

**Maturity and feasibility.** **Exists** are data models and matching/pledge
concepts. **Unverified:** durable multi-user storage, notification delivery,
and real privacy behavior. The first version should be a local export/import
board with explicit consent.

**Smallest useful demo.** Add three garden tasks, three helpers with different
availability, publish two bounded asks, accept one pledge, and close the ask
without exposing private notes.

**Acceptance criteria.** Closed tasks disappear from active asks; no task is
assigned without an explicit pledge; private fields are excluded from the
volunteer view; and unresolved needs show missing coverage rather than a
failure score.

**Why combine?** Tiltha supplies legitimate work, Apicola matches capacity, and
Commonsa supplies a bounded social commitment and privacy projection. The
shared entity is a garden task with a lifecycle.

**Rejected adjacent components.** `ussyverse/hoistussy` was not included even
though it appears in the existing volunteer-gap idea; the goal here is a
garden-specific task boundary, and adding another notice lifecycle before
testing the pledge flow would repeat rather than improve it.

## 8. Allergy-Aware Nature Observation Walk

**Exact repositories:** `ussyverse/palynoussy` + `ussyverse/obscuraussy` +
`ussyverse/celestialussy`

**User and recurring pain.** A nature photographer or field naturalist wants to
keep a useful observation record while tracking personal allergy symptoms and
light/time constraints, but does not want a speculative pollen forecast to
masquerade as medical advice.

**Product promise.** “Make an observation walk easier to review by keeping the
scene, exposure notes, and personal response in one dated packet.”

**Flow:** walk route and timing, manual environmental observations, symptoms or
exposure notes, photo-walk constraints, and waypoints -> record Palyno trigger
matching with uncertainty, Obscura session/constraint data, and Celestial route
timing -> private observation packet with photo IDs, timestamps, symptom notes,
and follow-up questions for a clinician when appropriate.

**Existing source to reuse.**

- **Exists:** `palynoussy` models exposure, symptoms, interventions, lag
  matching, trigger scores, and uncertainty in [`src/lib.zig`](https://github.com/ussyverse/palynoussy/blob/HEAD/src/lib.zig).
- **Exists:** `obscuraussy` supports photo-walk session configuration, walking
  mobility, light notes, constraints, notes, and photo IDs in [`obscura/config.py`](https://github.com/ussyverse/obscuraussy/blob/HEAD/obscura/config.py).
- **Exists:** `celestialussy` has typed waypoints, route legs, and timing/recovery
  structures in [`src/index.ts`](https://github.com/ussyverse/celestialussy/blob/HEAD/src/index.ts).

**Missing integration work.** Use one local `walkId` and stable observation
IDs; link photos to observations without assuming image analysis; separate
user-reported symptoms from environmental facts; and prevent Palyno scores from
being rendered as diagnosis, forecast, or exposure clearance.

**Maturity and feasibility.** **Exists** supports structured journaling and
heuristic matching. **Unverified:** pollen source data, medical validity, and
camera metadata ingestion. The safest MVP has manual inputs only.

**Smallest useful demo.** Record two walks at different times, attach three
photo IDs and symptom notes to each, and export a private comparison showing
what was observed versus inferred.

**Acceptance criteria.** No external pollen claim is generated; symptoms are
never scored into a diagnosis; photos can be omitted; uncertainty is retained;
and export has a privacy warning and clinician-directed question list.

**Why combine?** Obscura provides the creative observation surface, Celestial
provides a route/time spine, and Palyno adds a cautious personal response log.
The shared entity is a walk observation, not a health profile.

**Rejected adjacent components.** `ussyverse/solaraussy` was excluded from the
first version because UV exposure would add another health-relevant heuristic
without improving the manual observation record. It can be a separate,
explicitly optional field later.

## 9. Rain-Event Home and Trail Readiness Packet

**Exact repositories:** `ussyverse/sumpaussy` + `ussyverse/watershedussy` +
`ussyverse/arroyonaussy`

**User and recurring pain.** A homeowner near a trail, creek, or canyon wants a
single pre-storm checklist for basement equipment and outdoor route conditions,
but household readiness and route decisions are documented separately.

**Product promise.** “Collect the evidence you have, identify unknowns, and
route high-consequence conditions to qualified or official help.”

**Flow:** sump measurements, pump curve, discharge path, backup status,
watershed waypoints/water sources, and manually supplied rain/route observations
-> calculate conservative sump readiness cards and watershed carry/condition
context, while Arroyona applies explicit canyon/flood action gates -> printable
home-and-outdoor packet with route-away conditions, professional questions, and
no-go unknowns.

**Existing source to reuse.**

- **Exists:** `sumpaussy` defines route-away flags, pump curves, pit/discharge
  measurements, backup status, readiness cards, and a conservative disclaimer
  in [`src/lib.rs`](https://github.com/ussyverse/sumpaussy/blob/HEAD/src/lib.rs).
- **Exists:** `watershedussy` defines route/water-source/weather types and
  `CalculateCarryLegs` in [`pkg/hydro/types.go`](https://github.com/ussyverse/watershedussy/blob/HEAD/pkg/hydro/types.go)
  and [`pkg/hydro/carry.go`](https://github.com/ussyverse/watershedussy/blob/HEAD/pkg/hydro/carry.go).
- **Exists:** `arroyonaussy` provides a conservative canyon/flash-flood action
  model and disclaimer in [`src/lib.rs`](https://github.com/ussyverse/arroyonaussy/blob/HEAD/src/lib.rs).

**Missing integration work.** Keep property and route records separate; add a
storm-event ID and timestamp; require official forecasts and land-manager
conditions as external inputs; and make any electrical, structural, sewage,
unknown-water, or active-flooding flag an immediate route-away gate.

**Maturity and feasibility.** **Exists** are conservative worksheets, not a
flood model or emergency service. **Unverified:** pump assumptions in a real
property, local discharge codes, trail closure feeds, and cross-domain event
timing. This product should be a packet generator, not a unified risk score.

**Smallest useful demo.** Enter one sump sample and one manually observed trail
route, then generate a packet containing separate home and route cards. Toggle
an unsafe electrical flag and verify that the packet stops DIY instructions.

**Acceptance criteria.** Route-away reasons are preserved verbatim; no flood
probability is invented; household readiness never implies trail safety; all
unknowns are visible; and the export names the official sources a user must
check.

**Why combine?** Sumpa handles a concrete household readiness worksheet,
Watershed handles route/water logistics, and Arroyona provides an outdoor flood
stop boundary. The shared entity is a storm event with independent evidence
streams.

**Rejected adjacent components.** `ussyverse/fulguraussy` was not added because
lightning timing is a different hazard event and would make the packet harder to
audit. A future hazard bundle should compose independent cards, not merge their
heuristics.

## 10. Ethical Field Collection and Preservation Log

**Exact repositories:** `ussyverse/taphonussy` + `ussyverse/obscuraussy` +
`ussyverse/palynoussy`

**User and recurring pain.** An educator, citizen scientist, or naturalist
needs to document an outdoor object or trace without losing the observation
context, preservation conditions, or personal exposure notes. Physical
collection can also be restricted or harmful if provenance and permissions are
ignored.

**Product promise.** “Keep a reversible field record before deciding whether
anything should be collected, preserved, or shared.”

**Flow:** walk/session metadata, photo IDs, object/trace description, permission
and location sensitivity, preservation item/risk notes, and exposure symptoms
-> create a Taphon preservation triage record, an Obscura observation session,
and an optional Palyno personal exposure note -> private field packet with
chain of custody, unresolved identification, handling warnings, and a
redacted-share export.

**Existing source to reuse.**

- **Exists:** `taphonussy` models keepsake-preservation items and risk pathways
  in [`src/lib.rs`](https://github.com/ussyverse/taphonussy/blob/HEAD/src/lib.rs).
- **Exists:** `obscuraussy` supports photo-walk environment, mobility, light
  notes, constraints, notes, and photo references in [`obscura/config.py`](https://github.com/ussyverse/obscuraussy/blob/HEAD/obscura/config.py).
- **Exists:** `palynoussy` models exposure, symptoms, intervention, lag, trigger
  score, and uncertainty in [`src/lib.zig`](https://github.com/ussyverse/palynoussy/blob/HEAD/src/lib.zig).

**Missing integration work.** Add permission, land ownership, protected-status,
and location-sensitivity fields; distinguish an observation from a collected
item; preserve originals and redacted projections; and make “do not collect” a
first-class outcome. No component should infer legal permission or ecological
impact from a photo.

**Maturity and feasibility.** **Exists** are preservation and journaling
structures. **Unverified:** field taxonomy, conservation rules, chain-of-custody
requirements, and medical implications of exposure notes. The first version
should support documentation-only records.

**Smallest useful demo.** Log three observations, one permitted collected item,
and one restricted location. Export a private full packet and a public packet
with location and personal fields removed.

**Acceptance criteria.** Observation and collection states cannot be confused;
restricted locations are redacted by default; no preservation action bypasses a
permission check; uncertainty is visible; and the export preserves original
photo IDs without exposing local paths.

**Why combine?** Obscura captures the field encounter, Taphon organizes
preservation risk, and Palyno keeps a separate personal exposure trail. The
shared entity is a field record with an explicit permission state.

**Rejected adjacent components.** `ussyverse/cartoucheussy` was excluded
because its inspected strength is manuscript line/apparatus validation, not
field-object identity. Adding it would create a second evidence vocabulary
without improving the collection decision.

## Rejected Ideas

### A. Universal Outdoor Safety Score

**Rejected combination:** `wetbulbaussy` + `solaraussy` + `beaufortaussy` +
`arroyonaussy` + `fulguraussy`.

The components have potentially useful independent checklists, but a single
green/yellow/red score would hide different units, missing observations, and
different stop conditions. The result would invite users to treat a heuristic
as clearance. Prefer the separate hazard cards in ideas 1, 4, and 9, each with
its own evidence and route-away behavior.

### B. AI Trail Condition Predictor from Repository Metaphors

**Rejected combination:** `ussyverse/currentussy` + `ussyverse/taphonussy` +
`ussyverse/modesaussy` + a new model trained on trip notes.

The inspected components provide personal travel heuristics, preservation
records, and failure-mode planning, not trail-condition observations or a
validated predictive dataset. Turning personal notes and metaphorical labels
into a forecast would be unsupported and potentially unsafe. A manual,
source-linked observation log is acceptable; an automated trail prediction is
not.

## Evidence and Reproducibility

### Scope and limitations

The catalog and prior source-checked report screened 459 entries. This pass
focused on 22 candidate `ussyverse` repositories used above and inspected
source files, models, engines, and manifests where relevant. No candidate
repository was modified, built, installed, or runtime-tested. Existing tests
and manifests were treated as intended contracts, not proof that a package
currently passes or works in deployment.

### Pinned revisions inspected

The following are the checked-out `HEAD` values obtained with the command
listed below:

| Repository | HEAD |
|---|---|
| `ussyverse/acclimaussy` | `39b4fe9651a2cd8cfe7fbc1ae6d36402d43ce48a` |
| `ussyverse/arroyonaussy` | `6d80b397ff3ab1ab9901fab3b46ff78b4e1c3d70` |
| `ussyverse/apicolaussy` | `a7d9a743f79f3e196fdf8df0f4dc8c5976429809` |
| `ussyverse/beaufortaussy` | `36a9bd2e3d20b85a1183cd0a6852c34ce763b997` |
| `ussyverse/celestialussy` | `2fbe197a258d306871b2e3a3298d68271683b30d` |
| `ussyverse/cloforaussy` | `3b967eb9e498625ea896058828bc3eda2957cf7b` |
| `ussyverse/compostaussy` | `d27eaca5ed5987533c74e7c08e5e598e219ed8a1` |
| `ussyverse/currentussy` | `8227d1f189c1e553a8df736fc8e166c0476e0a31` |
| `ussyverse/ethylenoussy` | `0d2206edc20b19cd06989553e83007c00269ddb7` |
| `ussyverse/fulguraussy` | `2598ebfa2a9b1502f28585c1427872a6f070d7ad` |
| `ussyverse/koppenussy` | `1f539a4298c79c93262e727c4c8fd6096280e408` |
| `ussyverse/migrationussy` | `493a598c8decc3506e35ac91013e5463df524259` |
| `ussyverse/obscuraussy` | `3c91b6590695ee90da244774bec0640900dbe3b5` |
| `ussyverse/palynoussy` | `c12a506836b0752873aef64a330c4cadfd7d7764` |
| `ussyverse/plantaussy` | `b4b66466832d60f3ea3ecff77d1ecd07a6e84450` |
| `ussyverse/portolanussy` | `39736975ed88da4fc6c87d5fc65e3f0b9b141d74` |
| `ussyverse/solaraussy` | `437c8d3ea6de3fe3491eec5ddf2b2c95d1f288fd` |
| `ussyverse/sumpaussy` | `0d0fb785b4a63ac36caa4658200a11e28fcd0e4c` |
| `ussyverse/taphonussy` | `432c97d8d0e4948ad105c9d58adf6eaaeff07212` |
| `ussyverse/tilthaussy` | `b5864509f2810ef89680e556569d464fa1b850eb` |
| `ussyverse/watershedussy` | `c5c7cb668b224dbe95cb01b288d3da3736f5d6e5` |
| `ussyverse/wetbulbaussy` | `ca31da2aa15664a72b8a41482b900f51ac435c90` |

### Commands actually run

- Read `README.md`, `AGENTS.md`, `docs/SOURCE_CHECKED_COMBINATIONS.md`,
  `docs/REPOSITORY_INDEX.md`, and `docs/INITIAL_COMBINATIONS.md`.
- Inspected the source paths linked in each proposal using the workspace file
  reader.
- Ran `git -C /home/ubuntu/ussy/repos/ussyverse/<repository> rev-parse HEAD`
  for each repository in the revision table.
- No build, install, or test command was run.

## Next Validation Steps

1. Pick one concept, preferably the Trail Water and Heat Card or the Garden
   Workday Planner, and write a minimal cross-repository schema before building
   any UI.
2. Run each selected component's existing tests at the pinned revisions and
   record results; do not treat the result as proof of field validity.
3. Exercise the adapter with user-authored data, missing values, unit changes,
   and conflicting timestamps.
4. Validate the output and safety language with target users and relevant
   land-manager or professional guidance before adding live data feeds.
