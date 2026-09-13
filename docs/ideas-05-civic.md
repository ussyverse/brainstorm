# Civic and Mutual-Aid Recombination Ideas

**Date:** 2026-09-13
**Status:** proposals, not existing integrations
**Scope:** nine new civic or mutual-aid product concepts, plus two rejected
adjacent concepts. Ideas are ordered by local demonstrability and the amount of
concrete source reuse, not by measured demand.

The existing source-checked shortlist already covers a generic volunteer-gap
desk with `ussyverse/commonsaussy` + `ussyverse/hoistussy`. The proposals below
avoid repeating that exact pairing and focus on different recurring workflows.
Every serious proposal uses two to four repositories and at least two
`ussyverse` repositories. An **Exists** label means the cited source was
inspected. **Proposed** means adapter or product work still required.

## 1. The multilingual mutual-aid dispatch card

**Exact repositories:** `ussyverse/apicolaussy` + `ussyverse/hoistussy` +
`mojomast/Tchaikovskussy`

**User and recurring pain.** A neighborhood mutual-aid coordinator receives
requests in several languages and has to restate the need, find a suitable
offer, and keep track of whether the offer was actually accepted. Translation,
matching, and acknowledgment currently happen in separate conversations.

**Product promise.** Turn a resident's request into a translated, bounded ask
with a clear owner, expiry, and acknowledgment state.

**Flow:** resident, need, skill/resource, location and time window -> Apicola
normalizes the need and finds compatible offers; Tchaikovsky provides a
recipient-selected translation; Hoist creates the short-lived notice and
records response meaning -> a private dispatch card with the original text,
translated text, match rationale, expiry, and confirmed next step.

**Existing source to reuse.** **Exists:** Apicola's `Resident`, `Need`,
`LedgerEntry`, `HelperMatch`, `distanceKm`, `availabilityOverlap`, and ledger
functions in [`src/lib/apicola.ts`](https://github.com/ussyverse/apicolaussy/blob/HEAD/src/lib/apicola.ts).
**Exists:** Hoist's notice composition and acknowledgment summaries in
[`hoist/engine.py`](https://github.com/ussyverse/hoistussy/blob/HEAD/hoist/engine.py)
and its documented storage/render surfaces in
[`README.md`](https://github.com/ussyverse/hoistussy/blob/HEAD/README.md).
**Exists:** Tchaikovsky's chat models and translation path in
[`backend/models.py`](https://github.com/mojomast/Tchaikovskussy/blob/HEAD/backend/models.py),
[`backend/main.py`](https://github.com/mojomast/Tchaikovskussy/blob/HEAD/backend/main.py),
and [`frontend/src/components/Chat.tsx`](https://github.com/mojomast/Tchaikovskussy/blob/HEAD/frontend/src/components/Chat.tsx).

**Missing integration work.** Define a stable `needId`, `noticeId`, and
`translationId`; make source and translated text separately visible; add an
explicit accept/decline/needs-clarification response; and add expiry and
redaction rules. Apicola's `rankHelpers` must not become a public ranking of
people. Show matching inputs and alternatives instead. Tchaikovsky requires an
LLM provider and is not a local-only dependency.

**Maturity and feasibility caveats.** The three components have different
storage and language boundaries. Translation quality, consent to share a need,
and identity handling require user testing. A translated request is a
communication aid, not proof that the proposed helper is suitable or safe.

**Smallest useful demo.** Enter one food-delivery request in Spanish, one
English offer with a time window, and one unfulfilled request. Produce the
original/translated dispatch card, mark a response as confirmed, then show
expiry of the unfilled notice.

**Acceptance criteria.** The card preserves original text; recipients can
choose their display language; no request is marked fulfilled by a mere view or
reaction; the notice expires; and the raw match inputs remain exportable.

**Why better than separate tools.** The shared object is a bounded need with a
lifecycle, not merely a chat message. Translation makes the ask readable,
Apicola makes it concrete, and Hoist makes its status observable.

**Rejected adjacent components.** Do not add `ussyverse/vectorussy` here:
its recruitment analytics would tempt the product toward person or channel
ranking. Do not add another bot or agent runtime until the manual dispatch card
works.

## 2. Street-corner greening micro-project

**Exact repositories:** `ussyverse/vitalussy` + `ussyverse/tilthaussy` +
`ussyverse/forageussy`

**User and recurring pain.** A block steward wants to improve a vacant verge,
planter, or tree pit, but observations of the place, foot traffic, and materials
needed for the intervention live in separate notes. The result is either an
unbounded wish list or a workday with no supplies.

**Product promise.** Turn one observed street corner into a small, evidence-
linked improvement packet and a materials pickup run.

**Flow:** block observation, barrier, site dimensions, soil state, traffic
events, desired intervention, and available materials -> Vital records the
observation and produces dimension-specific prompts; Tiltha analyzes traffic,
soil, and path layout; Forage matches material needs to patches and builds a
collection route -> a one-site action card with assumptions, access notes,
materials list, pickup sequence, and follow-up observation.

**Existing source to reuse.** **Exists:** Vital's `Observation`,
`scoreObservation`, `generateRecommendations`, and local persistence in
[`src/vital.ts`](https://github.com/ussyverse/vitalussy/blob/HEAD/src/vital.ts).
**Exists:** Tiltha's `GardenZone`, `TrafficEvent`, `SoilObservation`,
`PathLayout`, `analyze_zone`, and `recommend_layout` in
[`src/tiltha/models.py`](https://github.com/ussyverse/tilthaussy/blob/HEAD/src/tiltha/models.py)
and [`src/tiltha/engine.py`](https://github.com/ussyverse/tilthaussy/blob/HEAD/src/tiltha/engine.py).
**Exists:** Forage's `Need`, `Patch`, `Assignment`, `TripInput`, `PlanTrip`,
`BuildRoute`, and JSON persistence in
[`pkg/forage/models.go`](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/models.go),
[`pkg/forage/engine.go`](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/engine.go),
and [`pkg/forage/persist.go`](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/persist.go).

**Missing integration work.** Define a site ID and map each requested material
to a real quantity and unit. Keep site observations, soil prompts, and supply
availability separate. Add an intervention-completion record and a later
observation; do not claim that the heuristics predict plant survival or public
safety.

**Maturity and feasibility caveats.** Vital and Tiltha use supplied,
heuristic observations. Forage uses approximate distance and stock/patch data,
not live inventory or navigation. Permissions, utilities, land ownership, and
local rules remain human responsibilities.

**Smallest useful demo.** Record one dark, compacted tree pit, request mulch and
three native plants from two sources, build a pickup route, and record whether
the site was accessible after the work.

**Acceptance criteria.** Every proposed action links to an observation or
explicit user input; material quantities and units are visible; missing stock
stays unresolved; the route references the requested materials; and a later
observation does not overwrite the initial condition.

**Why better than separate tools.** The common entity is a site improvement:
Vital frames the resident observation, Tiltha constrains physical intervention,
and Forage turns the plan into a supply handoff.

**Rejected adjacent components.** Do not add Symbiosis for a generic planting
recommendation. This MVP is about a bounded civic site and supply run; species
relationships would add domain scope before the site-to-material handoff is
validated.

## 3. Block walk to accessible action plan

**Exact repositories:** `ussyverse/vitalussy` + `ussyverse/controlaussy` +
`ussyverse/egressaussy`

**User and recurring pain.** Residents conducting a block walk can collect
interesting observations but struggle to choose a walk that works for children,
older residents, or people who need clear bailouts, and they often end without
a practical follow-up artifact.

**Product promise.** Produce an accessible observation walk with explicit route
choices, departure supports, and a small action memo.

**Flow:** resident-authored landmarks, route legs, accessibility needs, and
block observations -> Controla creates control cards and difficulty/bailout
details; Egressa analyzes event bottlenecks, meeting points, buddy protocol, and
departure waves; Vital records observations and produces dimension-specific
recommendations -> a printable walk packet plus an evidence-linked action list.

**Existing source to reuse.** **Exists:** Vital's `Observation`,
`scoreObservation`, `generateRecommendations`, and local observation storage in
[`src/vital.ts`](https://github.com/ussyverse/vitalussy/blob/HEAD/src/vital.ts).
**Exists:** Controla's `Control`, `makeLeg`, `buildWalkPlan`, JSON export, and
HTML report in [`src/controla.nim`](https://github.com/ussyverse/controlaussy/blob/HEAD/src/controla.nim).
**Exists:** Egressa's `EventPlan`, `compute_bottlenecks`,
`score_safe_eddies`, `recommend_departure_wave`, and `build_buddy_protocol` in
[`src/egressa/models.py`](https://github.com/ussyverse/egressaussy/blob/HEAD/src/egressa/models.py)
and [`src/egressa/engine.py`](https://github.com/ussyverse/egressaussy/blob/HEAD/src/egressa/engine.py).

**Missing integration work.** Map Controla leg IDs to Vital observation points
and Egressa meeting points. Make accessibility modes user-authored constraints,
not inferred judgments. Add an action record with owner, evidence, due date,
and follow-up observation. The adapter must preserve route uncertainty and
should not imply that a numeric vitality result establishes neighborhood
safety.

**Maturity and feasibility caveats.** Controla uses manually authored route
data; Egressa's scores depend on supplied event plans; Vital's scores are
heuristic. None supplies live maps, traffic, or emergency dispatch. Verify a
walk on site before publishing it.

**Smallest useful demo.** Create a 20-minute child-mode walk with two bailouts,
observe a dark crossing and an inactive frontage, then export a route card and
one follow-up memo.

**Acceptance criteria.** The packet names the source observation for each
action; a participant can select a shorter/bailout route; the product never
claims a route is universally safe; and a second walk can mark an observation
as changed without overwriting the original.

**Why better than separate tools.** The walk itself becomes the evidence
collection protocol and the handoff artifact. Navigation, group departure, and
observation-to-action are joined by leg and point IDs.

**Rejected adjacent components.** Do not add `ussyverse/egressaussy`-like
emergency tools or health-triage engines. This is a resident observation and
planning workflow, not an emergency authority.

## 4. Care-circle backup rehearsal

**Exact repositories:** `ussyverse/kinshipussy` + `ussyverse/raciaussy` +
`ussyverse/firelineussy`

**User and recurring pain.** A mutual-aid care circle supports several people
with rides, meals, check-ins, or medication pickup. The same two people carry
the work, and a backup gap is discovered only when somebody becomes
unavailable.

**Product promise.** Rehearse one week's care handoffs and expose missing
backup capacity before the next absence.

**Flow:** care people/edges, care types, tasks, availability, volunteers and
planned assignments -> Kinship identifies load, reciprocity, ambiguity and
backup gaps; Racia checks responsibility/access and load distribution;
Fireline models task fuel and recovery capacity -> a consented care-circle
roster with primary/backup cards, open asks, and a conversation agenda.

**Existing source to reuse.** **Exists:** Kinship `Network`, `CareEdge`,
`CareLoadScores`, `BackupPathGaps`, `SimulateUnavailable`, and
`ConversationGuide` in [`kinship/types.go`](https://github.com/ussyverse/kinshipussy/blob/HEAD/kinship/types.go)
and [`kinship/analysis.go`](https://github.com/ussyverse/kinshipussy/blob/HEAD/kinship/analysis.go).
**Exists:** Racia's role/access models and `analyzePlan`/`computeLoads` in
[`src/models.ts`](https://github.com/ussyverse/raciaussy/blob/HEAD/src/models.ts)
and [`src/engine.ts`](https://github.com/ussyverse/raciaussy/blob/HEAD/src/engine.ts).
**Exists:** Fireline's `Volunteer`, `Task`, `recovery_capacity`,
`prescribed_burns`, and `analyze_landscape` in
[`fireline/models.py`](https://github.com/ussyverse/firelineussy/blob/HEAD/fireline/models.py)
and [`fireline/engine.py`](https://github.com/ussyverse/firelineussy/blob/HEAD/fireline/engine.py).

**Missing integration work.** Define a common task and person identifier;
separate paid/professional care from informal help; add date-specific
availability; and make all sharing opt-in. Convert outputs into questions and
assignments, not a care-worthiness or burnout diagnosis.

**Maturity and feasibility caveats.** The models contain sensitive relationship
and care information. Fireline's capacity values are a planning metaphor and
must not be treated as a psychological or medical assessment. Racia's load is
a heuristic.

**Smallest useful demo.** Enter five care tasks, four participants, one absent
primary, and two possible backups. Generate the gap report, confirm one handoff
by the backup, and export the week card.

**Acceptance criteria.** Simulating an unavailable person identifies affected
tasks; each affected task has either a named backup or an explicit open gap;
the roster can be filtered before export; and the original assignments remain
auditable.

**Why better than separate tools.** Kinship finds network gaps, Racia tests
responsibility and access, and Fireline forces the group to account for finite
recovery capacity. The shared unit is a care task during a defined week.

**Rejected adjacent components.** Do not add a public volunteer leaderboard.
The product should reveal uncovered tasks and invite participation without
ranking individuals.

## 5. Meeting decision and follow-through packet

**Exact repositories:** `ussyverse/auscultussy` + `ussyverse/condorcetussy` +
`ussyverse/quorumussy`

**User and recurring pain.** A tenant association or neighborhood committee
spends meetings discussing the same issue, loses the minority concerns, and
leaves without a decision that can be revisited.

**Product promise.** Diagnose the meeting pattern, record a transparent choice,
and emit a time-bounded follow-up packet without pretending the algorithm has
made the civic decision.

**Flow:** agenda beats, meeting observations, participant-authored ranked
ballots, options, vetoes and tolerances -> Ausculta diagnoses clarity, rhythm,
and follow-up; Condorcet computes pairwise results and cycle information;
Quorum records threshold, veto, polarization, and suggestion diagnostics -> a
decision record containing raw ballots, unresolved disagreement, chosen action,
owner, review date, and next meeting prompt.

**Existing source to reuse.** **Exists:** Ausculta's `MeetingObservation`,
`diagnose_meeting`, `trend_analysis`, and Markdown/JSON rendering in
[`src/ausculta/models.py`](https://github.com/ussyverse/auscultussy/blob/HEAD/src/ausculta/models.py)
and [`src/ausculta/engine.py`](https://github.com/ussyverse/auscultussy/blob/HEAD/src/ausculta/engine.py).
**Exists:** Condorcet core/io/report modules for ranked ballots, pairwise
matrices, winners, cycle detection, and exports in
[`src/condorcet/core.py`](https://github.com/ussyverse/condorcetussy/blob/HEAD/src/condorcet/core.py),
[`src/condorcet/io.py`](https://github.com/ussyverse/condorcetussy/blob/HEAD/src/condorcet/io.py),
and [`src/condorcet/report.py`](https://github.com/ussyverse/condorcetussy/blob/HEAD/src/condorcet/report.py).
**Exists:** Quorum's `DecisionFile`, `RecordVote`, `Quorum`, `Polarization`,
`VetoDiagnostics`, and `Suggest` in
[`internal/quorum/model.go`](https://github.com/ussyverse/quorumussy/blob/HEAD/internal/quorum/model.go).

**Missing integration work.** Define a shared meeting/decision ID and preserve
the distinction between a ranked preference, a veto, a quorum result, and a
consensus claim. Add an action/follow-up schema and a human-readable dissent
view. Keep the components' different threshold and score semantics explicit.

**Maturity and feasibility caveats.** Ausculta's meeting labels are heuristic;
Condorcet and Quorum calculate formal outputs from supplied ballots, not civic
legitimacy. A result can be blocked or cyclic and still require a human
conversation. No component supplies identity, authentication, or secure
ballot handling.

**Smallest useful demo.** Use three options for a community-room policy, six
anonymous ballots, one veto, and two meeting observations. Export the raw
ballots, diagnostics, decision status, and a review task.

**Acceptance criteria.** Every computed result can be recomputed from the
exported ballots; a veto or cycle prevents a false "consensus" label; the group
can record a human resolution; and a review date produces a follow-up prompt.

**Why better than separate tools.** The common entity is a decision with a
meeting context and a later check. One tool explains how the meeting operated,
one explains preference aggregation, and one stores the group's declared rule.

**Rejected adjacent components.** Do not add a general parliamentary agent or
LLM facilitator. It would add an orchestration layer and make it harder to see
which statements and ballots actually supported the decision.

## 6. Restorative apartment-noise casebook

**Exact repositories:** `ussyverse/sonantaussy` + `ussyverse/lichenoussy` +
`ussyverse/auscultussy`

**User and recurring pain.** A resident committee handles repeated noise or
shared-space conflicts. Complaints become accusations, context is lost, and
the next conversation has no record of what was tried.

**Product promise.** Preserve a neutral incident record and turn it into a
small, revisable conversation plan.

**Flow:** resident-authored time, place, sound description, impact, and prior
attempts -> Sonanta classifies pathway, masking possibility, intervention
ladder, and documentation packet; Licheno stores place-based observations,
uncertainty, and restorative actions; Ausculta diagnoses the follow-up meeting ->
a private casebook page with hypotheses separated from accusations, agreed next
step, and review observation.

**Existing source to reuse.** **Exists:** Sonanta's `NoiseEvent`, `triage`,
`classify_pathway`, `build_intervention_ladder`, and
`create_documentation_packet` in
[`src/lib.rs`](https://github.com/ussyverse/sonantaussy/blob/HEAD/src/lib.rs).
**Exists:** Licheno models, engine, local storage, and exports in
[`src/licheno/models.py`](https://github.com/ussyverse/lichenoussy/blob/HEAD/src/licheno/models.py),
[`src/licheno/engine.py`](https://github.com/ussyverse/lichenoussy/blob/HEAD/src/licheno/engine.py),
and [`src/licheno/export.py`](https://github.com/ussyverse/lichenoussy/blob/HEAD/src/licheno/export.py).
**Exists:** Ausculta's meeting
diagnosis and follow-up fields in [`src/ausculta/models.py`](https://github.com/ussyverse/auscultussy/blob/HEAD/src/ausculta/models.py).

**Missing integration work.** Add consent and access controls, a common incident
ID, exact event dates, and an explicit "reported / observed / agreed" evidence
type. The app must allow a resident to reject or amend a generated description.

**Maturity and feasibility caveats.** Sonanta's classification is a supplied-
input heuristic and its safety guidance is not emergency advice. Licheno's
restorative language must not be used to minimize harassment or urgent danger.
No component validates an accusation or identifies a source of sound.

**Smallest useful demo.** Record three neutral incidents, generate a ladder for
one recurring impact noise, hold a meeting with one follow-up action, and add a
later observation showing whether the condition changed.

**Acceptance criteria.** Raw reports remain intact; hypotheses are visually
separate from observations; each intervention has an owner and review date;
and exporting a case excludes private notes unless explicitly selected.

**Why better than separate tools.** The common entity is a place-based incident
that must move through report, conversation, intervention, and review. The
combination supplies a lifecycle rather than another complaint score.

**Rejected adjacent components.** Do not add a neighborhood sentiment score or
automated accusation detector. Both would turn incomplete reports into claims
about people.

## 7. Mutual-aid pickup run sheet

**Exact repositories:** `ussyverse/forageussy` + `ussyverse/apicolaussy` +
`ussyverse/egressaussy`

**User and recurring pain.** A volunteer picking up groceries, donated items,
or library materials for several residents must decide what can be collected,
which requests are still open, and how the group will meet and leave without
losing the handoff.

**Product promise.** Produce one bounded pickup run with explicit assignments,
stops, meeting point, and unresolved requests.

**Flow:** resident needs, available stock/patches, volunteer home point,
capacity, event meeting points and departure constraints -> Apicola links needs
to suitable offers; Forage builds assignments and a route; Egressa adds a
meeting/departure or buddy protocol where a group pickup is involved -> a
printable run sheet with stop order, item/request IDs, collection confirmations,
and return-to-requester checklist.

**Existing source to reuse.** **Exists:** Forage `Need`, `Patch`, `Assignment`,
`TripInput`, `PlanTrip`, `BuildRoute`, and JSON persistence in
[`pkg/forage/models.go`](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/models.go),
[`pkg/forage/engine.go`](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/engine.go),
and [`pkg/forage/persist.go`](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/persist.go).
**Exists:** Apicola need, availability, distance, and ledger types/functions in
[`src/lib/apicola.ts`](https://github.com/ussyverse/apicolaussy/blob/HEAD/src/lib/apicola.ts).
**Exists:** Egressa meeting-point, buddy, and departure-wave models in
[`src/egressa/models.py`](https://github.com/ussyverse/egressaussy/blob/HEAD/src/egressa/models.py)
and [`src/egressa/engine.py`](https://github.com/ussyverse/egressaussy/blob/HEAD/src/egressa/engine.py).

**Missing integration work.** Add item-level quantity and substitution rules,
stable request/stop IDs, collection confirmation, and a privacy-preserving
export. Preserve Forage's route assumptions and never mark a need fulfilled
until the recipient confirms receipt.

**Maturity and feasibility caveats.** Forage uses Euclidean travel proxies and
has constraints around selected patches. It is not a live navigation or
delivery service. Food, medication, and identity-sensitive requests require
separate policy and human review.

**Smallest useful demo.** Create four requests, three collection points, one
volunteer capacity limit, and one missing item. Export the route, confirm two
collections, and leave the missing request open.

**Acceptance criteria.** Every route stop references one or more request IDs;
the plan flags capacity or stock shortfalls; completion requires recipient
confirmation; and the original request remains visible after a partial run.

**Why better than separate tools.** Matching answers "what belongs together,"
routing answers "in what order," and Egressa answers "how does the group
coordinate the physical handoff."

**Rejected adjacent components.** Do not add a general map or delivery SaaS
connector in the first demo. The local run sheet should establish whether the
handoff is useful before adding live travel data.

## 8. Repair-cafe tool library

**Exact repositories:** `ussyverse/paddockussy` + `ussyverse/forageussy` +
`ussyverse/apicolaussy`

**User and recurring pain.** A repair cafe lends drills, meters, sewing tools,
and spare parts, but loses track of condition, who has an item, which requests
can be served together, and when an item needs rest or inspection.

**Product promise.** Coordinate a small lending or pickup session while keeping
the commons ledger and condition evidence visible.

**Flow:** assets, condition observations, usage events, resident requests,
available patches, and pickup capacity -> Paddock reports pressure and rotation;
Apicola matches requests to skills/resources; Forage groups collection points
and builds a run -> loan card, pickup route, return checklist, and condition
follow-up.

**Existing source to reuse.** **Exists:** Paddock's asset/usage/condition
models, `analyze_asset`, `fairness_summary`, `recommend_rotation`, and report
rendering in [`src/lib.rs`](https://github.com/ussyverse/paddockussy/blob/HEAD/src/lib.rs).
**Exists:** Forage assignment, route, trip-plan, and persistence functions in
[`pkg/forage/engine.go`](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/engine.go)
and [`pkg/forage/persist.go`](https://github.com/ussyverse/forageussy/blob/HEAD/pkg/forage/persist.go).
**Exists:** Apicola's resident, need, skill, availability, and ledger contract
in [`src/lib/apicola.ts`](https://github.com/ussyverse/apicolaussy/blob/HEAD/src/lib/apicola.ts).

**Missing integration work.** Define loan, return, and inspection events;
separate asset condition from user blame; bind an asset ID to an assignment and
route stop; and add quantity/unit semantics so a tool, hour, and spare part are
not summed as if interchangeable.

**Maturity and feasibility caveats.** Paddock's fairness indicators are
planning aids, not a moral score. Forage's route is approximate. The first
version should be a local event ledger, not an always-on inventory system.

**Smallest useful demo.** List six tools, two condition observations, four
repair requests, and one Saturday pickup loop. Check out two tools, record a
return condition, and generate the next rotation suggestion.

**Acceptance criteria.** No loan can disappear without a return or open-status
record; condition changes retain before/after observations; the route references
the loans it carries; and the output never ranks borrowers.

**Why better than separate tools.** The shared transaction is a time-bounded
asset loan. Stewardship, need matching, and physical movement all affect
whether the repair session actually succeeds.

**Rejected adjacent components.** Do not add `ussyverse/commonsaussy` here:
its pledge-bottleneck workflow would duplicate the existing volunteer-gap
shortlist and is not needed to demonstrate the asset loan lifecycle.

## 9. Volunteer onboarding without a leaderboard

**Exact repositories:** `ussyverse/vectorussy` + `ussyverse/firelineussy` +
`ussyverse/raciaussy`

**User and recurring pain.** A small community group attracts people through
several channels, but newcomers do not know which concrete task to try, while
organizers cannot tell whether a role is under-described, over-capacity, or
missing a handoff.

**Product promise.** Turn an invitation into a low-risk first task and an
explicit handoff, using aggregate funnel evidence rather than scoring people.

**Flow:** campaign/source, invitation, response, task, role, access needs, and
volunteer capacity -> Vector summarizes recruitment edges and leakage by source;
Fireline identifies task load and recovery pressure at team level; Racia checks
role ownership and access requirements -> an onboarding packet with one starter
task, contact/knowledge handoff, role gaps, and aggregate follow-up metrics.

**Existing source to reuse.** **Exists:** Vector recruitment-chain models and
analytics in [`src/model.ts`](https://github.com/ussyverse/vectorussy/blob/HEAD/src/model.ts)
and [`src/analytics.ts`](https://github.com/ussyverse/vectorussy/blob/HEAD/src/analytics.ts).
**Exists:** Fireline's volunteer/task models, `fuel_load`,
`recovery_capacity`, `prescribed_burns`, and report generation in
[`fireline/models.py`](https://github.com/ussyverse/firelineussy/blob/HEAD/fireline/models.py)
and [`fireline/engine.py`](https://github.com/ussyverse/firelineussy/blob/HEAD/fireline/engine.py).
**Exists:** Racia's role, access, assignment, and load analysis in
[`src/models.ts`](https://github.com/ussyverse/raciaussy/blob/HEAD/src/models.ts)
and [`src/engine.ts`](https://github.com/ussyverse/raciaussy/blob/HEAD/src/engine.ts).

**Missing integration work.** Define a consented event schema for invitation,
response, attendance, and completion; use aggregate counts only; add a real
starter-task editor; and distinguish "no response," "declined," and "not yet
contacted." Do not expose Vector's ranking-oriented outputs as judgments of
individuals.

**Maturity and feasibility caveats.** Vector's analytics describe supplied
recruitment data; they do not establish why somebody did not respond. Fireline
and Racia use heuristic load/capacity models. The product must support people
who prefer not to be tracked.

**Smallest useful demo.** Import twenty anonymized invitations across three
channels, define four starter tasks, and show one role with unclear ownership.
Assign two tasks, complete one, and generate an aggregate follow-up report.

**Acceptance criteria.** No individual ranking appears in the UI or export; a
new participant sees the task's owner, time estimate, access needs, and backup;
the funnel distinguishes response states; and capacity warnings link to team
tasks rather than people.

**Why better than separate tools.** Recruitment evidence is useful only when it
leads to a concrete first contribution. Racia makes the handoff legible and
Fireline checks whether the organization can absorb the work.

**Rejected adjacent components.** Do not add `ussyverse/commonsaussy` or
`ussyverse/hoistussy` to make another open-ask board. The existing shortlist
already covers that need; this proposal is about onboarding and role clarity.

## Rejected Concepts

### A. Neighborhood trust and reliability score

**Temptation:** combine `ussyverse/apicolaussy`, `ussyverse/vectorussy`,
`ussyverse/kinshipussy`, and `ussyverse/commonsaussy` into a score used to
select the "most reliable" residents or volunteers.

**Why reject.** The components describe different entities: aid matches,
recruitment events, care-network relationships, and pledges. Their values are
not interchangeable evidence of character. Combining them would create a
person-ranking system, amplify missing-data bias, and make sensitive
relationship data operationally dangerous. The useful alternatives are the
bounded dispatch, care-circle, and onboarding workflows above, which retain
raw events and expose uncovered tasks without judging people.

### B. Civic command-center super-dashboard

**Temptation:** combine `ussyverse/vitalussy`, `ussyverse/egressaussy`,
`ussyverse/paddockussy`, `ussyverse/lichenoussy`, `ussyverse/quorumussy`, and a
new dashboard that shows one overall neighborhood health score.

**Why reject.** This stacks unrelated heuristics, route diagnostics, asset
condition, restorative observations, and group decisions without one natural
transaction or user deliverable. It would encourage false comparisons and
replace local judgment with an unexplained aggregate. A bounded walk, garden
workday, noise case, or decision packet has a clearer user, input, action, and
review loop.

## Inspection Record

The candidate source below was inspected on the date above. Revisions are the
short commit IDs returned by `git rev-parse --short HEAD`; no candidate
repository was modified.

| Repository | Revision | Relevant inspected source |
|---|---:|---|
| `ussyverse/apicolaussy` | `a7d9a74` | `src/lib/apicola.ts`, `src/lib/apicola.test.ts` |
| `ussyverse/auscultussy` | `875b0c2` | `src/ausculta/models.py`, `engine.py`, `render.py`, `io.py` |
| `ussyverse/condorcetussy` | `7f62d4c` | `src/condorcet/core.py`, `io.py`, `report.py` |
| `ussyverse/controlaussy` | `c3170f9` | `src/controla.nim`, `src/main.nim` |
| `ussyverse/egressaussy` | `df3811b` | `src/egressa/models.py`, `engine.py`, `main.py` |
| `ussyverse/firelineussy` | `319a946` | `fireline/models.py`, `engine.py`, `render.py`, tests |
| `ussyverse/forageussy` | `53bd956` | `pkg/forage/models.go`, `engine.go`, `persist.go`, tests |
| `ussyverse/hoistussy` | `1d51433` | `hoist/engine.py`, README storage/render documentation |
| `ussyverse/kinshipussy` | `308bbb3` | `kinship/types.go`, `analysis.go`, tests |
| `ussyverse/lichenoussy` | `7633132` | `src/licheno/models.py`, `engine.py`, `storage.py`, `export.py` |
| `ussyverse/paddockussy` | `b5fb590` | `src/lib.rs`, `src/main.rs`, tests |
| `ussyverse/quorumussy` | `397531d` | `internal/quorum/model.go`, `model_test.go` |
| `ussyverse/raciaussy` | `f7d1bfe` | `src/models.ts`, `engine.ts`, `render.ts`, tests |
| `ussyverse/sonantaussy` | `b8aee57` | `src/lib.rs`, `src/main.rs`, tests |
| `ussyverse/symbiosisussy` | `3bb7c01` | `src/symbiosis/models.py`, `ecology.py`, `main.py` |
| `ussyverse/tilthaussy` | `b586450` | `src/tiltha/models.py`, `engine.py`, `render.py` |
| `ussyverse/vectorussy` | `eae07cd` | `src/model.ts`, `analytics.ts`, extension tests |
| `ussyverse/vitalussy` | `859ce97` | `src/vital.ts`, extension and tests |
| `mojomast/Tchaikovskussy` | `ba91800` | `backend/models.py`, `main.py`, `llm.py`, frontend chat |

Commands run for this pass included `git rev-parse --short HEAD` in each
candidate checkout and `git status --short` in the brainstorm repository.
Searches and reads were performed against the checked-out files. No build,
installation, or test command was run, so this document makes no claim that
the inspected test suites currently pass or that any proposed integration is
operational.
