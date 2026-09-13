# Commerce and Consumer Workflow Ideas

**Research date:** 2026-09-13
**Focus:** shopping, returns-adjacent paperwork, resale, inventory, comparison, and small e-commerce
**Status:** proposals only. No end-to-end integration below was found in the inspected source, and no candidate repository was modified.

## Reading The Evidence

"Exists" means the named function, model, CLI, or export was present in the
source inspected. "Proposed" means an adapter, shared data model, UI, or
workflow still has to be built. "Unverified" means a catalog/README claim that
was not source-audited. The numeric scores in these projects are heuristics or
user-entered values, not authoritative prices, valuations, safety certifications,
financial forecasts, or retailer/carrier policies.

### Source audit

I inspected manifests, entry points, core models, and relevant engine/rendering
files in the repositories cited below. Revisions captured with
`git rev-parse --short HEAD` were:

| Repository | Revision |
|---|---|
| `ussyverse/metraussy` | `c4232e8` |
| `ussyverse/kanoaussy` | `4179c1d` |
| `ussyverse/forageussy` | `53bd956` |
| `ussyverse/apoptosisussy` | `ec31815` |
| `ussyverse/speleoussy` | `1013680` |
| `ussyverse/sortariaussy` | `13feac7` |
| `ussyverse/gemmaussy` | `30ab159` |
| `ussyverse/taphonussy` | `432c97d` |
| `ussyverse/taktussy` | `cf74d27` |
| `ussyverse/ethylenoussy` | `0d2206e` |
| `ussyverse/weberaussy` | `f084588` |
| `ussyverse/semaphoraussy` | `79d9d3e` |
| `ussyverse/equilibriaussy` | `3c03cd3` |
| `ussyverse/mustiaussy` | `122fc0a` |
| `ussyverse/transactaussy` | `fe526af` |
| `ussyverse/prospectaussy` | `aeeeca6` |
| `ussyverse/rotationussy` | `b483de0` |
| `ussyverse/kerfwiseussy` | `3717259` |
| `ussyverse/chargeguardussy` | `55b3ac9` |
| `ussyverse/bidussy` | `4073119` |
| `ussyverse/retouraussy` | `27ed2c4` |
| `mojomast/ticket2` | `7d514f7` |

The actual commands run for provenance were `git rev-parse --short HEAD` in
each checked-out repository above. I did not build, install, or runtime-test
these repositories in this pass. Existing tests cited as evidence therefore
show intended contracts, not current pass status.

## New Ideas

### 1. Checkout Fit Ledger

**Target user and pain.** A renter, caregiver, or household buying an appliance,
storage unit, desk, or other constrained object needs to compare catalog claims
with the actual opening, clearance, comfort, and household requirements. A
cheap-looking choice becomes an expensive return when one nominal dimension or
one person's comfort constraint was missed.

**Exact repositories.** `ussyverse/metraussy` + `ussyverse/kanoaussy` +
`ussyverse/weberaussy`.

**Product promise.** Produce a reviewable "buy / verify / do not buy yet" packet
before checkout, without pretending to know retailer inventory or prices.

**Existing evidence.** **Exists:** Metra's `MeasurementCard`, `analyze_card`,
and `stack_uncertainty` in [`metra_core/engine.py`](https://github.com/ussyverse/metraussy/blob/HEAD/metra_core/engine.py)
handle repeat readings, datum quality, tolerance, and a
`do-not-cut-or-buy-yet` label. Kanoa's `DecisionCase`, `Option`,
`OptionFeatureEvidence`, and `Analyze` in [`pkg/kanoa/models.go`](https://github.com/ussyverse/kanoaussy/blob/HEAD/pkg/kanoa/models.go)
and [`pkg/kanoa/engine.go`](https://github.com/ussyverse/kanoaussy/blob/HEAD/pkg/kanoa/engine.go)
support must-have filtering, unknown evidence, and option comparison. Webera's
`TrialSession`, `estimate_thresholds`, and `recommend_change` in
[`src/webera/engine.py`](https://github.com/ussyverse/weberaussy/blob/HEAD/src/webera/engine.py)
separate observed noticeability from comfort preference. **Proposed:** the
shared checkout ledger and retailer-entry workflow.

**Handoff/data flow.** Manual room measurements and repeated comfort trials ->
stable requirement IDs -> Kanoa feature/option evidence with source notes ->
Metra fit gate and Webera household overlay -> a comparison table preserving
raw readings, unknowns, catalog text, and the final human decision.

**MVP.** Compare three manually entered shelving or appliance options against
one alcove and two household comfort trials. Export a Markdown/JSON packet with
failed must-haves and a checklist of questions for the retailer.

**Acceptance criteria.** Every option carries a source note for each required
feature; an uncertain measurement cannot produce "buy"; and the export retains
raw readings, unknowns, and the user's final choice.

**Value of combination.** Kanoa says which requirements matter, Metra tests
whether dimensions are actionable, and Webera prevents a shared-space purchase
from silently optimizing for only one person. Separate tools would not share an
option ID or produce one pre-checkout artifact.

**Risks and maturity.** Catalog dimensions, prices, stock, warranties, and
return terms remain user-entered and stale unless a future connector is built.
Webera's JND/comfort estimates are staircase heuristics from sparse trials;
they are not consumer testing. Metra's units and tolerance semantics need
validation across cards before mixed-unit comparison. No browser checkout or
retailer API exists.

### 2. Errand Basket Compiler

**Target user and pain.** A time-constrained shopper with a multi-store list
needs to decide which store is worth visiting and which low-value item should
be deferred. Ordinary map routing does not explain why an item was assigned to
a store or expose the cost of an uncertain stock claim.

**Exact repositories.** `ussyverse/forageussy` + `ussyverse/metraussy` +
`ussyverse/kanoaussy`.

**Product promise.** Turn a manually verified basket into a route plus an
evidence queue, rather than an allegedly optimal shopping itinerary.

**Existing evidence.** **Exists:** Forage's `Need`, `Patch`, `StockInfo`,
`TripInput`, `PreyChoice`, `BuildRoute`, and `PlanTrip` in
[`pkg/forage/models.go`](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/models.go)
and [`pkg/forage/engine.go`](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/engine.go)
assign in-stock needs, respect max stores/budgets, and calculate a heuristic
round trip. **Exists:** Metra can flag a product whose supplied dimensions are
rounded, nominal, or too uncertain. **Exists:** Kanoa can preserve an option's
feature evidence and eliminate a candidate failing a must-have. **Proposed:**
the basket schema, stock-verification UI, and cross-store option adapter.

**Handoff/data flow.** Needs plus candidate options and manually checked store
stock -> Kanoa marks exact/acceptable alternatives and missing must-have proof
-> Metra validates dimensions for constrained items -> Forage receives only
verified item/store assignments and emits route, budget, and departure cues ->
shopping list with "ask staff / skip / visit" reasons.

**MVP.** Five items, three stores, one dimension-constrained item, and one
"any-brand" substitution. Demonstrate that removing an unverified stock row
changes the route and leaves the item visible as unresolved.

**Acceptance criteria.** The route never treats unresolved stock as confirmed;
every assigned item has a store and reason; and removing a store or item yields
a reproducible changed plan plus an explicit unresolved queue.

**Value of combination.** Forage alone optimizes supplied inputs; this product
adds a disciplined gate for "in stock" and "will fit," making the route useful
even when the shopper must still verify shelves in person.

**Risks and maturity.** Forage uses Euclidean coordinates as a travel proxy and
an EROI/value field that must not be presented as money saved. It does not
scrape retailers, reserve items, understand opening hours, or solve global
basket optimization. Kanoa's classifications depend on user reactions and
evidence. Adapter work must keep "not checked" distinct from "out of stock."

### 3. Low-Burden Group Buy Desk

**Target user and pain.** Families, clubs, or coworkers choosing a shared gift,
bulk purchase, or household item get stuck between one person's favorite and a
choice that creates clutter, cost pressure, or maintenance work for everyone.

**Exact repositories.** `ussyverse/semaphoraussy` + `ussyverse/kanoaussy` +
`ussyverse/equilibriaussy`.

**Product promise.** Make group purchase tradeoffs explicit and leave a human
with a documented shortlist, not an automated "best gift" verdict.

**Existing evidence.** **Exists:** Semaphora's `Candidate` and `analyze` in
[`src/lib.zig`](https://github.com/ussyverse/semaphoraussy/blob/HEAD/src/lib.zig)
record recipient evidence, clutter/storage/maintenance burden, proportionality,
and lower-burden alternatives. **Exists:** Kanoa's weighted participants,
must-be constraints, option evidence, and unresolved questions. **Exists:**
Equilibria's CSV `BidTable`, `bargaining_recommendation`, `envy_report`, and
resource division in [`src/lib.rs`](https://github.com/ussyverse/equilibriaussy/blob/HEAD/src/lib.rs).
**Proposed:** common feature IDs, anonymous response collection, and a group-buy
decision receipt.

**Handoff/data flow.** Candidate list and recipient constraints -> Semaphora
flags burden or weak fit evidence -> Kanoa asks paired functional/dysfunctional
questions about must-haves -> Equilibria receives clearly labeled participant
utilities for a balanced shortlist or resource split -> packet showing dissent,
unknowns, and who must confirm before purchase.

**MVP.** Compare three household gifts or one shared appliance with three
participants. Require a must-have confirmation, a burden alternative, and a
manual final approval.

**Acceptance criteria.** The result shows each participant's raw response and
unknowns; at least one must-have failure blocks an option; and no purchase can
be finalized without an explicit human approval.

**Value of combination.** Semaphora captures recipient-centered burden, Kanoa
separates requirements from delighters, and Equilibria makes disagreement
visible. This is a purchasing conversation artifact, not another rating widget.

**Risks and maturity.** Equilibria's numeric bids are not automatically
comparable across people or preferences; the UI must explain the scale and
retain raw inputs. Semaphora's total fit is a hand-authored heuristic. No
payment, group checkout, vendor catalog, or delivery coordination exists.

### 4. Provenance-Safe Resale Lot Desk

**Target user and pain.** Someone clearing a craft room, inherited box, or
keepsake shelf wants to sell a few items without mixing fragile objects,
discarding provenance, or making unsupported condition/value claims.

**Exact repositories.** `ussyverse/apoptosisussy` + `ussyverse/taphonussy` +
`ussyverse/sortariaussy`.

**Product promise.** Move an item from "consider selling" to a small, documented
resale lot while preserving evidence and uncertainty.

**Existing evidence.** **Exists:** Apoptosis `Item` includes condition,
redundancy, estimated value, location, lifecycle dates, and a `SELL` removal
route; `ApoptosisEngine.scan` and `caspase_cascade` are in
[`src/apoptosis/models.py`](https://github.com/ussyverse/apoptosisussy/blob/HEAD/src/apoptosis/models.py),
[`src/apoptosis/engine.py`](https://github.com/ussyverse/apoptosisussy/blob/HEAD/src/apoptosis/engine.py),
and [`src/apoptosis/cascade.py`](https://github.com/ussyverse/apoptosisussy/blob/HEAD/src/apoptosis/cascade.py).
**Exists:** Taphon parses JSON/CSV/TOML/text inventory files and produces
condition/context assessments, assemblage maps, rehousing checklists, and
Markdown/JSON reports in [`src/lib.rs`](https://github.com/ussyverse/taphonussy/blob/HEAD/src/lib.rs).
**Exists:** Sortaria's `ItemCard`, `SortSession`, ambiguity detection, retrieval
drills, and CSV/JSON/text reports are in [`internal/sortaria/model.go`](https://github.com/ussyverse/sortariaussy/blob/HEAD/internal/sortaria/model.go).
**Proposed:** a listing-lot record and export to a marketplace draft.

**Handoff/data flow.** Possession inventory -> Apoptosis suggests keep/review/
sell without asserting market value -> Taphon preserves context, assemblage,
condition notes, and fragile-item handling -> Sortaria groups photos, labels,
receipts, and item records into a findable lot -> human-authored listing draft
with "known," "observed," and "unknown" fields.

**MVP.** Ten craft or inherited items in two boxes; produce one sell lot, one
keep/archive lot, and one blocked item with missing context. Export a listing
checklist, not a price recommendation.

**Acceptance criteria.** A sell lot preserves item identity, condition, and
source context; missing provenance blocks the relevant listing claim; and the
export contains no generated market price or authenticity assertion.

**Value of combination.** Declutter disposition, preservation context, and
retrieval organization are separate stages that become one safer resale
workflow. The system can reduce accidental context loss without becoming an
appraiser.

**Risks and maturity.** Apoptosis scores are household decision heuristics and
`estimated_value` is user input. Taphon explicitly does not perform appraisal,
mold remediation, or conservation. Marketplace rules, shipping dimensions,
authentication, tax obligations, and prices require human/vendor verification.
The existing Taphon Markdown renderer contains Unicode warning glyphs; a plain
ASCII export should be added if portability is required.

### 5. Receipt and Warranty Retrieval Cabinet

**Target user and pain.** A household has receipts, manuals, serial notes,
warranty PDFs, and dispute records scattered across drawers, email, and cloud
folders. Filing everything is burdensome, but deleting the wrong "old" document
can destroy claim or return evidence.

**Exact repositories.** `ussyverse/sortariaussy` + `ussyverse/mustiaussy` +
`ussyverse/transactaussy`.

**Product promise.** Organize consumer paperwork by how it will be retrieved,
protect records with a concrete retention reason, and make ownership of the
source pointer explicit.

**Existing evidence.** **Exists:** Sortaria models receipts as `ItemCard`s with
owner, deadline, location, search words, ambiguity detection, and retrieval
drills; see [`internal/sortaria/model.go`](https://github.com/ussyverse/sortariaussy/blob/HEAD/internal/sortaria/model.go).
**Exists:** Mustia's `ItemCard` includes `warranty`, `tax`, `active-dispute`, and
`provenance` retention exceptions; `recommendDecision`, `analyzeCollection`,
and `exportWeedingLog` are in [`src/mustia.ts`](https://github.com/ussyverse/mustiaussy/blob/HEAD/src/mustia.ts).
**Exists:** Transacta's `KnowledgeDomain`, `TransactiveEntry`, source pointers,
freshness, backup knowers, and `buildTransitionPack` are in
[`src/models.ts`](https://github.com/ussyverse/transactaussy/blob/HEAD/src/models.ts)
and [`src/engine.ts`](https://github.com/ussyverse/transactaussy/blob/HEAD/src/engine.ts).
**Proposed:** document-to-product links, importers, and filtered exports.

**Handoff/data flow.** Receipt/manual/warranty records -> Sortaria card sort and
retrieval drill -> Mustia retention lane and safety stop -> Transacta links a
non-secret source pointer to a responsible household member and backup -> claim
packet containing the exact file path, product identifier, dates, and unresolved
gaps.

**MVP.** Import 30 manually entered records for five products, run one retrieval
drill, and demonstrate that a warranty/active-dispute record cannot be casually
discarded. Export a local index and a filtered claim packet.

**Acceptance criteria.** A retrieval drill locates the exact source pointer;
warranty, tax, provenance, or active-dispute records remain protected; and a
claim export contains only the selected product's records.

**Value of combination.** Retrieval success, retention policy, and source
ownership answer different failure modes. A folder taxonomy alone cannot say
which records must stay or whether another person can find them.

**Risks and maturity.** No OCR, email/cloud importer, attachment copier, or
document hash pipeline is supplied. Mustia is not legal advice. Transacta's
redaction metadata needs a product-level filtered export; source paths and
secrets must not leak. Do not claim that a successful drill proves future
retrieval under stress.

### 6. Refurbished Device Intake and Warranty Handoff

**Target user and pain.** A small repair or resale shop receives phones, tablets,
laptops, and power banks with inconsistent accessory lists, battery concerns,
condition notes, and customer expectations. A missing charger or an undocumented
stop-use issue becomes a dispute later.

**Exact repositories.** `mojomast/ticket2` + `ussyverse/chargeguardussy` +
`ussyverse/metraussy`.

**Product promise.** Produce one intake/triage packet that separates observed
condition, battery handling, dimensional fit, customer authorization, and
warranty follow-up.

**Existing evidence.** **Exists:** Ticket2's Prisma schema models `WorkOrder`
device type/brand/model/serial, condition notes/checklists, accessories,
parts, costs, signatures, warranty dates, worksheets, and follow-ups in
[`backend/prisma/schema.prisma`](https://github.com/mojomast/ticket2/blob/HEAD/backend/prisma/schema.prisma)
(for example `WorkOrder` and `PartUsed`). **Exists:** Chargeguard's
`BatteryItem`, `ConditionCheck`, `Charger`, `RiskAssessment`, `DisposalPlan`,
and `travel_card` in [`src/lib.rs`](https://github.com/ussyverse/chargeguardussy/blob/HEAD/src/lib.rs)
produce conservative stop-use/recycle, charger, station, and policy-verification
outputs. **Exists:** Metra captures repeated packaging/fit measurements and
uncertainty. **Proposed:** the intake adapter, shared device ID, and customer-safe
projection.

**Handoff/data flow.** Ticket2 work-order intake -> Chargeguard assesses battery,
charger, and charging context without giving repair or firefighting advice ->
Metra checks a manually measured shipping/repair fixture or packaging clearance
-> Ticket2 stores the resulting internal notes, attachments, warranty start,
and follow-up -> customer-facing packet excludes internal credentials and
unverified claims.

**MVP.** Intake three devices: a normal laptop, a tablet with charger mismatch,
and a damaged power bank. Produce an internal triage record plus a customer
receipt that clearly says what was observed and what requires manufacturer or
recycler guidance.

**Acceptance criteria.** Each work order records observed condition and
accessories separately; a battery concern cannot be silently cleared by the
intake flow; and the customer receipt omits internal notes while preserving
manufacturer/recycler follow-up.

**Value of combination.** Ticket2 supplies durable service workflow and
warranty/follow-up entities; Chargeguard supplies a specialized battery safety
boundary; Metra prevents packaging or fixture dimensions from being treated as
facts when they were only nominal.

**Risks and maturity.** Ticket2 is a full PostgreSQL/authenticated application,
not a drop-in local library, and its schema is evidence of data design rather
than a tested integration here. Chargeguard does not certify batteries,
transport eligibility, or recycler rules. Metra is not structural or electrical
certification. Do not auto-clear a device for resale based on any heuristic.

### 7. Maker Resupply and Small-Batch Board

**Target user and pain.** A jewelry or mixed-media maker loses sales because a
small consumable runs out, buys too much slow material, or visits several stores
for a batch without knowing which inputs are genuinely constrained.

**Exact repositories.** `ussyverse/taktussy` + `ussyverse/gemmaussy` +
`ussyverse/forageussy`.

**Product promise.** Convert a maker's own batch history and stock notes into a
reorder review and, when useful, a bounded supply trip.

**Existing evidence.** **Exists:** Takt's `Business`, `ServiceType`, demand
records, `average_demand_rate`, `safety_stock`, `reorder_point`, `kanban_wip_limit`,
and `eoq` are in [`src/lib.rs`](https://github.com/ussyverse/taktussy/blob/HEAD/src/lib.rs).
**Exists:** Gemma's `Material`, custom JSON catalog loading, compatibility,
`rankSparklePerDollar`, and `projectForecast` are in [`src/gemma.nim`](https://github.com/ussyverse/gemmaussy/blob/HEAD/src/gemma.nim).
**Exists:** Forage can map manually entered material needs to store stock,
handling, route, and max-store constraints. **Proposed:** map a batch BOM to
SKU/material IDs and keep purchase quantities separate from model suggestions.

**Handoff/data flow.** Batch recipe/BOM and weekly sales or order counts -> Gemma
checks material compatibility, weight, fragility, and user-entered cost fields
-> Takt produces a transparent reorder/safety-stock review -> Forage receives
only approved material needs and manually checked store stock -> purchase list,
batch card, and unresolved supplier questions.

**MVP.** One maker, six materials, eight weeks of manually entered demand, and
two candidate supply stores. Show one reorder threshold and one compatibility
warning; let the maker override every quantity.

**Acceptance criteria.** Every reorder quantity shows its source inputs; an
incompatible material is surfaced before route generation; and maker overrides
survive export without being rewritten as model output.

**Value of combination.** Gemma understands material/project consequences,
Takt handles repeated replenishment, and Forage handles the physical trip. A
stock count without batch context does not tell the maker what to buy next.

**Risks and maturity.** Takt's model is for service types and uses simplified
demand statistics; mapping it to discrete craft SKUs is new work. Gemma's
"sparkle per dollar" is a formula over user-entered catalog values, not an
authoritative value or quality ranking. Forage's route and EROI are proxies.
No marketplace, supplier feed, purchase order, or accounting integration exists.

### 8. Pantry Rescue Shopping List

**Target user and pain.** A household sees produce going soft while planning a
shopping trip and buys replacements without resolving what should be eaten,
separated, or moved first. The result is avoidable waste and a confusing list.

**Exact repositories.** `ussyverse/ethylenoussy` + `ussyverse/forageussy`.

**Product promise.** Start with what is already in the kitchen, then generate a
small shopping/meal-prep list that respects urgency and explicitly entered
store availability.

**Existing evidence.** **Exists:** Ethyleno's `ProduceItem`, CSV inventory
parser/profile defaults, `ethyleno_item_urgency`, pair conflict scoring, and
`ethyleno_analyze` in [`ethyleno.h`](https://github.com/ussyverse/ethylenoussy/blob/HEAD/ethyleno.h)
and [`ethyleno.c`](https://github.com/ussyverse/ethylenoussy/blob/HEAD/ethyleno.c)
produce same-day use, meal timing, isolation, storage, and ripening actions.
**Exists:** Forage's `Need`, `Patch`, `StockInfo`, and `PlanTrip` can route
manually entered missing items. **Proposed:** translate rescue actions into
needs and preserve quantity/use-window context.

**Handoff/data flow.** CSV of current produce and intended meals -> Ethyleno
emits urgency/conflict/storage actions -> adapter subtracts usable inventory and
creates exact/any shopping needs -> Forage assigns verified needs to stores and
builds a bounded route -> combined board puts "use today," "separate," "buy,"
and "unknown" in distinct queues.

**MVP.** Use the repository's ten-item style of CSV with two stores and three
planned meals. Demonstrate that a same-day item is surfaced before a replacement
purchase and that a mold flag remains a safety check rather than an automatic
food-safety ruling.

**Acceptance criteria.** Existing usable inventory is shown before new buys;
each purchase need has a store or unresolved status; and mold/storage warnings
are displayed as prompts for user judgment, never as food-safety clearance.

**Value of combination.** Ethyleno reasons about current inventory and timing;
Forage handles acquisition effort. The shared item ID prevents a shopper from
buying a duplicate simply because the existing item was not in the shopping
list.

**Risks and maturity.** Ethyleno's profiles and actions are coarse heuristics;
they do not establish food safety, shelf life, or universal storage rules.
Forage has no store API, opening-hours data, or substitution semantics beyond
the supplied fields. Keep "use/cook/freeze now" as a planning prompt and route
uncertain or mold-related cases to the user's normal food-safety guidance.

### 9. Buy, Measure, Then Cut Procurement Packet

**Target user and pain.** A hobby woodworker buys boards and hardware before
checking the real opening, grain movement, or store trip. The first cut then
locks in a bad assumption and creates waste.

**Exact repositories.** `ussyverse/metraussy` + `ussyverse/kerfwiseussy` +
`ussyverse/forageussy`.

**Product promise.** Produce a procurement packet that distinguishes "measure
again," "buy this material class," "allow movement," and "visit this store,"
without claiming structural certification.

**Existing evidence.** **Exists:** Metra's `MeasurementCard`, fit confidence
labels, catalog-dimension warning, tolerance stack, and Markdown packet in
[`metra_core/engine.py`](https://github.com/ussyverse/metraussy/blob/HEAD/metra_core/engine.py).
**Exists:** Kerfwise's `Part`, `Environment`, `AssemblyFeature`, `AssessProject`,
`AssessPart`, `AssessFeature`, `BuildChecklist`, `RiskCard`, and CSV/JSON exports
are in [`kerfwise.go`](https://github.com/ussyverse/kerfwiseussy/blob/HEAD/kerfwise.go).
**Exists:** Forage's store patches, item assignments, route limits, and JSON
persistence. **Proposed:** a bill-of-materials adapter and procurement packet.

**Handoff/data flow.** Measured opening and parts list -> Metra blocks uncertain
fit and records datum/tolerance -> Kerfwise checks material, humidity,
acclimation, grain direction, and restraint -> adapter emits exact material
needs and unanswered supplier questions -> Forage creates a manually verified
store route -> packet links each purchased part to the measurement and assembly
feature it serves.

**MVP.** A small shelf or box project with three boards, one hardware stop, two
stores, and one intentionally nominal catalog dimension. Acceptance is an
export that makes the nominal item "verify" rather than silently allowing a cut.

**Acceptance criteria.** No cut list is released while the nominal dimension is
unverified; every material need links to a part and store decision; and the
packet preserves the measurement tolerance and assembly risk card.

**Value of combination.** Measurement uncertainty, wood movement, and trip
planning share a part ID and a real sequence: prove fit, buy inputs, then cut.
Each tool alone stops before the next physical handoff.

**Risks and maturity.** Kerfwise explicitly uses rough hobby heuristics and is
not structural engineering. Forage uses proxy distances and does not know
store hours or live stock. Metra's CSV is lossy for editable projects, so the
adapter must retain the richer JSON cards. Do not turn a green card into a
guarantee against defects or returns.

### 10. Household Battery Lifecycle Desk

**Target user and pain.** A household has phones, tools, power banks, chargers,
receipts, and spare batteries with unclear ownership and disposal follow-up.
People either lose replacement evidence or forget a suspect battery until it is
needed for travel.

**Exact repositories.** `ussyverse/chargeguardussy` + `ussyverse/sortariaussy` +
`ussyverse/prospectaussy`.

**Product promise.** Maintain a local battery inventory with a clear separation
between routine checks, manufacturer questions, recycling tasks, and travel
policy verification.

**Existing evidence.** **Exists:** Chargeguard models devices, chargers,
locations, condition checks, risk assessments, disposal tasks, travel cards,
and household summaries in [`src/lib.rs`](https://github.com/ussyverse/chargeguardussy/blob/HEAD/src/lib.rs).
**Exists:** Sortaria can organize receipts, warranty cards, charger labels, and
drop-off notes as item cards, then test retrieval with `RetrievalDrill` in
[`internal/sortaria/model.go`](https://github.com/ussyverse/sortariaussy/blob/HEAD/internal/sortaria/model.go).
**Exists:** Prospecta's `Intention`, `CuePlan`, `DesignPlan`, `ClassifyMiss`, and
`RecommendAids` in [`prospecta.go`](https://github.com/ussyverse/prospectaussy/blob/HEAD/prospecta.go)
support a visible recycling/replacement cue. **Proposed:** stable battery,
charger, document, and task IDs plus a local task ledger.

**Handoff/data flow.** Device/charger inspection and purchase paperwork ->
Chargeguard emits the conservative status and, where appropriate, a disposal or
travel verification task -> Sortaria links the receipt/manual/drop-off note and
checks that it can be found -> Prospecta binds the task to a place, object, or
date cue -> completion record retains the original observation and the user's
local-rule verification.

**MVP.** Four devices, two chargers, one suspect power bank, and one user-entered
recycler. Demonstrate that a disposal task stays open until the user confirms
the local instruction and that travel output says to verify current policy.

**Acceptance criteria.** Suspect items produce an unresolved task rather than a
clearance; each document is retrievable by device or charger ID; and disposal
or travel status cannot be marked complete without an explicit local-policy
confirmation.

**Value of combination.** Chargeguard identifies the specialized lifecycle
boundary, Sortaria protects the paperwork path, and Prospecta addresses the
follow-through gap. This is more useful than a battery dashboard or a generic
reminder list alone.

**Risks and maturity.** Chargeguard's status is conservative decision support,
not a certification or emergency procedure. Local recycling rules and carrier
policies change and must be verified outside the tool. Prospecta cue scores are
fixed human-rated heuristics and it sends no notifications. Sortaria's local
JSON state needs atomicity, backup, and privacy work before multi-user use.

## Rejected Ideas

### A. Automated "best deal" and resale-price oracle

**Rejected repositories/shape:** `ussyverse/bidussy` + `ussyverse/gemmaussy` +
`ussyverse/apoptosisussy`, with scraped marketplace feeds.

**Why rejected.** Bidussy's inspected catalog/source contract is for historical
freelancer quotes and demand-curve/reserve-price guidance, not second-hand goods.
Gemma's "sparkle per dollar" is a craft-material formula over user-entered
fields, and Apoptosis's `estimated_value` is a household input, not an appraisal.
Adding live marketplace prices would be a major unbuilt connector and would
still not establish condition, authenticity, demand, fees, taxes, or shipping
comparability. The resale idea above deliberately exports evidence and asks a
human to set a listing price.

### B. Fully automatic shopping agent with checkout and return decisions

**Rejected repositories/shape:** `ussyverse/forageussy` + `ussyverse/retouraussy`
+ `ussyverse/prospectaussy`, with browser automation that purchases, returns,
and disputes items automatically.

**Why rejected.** Forage only consumes user-entered patches, stock, coordinates,
budgets, and proxy values. Retoura's source-checked limitations include no
retailer/carrier integration, no receipt authentication, and date semantics that
need adapter correction; Prospecta supplies cue plans, not notifications or
transaction authority. Browser checkout would add credentials, payment,
fraud, accessibility, retailer terms, and irreversible-action risks before the
basic evidence handoff is validated. A local, human-approved basket and
paperwork packet is a safer first boundary.

## Selection Notes

These ideas were selected for a natural shared entity: option, basket item,
receipt, lot item, work order, material, produce item, or battery task. They
favor a useful local artifact before authentication, scraping, payment, or
multi-user hosting. None should be marketed using heuristic scores as
authoritative financial, safety, food, legal, appraisal, or transport advice.
