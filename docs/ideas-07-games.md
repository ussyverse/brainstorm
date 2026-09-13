# Games and Interactive Systems: New Product Ideas

**Date:** 2026-09-13
**Pass:** source-checked game, MUD, emulator, and game-tooling combinations
**Target:** eight new product candidates and two rejected adjacent ideas

## Scope and Evidence

This pass deliberately avoids repeating the existing broad proposals for an
LLM-native MUD, an AI playtesting rig for the SotN recompilation, or a general
code-health observatory. The candidates below are narrower workflows with a
concrete artifact at the end. None of these combinations exists as an
end-to-end integration in the inspected source.

Labels have their literal research meaning:

- **Exists:** implemented in the inspected repository source.
- **Proposed:** adapter, product behavior, or workflow that still must be built.
- **Unverified:** described or inferred, but not established by source or runtime
  testing.

Static source inspection was performed on the default checkouts listed below.
No candidate repository was modified, installed, built, or runtime-tested.
Existing tests and manifests are evidence of intended contracts, not evidence
that those tests currently pass.

### Repositories and inspected revisions

| Repository | Revision | Relevant inspected source |
|---|---:|---|
| `ussyverse/cartographerussy` | `5e1cb8b` | [`src/cartographer/grid.py`](https://github.com/ussyverse/cartographerussy/blob/HEAD/src/cartographer/grid.py), [`src/cartographer/audit.py`](https://github.com/ussyverse/cartographerussy/blob/HEAD/src/cartographer/audit.py), `pyproject.toml` |
| `ussyverse/driftlineussy` | `fe62970` | [`src/driftline/game.py`](https://github.com/ussyverse/driftlineussy/blob/HEAD/src/driftline/game.py), [`src/driftline/phylogeny.py`](https://github.com/ussyverse/driftlineussy/blob/HEAD/src/driftline/phylogeny.py), `pyproject.toml` |
| `ussyverse/tellussy` | `82a4f73` | [`src/tell/game.py`](https://github.com/ussyverse/tellussy/blob/HEAD/src/tell/game.py), [`src/tell/artifacts.py`](https://github.com/ussyverse/tellussy/blob/HEAD/src/tell/artifacts.py), `pyproject.toml` |
| `ussyverse/escutcheonussy` | `51a0385` | [`escutcheon/engine.py`](https://github.com/ussyverse/escutcheonussy/blob/HEAD/escutcheon/engine.py), [`escutcheon/levels.py`](https://github.com/ussyverse/escutcheonussy/blob/HEAD/escutcheon/levels.py) |
| `ussyverse/maneuverussy` | `fc9f5be` | [`src/game/campaign.ts`](https://github.com/ussyverse/maneuverussy/blob/HEAD/src/game/campaign.ts), [`src/game/battlefield.ts`](https://github.com/ussyverse/maneuverussy/blob/HEAD/src/game/battlefield.ts), `package.json` |
| `ussyverse/quorumussy` | `397531d` | [`internal/quorum/model.go`](https://github.com/ussyverse/quorumussy/blob/HEAD/internal/quorum/model.go) |
| `ussyverse/raciaussy` | `f7d1bfe` | [`src/models.ts`](https://github.com/ussyverse/raciaussy/blob/HEAD/src/models.ts), [`src/engine.ts`](https://github.com/ussyverse/raciaussy/blob/HEAD/src/engine.ts) |
| `mojomast/ludotape` | `403d227` | [`src/index.mjs`](https://github.com/mojomast/ludotape/blob/HEAD/src/index.mjs), [`src/authoring.mjs`](https://github.com/mojomast/ludotape/blob/HEAD/src/authoring.mjs), [`src/cores/js-ts-core/core.mjs`](https://github.com/mojomast/ludotape/blob/HEAD/src/cores/js-ts-core/core.mjs) |
| `mojomast/feverfall` | `e5f8084` | [`crates/run_mode/src/lib.rs`](https://github.com/mojomast/feverfall/blob/HEAD/crates/run_mode/src/lib.rs), [`tools/replay_runner/src/main.rs`](https://github.com/mojomast/feverfall/blob/HEAD/tools/replay_runner/src/main.rs), [`tools/content_linter/src/main.rs`](https://github.com/mojomast/feverfall/blob/HEAD/tools/content_linter/src/main.rs), [`tools/balance_sim/src/main.rs`](https://github.com/mojomast/feverfall/blob/HEAD/tools/balance_sim/src/main.rs) |
| `mojomast/mudussy` | `c76270d` | [`engine/core/engine.service.ts`](https://github.com/mojomast/mudussy/blob/HEAD/engine/core/engine.service.ts), [`engine/modules/world/world-manager.ts`](https://github.com/mojomast/mudussy/blob/HEAD/engine/modules/world/world-manager.ts), `package.json` |
| `mojomast/rpg-dm-bot` | `547566b` | [`src/game_engine/models.py`](https://github.com/mojomast/rpg-dm-bot/blob/HEAD/src/game_engine/models.py), [`src/game_engine/harness.py`](https://github.com/mojomast/rpg-dm-bot/blob/HEAD/src/game_engine/harness.py), [`src/game_engine/service.py`](https://github.com/mojomast/rpg-dm-bot/blob/HEAD/src/game_engine/service.py), [`src/game_map/engine.py`](https://github.com/mojomast/rpg-dm-bot/blob/HEAD/src/game_map/engine.py) |
| `mojomast/hermespokemongoldbot` | `bfbf22d` | [`pokemon_agent/server.py`](https://github.com/mojomast/hermespokemongoldbot/blob/HEAD/pokemon_agent/server.py), [`pokemon_agent/autoplayer/runner.py`](https://github.com/mojomast/hermespokemongoldbot/blob/HEAD/pokemon_agent/autoplayer/runner.py), [`pokemon_agent/dashboard/history.py`](https://github.com/mojomast/hermespokemongoldbot/blob/HEAD/pokemon_agent/dashboard/history.py), [`pokemon_agent/memory/gold.py`](https://github.com/mojomast/hermespokemongoldbot/blob/HEAD/pokemon_agent/memory/gold.py) |
| `mojomast/clanker03` | `e9f8608` | [`agentreplay/session.py`](https://github.com/mojomast/clanker03/blob/HEAD/packages/sdk-python/src/agentreplay/session.py), [`agentreplay/store.ts`](https://github.com/mojomast/clanker03/blob/HEAD/agentreplay/store.ts), [`agentreplay/types.ts`](https://github.com/mojomast/clanker03/blob/HEAD/agentreplay/types.ts) |
| `mojomast/evenia-mudlet-llm` | `549734f` | [`evennia/contrib/llm_integration/__init__.py`](https://github.com/mojomast/evenia-mudlet-llm/blob/HEAD/evennia/contrib/llm_integration/__init__.py), [`tests/llm_integration/test_basic.py`](https://github.com/mojomast/evenia-mudlet-llm/blob/HEAD/tests/llm_integration/test_basic.py), `pyproject.toml` |

The only commands run for this pass were UTC date capture and
`git -C <checkout> rev-parse --short HEAD` for the revisions above. No tests
were run.

## Ranked Candidates

The ranking favors a recurring user task, a natural shared object, useful
output before hosting or authentication, concrete reuse, and limited adapter
work. It is a product judgment, not a market-size estimate.

| Rank | Product | Exact repositories | Primary output |
|---:|---|---|---|
| 1 | Replayable authored-content regression bench | `mojomast/ludotape` + `mojomast/feverfall` + `ussyverse/cartographerussy` | A failing content case with deterministic replay and map/content evidence |
| 2 | Text-game player-report reproduction packet | `mojomast/rpg-dm-bot` + `mojomast/ludotape` + `mojomast/clanker03` | A shareable command, state, and agent-trace reproduction bundle |
| 3 | MUD map and scenario conformance kit | `mojomast/mudussy` + `ussyverse/cartographerussy` + `mojomast/rpg-dm-bot` | A preflight report plus deterministic smoke scenario |
| 4 | NPC dialogue regression studio | `mojomast/evenia-mudlet-llm` + `mojomast/mudussy` + `mojomast/clanker03` | Human-reviewable prompt/world-state regression cases |
| 5 | Tactical campaign decision desk | `ussyverse/maneuverussy` + `ussyverse/quorumussy` + `ussyverse/raciaussy` | A voted, assigned, and auditable next-turn order |
| 6 | Heraldic expedition puzzle author | `ussyverse/escutcheonussy` + `ussyverse/cartographerussy` + `ussyverse/tellussy` | A constrained map puzzle and in-world artifact/journal pack |
| 7 | Evolving-world field journal | `ussyverse/driftlineussy` + `ussyverse/cartographerussy` + `ussyverse/tellussy` | A seeded setting bible with map locations and discoverable evidence |
| 8 | Emulator route coverage lab | `mojomast/hermespokemongoldbot` + `mojomast/clanker03` + `mojomast/ludotape` | A reproducible route/checkpoint report for a retro game agent |

## 1. Replayable Authored-Content Regression Bench

**Exact repositories:** `mojomast/ludotape`, `mojomast/feverfall`, and
`ussyverse/cartographerussy`.

**User and recurring pain.** A small game team repeatedly changes cards,
encounters, or level grids and discovers broken progression only after a human
plays a long run. Content linting catches malformed data, while playtesting
finds behavior, but the failure is difficult to reproduce and explain.

**Product promise.** "Turn every content failure into a short, deterministic
case that a designer can rerun after editing the level."

**Flow:** authored card/encounter data plus CSV grid and seed -> Cartographer
topology/directional audit and Feverfall content validation -> a normalized
scenario -> Ludotape dispatch/replay -> Markdown/JSON regression packet with
raw findings, expected invariant, actual state, and replay command.

**Existing source to reuse:** **Exists.** Ludotape exposes deterministic
dispatch, replay creation/verification, rewind, and authoring in
[`src/index.mjs`](https://github.com/mojomast/ludotape/blob/HEAD/src/index.mjs)
and [`src/authoring.mjs`](https://github.com/mojomast/ludotape/blob/HEAD/src/authoring.mjs).
Feverfall has a typed run state, replay runner, content linter, and balance
simulation in the files listed in the evidence table. Cartographer loads CSV
grids and performs directional/spatial audits.

**Missing integration work:** **Proposed.** Define a scenario manifest with
stable content IDs, seed, grid ID, action list, and explicit invariants. Write
adapters for Feverfall findings and Cartographer coordinates into that
manifest. Do not assume Feverfall's content schema and Ludotape's event schema
are interchangeable; preserve each raw input and result beside the normalized
case.

**Maturity and feasibility caveats:** Ludotape is MIT. Cartographer is MIT.
Feverfall's workspace is marked `UNLICENSED`; distribution or embedding needs
an explicit licensing decision. **Unverified:** the proposed adapters and any
cross-engine semantic equivalence. Balance output is evidence for review, not
proof that a game is fun or fair.

**Smallest useful demo:** one five-room grid and three card encounters, with
one unreachable room and one invalid content reference. Run the same seed
before and after a fix and attach the replay plus both validator outputs.

**Acceptance criteria:**

- The same manifest produces the same replay result and state hash twice.
- A malformed reference and an unreachable room appear as separate findings.
- A changed content ID invalidates the relevant case rather than silently
  reusing an old result.
- The packet contains the raw input, exact seed, tool revisions, and replay
  command.

**Why better than separate tools:** The designer gets one failure object that
connects map validity, content validity, and observed behavior. Three separate
reports would leave the designer to guess whether the same level was tested.

**Rejected adjacent components:** `ussyverse/driftlineussy` adds a different
procedural-world model without helping the first content-regression workflow;
`mojomast/clanker03` is unnecessary until an LLM or agent trace is part of the
failure.

## 2. Text-Game Player-Report Reproduction Packet

**Exact repositories:** `mojomast/rpg-dm-bot`, `mojomast/ludotape`, and
`mojomast/clanker03` (`AgentReplay`).

**User and recurring pain.** A solo developer receives "the goblin vanished,"
"the command worked twice," or "the agent got stuck" without the exact command
sequence, persistence state, or model/tool context needed to investigate.

**Product promise.** "A player or agent report becomes a replayable bug packet,
not a vague transcript."

**Flow:** command transcript, save state, and optional LLM/tool events -> RPG
DM Bot's authoritative command/event service -> normalized Ludotape action
sequence -> AgentReplay session/state timeline when an agent participated ->
packet containing the first divergent event, state snapshot, and reproduction
instructions.

**Existing source to reuse:** **Exists.** RPG DM Bot defines typed command/event
models, deterministic dispatch in `harness.py`, persistent service behavior in
`service.py`, and map/pathfinding/line-of-sight logic. Ludotape supplies a
generic deterministic replay core. AgentReplay supplies session/event/blob/
state-snapshot types, a Python session recorder, and a SQLite store.

**Missing integration work:** **Proposed.** Add a stable `caseId`, command
sequence number, world-state serialization, and an explicit mapping from RPG
events to Ludotape actions. Capture the original command result before any
replay. AgentReplay should store model/tool context as evidence, not decide
whether the game behavior is correct.

**Maturity and feasibility caveats:** The three projects have different
languages and persistence formats; no direct bridge was found. **Unverified:**
state round-tripping across the RPG service and Ludotape, and AgentReplay's
deployment behavior. License terms for RPG DM Bot and AgentReplay were not
recorded in this pass and must be checked before redistribution.

**Smallest useful demo:** a local RPG session with ten commands, one deliberately
duplicated state transition, and one mocked agent tool call. Export a packet
that replays the divergence without contacting an LLM.

**Acceptance criteria:**

- Replaying a packet requires no network access or model API key.
- The packet identifies the first differing event and includes before/after
  state JSON.
- Raw transcript order and agent/tool events remain available.
- A fixed bug can be rerun against the same packet and marked resolved without
  rewriting the original evidence.

**Why better than separate tools:** The authoritative game event and the agent
trace explain different parts of the same failure. A transcript alone cannot
reconstruct state, and a generic agent trace cannot validate game invariants.

**Rejected adjacent components:** `mojomast/mudussy` is a larger real-time
engine and would turn a local bug-packet MVP into a runtime migration;
`mojomast/evenia-mudlet-llm` introduces another world/LLM integration instead of
improving reproduction.

## 3. MUD Map and Scenario Conformance Kit

**Exact repositories:** `mojomast/mudussy`, `ussyverse/cartographerussy`, and
`mojomast/rpg-dm-bot`.

**User and recurring pain.** A MUD author edits rooms and exits in a growing
world. A typo can leave a room unreachable, make a one-way exit inconsistent,
or invalidate a common quest path. Manual smoke tests do not cover the map
after every content change.

**Product promise.** "Preflight the world graph and run a small deterministic
scenario before publishing a MUD content pack."

**Flow:** room/exit export from a MUD content workspace -> Cartographer grid and
directional audit -> generated smoke commands and expected transitions -> RPG
DM Bot-style deterministic path/LOS checks as a reference harness -> report of
unreachable nodes, contradictory exits, and failed scenario steps.

**Existing source to reuse:** **Exists.** Mudussy has a modular NestJS engine,
world manager, entity management, networking, persistence, and plugin seams.
Cartographer loads CSV level grids and audits spatial/directional relations.
RPG DM Bot has command/event contracts, deterministic dispatch, map generation,
pathfinding, and LOS code.

**Missing integration work:** **Proposed.** Define a portable room export with
stable room IDs, coordinates, exits, blockers, and scenario fixtures. Build a
MUD-specific exporter and a reference-harness adapter. The RPG map engine is
not evidence that Mudussy movement semantics match; mismatches must be shown
as compatibility findings rather than hidden.

**Maturity and feasibility caveats:** This is a conformance tool, not a claim
that the two engines share a runtime. Coordinate systems, exit semantics,
entity permissions, and persistence behavior need contract tests. The license
for Mudussy and RPG DM Bot was not recorded in this pass. **Unverified:**
export surfaces in the current Mudussy application and semantic parity.

**Smallest useful demo:** export ten rooms with one unreachable room, one
one-way exit, and a three-step player scenario. Run the linter and reference
scenario locally without starting a multiplayer server.

**Acceptance criteria:**

- Every reported room and exit links back to a stable source ID.
- The tool distinguishes a topology error from a reference-harness semantic
  mismatch.
- The smoke scenario reports the exact failed step and expected/actual room.
- An empty or incomplete export is reported as incomplete, not as a valid map.

**Why better than separate tools:** The author gets a publish gate tied to a
specific scenario, rather than an isolated map picture or a server smoke test
that cannot explain the source content defect.

**Rejected adjacent components:** `mojomast/ludotape` is attractive for replay,
but adding it before the room/export contract is stable would create a third
event model; `mojomast/evenia-mudlet-llm` is excluded because nondeterministic
NPC responses are not needed for map conformance.

## 4. NPC Dialogue Regression Studio

**Exact repositories:** `mojomast/evenia-mudlet-llm`, `mojomast/mudussy`, and
`mojomast/clanker03` (`AgentReplay`).

**User and recurring pain.** A MUD developer changes an NPC prompt, provider,
world fact, or tool permission and later notices that an important response
changed. Screenshots do not capture the prompt, world state, or tool calls that
caused the regression.

**Product promise.** "Run the same NPC scenario against a pinned world fixture
and inspect what changed, without reducing dialogue quality to one score."

**Flow:** human-authored scenario with player intent, NPC fixture, expected
facts, and forbidden actions -> Evennia LLM integration/provider call -> MUD
world-state/tool events -> AgentReplay session and state timeline -> side-by-
side transcript, structured fact checks, and human review decision.

**Existing source to reuse:** **Exists.** Evenia contains an LLM integration
package and mock/provider-oriented tests. Mudussy supplies a modular world and
entity runtime. AgentReplay supplies session recording, event sequencing,
state inspection, and replay-oriented storage.

**Missing integration work:** **Proposed.** Define scenario fixtures and a
provider-recording boundary, redact secrets, capture world-state hashes, and
write human-readable assertions for facts, tool permissions, and continuity.
Provide a deterministic mock-provider mode for local regression. Do not treat
embedding similarity or an LLM judge as authoritative.

**Maturity and feasibility caveats:** The expected `llm_client.py` and
`worldbuilder.py` paths were not present in the checkout; their capabilities
are therefore **Unverified**. The observed package and tests establish an
integration area, not a complete production API. Real model replay may require
recorded responses or a mock. Licenses for all three repositories require a
separate distribution check.

**Smallest useful demo:** five NPC scenarios using a mock provider, one changed
world fact, and one newly attempted forbidden tool. Show the old/new trace and
ask a human to accept or reject the change.

**Acceptance criteria:**

- A scenario can run offline with recorded provider responses.
- The report shows prompt/world fixture revisions and raw event order.
- Fact and permission assertions are independently reviewable.
- Secrets are absent from the exported packet.

**Why better than separate tools:** Dialogue, world state, and tool activity
are one regression unit. A transcript diff without the world fixture cannot
distinguish prompt drift from changed game state.

**Rejected adjacent components:** `mojomast/rpg-dm-bot` would add a second
authoritative game service; `mojomast/llmproxy` would be infrastructure rather
than a regression artifact and is unnecessary for the offline first demo.

## 5. Tactical Campaign Decision Desk

**Exact repositories:** `ussyverse/maneuverussy`, `ussyverse/quorumussy`, and
`ussyverse/raciaussy`.

**User and recurring pain.** A small asynchronous tabletop or tactics group
agrees on an operation in chat, forgets who owns the next action, and loses the
reasoning when the next turn starts.

**Product promise.** "Turn a campaign decision into a voted, assigned, and
reviewable next-turn order."

**Flow:** seeded battlefield and campaign state -> candidate maneuvers ->
weighted ballot, threshold, or veto in Quorum -> RACI ownership/access analysis
-> exported operation order and next-turn checklist -> updated Maneuver campaign
state with the decision and result linked.

**Existing source to reuse:** **Exists.** Maneuver has seeded battlefield and
module models, campaign state, an OODA timer, and tactical maneuvers. Quorum has
JSON decision files, weighted ballots, thresholds, vetoes, and reports.
Racia has typed plans, assignments, analyses, and workload reports.

**Missing integration work:** **Proposed.** Define shared `campaignId`,
`operationId`, `turnId`, and member IDs. Add proposal-to-ballot and ballot-to-
assignment links. Keep Quorum's vote as the group's recorded decision and
Maneuver's outcome as a separate observed result; do not infer that majority
choice was tactically correct.

**Maturity and feasibility caveats:** These are generic deterministic/procedural
models, not a complete multiplayer game. Racia workload findings are
heuristics. Quorum's governance rules may not fit every table. Licenses for
Quorum and Racia were not recorded in this pass; Maneuver's manifest indicates
ISC. **Unverified:** persistence and round-trip contracts across the three
projects.

**Smallest useful demo:** three players, one seeded battlefield, three candidate
maneuvers, a veto-capable vote, and four assigned tasks. Export the accepted
order and record the following turn's actual outcome.

**Acceptance criteria:**

- A decision cannot become an assignment without a recorded decision status.
- Every accepted task has one accountable member and an explicit turn.
- Reopening a proposal preserves the original vote and assignment history.
- The report separates chosen action, ownership gap, and observed outcome.

**Why better than separate tools:** A campaign plan needs both collective
choice and execution ownership. A vote report or a workload table alone does
not tell the group what to do next.

**Rejected adjacent components:** `ussyverse/driftlineussy` would introduce a
second campaign/world simulation with no necessary handoff; `mojomast/rpg-dm-bot`
would turn a decision ledger into an engine migration before the social workflow
is validated.

## 6. Heraldic Expedition Puzzle Author

**Exact repositories:** `ussyverse/escutcheonussy`, `ussyverse/cartographerussy`,
and `ussyverse/tellussy`.

**User and recurring pain.** An indie designer wants a compact exploration
puzzle in which map placement, heraldic clues, and discovered artifacts agree.
Hand-authored puzzle content often has a valid-looking shield rule but no
reachable location or no coherent discovery record.

**Product promise.** "Author a small, auditable map puzzle whose visual rule,
route, and discovery journal stay connected."

**Flow:** grid, gates, and heraldic constraints -> Cartographer spatial audit and
Escutcheon shield/level validation -> generated exploration objectives -> Tell
builder/excavator artifact and journal records -> portable puzzle pack for a
player or playtest group.

**Existing source to reuse:** **Exists.** Escutcheon implements shield, tincture,
charge, and level-constraint validation plus save behavior. Cartographer loads
grids and checks directional/spatial relationships. Tell has builder and
excavator phases, artifact generation, journal behavior, and save/load paths.

**Missing integration work:** **Proposed.** Assign stable cell, shield, gate,
and artifact IDs. Map a validated heraldic condition to a reachable cell and a
Tell discovery objective. Export the source rule, route assumptions, and player
journal separately so a completed artifact is not mistaken for proof that the
puzzle was understandable.

**Maturity and feasibility caveats:** The three projects do not share a game
engine or content schema. Escutcheon and Tell's precise license status was not
recorded in this pass; Cartographer is MIT. **Unverified:** whether the current
save formats can carry foreign IDs without an adapter. This is a puzzle-
authoring workflow, not a claim that heraldic rules have universal meaning.

**Smallest useful demo:** one 7x7 map, three shield clues, one blocked route,
and one excavated artifact whose journal entry links to the relevant cell and
rule.

**Acceptance criteria:**

- Every objective has a reachable cell and a referenced rule.
- Invalid tincture/charge combinations fail before export.
- A saved and reloaded pack preserves cell, rule, artifact, and journal IDs.
- A player can see the evidence trail without seeing hidden solution fields.

**Why better than separate tools:** The combination tests the puzzle as a
playable chain rather than validating heraldry, geometry, and narrative records
in isolation.

**Rejected adjacent components:** `ussyverse/maneuverussy` would add tactical
combat unrelated to the puzzle's core loop; `mojomast/feverfall` has a useful
content linter but its card/run schema is not evidence of a heraldic puzzle
contract.

## 7. Evolving-World Field Journal

**Exact repositories:** `ussyverse/driftlineussy`, `ussyverse/cartographerussy`,
and `ussyverse/tellussy`.

**User and recurring pain.** A worldbuilder or classroom facilitator wants a
procedural island setting that can be explored and revised, but generated
species, places, and discoveries end up as disconnected notes. Changing a seed
can silently invalidate a journal entry or map reference.

**Product promise.** "Generate a seeded living setting, explore selected places,
and preserve what each discovery proves about that setting."

**Flow:** seed and world parameters -> Driftline archipelago/species evolution
and phylogeny -> Cartographer location grid/audit -> Tell excavation/artifact
and journal entry -> setting bible containing seed, lineage, location, and
discovery provenance.

**Existing source to reuse:** **Exists.** Driftline provides seeded game state,
archipelago generation, species evolution, phylogeny, and save/load. Cartographer
provides grid loading and spatial audits. Tell provides two-phase exploration,
artifacts, journaling, and serialization.

**Missing integration work:** **Proposed.** Create a world manifest with seed,
generation revision, species IDs, cell IDs, expedition IDs, and artifact
provenance. Define a deliberate projection from Driftline's generated world to
Cartographer cells; do not claim the projection is native to Driftline. Make
stale journal references visible after regeneration.

**Maturity and feasibility caveats:** All three are small prototypes; Driftline
and Cartographer are MIT, while Tell's license needs confirmation. No source
evidence establishes ecological realism, educational effectiveness, or a
shared coordinate system. The output is a creative setting artifact, not a
scientific ecosystem model.

**Smallest useful demo:** one fixed seed, two islands, three species with a
visible lineage, four mapped sites, and two excavation entries. Regenerate with
a changed seed and show old references as stale rather than silently retargeted.

**Acceptance criteria:**

- Identical seed and pinned revisions reproduce the same world manifest.
- Every journal entry points to a location and artifact that exist in that
  manifest.
- Changed seed or generator revision creates a new world revision.
- A player-facing export omits hidden generator parameters while retaining
  provenance in the author export.

**Why better than separate tools:** Driftline supplies change over time,
Cartographer supplies spatial discipline, and Tell supplies a human-readable
record of discovery. The journal gives the generated world a usable authoring
and playtest artifact.

**Rejected adjacent components:** `ussyverse/escutcheonussy` is a possible
future puzzle layer but would conflate world provenance with a new rule system;
`mojomast/evenia-mudlet-llm` is excluded because generated dialogue would make
the first seed/revision contract harder to inspect.

## 8. Emulator Route Coverage Lab

**Exact repositories:** `mojomast/hermespokemongoldbot`, `mojomast/clanker03`
(`AgentReplay`), and `mojomast/ludotape`.

**User and recurring pain.** A retro-game automation developer changes an
autoplayer or memory reader and needs to know whether a known route still
reaches its milestones. A video or final save file does not explain which input
or state transition first diverged.

**Product promise.** "Replay a short, named emulator route from a save state and
show the first milestone or memory-state divergence."

**Flow:** legal local emulator/save state -> Hermes server and
`UniversalAutoplayer` inputs -> Gold-specific structured memory reads and JSONL
event history -> AgentReplay session/state timeline -> Ludotape-normalized
checkpoint replay -> route report with milestone assertions, screenshots or
bounded memory evidence, and raw events.

**Existing source to reuse:** **Exists.** Hermes provides an emulator
HTTP/WebSocket server, save/load, structured Gold memory reading, a generic
fallback reader, an autoplayer, and `EventLogger`. AgentReplay provides event,
blob, and state-snapshot storage. Ludotape provides a small deterministic
action/replay contract that can serve as the exported checkpoint format.

**Missing integration work:** **Proposed.** Define route milestones explicitly
(for example, room, party, badge, or inventory facts), map emulator input and
memory events into a stable checkpoint schema, and preserve emulator version,
ROM identity metadata, save-state hash, and tool revisions. Use only user-owned
game data and do not distribute ROMs or proprietary assets.

**Maturity and feasibility caveats:** This is not the existing SotN AI
playtesting proposal and does not require OpenClaw or a general autonomous
agent. Emulator behavior, memory offsets, and save compatibility are
game/version-specific. **Unverified:** cross-project replay fidelity and the
current server's long-run stability. License terms for Hermes, AgentReplay, and
Ludotape must be checked; Ludotape is MIT.

**Smallest useful demo:** one user-owned Gold save, three named route
milestones, a mocked autoplayer input sequence, and one intentional memory
reader regression. Export a packet that resumes from the save and identifies
the first missed milestone.

**Acceptance criteria:**

- The route declares its milestones instead of relying on a vague coverage
  percentage.
- A rerun from the same save-state hash records the same input/checkpoint order
  in offline or mocked mode.
- A reader change produces a field-level difference with raw memory evidence.
- The export contains no ROM or other proprietary game asset.

**Why better than separate tools:** The emulator knows the game state, the
replay store knows the execution history, and Ludotape supplies a compact
rerun boundary. Together they make an agent failure inspectable without
pretending that a screenshot is structured evidence.

**Rejected adjacent components:** `mojomast/SymphonyRecomp` is excluded because
the existing source-checked document already covers an AI playtesting rig for
that ecosystem; `mojomast/rpg-dm-bot` is a different game-state contract and
would not improve the first emulator-specific demo.

## Rejected Adjacent Ideas

### A. Universal game-quality oracle

**Temptation:** combine Driftline evolution metrics, Escutcheon's constraint
passes, Feverfall balance simulation, and Maneuver campaign outcomes into one
"game quality" score.

**Why reject:** These outputs describe different entities, scales, and purposes.
Passing a content constraint, a simulated balance result, and a tactical
outcome do not form a validated measure of fun, accessibility, or quality.
The product would add an unexplained score instead of a user-facing artifact.
The serious candidates above retain raw findings and named acceptance criteria.

### B. Autonomous everything-game megastack

**Temptation:** combine Mudussy, Evenia's LLM integration, RPG DM Bot,
AgentReplay, Hermes Pokemon automation, and Ludotape into one universal agent
that authors worlds, plays them, and judges them.

**Why reject:** This duplicates the existing broad LLM-native MUD and SotN
playtesting directions while stacking multiple authoritative world models,
LLM boundaries, replay formats, and game runtimes. It has no stable first user
workflow or acceptance oracle. A selected narrow candidate can add one of these
components later after its event and state contract is demonstrated.

## Recommended Next Validation

Start with **Replayable authored-content regression bench** if the goal is the
smallest cross-repository game-tool vertical slice. It has a crisp local demo,
two concrete validators, and a deterministic replay artifact. Run the existing
test suites first, then pin a shared scenario manifest and test one real
user-authored case. If the target user is an AI/game developer rather than a
content designer, choose **Text-game player-report reproduction packet** and
validate state round-tripping before adding a UI.
