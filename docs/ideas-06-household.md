# Household Organization Product Ideas

**Date:** 2026-09-13

**Scope:** New product proposals for ordinary household organization, recurring
planning, and human-confirmed handoffs. These are proposals, not existing
integrations.

## Research Notes

This pass started from the household, organization, purchase, travel, and
conservative decision-card entries in [REPOSITORY_INDEX.md](REPOSITORY_INDEX.md),
then compared candidates with the existing [source-checked shortlist](SOURCE_CHECKED_COMBINATIONS.md).
The current shortlist already covers `raciaussy` + `transactaussy` for household
handoff rehearsal, `retouraussy` + `prospectaussy` for returns, and
`speleoussy` + `apoptosisussy` as the indexed home-organization pairing. The
ideas below use different combinations or a materially different end-user
workflow.

Repositories were inspected from shallow clones under `/home/ubuntu/ussy/repos`
on 2026-09-13. Revision identifiers were not captured in this pass. Source
inspection used file reads; no candidate repository was modified, built,
installed, or runtime-tested, and no tests are claimed to pass. **Unverified:**
runtime behavior, revision-specific interfaces, and every cross-repository
adapter described below. Links use `HEAD` because exact revisions still need to
be pinned before implementation.

The ordering is a product judgment based on recurring usefulness,
complementarity, concrete source reuse, local demonstrability, and limited
adapter work. Every proposal keeps raw inputs and component reports beside any
derived summary. Scores, classifications, and forecasts are planning aids, not
proof of causality or professional advice.

## Ranking

| Rank | Working title | Exact repositories | Shared entity | Local prototype estimate |
|---|---|---|---|---|
| 1 | Household week pact | `mojomast/familydashboardussy` + `ussyverse/equilibriaussy` + `ussyverse/quorumussy` | Weekly task and decision | 4-7 days |
| 2 | Seasonal home stewardship board | `ussyverse/phenoaussy` + `ussyverse/capillaussy` + `ussyverse/formicaussy` | Seasonal action window | 4-6 days |
| 3 | Use-first kitchen loop | `ussyverse/ethylenoussy` + `ussyverse/myceliumussy` + `ussyverse/compostaussy` | Food item / kitchen batch | 5-8 days |
| 4 | Room reset before the pile | `ussyverse/speleoussy` + `ussyverse/sortariaussy` + `ussyverse/formicaussy` | Room surface and reset task | 4-6 days |
| 5 | Household papers and warranty finder | `ussyverse/mustiaussy` + `ussyverse/sortariaussy` + `ussyverse/patchwiseussy` | Document or record | 4-7 days |
| 6 | Small repair decision packet | `ussyverse/crackwiseussy` + `ussyverse/adheraussy` + `ussyverse/pokayokeussy` | Repair case | 4-7 days |
| 7 | Leave-the-house run packet | `ussyverse/forageussy` + `ussyverse/prospectaussy` + `ussyverse/portolanussy` | Errand run | 4-7 days |
| 8 | Find it, then give it a home | `ussyverse/saccadaussy` + `ussyverse/patchwiseussy` + `ussyverse/prospectaussy` | Lost-item episode | 3-5 days |
| 9 | Room comfort observation loop | `ussyverse/psychraussy` + `ussyverse/adsorbaussy` + `ussyverse/formicaussy` | Observation and follow-up task | 4-6 days |
| 10 | Guest visit setup blueprint | `ussyverse/hospitiaussy` + `ussyverse/ritualaussy` + `ussyverse/quorumussy` | Visit and transition | 4-7 days |

## 1. Household Week Pact

**Exact repositories:** `mojomast/familydashboardussy`,
`ussyverse/equilibriaussy`, and `ussyverse/quorumussy`.

**User and recurring pain.** Roommates, partners, or families repeatedly
renegotiate chores, meals, and small household obligations. A list of assigned
tasks does not show whether the effort is balanced or which unresolved choices
still need agreement.

**Product promise.** "Make this week's work visible, negotiate the disputed
parts, and leave each person with an inspectable plan."

**Flow:** task templates, recurrence, completions, members, rough effort, and
preferences -> Equilibria produces candidate allocations and fairness/ledger
reports -> Quorum records only the choices that need a group decision -> a
weekly board with owner, due date, effort, decision record, and completion
history.

**Existing source to reuse.** **Exists:**
[familydashboardussy task and profile types](https://github.com/mojomast/familydashboardussy/blob/HEAD/src/types.ts)
and [recurrence calculation](https://github.com/mojomast/familydashboardussy/blob/HEAD/src/lib/recurrence.ts)
provide recurring instances, completions, assignments, and household roles.
**Exists:** `ussyverse/equilibriaussy/src/lib.rs` contains chore/resource bid
tables, allocation, fairness, envy, and ledger reports. **Exists:**
`ussyverse/quorumussy/internal/quorum/model.go` models persisted decision files,
members, options, weighted ballots, vetoes, and tolerance.

**Missing integration work.** Define a small canonical `HouseholdTask` with
stable IDs, duration/effort units, availability, and an explicit reason for
each proposed assignment. Translate Equilibria's bids into board edits rather
than silently applying them. Put a group decision link on a task revision and
render a printable weekly packet. The local grocery adapter in the dashboard is
not evidence of a working shopping integration, so groceries stay out of the
first slice.

**Maturity and feasibility caveats.** The dashboard has a useful model and UI
surface, but its local persistence and data-access behavior need runtime
verification. Equilibria's fairness is a model over supplied ratings, not an
objective measure of household labor. Quorum's weights and vetoes should be
visible to participants rather than presented as neutral truth.

**Smallest useful demo.** Enter four recurring chores for two roommates, show a
candidate allocation, change one effort estimate, record a decision about the
remaining disputed task, and export the week as Markdown/JSON.

**Acceptance criteria.** Every displayed task has a stable ID, owner, date, and
raw effort input. A user can reject a proposed allocation. A decision remains
linked to the task version that prompted it. Completed instances do not mutate
historical weeks.

**Why better than separate tools.** The dashboard supplies the calendar
surface, Equilibria exposes the burden tradeoff, and Quorum preserves the
agreement. Separate task lists and a separate poll cannot show whether the
poll actually changed the plan.

**Rejected adjacent components.** `ussyverse/raciaussy` +
`ussyverse/transactaussy` is not included because its household handoff
rehearsal is already a source-checked proposal. `ussyverse/orbitalussy` is held
for a later goal/stability product; adding its goal model here would introduce
another score without improving the weekly task artifact.

## 2. Seasonal Home Stewardship Board

**Exact repositories:** `ussyverse/phenoaussy`, `ussyverse/capillaussy`, and
`ussyverse/formicaussy`.

**User and recurring pain.** A plant owner or renter with a small garden loses
track of seasonal preparation, plant-care experiments, and the recovery work
after a missed window. Generic recurring reminders fire at the wrong time or
do not carry forward what happened last season.

**Product promise.** "Turn observed seasonal cues into a short preparation,
care, and recovery board."

**Flow:** manually entered season context, cues, thermal signals, plant cards,
and care observations -> Phenoa computes watch/prepare/act/wind-down/recover
windows -> Capilla contributes plant watering assessments and vacation handoff
notes -> Formica ranks the resulting concrete tasks by urgency, effort, and
cue context -> a dated stewardship board and handoff card.

**Existing source to reuse.** **Exists:**
[Phenoa models](https://github.com/ussyverse/phenoaussy/blob/HEAD/src/phenoa/models.py)
define `SeasonContext`, `CueObservation`, `ThermalSignal`, `SeasonalTask`, and
`ActionWindow`; [its engine](https://github.com/ussyverse/phenoaussy/blob/HEAD/src/phenoa/engine.py)
handles cue matching, lead times, false-spring risk, and recovery. **Exists:**
[`capillaussy/src/lib.rs`](https://github.com/ussyverse/capillaussy/blob/HEAD/src/lib.rs)
contains plant, pot, watering-event, follow-up-observation, hydraulic
assessment, and `vacation_handoff` logic. **Exists:** `ussyverse/formicaussy/src/formica.nim`
models task kinds/statuses, effort, cues, pheromone momentum, and stale-task
health.

**Missing integration work.** Add a shared task ID and make a plant-care
handoff an ordinary task packet, not an automatic watering command. Keep
Phenoa's matched cues and thermal values beside the output. Add a simple local
editor for observations and a manual next-review date.

**Maturity and feasibility caveats.** Phenoa's season model depends on coarse
regions and manually entered observations; it is not a weather service. Capilla
uses a small hydraulic model and observations, not a plant-identification or
horticultural authority. Formica's prioritization is heuristic. The product
should say "review this window" rather than "the plant needs water now."

**Smallest useful demo.** Create a spring repotting task and two plant cards,
enter a warm-spell observation plus a frost-risk observation, generate a
prepare-state board, and export a vacation handoff for one plant.

**Acceptance criteria.** A false-spring case never becomes an unconditional
act instruction. A missed window emits the task's recovery action. A receiving
person can see the raw plant observations and the last care event. No external
weather or notification service is required.

**Why better than separate tools.** Seasonal timing, plant-specific care, and
task follow-through meet at one action window. The output is a short care packet
rather than three unrelated reports.

**Rejected adjacent components.** Heat, storm, and other emergency engines are
not included: they would shift an ordinary garden planner toward a safety
authority and require different evidence and escalation boundaries.

## 3. Use-First Kitchen Loop

**Exact repositories:** `ussyverse/ethylenoussy`, `ussyverse/myceliumussy`, and
`ussyverse/compostaussy`.

**User and recurring pain.** Home cooks repeatedly discover produce that is
near peak, leftovers with no obvious next use, or kitchen scraps that need a
separate disposal decision. A shopping list alone does not connect condition,
meal opportunity, and the final discard/compost route.

**Product promise.** "Use the food that needs attention first, then route what
remains to an appropriate next step."

**Flow:** produce CSV plus manually tagged pantry/leftover ingredients and
compost observations -> Ethyleno ranks urgency, storage conflicts, and meal
timing -> Mycelium grows dish suggestions, substitutions, and decomposition
uses from available ingredients -> Composta assesses a separately entered scrap
batch and emits a rescue or local-guidance card -> a use-first kitchen board
with meal candidates, storage moves, and disposal notes.

**Existing source to reuse.** **Exists:**
[`ethylenoussy/ethyleno.h`](https://github.com/ussyverse/ethylenoussy/blob/HEAD/ethyleno.h)
and [`ethylenoussy/ethyleno.c`](https://github.com/ussyverse/ethylenoussy/blob/HEAD/ethyleno.c)
provide CSV inventory parsing, ripeness/stage and storage-zone models,
urgency, pair-conflict scoring, and recommendations. **Exists:**
[`myceliumussy/src/mycelium/data.py`](https://github.com/ussyverse/myceliumussy/blob/HEAD/src/mycelium/data.py)
contains the curated ingredient substrate and decomposition notes; its
[network engine](https://github.com/ussyverse/myceliumussy/blob/HEAD/src/mycelium/network.py)
provides dish suggestions, substitution chains, symbiotic clusters, and
leftover decomposition suggestions. **Exists:** [`compostaussy/src/lib.rs`](https://github.com/ussyverse/compostaussy/blob/HEAD/src/lib.rs)
models feedstock, moisture, structure, phase, odor, and safety flags.

**Missing integration work.** Create a `KitchenItem` wrapper that distinguishes
produce, planned food, leftovers, and scraps. Do not infer that a suggested
dish is safe to eat from a ripeness score. Keep the compost assessment as a
separate user-confirmed batch after food has been discarded. Add dietary
constraints and household servings as explicit fields rather than treating the
curated dish list as a recipe database.

**Maturity and feasibility caveats.** Ethyleno's profiles and urgency are
coarse rules; Mycelium is a curated flavor graph, not a recipe validator;
Composta explicitly does not certify pathogen kill or replace local guidance.
Mold, uncertain food condition, allergy, and local compost rules need a stop or
refer-out state, not a clever meal suggestion.

**Smallest useful demo.** Enter bananas, spinach, tomatoes, and stale bread;
show a storage conflict, two use-first dish candidates, then assess a small
post-discard compost batch and export the resulting board.

**Acceptance criteria.** The board never turns a compost-only or safety-flagged
item into a meal. Every dish suggestion lists its missing bridges and source
ingredients. The user can override a suggested storage move and see the raw
reasoning.

**Why better than separate tools.** Ethyleno handles condition, Mycelium
handles culinary opportunity, and Composta handles the final material route.
The value is reducing one kitchen item's entire decision loop, not adding a
generic recipe dashboard.

**Rejected adjacent components.** `mojomast/familydashboardussy` has recipe
and meal-plan types, but it is not used in the first slice because its current
schema does not supply the inventory-condition join and would add persistence
surface before the use-first loop is validated.

## 4. Room Reset Before the Pile

**Exact repositories:** `ussyverse/speleoussy`, `ussyverse/sortariaussy`, and
`ussyverse/formicaussy`.

**User and recurring pain.** A household has a few recurring landing surfaces:
the entry table, kitchen counter, chair, or mail shelf. By the time the pile is
obvious, nobody knows which surface is the source or which reset is worth doing
first.

**Product promise.** "Find the surfaces that create the next pile, sort the
items there into usable destinations, and schedule the smallest reset."

**Flow:** room dimensions, surfaces, traffic, drip sources, and rough capacity
-> Speleoussy ranks clutter-prone surfaces and forecasts accumulation -> cards
for the observed items go through Sortaria's open/closed/hybrid sort and
retrieval analysis -> Formica turns the selected reset into a bounded task with
an owner and cue -> a room reset card plus a next-week check.

**Existing source to reuse.** **Exists:**
[`speleoussy/internal/models/models.go`](https://github.com/ussyverse/speleoussy/blob/HEAD/internal/models/models.go)
defines chambers, surfaces, drip sources, capacities, and forecasts; [its
analysis](https://github.com/ussyverse/speleoussy/blob/HEAD/internal/analysis/analysis.go)
classifies surfaces and predicts four-, twelve-, and twenty-six-week clutter.
**Exists:** [`sortariaussy/internal/sortaria/model.go`](https://github.com/ussyverse/sortariaussy/blob/HEAD/internal/sortaria/model.go)
defines item cards, piles, assignments, ambiguity, label quality, and retrieval
drills. **Exists:** `ussyverse/formicaussy/src/formica.nim` supplies task status,
effort, cues, and stale-task analysis.

**Missing integration work.** Define a `SurfaceID` and map each reset card to a
specific surface and item pile. Preserve the human's pile labels instead of
auto-generating a taxonomy from clutter. Add a before/after observation so a
forecast can be checked against what actually accumulated.

**Maturity and feasibility caveats.** Speleoussy's "cave-in" and dissolution
language is a metaphorical clutter forecast; its capacity values are supplied
by the user and are not a structural hazard assessment. Sortaria's retrieval
success rate needs actual drills. Formica's task score should not become a
household performance grade.

**Smallest useful demo.** Model an entry table with three drip sources, sort ten
items into four piles, generate one five-minute reset, and repeat the same
surface check after a week of manually recorded observations.

**Acceptance criteria.** The product identifies the source surface and its raw
rate assumptions. Ambiguous items remain visible as ambiguous. A reset can be
completed without opening another application. The second observation is not
silently treated as validation of the forecast.

**Why better than separate tools.** Speleoussy explains where accumulation
starts, Sortaria explains where objects should live, and Formica creates a
follow-through action. A decluttering report without the surface and reset
loop would not change the recurring problem.

**Rejected adjacent components.** `ussyverse/apoptosisussy` is not paired with
Speleoussy here because that exact complementary pairing is already named in
the repository index. Its keep/remove lifecycle would also shift this concept
from recurring surface maintenance to a different decluttering decision.

## 5. Household Papers and Warranty Finder

**Exact repositories:** `ussyverse/mustiaussy`, `ussyverse/sortariaussy`, and
`ussyverse/patchwiseussy`.

**User and recurring pain.** Households accumulate receipts, warranties,
manuals, renewal notices, and scanned records. They can decide what to retain
but still fail to find the surviving document when an appliance or lease issue
appears.

**Product promise.** "Decide what a household record is for, put it in a
retrievable place, and test that the future cue is good enough."

**Flow:** manually entered document cards and retention exceptions -> Mustia
places each item in a review/keep/archive decision lane -> Sortaria tests labels,
facets, ambiguity, and retrieval drills -> Patchwise scores titles, paths, URLs,
dates, snippets, duplicate trails, and refinding scent -> a retention ledger,
clean index, and one recovery drill for each important record.

**Existing source to reuse.** **Exists:** `ussyverse/mustiaussy/src/mustia.ts`
contains document item cards, retention exceptions, collection types, and
decision lanes. **Exists:** [`sortariaussy/internal/sortaria/model.go`](https://github.com/ussyverse/sortariaussy/blob/HEAD/internal/sortaria/model.go)
provides card sorts, category candidates, ambiguity detection, facet rules, and
retrieval drills. **Exists:** [`patchwiseussy/src/lib.zig`](https://github.com/ussyverse/patchwiseussy/blob/HEAD/src/lib.zig)
provides scent/refindability audits, duplicate grouping, repair priorities, and
cue-only refinding drills.

**Missing integration work.** Add a stable `RecordID`, document type, owner,
retention reason, storage location, and sensitivity level. Build a local import
editor for filenames and user-entered metadata; neither Patchwise nor Mustia
provides OCR or a managed document vault. Ensure exports do not expose private
paths or contents accidentally.

**Maturity and feasibility caveats.** The result is a metadata and retrieval
tool, not legal retention advice, tax advice, or document authenticity
verification. Sortaria's category and label scores are heuristics. Patchwise
can score a cue but cannot prove the underlying file still exists or is readable
without a separately implemented check.

**Smallest useful demo.** Add a dishwasher receipt, lease renewal note, and
manual; retain/archive two of them, run a sort, repair weak filenames, and
successfully complete a manual "find the warranty" drill.

**Acceptance criteria.** Every retained record has an explicit retention reason
and location. A retrieval drill records success or failure without changing the
record silently. Private metadata is excluded from a share export by default.

**Why better than separate tools.** Mustia handles the decision to keep, Sortaria
handles household vocabulary, and Patchwise handles future refinding. Their
shared record ID turns decluttering into reliable retrieval rather than a one-
time filing session.

**Rejected adjacent components.** `ussyverse/cartoucheussy` +
`ussyverse/archivioussy` is not used because it is already the source-checked
family-history archive proposal and has a different line-level evidence
problem. General OCR/RAG tools are also out of scope until the local metadata
workflow proves useful.

## 6. Small Repair Decision Packet

**Exact repositories:** `ussyverse/crackwiseussy`, `ussyverse/adheraussy`, and
`ussyverse/pokayokeussy`.

**User and recurring pain.** A renter, maker, or household member encounters a
small broken, loose, stuck, or poorly attached item. They need to choose whether
to repair, replace, or ask for help, and they often repeat the same mistake
during the repair.

**Product promise.** "Capture the case, choose a reversible next step, and make
the failure mode visible before trying again."

**Flow:** symptom, material, load, adhesive/substrate details, environment,
damage tolerance, and prior error notes -> Crackwise supplies conservative
repair-vs-replace classes -> Adhera evaluates adhesion/removal constraints and
risk cards -> Pokayoke classifies the household error and proposes a
countermeasure -> a repair packet with observations, stop conditions, chosen
experiment, and post-check.

**Existing source to reuse.** **Exists:** [`crackwiseussy/crackwise.go`](https://github.com/ussyverse/crackwiseussy/blob/HEAD/crackwise.go)
contains repair/replace decision classes and conservative repair logic.
**Exists:** [`adheraussy/src/adhera/models.py`](https://github.com/ussyverse/adheraussy/blob/HEAD/src/adhera/models.py)
and [`rules.py`](https://github.com/ussyverse/adheraussy/blob/HEAD/src/adhera/rules.py)
model substrates, adhesives, loads, environments, dwell time, removal risk,
and repair cards. **Exists:** [`pokayokeussy/pokayoke.py`](https://github.com/ussyverse/pokayokeussy/blob/HEAD/pokayoke.py)
parses error cases, classifies missing/wrong/interrupted/ownership mechanisms,
and emits countermeasure cards plus safety notes.

**Missing integration work.** Normalize material and severity vocabularies,
attach one error case to one repair experiment, and retain original inputs
beside each recommendation. Add explicit "stop and ask a qualified
professional" handling for electrical, gas, structural, legal, medical, or
other flagged cases. No automated action should alter a fixture.

**Maturity and feasibility caveats.** These are deterministic decision aids,
not engineering certification or product warranties. Adhesion and repair
outcomes depend on materials not represented by the small models. Pokayoke's
countermeasures improve process clarity but do not establish that a repair is
safe.

**Smallest useful demo.** Record a loose cable clip on a painted wall, compare
two reversible attachment options, show the removal-risk card, and add a
"wrong orientation" error case that produces a visible final-state cue.

**Acceptance criteria.** A high-risk input produces a route-away note rather
than a DIY instruction. Each proposed experiment names what to observe and
when to stop. The user can select "replace" or "ask for help" without being
forced through the repair path.

**Why better than separate tools.** Crackwise frames the decision, Adhera
frames the attachment-specific tradeoff, and Pokayoke addresses why the same
failure recurs. The artifact is a bounded repair packet, not a stack of scores.

**Rejected adjacent components.** Other repair/safety siblings such as
`ussyverse/hammeraussy` are not included because they were not source-audited
for this pass and would add another overlapping risk engine without a distinct
handoff.

## 7. Leave-the-House Run Packet

**Exact repositories:** `ussyverse/forageussy`, `ussyverse/prospectaussy`, and
`ussyverse/portolanussy`.

**User and recurring pain.** A household combines several errands with a
departure window, forgets the staged item, or spends time at a store without a
clear stopping rule. A route estimate alone does not make the run executable.

**Product promise.** "Turn needs and time constraints into a staged, cue-bound
run plan that a person can edit before leaving."

**Flow:** item needs, exact/any flexibility, manually entered store patches and
stock, travel windows, luggage or mobility notes, and a time budget -> Forage
assigns needs and builds a route/departure plan -> Portolan adds reserve and
transition timing -> Prospecta designs object-, location-, or event-bound cues
for the items and deadlines -> a printable run packet with route, shopping
list, staging checklist, and explicit unknowns.

**Existing source to reuse.** **Exists:** [`forageussy/pkg/forage/models.go`](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/models.go)
defines needs, stock, patches, routes, budgets, and assignments; [the engine](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/engine.go)
implements profitability assignment, store limits, nearest-neighbor/2-opt
routes, EROI, and marginal departure estimates. **Exists:**
`ussyverse/prospectaussy/prospecta.go` defines intentions, cues, cue plans,
miss classifications, aid recommendations, and deterministic cue scores.
**Exists:** `ussyverse/portolanussy/src/lib.rs` models travel windows, reserve
time, luggage, and mobility notes.

**Missing integration work.** Define a shared run ID and distinguish departure
time, store opening time, delivery deadline, and user-entered availability.
Render an item-staging card before route calculation. Add mandatory-stop and
deadline semantics rather than relying on Forage's value/profit ordering.

**Maturity and feasibility caveats.** Forage uses arbitrary coordinates and
Euclidean distance as a time proxy; it does not fetch live stock, opening hours,
traffic, or transit data. Prospecta designs cues but sends no notifications.
Portolan's reserve calculations are planning aids. The product must show these
unknowns and let the user override the route.

**Smallest useful demo.** Enter three needs across two manually modeled stores,
set a 90-minute budget and a departure window, generate a route, and print a
door-side staging card for one package and one reusable bag.

**Acceptance criteria.** The packet labels every stock and travel value as
user-entered or unknown. A user can mark a need mandatory and see when no route
meets it. The cue plan is still useful without OS notifications. The route is
never described as real-time optimized.

**Why better than separate tools.** Forage answers where to go, Portolan
answers how much transition slack to reserve, and Prospecta answers how the
items will be noticed at the right moment. The shared run artifact closes the
gap between planning and departure.

**Rejected adjacent components.** `ussyverse/retouraussy` +
`ussyverse/prospectaussy` is already the source-checked return workflow. This
concept deliberately handles ordinary multi-stop errands and does not add
return-stage semantics.

## 8. Find It, Then Give It a Home

**Exact repositories:** `ussyverse/saccadaussy`, `ussyverse/patchwiseussy`, and
`ussyverse/prospectaussy`.

**User and recurring pain.** A household loses keys, tools, documents, chargers,
or other ordinary objects, finds them once, and then loses them again because
the home location and future cue were never repaired.

**Product promise.** "Make this search less random, choose a stable home, and
add a cue for the next transition."

**Flow:** lost-item description, alternate appearances, likely containers,
rooms, surfaces, clutter, prior search passes, and intended home -> Saccada
creates a ranked one-pass search -> Patchwise checks the label/location cue and
refindability of the new home record -> Prospecta writes an if-then plan and
external-aid recommendation for the next leave/return/use event -> a recovery
episode plus a home-location card.

**Existing source to reuse.** **Exists:** [`saccadaussy/src/lib.rs`](https://github.com/ussyverse/saccadaussy/blob/HEAD/src/lib.rs)
models item templates, search zones, ordered search steps, anti-revisit memory,
interventions, and urgency guardrails. **Exists:** [`patchwiseussy/src/lib.zig`](https://github.com/ussyverse/patchwiseussy/blob/HEAD/src/lib.zig)
audits titles, paths, dates, snippets, duplicates, repair priority, and
cue-only refinding drills. **Exists:** `ussyverse/prospectaussy/prospecta.go`
provides implementation intentions, cue scoring, aid suggestions, and miss
classification.

**Missing integration work.** Add an ordinary `HomeSlot` record and distinguish
"found during search" from "verified home location." The product must not claim
to locate an object automatically. A home slot may be a shelf, tray, bag, or
named staging spot and should include a user-confirmed photo-free description.

**Maturity and feasibility caveats.** Saccada is not a tracker, camera system,
inventory manager, or medical device. Patchwise scores information scent, not
physical availability. Prospecta's cue score is a bounded heuristic and does
not guarantee recall.

**Smallest useful demo.** Search for a missing key pouch with three prior search
passes, record the successful zone, assign it to an entry tray, run a refinding
drill, and generate a "when I put on shoes" cue card.

**Acceptance criteria.** Revisited zones are ranked lower unless the user
records a changed condition. The home card records the evidence for the chosen
slot. A failed cue can be classified and revised without deleting the original
episode.

**Why better than separate tools.** Saccada solves the immediate search,
Patchwise solves the future description, and Prospecta solves retrieval at the
next busy moment. The product has a beginning and an end rather than an
unresolved lost-item report.

**Rejected adjacent components.** `ussyverse/palpaussy` +
`ussyverse/pokayokeussy` is a documented tactile differentiation pairing and is
not included in this first slice. Tactile labeling can become a later optional
countermeasure after the basic home-slot loop is proven.

## 9. Room Comfort Observation Loop

**Exact repositories:** `ussyverse/psychraussy`, `ussyverse/adsorbaussy`, and
`ussyverse/formicaussy`.

**User and recurring pain.** A household notices recurring mustiness,
condensation, or odor in one room but cannot remember when it happens, what
changed, or whether a low-cost cleaning/ventilation experiment helped.

**Product promise.** "Keep a small observation record, separate likely pathways,
and schedule a reversible follow-up without pretending to diagnose the room."

**Flow:** manually entered room temperature/humidity, surface observations,
odor event, airflow notes, and prior interventions -> Psychra computes
dew-point/condensation-oriented values -> Adsorba normalizes the odor event and
builds source/reservoir/airflow intervention cards -> Formica schedules the
observation and follow-up task -> a dated experiment log showing observations,
actions, and unresolved questions.

**Existing source to reuse.** **Exists:** [`psychraussy/src/psychra/psychrometrics.py`](https://github.com/ussyverse/psychraussy/blob/HEAD/src/psychra/psychrometrics.py)
and its neighboring recommendation modules provide deterministic humidity,
dew-point, condensation, and ventilation calculations.
**Exists:** [`adsorbaussy/src/adsorba/models.py`](https://github.com/ussyverse/adsorbaussy/blob/HEAD/src/adsorba/models.py)
and [`engine.py`](https://github.com/ussyverse/adsorbaussy/blob/HEAD/src/adsorba/engine.py)
model odor events, sources, reservoirs, airflow, humidity, intervention ladders,
rebound, masking warnings, and experiment logs. **Exists:**
`ussyverse/formicaussy/src/formica.nim` provides task states, cues, effort, and
staleness review.

**Missing integration work.** Define a shared room and observation ID, preserve
raw readings, and allow "unknown" for both source and pathway. Add a clear
route-away card for gas, smoke, sewer, solvent, electrical, or serious health
concerns. No sensor ingestion or automated fan control belongs in the MVP.

**Maturity and feasibility caveats.** Psychra's calculations require user
measurements and do not establish building causality. Adsorba explicitly is not
a gas detector or medical device. Formica only manages follow-up work. The
output should say "observe, ventilate if appropriate, document, or seek qualified
help," not "the room is safe."

**Smallest useful demo.** Log three odor/condensation observations in one room,
compare a source-removal and airflow experiment, and schedule a one-week review
with the original readings visible.

**Acceptance criteria.** Every intervention is linked to an observation and
has a review date. Safety-sensitive terms produce a boundary note. A no-change
result remains a valid result and does not inflate a success score.

**Why better than separate tools.** Psychra supplies a measurable environmental
observation, Adsorba supplies a pathway-oriented next step, and Formica keeps
the experiment from disappearing. The shared log is the product deliverable.

**Rejected adjacent components.** `ussyverse/wetbulbaussy` is not included
because it belongs to heat-stress pacing and could be mistaken for a household
health/safety authority. This product stays with ordinary comfort observations.

## 10. Guest Visit Setup Blueprint

**Exact repositories:** `ussyverse/hospitiaussy`, `ussyverse/ritualaussy`, and
`ussyverse/quorumussy`.

**User and recurring pain.** Hosting a guest repeatedly creates hidden work:
arrival details, meals, keys, bathroom timing, pets, quiet hours, work blocks,
and departure. The host may know the constraints but fail to turn them into a
mutually agreed, low-friction plan.

**Product promise.** "Prepare the visit around explicit boundaries and energy
limits, then record only the small choices that require agreement."

**Flow:** guest profile, arrival/departure windows, food/accessibility notes,
host energy, private-time needs, touchpoints, and non-negotiables -> Hospitia
generates a touchpoint blueprint, guest card, hidden-labor count, boundaries,
and recovery plan -> Rituala models the household transition cues and logs
whether a repeated sequence was noticed/completed without coercion -> Quorum
records agreed choices such as meal plan, keys, quiet time, or pet boundaries ->
a guest-facing card plus private host preparation list.

**Existing source to reuse.** **Exists:** [`hospitiaussy/pkg/hospitia/model.go`](https://github.com/ussyverse/hospitiaussy/blob/HEAD/pkg/hospitia/model.go)
defines `VisitProfile`, touchpoints, boundaries, artifacts, failure warnings,
recovery plans, and `GenerateBlueprint`. **Exists:**
[`ritualaussy/main.go`](https://github.com/ussyverse/ritualaussy/blob/HEAD/main.go)
defines transitions, rituals, opt-out rules, test logs, cue reliability,
habituation, ambiguity, and safety checks. **Exists:**
`ussyverse/quorumussy/internal/quorum/model.go` provides a persisted decision
model for explicit group choices.

**Missing integration work.** Separate private host notes from guest-visible
artifacts with an allowlist, not string filtering. Define which choices are
actually shared decisions and which are host preparation. Add a simple visit ID
and revision history so a changed arrival window does not erase previous plans.

**Maturity and feasibility caveats.** Hospitia's blueprint is a structured
planning aid, not a guarantee of a good visit. Rituala contains consent and
unsafe-dynamics checks; it must never be used to pressure participation,
mediate abuse, or score a person's compliance. Quorum's decision weights are
negotiation settings, not interpersonal authority.

**Smallest useful demo.** Create a two-night visit with a work call, a shared
bathroom, one dietary constraint, and limited host energy; produce a guest card,
one private host checklist, and one explicitly recorded meal decision.

**Acceptance criteria.** Guest exports contain no private host notes. Every
ritual-like cue has a plain opt-out or skip path. A host can reduce labor without
being marked as failing hospitality. Decision history remains inspectable.

**Why better than separate tools.** Hospitia exposes the visit's hidden labor,
Rituala handles repeated transition cues with consent boundaries, and Quorum
keeps negotiated choices from becoming assumptions. The output is a usable
visit packet, not a generic family dashboard.

**Rejected adjacent components.** `mojomast/familydashboardussy` is not added
because its generic task surface would duplicate the guest blueprint without
adding the visit-specific touchpoints, boundaries, or host recovery artifact.

## Next Verification Steps

1. Capture the current commit for each selected repository and confirm the
   linked symbols still exist on those revisions.
2. Run each component's documented test/build command in its own checkout and
   record failures without treating sample-data output as integration proof.
3. For the top three candidates, write one small user-authored JSON/CSV fixture
   and verify IDs, units, dates, privacy fields, and unknown-state handling at
   every boundary.
4. Interview or observe one target household per candidate before adding cloud
   sync, notifications, OCR, sensors, or live external data.

## Explicitly Rejected Ideas

### A. Household safety super-advisor

**Rejected.** Combine the emergency, indoor-air, repair, and health-triage
engines into one household assistant that tells a person whether a situation is
safe and what to do next. The existing source-checked analysis already rejected
this shape: deterministic heuristics and printable cards do not establish
clinical, engineering, emergency, or predictive validity. Conflicting inputs
would create an authority-shaped output while hiding uncertainty. The proposals
above keep ordinary planning separate from route-away boundaries and qualified
help.

### B. Universal household score

**Rejected.** Feed chores, clutter, food, errands, comfort observations, and
guest visits into one "household health" score. The domains have incompatible
units, baselines, owners, and meanings. A single score would reward dashboard
completeness rather than help with a recurring task, and would make a heuristic
look like a measurement of the household itself. The ideas above retain
domain-specific records and produce a concrete packet, decision, or follow-up
task instead.
