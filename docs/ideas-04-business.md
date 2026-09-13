# Business Operations Ideas: Pass 04

**Date:** 2026-09-13

**Focus:** small service businesses, inventory, scheduling, finance, and quality
improvement.

## Scope and evidence boundary

These are new product proposals, not existing integrations. The current shortlist
already covers `andoniaussy` + `shewhartaussy` + `a3viaussy` for recurring service
problems, and the broad `mojomast/ticket2` operations cockpit. The proposals below
use different handoffs and narrower first outcomes; none claims to replace a ticket,
accounting, calendar, inventory, or audit system.

I inspected the following checked-out revisions under `/home/ubuntu/ussy/repos`:

| Repository | Revision | Evidence inspected |
|---|---|---|
| `ussyverse/bidussy` | `4073119` | [`src/bid/models.py`](https://github.com/ussyverse/bidussy/blob/4073119/src/bid/models.py), `demand.py`, `analysis.py`, `recommendations.py`, tests |
| `ussyverse/queueussy` | `a8f2f32` | [`src/queueussy/data.py`](https://github.com/ussyverse/queueussy/blob/a8f2f32/src/queueussy/data.py), [`engine.py`](https://github.com/ussyverse/queueussy/blob/a8f2f32/src/queueussy/engine.py), README, tests |
| `ussyverse/taktussy` | `cf74d27` | [`src/lib.rs`](https://github.com/ussyverse/taktussy/blob/cf74d27/src/lib.rs), `src/main.rs`, `Cargo.toml`, tests |
| `ussyverse/stoichussy` | `93d77c4` | [`pkg/stoich/model.go`](https://github.com/ussyverse/stoichussy/blob/93d77c4/pkg/stoich/model.go), `main.go`, tests |
| `ussyverse/cyclaraussy` | `b4185c9` | [`src/cyclara/models.py`](https://github.com/ussyverse/cyclaraussy/blob/b4185c9/src/cyclara/models.py), [`engine.py`](https://github.com/ussyverse/cyclaraussy/blob/b4185c9/src/cyclara/engine.py), README/index evidence |
| `ussyverse/recapturaussy` | `2640919` | [`src/lib.zig`](https://github.com/ussyverse/recapturaussy/blob/2640919/src/lib.zig), `src/main.zig`, README, integration tests |
| `ussyverse/forageussy` | `53bd956` | [`pkg/forage/models.go`](https://github.com/ussyverse/forageussy/blob/53bd956/pkg/forage/models.go), [`engine.go`](https://github.com/ussyverse/forageussy/blob/53bd956/pkg/forage/engine.go), `persist.go`, README, tests |
| `ussyverse/rotationussy` | `b483de0` | [`src/model.ts`](https://github.com/ussyverse/rotationussy/blob/b483de0/src/model.ts), [`agronomy.ts`](https://github.com/ussyverse/rotationussy/blob/b483de0/src/agronomy.ts), manifest, tests |
| `ussyverse/allomaussy` | `ce4487d` | [`src/alloma/models.py`](https://github.com/ussyverse/allomaussy/blob/ce4487d/src/alloma/models.py), [`analyzer.py`](https://github.com/ussyverse/allomaussy/blob/ce4487d/src/alloma/analyzer.py), `report.py` |
| `ussyverse/shewhartaussy` | `8955b86` | [`pkg/shewharta/model.go`](https://github.com/ussyverse/shewhartaussy/blob/8955b86/pkg/shewharta/model.go), [`engine.go`](https://github.com/ussyverse/shewhartaussy/blob/8955b86/pkg/shewharta/engine.go), `csvio.go`, tests |
| `ussyverse/pokayokeussy` | `454eabd` | [`pokayoke.py`](https://github.com/ussyverse/pokayokeussy/blob/454eabd/pokayoke.py), README, tests |
| `ussyverse/capstanussy` | `01cd17d` | [`pkg/capstan/model.go`](https://github.com/ussyverse/capstanussy/blob/01cd17d/pkg/capstan/model.go), [`scorer.go`](https://github.com/ussyverse/capstanussy/blob/01cd17d/pkg/capstan/scorer.go), `render.go`, tests |

**Important:** source and existing tests were inspected, but no candidate project
was installed, built, or runtime-tested in this pass. “Exists” below means present
in inspected source. “Proposed” means adapter or product work that does not exist.
The recommendations are not financial, tax, audit, safety-certification, or demand-
forecast authority.

For provenance, `git rev-parse --short HEAD` was run in each listed checkout. No
candidate checkout was modified.

## New proposals

### 1. Quote-to-bookable capacity pack

**Target user and pain:** A solo consultant, alteration shop, tutor, or repair
provider has enough quote history to see different willingness to pay, but accepts
work without checking whether its promised duration fits the appointment book. The
result is profitable-looking work that creates late delivery, overbooking, or a
queue of unpriced requests.

**Exact repositories:** `ussyverse/bidussy`, `ussyverse/queueussy`,
`ussyverse/taktussy`.

**Existing evidence (Exists):** `bidussy/src/bid/models.py` defines quote outcome,
service type, estimated hours, channel, segment, urgency, and a minimum viable rate.
`bidussy/src/bid/analysis.py` joins demand, quote optimization, group comparisons,
and guidance cards. `queueussy/src/queueussy/data.py` has appointment duration,
show-up, lateness, and schedule configuration models; `engine.py` has slot duration,
utilization, overbooking, waitlist, and scenario simulation functions.
`taktussy/src/lib.rs` persists service production time and weekly demand and exposes
capacity, takt-time, WIP, and throughput calculations.

**Proposed handoff/data flow:** A user enters a quote with `quoteId`, service,
estimated hours, amount, channel, outcome, and urgency. The adapter sends the same
service's accepted/lost history to Bid for a price range and sends historical actual
durations and no-shows to Queue. It sends accepted demand and production-time
assumptions to Takt. The product emits a quote card with (1) a floor entered by the
owner, (2) observed empirical points, (3) a provisional amount, (4) a capacity
warning, and (5) a suggested slot or waitlist experiment. Raw rows and all sample
sizes remain attached.

**MVP:** CSV import for 20 manually recorded quotes and appointments, one service
type, and a local page that compares a proposed 4-hour job at three prices and two
slot policies. No calendar write-back. Acceptance means the output preserves quote
IDs, shows the observed price range, rejects a quote below the explicit floor, and
shows when the selected weekly demand exceeds the entered capacity.

**Value of the combination:** Bid alone answers “what might this quote be worth?”
Queue alone answers “how could appointments fit?” Takt supplies the shared unit of
service hours and weekly demand. Together they turn a price suggestion into a
promise the owner can inspect before booking.

**Risks and maturity:** Bid fits a one-variable logistic curve and labels samples
under 20 as high uncertainty; it does not control for scope, client selection, or
actual margin. Queue's arrival-rate calculation uses the span between first and last
appointment, and its simulator assumes 40 working hours per week. Takt's service
and demand fields are simple and its `reorder_point` is not service-specific despite
the CLI argument. These outputs must be labelled “directional scenario,” not a
guaranteed price or capacity commitment.

**Rejected adjacent component:** Do not add `ussyverse/allomaussy` to produce a
fourth overall growth score. The three existing signals already produce a concrete
quote-and-booking decision; another aggregate would obscure the raw assumptions.

### 2. Evidence-bound waitlist sizing

**Target user and pain:** A small clinic, salon, workshop, or classes business sees
interest across a newsletter, social messages, and a manual waitlist, but cannot tell
whether an apparent full book is real demand or duplicate capture. They either add a
slot too early or leave a viable class unoffered.

**Exact repositories:** `ussyverse/recapturaussy`, `ussyverse/queueussy`,
`ussyverse/taktussy`.

**Existing evidence (Exists):** `recapturaussy/src/lib.zig` normalizes email, phone,
handle, name/postal, and manual aliases; builds overlap matrices; computes Chapman
and Lincoln-Petersen estimates; and emits warnings for sparse, dependent, zero-overlap,
and ambiguous-name sources. Its tests verify that zero overlap refuses a pairwise
estimate. Queue has appointment/no-show models and waitlist/slot/simulation functions.
Takt has weekly demand records, capacity hours, WIP limit, and JSON persistence.

**Proposed handoff/data flow:** Import source records with a source relationship
(`independent`, `shared_audience`, or `downstream`) and an offer ID. Recaptura returns
observed unique contacts, overlap, aliases needing review, and its recommendation.
Only an owner-approved lower-bound or observed count is passed to a capacity view.
Queue compares the proposed extra slot with actual durations and no-show history;
Takt compares that slot's demand with weekly capacity. The output is “open one trial
slot,” “keep a waitlist,” or “collect another source-specific sample,” with the raw
source table beside it.

**MVP:** Two CSV source lists for one class, manually reviewed aliases, eight weeks
of completed appointments, and a single extra-slot scenario. Acceptance means a
zero-overlap source pair cannot generate a hidden-demand number, a downstream source
produces a visible warning, and no capacity recommendation can be emitted without
an owner-entered capacity and duration.

**Value of the combination:** It connects marketing capture evidence to an actual
operational experiment. Recaptura prevents duplicate leads from becoming invented
demand; Queue tests service consequences; Takt makes the capacity constraint explicit.

**Risks and maturity:** Capture-recapture assumes conditions that small-business
lists rarely satisfy. The source uses a lower-bound framing, but that does not make
the estimate statistically validated for this business. Queue's waitlist threshold
is tied to an Erlang-C heuristic and Takt averages weekly demand. Treat the product
as a sample-and-measure workflow, never as a market-size forecast.

**Rejected adjacent component:** Do not route every source through a CRM or add an
LLM lead classifier in the MVP. Manual identity review and source-specific signup
paths are the evidence needed first.

### 3. Mobile service parts run planner

**Target user and pain:** A mobile repairer, installer, or maintenance contractor
loses time making several parts runs, buys stock before a job is confirmed, and has
no single view of whether a replenishment trip consumes the day's margin.

**Exact repositories:** `ussyverse/forageussy`, `ussyverse/taktussy`,
`ussyverse/cyclaraussy`.

**Existing evidence (Exists):** `forageussy/pkg/forage/models.go` models needs,
patches/stores, stock, price, handling time, route, gas cost, and time/gas budgets.
`engine.go` implements stock-aware assignment, max-store filtering, nearest-neighbor
plus 2-opt routing, EROI, and departure signals; `persist.go` saves inputs and plans
as JSON. Takt's `ServiceType` includes production time, setup cost, and holding cost,
while `lib.rs` exposes average demand, safety stock, reorder point, Kanban WIP, and
EOQ. Cyclara's `BusinessFlow` has inventory holds, batch size, deposits, receivable and
payable delays, and explicit cash events.

**Proposed handoff/data flow:** A confirmed work order becomes a list of required
parts with due date, job value, and substitution policy. The owner manually records
part availability and travel-time proxy at suppliers. Forage proposes assignments and
a round trip. Takt provides a provisional reorder/WIP quantity from historical part
usage. Cyclara receives only the selected purchase amount, expected customer deposit,
and supplier terms and returns a cash-gap view. The handoff must preserve units,
currency, due dates, and “unknown stock” separately from “out of stock.”

**MVP:** One technician, five part types, three manually entered suppliers, and two
jobs in the same week. Show the cheapest-time route, a “buy now versus consolidate”
comparison, and estimated owner cash tied up. Acceptance means no item is silently
dropped when a supplier lacks stock, the route starts/ends at the depot, and the
cash report identifies every assumed deposit and supplier date.

**Value of the combination:** Forage reduces travel and handling; Takt prevents a
single urgent job from being mistaken for a replenishment policy; Cyclara exposes
the working-capital consequence. This is a purchase-run artifact, not three separate
dashboards.

**Risks and maturity:** Forage explicitly uses arbitrary coordinates and Euclidean
distance as a travel-time proxy, and its `max_stores` rule can drop needs when a store
limit is applied. It does not verify live inventory or prices. Takt's safety-stock
formula is a simple model and does not distinguish part types in the business-level
history. Cyclara's “owner-funded amount” depends on manually supplied event timing.
The first release must display assumptions and require human confirmation before a
purchase.

**Rejected adjacent component:** Do not add an online retailer connector or live
maps initially. Those integrations would make data freshness and vendor terms the
primary problem before the handoff is validated.

### 4. Small-batch maker cash gate

**Target user and pain:** A craft seller or small workshop prebuys materials for a
seasonal batch, then discovers that finished inventory and payout delays consume the
cash needed for the next order. The owner needs a reversible “how much to make now?”
review, not a generic budget score.

**Exact repositories:** `ussyverse/taktussy`, `ussyverse/cyclaraussy`,
`ussyverse/stoichussy`.

**Existing evidence (Exists):** Takt's `Business` stores capacity, revenue per hour,
service types, production time, setup cost, holding cost, and weekly demand. Its
library computes demand variance, bullwhip indicator, safety stock, reorder point,
Kanban WIP, EOQ, and throughput. Cyclara models `InventoryHold`, batch size, deposit,
cash-in/out events, supplier terms, and compares working-capital scenarios. Stoich's
`Budget` calculates income, expense slack, product balances, limiting reagent,
equilibrium, activation ladders, and catalyst suggestions in
`pkg/stoich/model.go`.

**Proposed handoff/data flow:** A batch record contains SKU, units, labor hours,
material cost, expected sale timing, customer deposits, and supplier due dates. Takt
turns recent unit demand and setup/holding assumptions into candidate batch sizes and
WIP limits. Cyclara computes timing for the selected batch. Stoich receives a separate
owner-entered monthly cash budget and renders which flexible categories or goals are
affected by the batch. The final card shows the batch, cash events, and explicit
questions for the owner rather than a single “approve” result.

**MVP:** Compare 10, 20, and 30 units of one seasonal product using a hand-entered
20-week demand series, one supplier term, and one payout date. Acceptance means each
scenario preserves unit/currency/date labels, exposes the assumed sell-through and
deposit, and lets the user reject the scenario without changing source data.

**Value of the combination:** Takt addresses flow and batch size, Cyclara addresses
cash timing, and Stoich makes the owner tradeoff legible when the same cash could fund
materials, reserves, or another goal. The result is a documented prebuy decision.

**Risks and maturity:** Takt's formulas use averaged demand and a generic lead time;
the CLI's service label does not change the calculation. Cyclara is management-
accounting scenario support, not bookkeeping. Stoich's coefficients are user-entered
allocation weights and its “catalyst ROI” is a heuristic. Do not present this as a
loan, solvency, tax, or investment recommendation.

**Rejected adjacent component:** Do not add `ussyverse/benfordaussy` to validate the
batch decision. Benforda explicitly warns that fixed prices and small or constrained
populations are unsuitable; it would not establish whether a batch is affordable.

### 5. Service portfolio pricing clinic

**Target user and pain:** A freelancer or tiny studio has several services, a dominant
client, and uneven energy or delivery burden. They need to decide which offer to test,
which client concentration to reduce, and what price evidence to collect next without
turning a metaphorical “health” number into a growth mandate.

**Exact repositories:** `ussyverse/rotationussy`, `ussyverse/bidussy`,
`ussyverse/allomaussy`.

**Existing evidence (Exists):** Rotation's `ServiceCrop`, `ClientField`, and
`WorkLogEntry` models are in `src/model.ts`. `src/agronomy.ts` computes harvest index,
soil/recovery reports, monoculture risk, companion bundles, seasonal rotation, fallow
recommendations, and lead warmth. Bid records quote outcomes and estimates demand by
hourly price, with channel/segment comparisons and uncertainty messages. Alloma's
`BusinessSnapshot` accepts headcount, clients, revenue, hours, handoffs, delays, and
quality fields; `analyze_business` produces metric details and scenario notes.

**Proposed handoff/data flow:** Import service/work logs and quote history using a
stable service ID. Rotation identifies high-effort/revenue combinations, client
concentration, and candidate companion offers. Bid analyzes price/outcome only within
an owner-selected service/channel slice. Alloma receives a manually prepared current
snapshot to identify operational inputs that should be measured before expansion.
The product produces a one-week experiment brief: target offer, sample size, price
variants, capacity cap, and follow-up date.

**MVP:** Three services, ten historical quotes per service where available, four
clients, and one proposed bundle. Acceptance means every recommendation links back to
the source rows and labels missing samples; the user can choose “collect data” instead
of changing price or client mix.

**Value of the combination:** Rotation supplies portfolio and workload context, Bid
supplies observed quote behavior, and Alloma identifies process fields that must be
instrumented before growth. It turns broad strategic reflection into a bounded pricing
experiment.

**Risks and maturity:** Rotation's harvest index divides revenue by effort and an
energy rating; its exponential rest, seasonal factors, and 50% monoculture threshold
are explicit heuristics. Alloma's allometric capacity and headcount threshold are
also models, not empirical business laws. Bid's one-variable curve confounds scope and
selection. No output should say a service is objectively “best” or that hiring will
produce a specified return.

**Rejected adjacent component:** Do not add `ussyverse/predatorussy`'s ecological
simulation. It would add another client-load metaphor and time-series model without
improving the small experiment artifact.

### 6. Quote and payment-terms experiment ledger

**Target user and pain:** A small agency or home-service operator changes prices,
deposits, and invoice timing together, then cannot tell whether acceptance, cash
arrival, or customer delay changed. The owner needs a ledger that separates commercial
demand evidence from collection timing.

**Exact repositories:** `ussyverse/bidussy`, `ussyverse/cyclaraussy`,
`ussyverse/shewhartaussy`.

**Existing evidence (Exists):** Bid has quote amount, outcome, estimated hours,
channel, segment, urgency, demand curves, minimum-rate floors, and guidance cards.
Cyclara's `BusinessFlow` and `WorkingCapitalScenario` represent deposits, invoice
delay, customer payment days, payout delay, inventory, supplier terms, and batch
changes; `compare_scenarios` returns deltas and relationship/sustainability risk
notes. Shewharta's `MetricCard`, `Observation`, `ProcessChange`, and `InterventionNote`
model dated metrics and context; `ComputeLimits` and `AnalyzeMetric` provide XmR,
run, trend, process-change, and overcontrol signals. `csvio.go` imports metric/date/
value CSV rows.

**Proposed handoff/data flow:** Each quote gets a stable experiment ID and later links
to a payment timeline: deposit received, work delivered, invoice sent, paid. Bid
summarizes quote outcomes by the predeclared variant. Cyclara estimates the proposed
terms before rollout and records actual cash events after it. Shewharta receives one
metric at a time, such as accepted quotes per week or invoice-to-payment days, with
the launch date marked as a process change. The output is a before/after evidence
packet with raw counts, not a causal verdict.

**MVP:** One service, three price/deposit variants, 12 weeks of historical records,
and a manual CSV export. Acceptance means pending quotes are not treated as outcomes,
payment dates are not substituted for invoice dates, and every apparent signal shows
its baseline size and marked changes.

**Value of the combination:** It stops the common mistake of calling a quote change
successful because the invoice was paid later, or calling a deposit policy harmful
because a low-demand week followed. Each component owns a different stage of the
experiment.

**Risks and maturity:** Bid warns on small samples. Cyclara's event timeline is based
on owner-entered timing and does not reconcile bank records. Shewharta's baseline
needs at least eight points by default and warns that tiny baselines are not proof.
The ledger must support missing, disputed, and excluded observations and must not
claim statistical causality.

**Rejected adjacent component:** Do not add `ussyverse/benfordaussy` to score the
experiment's invoices as fraud evidence. At most it could be a separate bookkeeping
review queue, and it is not part of this product's decision boundary.

### 7. Mistake-proof repair bench

**Target user and pain:** A two-to-six-person repair, alteration, or fulfillment shop
repeats omissions such as missing parts, wrong quantity, skipped reset, or an
interrupted final inspection. Staff know the failure after the customer returns, but
the fix is usually a reminder that is not checked for effect.

**Exact repositories:** `ussyverse/pokayokeussy`, `ussyverse/taktussy`,
`ussyverse/shewhartaussy`.

**Existing evidence (Exists):** `pokayoke.py` parses structured cases, classifies
missing-item, wrong-item, wrong-quantity, skipped-reset, interrupted-sequence,
wrong-time, and unclear-ownership mechanisms, then emits source-inspection points,
countermeasure families, proof signals, review dates, and safety boundaries. Its
README describes local JSON/YAML input and a deterministic Markdown report. Takt
provides service time, demand, WIP, and throughput calculations. Shewharta provides
dated count/duration observations, process-change markers, control limits, and an
overcontrol warning when interventions occur without matching signals.

**Proposed handoff/data flow:** A bench case contains job ID, service, station,
failure/near-miss description, step sequence, and consequence. Pokayoke returns a
candidate source inspection and one or two reversible countermeasures. The supervisor
chooses one and records the change date. Takt converts jobs in progress and observed
service time into a visible WIP limit. Shewharta receives weekly defects per completed
job, rework duration, or first-pass completion, with zero-work weeks kept distinct
from missing data. The artifact is a one-page countermeasure plus a follow-up chart.

**MVP:** One station, 15 historical cases, two weeks of before data, one staged tray
or reset token, and manually entered daily defect counts. Acceptance means a case is
linked to a concrete step, the report rejects “be more careful” as the only response,
and the follow-up cannot be called successful without a dated observation series.

**Value of the combination:** Pokayoke identifies where the error is created; Takt
prevents the countermeasure from creating an uncontrolled WIP pile; Shewharta checks
whether the observed defect series warrants follow-up rather than celebrating one
good day.

**Risks and maturity:** Pokayoke is implemented and documented as a household action,
so business vocabulary, authentication, durable case storage, and permissions are
new work. Its text matching can misclassify a case. Takt has no job-level scheduler.
Shewharta distinguishes common cause from signals only under its stated baseline
assumptions. It is quality-improvement support, not a compliance certification.

**Rejected adjacent component:** Do not reuse Andonia here. That would recreate the
existing service-problem improvement shortlist; this proposal deliberately focuses
on concrete mistake-proofing and measurable first-pass quality.

### 8. Cable-installation work pack

**Target user and pain:** A small AV, networking, or smart-office installer schedules
short site visits, carries a changing mix of cables and adapters, and receives
callbacks because routes are hard to inspect, strain relief is missing, or a cable
crosses a walking path. The business needs a repeatable install packet, not a generic
safety score.

**Exact repositories:** `ussyverse/capstanussy`, `ussyverse/queueussy`,
`ussyverse/taktussy`.

**Existing evidence (Exists):** Capstan's `Cord`, `Segment`, `HazardZone`, and
`Station` models capture cable type, bend radius, power class, service loop,
inspection visibility, labels, floor crossings, heat, abrasion, and moving furniture.
`AnalyzeCord`/`AnalyzeStation` produce warnings, fixes, route cards, and damaged-cord
escalations. Queue models appointment duration, lateness, no-shows, slot duration,
utilization, and scenario simulation. Takt persists service production time and
weekly demand and provides WIP/buffer calculations.

**Proposed handoff/data flow:** A site survey creates a station and explicit cable
segments plus hazards. Capstan produces a route card and unresolved observations.
The installer enters estimated and actual visit duration; Queue compares that history
with bookable slot policies. Takt receives service type, weekly demand, and a manually
entered buffer or WIP limit. A work pack contains the customer/site reference, route
observations, duration slot, parts checklist, and sign-off fields. No component should
silently certify an installation.

**MVP:** One office room, two cable routes, one technician, and ten historical visits.
Acceptance means every route card names the segment behind a warning, a damaged cord
routes to replacement/qualified help, and the schedule packet preserves actual versus
estimated duration. The pack must be printable without requiring a calendar or
inventory integration.

**Value of the combination:** Capstan handles physical route quality, Queue protects
the day's appointment promise, and Takt exposes the amount of work in the pipeline.
The shared entity is the install visit, with a clear handoff from survey to booking to
completion.

**Risks and maturity:** Capstan's values are deterministic household heuristics, not
electrical code or engineering approval. Queue assumes simplified arrivals and its
simulator is stochastic. Takt's generic “service type” is not a bill of materials.
The product must say “inspection checklist” and “planning estimate,” never “safe by
code” or “guaranteed on time.”

**Rejected adjacent component:** Do not add a live electrical-diagnostics or smart-
building integration. It would cross the product from route documentation into
high-consequence technical advice without evidence or a qualified review boundary.

### 9. Source-to-bundle follow-up desk

**Target user and pain:** A maker, photographer, coach, or independent studio gets
leads through markets, referrals, a newsletter, and social channels. The owner knows
some audiences overlap but does not know which service bundle to offer or which
follow-up experiment is worth the limited admin time.

**Exact repositories:** `ussyverse/recapturaussy`, `ussyverse/bidussy`,
`ussyverse/rotationussy`.

**Existing evidence (Exists):** Recaptura supports source records, manual aliases,
source relationship warnings, overlap matrices, conservative population reporting,
and redacted identity hashes. Bid supports quote outcome, channel and segment
comparison, empirical price points, demand estimates, and guidance cards including
bundle anchors. Rotation's `companionBundles` computes client-set overlap between
services; its models also include client revenue share, work logs, energy rating, and
lead warmth days.

**Proposed handoff/data flow:** Import anonymized or locally retained lead records
with source, offer, and outcome fields. Recaptura resolves only owner-approved
identities and reports overlap; it must not infer consent to contact. Rotation maps
service/client overlap into candidate bundles. Bid analyzes accepted/lost quotes for
one selected bundle or channel. The desk emits a finite queue of follow-ups with the
source evidence, one offer variant, an owner-entered contact permission flag, and a
review date. No automatic outreach is in the MVP.

**MVP:** Three source lists, two services, manual aliases, and a 10-row quote history.
Generate one bundle hypothesis and a copyable, permission-filtered follow-up sheet.
Acceptance means a lead with no permission is excluded from the sheet, dependent
sources stay visibly marked, and a bundle is labelled a hypothesis until a quote
outcome exists.

**Value of the combination:** Recaptura answers “who may be duplicated across
sources?”, Rotation answers “which offers share observed client fields?”, and Bid
answers “what quote evidence exists for this slice?” The product reduces admin
guesswork without pretending to measure the whole market.

**Risks and maturity:** Recaptura's identity normalization can merge ambiguous names
and its estimates depend on source independence. Rotation's Jaccard overlap is not a
conversion probability. Bid can confound price with channel and scope. Privacy,
retention, deletion, and consent controls are new product work; redacted hashes do
not make raw contact data safe by themselves.

**Rejected adjacent component:** Do not add `ussyverse/apicolaussy`'s helper-ranking
or reciprocity score. It would introduce a community allocation model unrelated to
commercial consent and quote follow-through.

### 10. Owner operating-review packet

**Target user and pain:** A one-to-five-person service business reviews monthly
revenue, workload, cash timing, and owner availability in separate spreadsheets. The
owner needs a short meeting packet that identifies which assumption to test next,
without receiving a pseudo-precise “health” verdict or investment advice.

**Exact repositories:** `ussyverse/allomaussy`, `ussyverse/cyclaraussy`,
`ussyverse/stoichussy`.

**Existing evidence (Exists):** Alloma accepts monthly business snapshots including
headcount, contractors, clients, service lines, revenue, recurring revenue, admin /
sales / meeting / support / rework hours, invoice delay, cash buffer, handoffs,
process docs, role clarity, and quality issues. It computes metric details and
scenario notes in `analyzer.py`. Cyclara models each business flow's revenue,
variable cost, inventory hold, receivable/payable delays, deposits, batch size, and
cash events, and compares scenarios. Stoich calculates monthly slack, product
balances, limiting category, goal ladders, and user-entered catalyst suggestions.

**Proposed handoff/data flow:** A monthly review imports a snapshot and one or more
service flows with provenance notes. Alloma identifies which operational fields are
missing or elevated. Cyclara turns one selected flow into baseline and reversible
terms/deposit/batch scenarios. Stoich shows the owner-entered household or business
allocation consequences separately, with no automatic transfer instruction. The
packet ends with one experiment owner, one measure, one check date, and an explicit
“do not decide from this model” note where data is absent.

**MVP:** Two monthly snapshots, two flows, one staffing or deposit scenario, and a
static Markdown export. Acceptance means the packet preserves raw inputs, shows the
date and scope of every scenario, and distinguishes operational observation from
owner-entered allocation preference.

**Value of the combination:** Alloma organizes the operating review, Cyclara puts
working capital on a dated flow, and Stoich makes competing uses of slack discussable.
The deliverable is a meeting agenda and experiment record, not another dashboard.

**Risks and maturity:** Alloma's allometric scaling relationships and thresholds are
not validated financial forecasts. Cyclara's confidence field reflects presence of
cash events, not accounting assurance. Stoich coefficients are subjective and its
recommendations can sound prescriptive. Keep currency, tax, payroll, debt, and owner
draw decisions under qualified human review.

**Rejected adjacent component:** Do not add `ussyverse/keelussy` or `ussyverse/mortussy`.
Both would widen this into household/actuarial stress advice, while the proposed
packet only needs a bounded operational cash conversation.

## Rejected ideas

### R1. Automatic “best staffing and price” authority

**Candidate repositories:** `ussyverse/bidussy`, `ussyverse/queueussy`,
`ussyverse/allomaussy`, `ussyverse/cyclaraussy`.

**Why rejected:** These components expose useful inputs and transparent calculations,
but they do not share a validated unit for demand, service capacity, margin, or
employee productivity. Bid's price curve is one-variable and warns about small
samples; Queue uses simplified arrival/service assumptions; Alloma uses metaphorical
scaling relationships; Cyclara relies on hand-entered timing. Combining their scores
into an automatic staffing, pricing, or payroll recommendation would turn heuristics
into financial and employment authority. The narrower proposals above retain raw
evidence and require owner-selected experiments instead.

### R2. Universal inventory truth and auto-purchasing mesh

**Candidate repositories:** `ussyverse/taktussy`, `ussyverse/forageussy`,
`ussyverse/recapturaussy`, `ussyverse/benfordaussy`.

**Why rejected:** Takt has simple demand and reorder formulas, Forage uses manually
entered stock and Euclidean travel proxies, Recaptura estimates lead-list overlap
rather than stock availability, and Benforda is explicitly a bookkeeping anomaly
triage tool. None provides authoritative SKU identity, live supplier stock, purchase
orders, accounting reconciliation, or safe handling of substitutions. An “inventory
truth” product would require implementing the largest missing system first and would
invite silent stock and cash errors. The mobile parts-run proposal uses these limits
honestly: manual inputs, visible assumptions, and human confirmation before buying.

## Next validation steps

1. Pick one proposal and pin the listed revisions in a new integration repository;
   do not modify these candidate checkouts.
2. Run each component's declared test suite in isolated environments and record
   failures rather than inferring readiness from the source inspection.
3. Create one user-authored fixture with stable IDs, units, dates, and missing-data
   cases. Verify round trips and rejected/uncertain states before adding a UI.
4. Test the smallest artifact with one real operator, especially whether the proposed
   handoff changes a recurring decision rather than merely producing a report.
