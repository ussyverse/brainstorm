# Social, Discord, and Creator-Community Ideas

**Research date:** 2026-09-13

**Focus:** online communities, Discord, group rituals, moderation, collaboration,
and creator communities.

These are new proposals, not additions to the ten-item shortlist in
`SOURCE_CHECKED_COMBINATIONS.md`. The existing shortlist already covers the
Commonsa/Hoist volunteer desk, the bot-fleet community operating system, and
the other combinations listed there; those are not repeated below.

## Evidence and Scope

I inspected source and manifests in the cloned repositories under
`/home/ubuntu/ussy/repos`. The revision IDs below were collected with
`git -C <repo> rev-parse --short HEAD`:

| Repository | Revision |
|---|---|
| `mojomast/Tchaikovskussy` | `ba91800` |
| `ussyverse/circleraussy` | `dd19b24` |
| `ussyverse/quorumussy` | `397531d` |
| `ussyverse/parliamentussy` | `1de34fe` |
| `mojomast/onno` | `5fb9af7` |
| `ussyverse/obscuraussy` | `3c91b65` |
| `ussyverse/scansionussy` | `6db8fc0` |
| `ussyverse/olfactoussy` | `496619f` |
| `mojomast/gemini-nano-banana-discord-bot` | `ac6a403` |
| `ussyverse/chromascriptussy` | `5940bde` |
| `mojomast/scoreboardussy` | `28ce25e` |
| `ussyverse/egressaussy` | `df3811b` |
| `mojomast/arrhivescrape` | `afffec1` |
| `ussyverse/archivioussy` | `918d690` |
| `mojomast/ussybot` | `c5727c1` |
| `ussyverse/orbitalussy` | `276d27f` |

No candidate repository was modified. I did not build or run the candidate
projects in this pass. Thus, even source-backed functions below are **not
runtime-verified**; existing tests and README claims are not treated as proof
that a full product works.

## Proposals

### 1. Translation-Aware Repair Room

**Target user and pain.** A multilingual Discord or online affinity group has a
bounded interpersonal rupture. Members can understand the broad topic but not
all of the nuance, and public arguments turn into permanent searchable context.
The moderator needs a voluntary repair path without making a bot judge who was
right.

**Exact repositories.**

- [`mojomast/Tchaikovskussy`](https://github.com/mojomast/Tchaikovskussy)
- [`ussyverse/circleraussy`](https://github.com/ussyverse/circleraussy)
- [`ussyverse/quorumussy`](https://github.com/ussyverse/quorumussy)

**Existing evidence.**

- **Exists:** Tchaikovskussy's [`backend/models.py`](https://github.com/mojomast/Tchaikovskussy/blob/HEAD/backend/models.py) has per-user speaking/perceiving languages and message records retaining original and translated text. Its [`backend/main.py`](https://github.com/mojomast/Tchaikovskussy/blob/HEAD/backend/main.py) broadcasts personalized WebSocket payloads and caches translations per recipient language.
- **Exists:** Circlera's [`models.py`](https://github.com/ussyverse/circleraussy/blob/HEAD/src/circlera/models.py) models consent, private statements, needs, repair commitments, and follow-ups. [`rules.py`](https://github.com/ussyverse/circleraussy/blob/HEAD/src/circlera/rules.py) blocks coercion, threats, abuse, retaliation fears, legal constraints, and forced participation before creating a session.
- **Exists:** Quorum's [`internal/quorum/model.go`](https://github.com/ussyverse/quorumussy/blob/HEAD/internal/quorum/model.go) stores options, 0-10 preferences, vetoes, tolerances, and local JSON reports. It describes polarization as a stuck-pattern warning rather than a person label.

**Proposed handoff/data flow.** A human moderator creates a case from a
specific Discord thread and invites only the affected people. The adapter
stores a case ID, participant IDs, language preferences, and a short neutral
incident description. Circlera runs the consent/safety gate and its harm,
needs, and accountability rounds. Statements remain private by default. The
group may put two or three concrete repair options into a Quorum decision file;
votes are preferences and constraints, not a verdict. Tchaikovskussy renders
each participant's opted-in prompt or shared summary in their chosen language.
The final artifact is a consent log, repair agreement, and follow-up date, not
a moderation score.

**MVP.** A local web form plus a Discord command that creates a case, sends
opt-in private prompts, imports manually pasted statements, and exports a
filtered repair agreement. Use two languages and two repair options. Keep
actual message capture out of the first slice.

**Why the combination is valuable.** Circlera supplies a safety boundary and a
repair sequence; Tchaikovskussy reduces language friction; Quorum gives a
small group a transparent way to choose among acceptable next steps. Separate
translation and moderation tools would not preserve consent, privacy, and
repair follow-up together.

**Risks, maturity, and privacy.** Translation can flatten legal, cultural, or
emotional nuance, so every translated statement must show the original and be
editable by its author. Circlera is explicitly not abuse mediation or therapy;
blocked cases need human/outside support. Quorum's weights and polarization
heuristics are not fair authority. Do not ingest whole channels, expose
private notes to moderators by default, or retain translated copies longer
than the case policy allows. The Discord adapter, authentication, encryption,
and deletion workflow are **Proposed**; end-to-end behavior is **Unverified**.

### 2. Proposal-to-Motion Desk for Open Communities

**Target user and pain.** An open-source or creator community receives ideas in
Discord, but decisions disappear in chat. Members need a visible proposal,
seconding, alternatives, a time-bounded vote, and minutes that can be appealed
without granting a moderator opaque power.

**Exact repositories.**

- [`mojomast/onno`](https://github.com/mojomast/onno)
- [`ussyverse/quorumussy`](https://github.com/ussyverse/quorumussy)
- [`ussyverse/parliamentussy`](https://github.com/ussyverse/parliamentussy)

**Existing evidence.**

- **Exists as a documented protocol, not a tested service:** ONNO's [`skill.md`](https://github.com/mojomast/onno/blob/HEAD/skill.md) defines PRs as threads, files as conversations, reviews as governance, append-only replies, and merge-optional participation. Its [`forum/README.md`](https://github.com/mojomast/onno/blob/HEAD/forum/README.md) defines the file-based forum workflow.
- **Exists:** Quorum's CLI in [`main.go`](https://github.com/ussyverse/quorumussy/blob/HEAD/main.go) supports local JSON initialization, member/option registration, votes, status, diagnosis, and suggestions.
- **Exists:** Parliament's [`session.py`](https://github.com/ussyverse/parliamentussy/blob/HEAD/src/parliament/session.py) joins motions, seconders, quorum calls, voting, points of order, appeals, and minutes. [`journal.py`](https://github.com/ussyverse/parliamentussy/blob/HEAD/src/parliament/journal.py) appends hash-linked entries and renders session minutes.

**Proposed handoff/data flow.** A Discord `/proposal` command creates a
proposal record and a corresponding ONNO-style Markdown thread. A maintainer
publishes the scope, alternatives, decision deadline, and eligibility rule.
For a low-stakes choice, the adapter exports member preferences, tolerances,
and vetoes to Quorum. For a consequential policy change, a human promotes the
proposal to a Parliament motion, records seconders and quorum, accepts written
points of order, and publishes minutes. The canonical record links the
Discord message, forum file, decision JSON, motion ID, and final action.

**MVP.** A local CLI that turns a pasted proposal into a Markdown thread and a
Quorum JSON file, plus a review form that writes a decision summary. Add the
Parliament path only for one policy type, such as channel naming or event
format. No automatic merge, ban, or role change.

**Why the combination is valuable.** ONNO provides an asynchronous, portable
discussion surface; Quorum handles member constraints for ordinary choices;
Parliament supplies procedural checkpoints and appealable minutes for higher-
impact decisions. This is a decision trail rather than another chat bot or
activity dashboard.

**Risks, maturity, and privacy.** ONNO's core is a protocol and repository
content, not a Discord connector. Parliament's source calls participants
`Agent` and includes weighted votes and error-based weights; human-community
use requires a new explicit eligibility model and must not silently inherit
those defaults. A hash chain proves record continuity, not truth. Keep private
ballots and sensitive moderator evidence separate from public minutes. Never
let the adapter execute bans, merges, or permission changes from a vote.
The protocol-to-Discord bridge and human policy review are **Proposed** and
runtime behavior is **Unverified**.

### 3. Constraint-Based Creator Critique Circle

**Target user and pain.** A photography, sketching, or writing club wants a
repeatable critique ritual. Unstructured "thoughts?" prompts favor confident
speakers, while numeric judging turns peers into a leaderboard and gives
little help to the maker.

**Exact repositories.**

- [`ussyverse/obscuraussy`](https://github.com/ussyverse/obscuraussy)
- [`ussyverse/scansionussy`](https://github.com/ussyverse/scansionussy)
- [`ussyverse/olfactoussy`](https://github.com/ussyverse/olfactoussy)

**Existing evidence.**

- **Exists:** Obscura's [`obscura/generator.py`](https://github.com/ussyverse/obscuraussy/blob/HEAD/obscura/generator.py) produces seeded prompt cards with timeboxes, capture limits, unlock rules, and reflection questions. [`obscura/reports.py`](https://github.com/ussyverse/obscuraussy/blob/HEAD/obscura/reports.py) exports Markdown, JSON, and printable HTML cards.
- **Exists:** Scansion's [`src/lib.rs`](https://github.com/ussyverse/scansionussy/blob/HEAD/src/lib.rs) exposes `analyze` and reports breath groups, cadence, sound devices, and revision prompts. Its [`src/main.rs`](https://github.com/ussyverse/scansionussy/blob/HEAD/src/main.rs) accepts text, files, or stdin and emits text, Markdown, or JSON.
- **Exists:** Olfacto's [`src/engine.ts`](https://github.com/ussyverse/olfactoussy/blob/HEAD/src/engine.ts) validates a scene profile and emits craft expansions, fatigue warnings, tone checks, persistence maps, and memory prompts. Its [`src/types.ts`](https://github.com/ussyverse/olfactoussy/blob/HEAD/src/types.ts) defines the structured report.

**Proposed handoff/data flow.** The facilitator chooses a seeded Obscura deck
for the week's shared constraint. Each maker submits a work sample and an
optional self-question. The coordinator runs Scansion on text or captions and
Olfacto on an explicitly authored fiction/memoir smellscape, preserving raw
submission text beside the reports. It builds a critique packet with one
observation prompt, one maker-selected question, and one optional craft
experiment per submission. Members respond in a fixed order; no composite
score or creator ranking is produced.

**MVP.** A local folder format with `session.json`, submissions, and a command
that generates the deck and per-submission Markdown cards. Start with photos
and captions, making Scansion/Olfacto optional by medium. Run one four-person
critique and ask whether every maker received an actionable next experiment.

**Why the combination is valuable.** Obscura gives the group a shared practice
ritual; Scansion and Olfacto turn different kinds of work into concrete,
inspectable questions. The output improves the conversation without claiming
to know which work is best.

**Risks, maturity, and privacy.** Scansion syllable and stress estimates are
heuristics, and Olfacto's genre/tone checks are craft prompts, not audience
research. A submission may contain unpublished work, identities, or private
memories; default to local storage, explicit sharing per artifact, and
deletion after the session. The folder schema, submission UI, access control,
and chat integration are **Proposed**; candidate runtime behavior is
**Unverified**.

### 4. Multilingual Writing Relay

**Target user and pain.** A distributed writing group wants to exchange short
scenes or poems across languages. Machine translation can make a reply
possible, but it often hides the original voice and gives no structured reason
for a revision conversation.

**Exact repositories.**

- [`mojomast/Tchaikovskussy`](https://github.com/mojomast/Tchaikovskussy)
- [`ussyverse/scansionussy`](https://github.com/ussyverse/scansionussy)
- [`ussyverse/olfactoussy`](https://github.com/ussyverse/olfactoussy)

**Existing evidence.**

- **Exists:** Tchaikovskussy's [`backend/models.py`](https://github.com/mojomast/Tchaikovskussy/blob/HEAD/backend/models.py) stores original text, source language, target language, and translated output. [`frontend/src/components/Chat.tsx`](https://github.com/mojomast/Tchaikovskussy/blob/HEAD/frontend/src/components/Chat.tsx) visibly distinguishes original text and the recipient's language.
- **Exists:** Scansion has a pure Rust `analyze` function and JSON/Markdown rendering in [`src/lib.rs`](https://github.com/ussyverse/scansionussy/blob/HEAD/src/lib.rs).
- **Exists:** Olfacto's `expandPrompts`, `proustTriggers`, and `persistenceMap` are implemented in [`src/engine.ts`](https://github.com/ussyverse/olfactoussy/blob/HEAD/src/engine.ts), with explicit typed output rather than a free-form critique.

**Proposed handoff/data flow.** A host posts one seed prompt and a deadline.
Each participant submits an original paragraph in a private form. The relay
renders a recipient-opted translation while retaining the original beside it.
For English source text in the first version, Scansion generates rhythm and
breath observations; for supported fiction/memoir profiles, Olfacto generates
sensory expansion questions. Participants reply to the craft question, then
the author accepts, rejects, or annotates the translation and feedback.

**MVP.** One Discord channel, two languages, text-only submissions, and a
manual host command that posts original/translated pairs as separate embeds.
Run Scansion only on English samples and label other languages unsupported
rather than silently applying English heuristics.

**Why the combination is valuable.** Tchaikovskussy handles access to the
conversation, while the two ussyverse tools turn a translated exchange into a
bounded craft exercise. A translation-only room cannot preserve the author's
voice and next revision question as explicit objects.

**Risks, maturity, and privacy.** Translation uses an LLM and may send
unpublished writing to a provider. Require per-post consent, provider notice,
original visibility controls, and a delete command. Scansion is language-
limited and heuristic; Olfacto's confidence fields are not probabilities.
Tchaikovskussy currently has session/global statistics and admin controls, so
do not expose those to the relay by default. Persistence, Discord permissions,
and provider isolation are **Proposed**; end-to-end behavior is **Unverified**.

### 5. Weekly Visual Prompt Jam

**Target user and pain.** An art Discord wants a recurring low-pressure event
that produces work rather than an endless prompt backlog. Members need a fair
starting constraint, a way to iterate together, and a readable record of what
was made without turning output into popularity ranking.

**Exact repositories.**

- [`mojomast/gemini-nano-banana-discord-bot`](https://github.com/mojomast/gemini-nano-banana-discord-bot)
- [`ussyverse/obscuraussy`](https://github.com/ussyverse/obscuraussy)
- [`ussyverse/chromascriptussy`](https://github.com/ussyverse/chromascriptussy)

**Existing evidence.**

- **Exists:** The image bot's [`src/commands/imagine.py`](https://github.com/mojomast/gemini-nano-banana-discord-bot/blob/HEAD/src/commands/imagine.py), [`edit.py`](https://github.com/mojomast/gemini-nano-banana-discord-bot/blob/HEAD/src/commands/edit.py), and [`blend.py`](https://github.com/mojomast/gemini-nano-banana-discord-bot/blob/HEAD/src/commands/blend.py) expose generation, editing, and blending commands. [`src/commands/utils/queue.py`](https://github.com/mojomast/gemini-nano-banana-discord-bot/blob/HEAD/src/commands/utils/queue.py) and [`rate_limiter.py`](https://github.com/mojomast/gemini-nano-banana-discord-bot/blob/HEAD/src/commands/utils/rate_limiter.py) provide job/rate-control primitives.
- **Exists:** Obscura's [`generator.py`](https://github.com/ussyverse/obscuraussy/blob/HEAD/obscura/generator.py) gives a deterministic deck and reflection grid from a session config and seed.
- **Exists:** Chromascript's [`src/lib.rs`](https://github.com/ussyverse/chromascriptussy/blob/HEAD/src/lib.rs) and [`src/main.rs`](https://github.com/ussyverse/chromascriptussy/blob/HEAD/src/main.rs) analyze supplied beat palettes and export Markdown, CSV, SVG, and JSON. It does not extract a palette from an image.

**Proposed handoff/data flow.** The host runs Obscura for a 20-minute visual
constraint, posts one card and a deadline, and opens a thread per participant.
Members can use the image bot's `/imagine`, `/edit`, or `/blend` commands, with
the original prompt and iteration IDs retained. After the jam, each maker may
manually enter two to five chosen colors and a narrative role; Chromascript
turns those supplied beats into a private or shared palette strip. The export
contains the prompt, image references, opt-in attribution, and palette report,
not a winner.

**MVP.** One scheduled Discord command, one seeded Obscura card, one image
generation path, and a moderator-created gallery index. Add Chromascript only
for the closing retrospective after a creator supplies colors.

**Why the combination is valuable.** Obscura creates a repeatable ritual,
Nano Banana makes low-friction iteration available in the same room, and
Chromascript gives the retrospective a concrete visual artifact. The tools
form a prompt -> making -> reflection loop rather than three unrelated bots.

**Risks, maturity, and privacy.** The image bot uses OpenRouter and caches
images locally; provider terms, copyright, consent for reference images, and
prompt/image retention must be explicit. Rate limits and queue behavior are
source-backed but not runtime-tested. Chromascript checks author-supplied
intent, not image quality or color meaning. Store only opt-in thread content,
avoid face/reference uploads in the default channel, and provide deletion.
The gallery, scheduler, IDs, and palette-entry UI are **Proposed**.

### 6. Accessible Live-Show Companion

**Target user and pain.** An improv, school, or community performance has a
live audience display and audience interaction, but organizers separately
remember accessibility needs, meeting points, and a calm way home. A show tool
should not imply that its display is an emergency or crowd-control system.

**Exact repositories.**

- [`mojomast/scoreboardussy`](https://github.com/mojomast/scoreboardussy)
- [`ussyverse/egressaussy`](https://github.com/ussyverse/egressaussy)

**Existing evidence.**

- **Exists:** Scoreboardussy's [`README.md`](https://github.com/mojomast/scoreboardussy/blob/HEAD/README.md) documents separate control/display views, Socket.IO updates, round timers, audience voting, QR linking, English/French support, responsive layout, and HTML export. Its [`client/src/contexts/ScoreboardContext.tsx`](https://github.com/mojomast/scoreboardussy/blob/HEAD/client/src/contexts/ScoreboardContext.tsx) has round history, playlists, upcoming rounds, and server event emitters.
- **Exists:** Egressa's [`models.py`](https://github.com/ussyverse/egressaussy/blob/HEAD/src/egressa/models.py) models group communication needs, buddy pairs, venue features, meeting points, and observations. [`engine.py`](https://github.com/ussyverse/egressaussy/blob/HEAD/src/egressa/engine.py) produces bottlenecks, departure waves, safe meeting points, and lost-link protocols; [`main.py`](https://github.com/ussyverse/egressaussy/blob/HEAD/src/egressa/main.py) exposes local `GET /api/sample` and `POST /api/analyze` routes.

**Proposed handoff/data flow.** Before doors open, the organizer enters an
event plan and exports Egressa's offline card for the named group. Independently,
the show operator loads a Scoreboard playlist with round names, player limits,
timers, and audience interaction. The shared event ID links only the show
schedule and the card version; personal access needs stay in the local Egressa
file. A QR on the program can open the local display or a voluntary audience
vote, never a live location tracker.

**MVP.** A local LAN deployment with a control display, three rounds, a manual
audience prompt, and a printable Egressa card containing two meeting points and
buddy instructions. Test with venue staff and a small group before any public
network exposure.

**Why the combination is valuable.** Scoreboardussy handles the visible,
time-sensitive show ritual; Egressa handles pre-committed regrouping and
access needs. The handoff makes accessibility preparation part of the event
workflow without turning either tool into real-time safety authority.

**Risks, maturity, and privacy.** Scoreboardussy's audience votes are
experimental and in-memory, and its internet exposure guidance warns against
direct exposure. Egressa uses manually entered heuristics and explicitly is
not emergency guidance or real-time crowd prediction. Do not send
vulnerabilities or contact details to the scoreboard server. Bind locally,
use venue staff instructions as authoritative, and separate audience votes
from member identities. The event-ID adapter and unified setup are **Proposed**;
runtime behavior is **Unverified**.

### 7. Community Archive Recovery Desk

**Target user and pain.** A forum, fan community, or creator collective loses
its old host. The owner can recover pages from web archives, but readers need
to know which capture was used, which links are broken, which claims are
contested, and which posts should remain private.

**Exact repositories.**

- [`mojomast/arrhivescrape`](https://github.com/mojomast/arrhivescrape)
- [`ussyverse/archivioussy`](https://github.com/ussyverse/archivioussy)

**Existing evidence.**

- **Exists:** Arrhivescrape's [`pipeline/inventory.py`](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/pipeline/inventory.py), [`selection.py`](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/pipeline/selection.py), [`download.py`](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/pipeline/download.py), and [`validation.py`](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/pipeline/validation.py) implement source capture inventory/selection, content-addressed download, normalization, and validation surfaces.
- **Exists:** Archivio's [`storage.py`](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/storage.py) stores artifacts, claims, source notes, evidence links, counterclaims, verification tasks, and SHA-256 fixity. [`models.py`](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/models.py) has sensitivity and confidence fields. [`export.py`](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/export.py) renders finding aids using export profiles.

**Proposed handoff/data flow.** An archivist runs Arrhivescrape against an
owned or authorized domain and keeps its capture manifest, URLs, hashes,
validation results, and unresolved links. The adapter creates one Archivio
artifact per recovered page or attachment, one source note for the capture,
and claims only when a human makes an explicit historical or community claim.
Counterclaims and verification tasks remain first-class. A public export
contains only approved pages and a provenance banner; the private working
archive retains raw material and fixity results.

**MVP.** Recover one small static forum category from two capture dates, show
the capture manifest and broken-link report, accession five pages into a local
Archivio store, mark one post private, and produce a reviewed read-only export.

**Why the combination is valuable.** Arrhivescrape answers "can we recover and
validate this page?" Archivio answers "what are we claiming from it, with what
sensitivity and uncertainty?" A recovered dump alone encourages unmarked
copies to become community canon.

**Risks, maturity, and privacy.** Archive recovery may copy personal data,
deleted posts, images, and copyrighted material; obtain authorization and
respect takedown requests. Archivio's source has a concrete export hazard:
`export_json` includes all artifacts rather than fully applying the claim
filter, so a safe public projection must be new code and tested. Local paths,
living-person names, and attachment URLs must be scrubbed. Arrhivescrape's
source is substantial but its deployment and legal workflow are not validated
here. The import join, redaction projection, and community consent process are
**Proposed**; runtime behavior is **Unverified**.

### 8. Human Moderator Casebook with Appeal

**Target user and pain.** Volunteer moderators repeatedly handle interpersonal
conflict and policy disputes in a Discord server. Notes are scattered across
DMs, actions are hard to explain later, and an automated classifier would
silently convert uncertain context into a sanction.

**Exact repositories.**

- [`mojomast/ussybot`](https://github.com/mojomast/ussybot)
- [`ussyverse/circleraussy`](https://github.com/ussyverse/circleraussy)
- [`ussyverse/parliamentussy`](https://github.com/ussyverse/parliamentussy)

**Existing evidence.**

- **Exists:** Ussybot's [`src/cogs/projects.py`](https://github.com/mojomast/ussybot/blob/HEAD/src/cogs/projects.py) demonstrates Discord modals, public threads, scoped guild checks, and SQLite-backed project/task records. [`src/database.py`](https://github.com/mojomast/ussybot/blob/HEAD/src/database.py) has guild-scoped storage, notes, and configurable admin roles. These are collaboration primitives, not a moderation engine.
- **Exists:** Circlera's safety and consent gate, private statement flags, round ordering, punishment-shaped repair detection, and follow-up states are in [`src/circlera/rules.py`](https://github.com/ussyverse/circleraussy/blob/HEAD/src/circlera/rules.py) and [`src/circlera/export.py`](https://github.com/ussyverse/circleraussy/blob/HEAD/src/circlera/export.py).
- **Exists:** Parliament's [`points_of_order.py`](https://github.com/ussyverse/parliamentussy/blob/HEAD/src/parliament/points_of_order.py) records procedural challenges and appeals. Its `JournalEngine` writes an append-only record through [`journal.py`](https://github.com/ussyverse/parliamentussy/blob/HEAD/src/parliament/journal.py).

**Proposed handoff/data flow.** A moderator explicitly invokes `/case` on a
message or creates a case from a manually pasted link. Ussybot stores case
metadata and restricted notes with retention/deletion controls. If all affected
people opt in and Circlera's safety screen is clear, the case becomes a
voluntary repair conversation. If the issue is a policy interpretation or
moderator action, a separate Parliament motion records the rule, evidence
references, ruling, and appeal. The bot posts only status transitions and
filtered outcomes to the public channel.

**MVP.** Case creation, role-based visibility, consent invitation, a Circlera
keeper script/export, and a manual appeal form. Use a fake/pasted message URL;
do not add message-history scraping, auto-detection, or sanction commands.

**Why the combination is valuable.** Ussybot provides the Discord entry point
and durable case shell; Circlera provides a bounded, non-punitive path when
appropriate; Parliament makes policy disputes inspectable and appealable. The
human chooses the route, so the integration does not claim to infer intent or
guilt.

**Risks, maturity, and privacy.** This is sensitive data. Use least privilege,
encrypted local storage where feasible, short retention, participant access
logs, and explicit export/deletion controls. Circlera must block coercion,
abuse, threats, and legal/custody cases rather than invite a group session.
Parliament's agent-oriented weighted-vote model needs a human-community policy
adapter; its procedural result is not a truth finding. Ussybot's dynamic SQL
update helpers and existing bot auth need a security review. All Discord
integration and retention behavior are **Proposed** and **Unverified**.

### 9. Opt-In Ritual Design Lab

**Target user and pain.** A small online coworking, study, or creator cohort
wants a weekly ritual but keeps adding ambitious formats until attendance
decays. Organizers need to design a smaller experiment from group preferences,
not rank members by attendance or label people as disengaged.

**Exact repositories.**

- [`ussyverse/orbitalussy`](https://github.com/ussyverse/orbitalussy)
- [`ussyverse/quorumussy`](https://github.com/ussyverse/quorumussy)

**Existing evidence.**

- **Exists:** Orbital's [`src/lib.rs`](https://github.com/ussyverse/orbitalussy/blob/HEAD/src/lib.rs) accepts goals with frequency, attraction, friction, and participation history, then emits resonance windows, low-friction activity suggestions, and a Markdown/SVG report. The source also exposes the raw member/goal pair analyses.
- **Exists:** Quorum's [`internal/quorum/model.go`](https://github.com/ussyverse/quorumussy/blob/HEAD/internal/quorum/model.go) accepts member preferences, vetoes, tolerances, and notes, then reports thresholds and compromise suggestions in local JSON.

**Proposed handoff/data flow.** The organizer defines three candidate rituals
and asks members to opt into a short anonymous or pseudonymous check-in. The
adapter aggregates attendance and self-reported friction into group-level
inputs rather than publishing member scores. Orbital proposes cadence anchors
and small experiments. Quorum collects each member's acceptable options and
dealbreakers. The result is a two-week ritual card with a host, timebox,
fallback async version, and a review question. After the trial, the group
records aggregate observations and chooses keep/change/drop.

**MVP.** A local JSON editor and static report for a four-person cohort, with
three candidate rituals, one weekly frequency, and one anonymous before/after
check-in. Do not use Orbital's per-member report in the public view.

**Why the combination is valuable.** Orbital makes cadence and friction
explicit; Quorum makes the choice member-led and constraint-aware. The product
outputs a reversible experiment, not a "healthy community" score.

**Risks, maturity, and privacy.** Orbital's engagement/stability values are
heuristics and its data model is named for family members; adapting it to a
cohort requires a new schema and careful language. Small groups make
"anonymous" responses easy to re-identify. Store only aggregates where
possible, let members inspect/delete their inputs, and never publish a
participation trend per person. The aggregate adapter and ritual review loop
are **Proposed**; candidate calculations are source-backed but **Unverified**
at runtime.

### 10. Audience Prompt Council for Improv

**Target user and pain.** An improv or community performance wants audience
participation that changes the next round without reducing performers to a
social popularity contest. Hosts need bounded prompt choices, a visible timer,
and a record of why the next prompt was selected.

**Exact repositories.**

- [`mojomast/scoreboardussy`](https://github.com/mojomast/scoreboardussy)
- [`ussyverse/obscuraussy`](https://github.com/ussyverse/obscuraussy)
- [`ussyverse/quorumussy`](https://github.com/ussyverse/quorumussy)

**Existing evidence.**

- **Exists:** Scoreboardussy's [`README.md`](https://github.com/mojomast/scoreboardussy/blob/HEAD/README.md) documents rounds, server-authoritative timers, QR links, audience voting, and HTML match export. The frontend context in [`client/src/contexts/ScoreboardContext.tsx`](https://github.com/mojomast/scoreboardussy/blob/HEAD/client/src/contexts/ScoreboardContext.tsx) supports upcoming rounds, playlists, round history, and event-driven state updates.
- **Exists:** Obscura's seeded `generate_deck` in [`obscura/generator.py`](https://github.com/ussyverse/obscuraussy/blob/HEAD/obscura/generator.py) creates timeboxed constraints and reflection questions suitable for host-authored prompts.
- **Exists:** Quorum's CLI/model support local options, tolerances, vetoes, and explicit reasons in [`main.go`](https://github.com/ussyverse/quorumussy/blob/HEAD/main.go) and [`internal/quorum/model.go`](https://github.com/ussyverse/quorumussy/blob/HEAD/internal/quorum/model.go).

**Proposed handoff/data flow.** Before a round, the host selects two Obscura
cards and publishes their plain-language prompt text. The audience uses a
short-lived QR vote to choose a prompt; the vote is aggregated and not tied to
Discord identities. The host and performers may record preferences or a veto
in a Quorum decision file, which retains the selected option and reason. The
adapter starts the next Scoreboard round with the chosen theme, timer, and
player limits, then exports the round history and prompt decision.

**MVP.** Support exactly two prompt choices, one local QR page, one manually
started Scoreboard round, and a Quorum JSON receipt. Do not auto-award team
points from audience votes; the existing Scoreboard voting path is explicitly
experimental and intended for a different team-vote use case.

**Why the combination is valuable.** Obscura supplies genuinely constrained
creative material; Quorum preserves performer/host constraints; Scoreboardussy
turns the result into a live, timeboxed round. It adds audience agency to the
show without ranking audience members or using engagement as a performer
quality proxy.

**Risks, maturity, and privacy.** Scoreboardussy's current audience API is
two-team and in-memory, so multi-option prompt voting is new work. QR links
can be spammed; use one-time tokens, rate limits, and host confirmation. Keep
audience ballots aggregate and short-lived. Obscura prompts are deterministic
but not guaranteed accessible for every participant; host review is required.
Quorum's suggestion is a heuristic, not a mandate. The prompt-vote adapter,
anti-abuse controls, and round handoff are **Proposed** and **Unverified**.

## Rejected Ideas

### R1. Community Trust and Retention Score

**Exact repositories considered.**

- [`mojomast/Tchaikovskussy`](https://github.com/mojomast/Tchaikovskussy)
- [`mojomast/ghstatsussy`](https://github.com/mojomast/ghstatsussy)
- [`ussyverse/hazardaussy`](https://github.com/ussyverse/hazardaussy)

**Temptation:** combine Tchaikovskussy message/user statistics, GhStats GitHub
activity, and `ussyverse/hazardaussy` retention/hazard concepts to assign a
trust, belonging, or churn score to each Discord member.

**Decision:** reject. Per-user message counts, last-active timestamps, coding
activity, or inferred retention windows would create surveillance and social
ranking. Quiet participation, accessibility needs, pseudonyms, and different
creative roles would be misread as lack of value. A community can use
opt-in aggregate event counts to plan capacity, but not a hidden member score
or moderator eligibility gate. `hazardaussy` was not source-audited in this
pass; its catalog description is not evidence for a safe community use.

### R2. Automatic Tone-Based Moderator

**Exact repositories considered.**

- [`mojomast/diffusionchatussy`](https://github.com/mojomast/diffusionchatussy)
- [`mojomast/Tchaikovskussy`](https://github.com/mojomast/Tchaikovskussy)
- [`mojomast/ussybot`](https://github.com/mojomast/ussybot)

**Temptation:** place `mojomast/diffusionchatussy` or Tchaikovskussy in front of
`mojomast/ussybot` and automatically rewrite, soften, hide, or escalate messages
based on an LLM tone transformation.

**Decision:** reject as a moderation product. Rewriting a message can remove
context, change consent, obscure a slur or threat, and prevent the author from
knowing what was shown to others. A tone label is not a reliable abuse or
policy determination, and automatic escalation would be an opaque moderation
claim. The source-checked Tchaikovskussy implementation is useful for
recipient-opted translation, with originals visible; that is materially
different from silently changing public speech. If a future community uses
tone transformation, it should be an explicit author-side drafting aid with
original/edited text, no sanctions, human review, and short retention.
