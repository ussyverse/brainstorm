# The Ussyverse: Complete Repository Index

> Full working index of every public repository found in the GitHub org **ussyverse** (330 repos) and user **mojomast** (129 repos), based on shallow clones captured on 2026-09-13.
>
> Each entry lists: what the repo is, its stack, concrete capabilities, intended uses, and other ecosystem repos it can integrate with.

## Contents
1. Ecosystem overview & project clusters
2. Combining projects (multi-repo build ideas)
3. Full repository index (A–Z by owner, then name)

---

# Ussyverse Ecosystem — Combos & Cluster Analysis

Derived from a complete read of the 459-repo index (mojomast + ussyverse orgs).

## Ecosystem Overview

The Ussyverse is Kyle Durepos's sprawling personal build ecosystem, and it has three distinct layers. The first is serious AI-infrastructure work: forks of AI coding agents (opencode, kilocode, Roo Code), a five-generation lineage of autonomous build harnesses (devussy → swarmussy → ralphussy → geoffrussy → nexussy), agent runtimes and governance tools (hermes-agent, openclawssy, becomussy, parliamentussy), self-hosted LLM proxies and routers (llmproxy, routetok, ussyrouter), and real hosting infrastructure (ussycode Firecracker microVMs, fireslice, webring/DNS services, Discord bots for communities). The second layer is games: browser and terminal games, a TypeScript MUD engine, an LLM-enhanced Evennia MUD fork, and an impressive PlayStation 1 static-recompilation toolchain (RecompOne → SymphonyRecomp and its mods). The third — the bulk of the ussyverse org — is a vast family of small, deterministic, local-first, single-purpose tools that translate one real scientific domain (epidemiology, glaciology, HACCP, pharmacokinetics, actuarial science, crystallography, seismology…) into conservative decision cards for codebases, households, health triage, learning, personal finance, and small business. The through-lines: everything is self-hostable, privacy-first, explainable rather than ML-black-box, and wired together by a Discord-centered community (ussy.host / ussyco.de).

## Key Project Clusters

- **AI coding agent forks & terminals** — `mojomast/opencode`, `mojomast/kilocode`, `mojomast/roo-code-cloud-alternate-auth`, `mojomast/openwarp`, `mojomast/warp` (warpussy), `mojomast/warpussy`, `mojomast/fossilrecordussy`
- **Autonomous build harnesses (the "ussyverse coding harness" lineage)** — `mojomast/devussy` (+ `devussy-fresh`, `devussy-testing`, `devussy_old`), `mojomast/swarmussy`, `mojomast/SwarmCraft`, `mojomast/geoffrussy`, `mojomast/ralphussy`, `mojomast/nexussy`, `mojomast/nexdev`, `mojomast/hermesswarmbuilder`, `mojomast/clanker01` (SWARM), `mojomast/clanker04` (ParallelForge), `mojomast/cabinet-of-almosts`, `mojomast/repoworkshop`
- **LLM proxies, routing & provider plumbing** — `mojomast/llmproxy`, `mojomast/routetok`, `mojomast/ussyrouter` (Routussy), `mojomast/ussycodeproxy`, `mojomast/ragussy`, `mojomast/citewiser`
- **Agent runtimes, governance & monitoring** — `mojomast/hermes-agent` (+ `hermes-agent-improvements`, `hermes-correction-aware-learning`, `mojomast/hermesdashboard`), `mojomast/openclawssy`, `mojomast/openclawremoteussy`, `mojomast/becomussy`, `mojomast/kportussy`, `ussyverse/parliamentussy`, `mojomast/uberclawcontrol` (ClawDeck), `mojomast/agentussy`, `mojomast/agenttrafficcontrol`, `mojomast/ussyverse-monitor`
- **Agent debugging / eval / research automation** — `mojomast/clanker02` (Knexus), `mojomast/clanker03` (AgentReplay), `mojomast/clanker05/06/07`, `mojomast/vesuvius-autoresearch`, `ussyverse/reverseoracleussy`, `ussyverse/kintsugiussy`
- **MUD / text worlds / multiplayer games** — `mojomast/mudussy`, `mojomast/evenia-mudlet-llm`, `mojomast/rpg-dm-bot`, `mojomast/partymemberbotussy`, `ussyverse/driftlineussy`, `ussyverse/tellussy`, `ussyverse/escutcheonussy`, `mojomast/velvetrp`
- **Game engines & browser/desktop games** — `mojomast/gamengine`, `mojomast/ludotape`, `mojomast/roguelitussy`, `mojomast/voltronussy`, `mojomast/feverfall`, `mojomast/CONTAINERWARZ`, `mojomast/brawler1`, `mojomast/buttfights-project`, `mojomast/nhlclicker2`, `mojomast/pawn-shop-pioneers`, `mojomast/psp2`, `mojomast/stallionussy`, `mojomast/tokenarena`, `mojomast/slophero`, `mojomast/tcg2`, `ussyverse/cartographerussy`, `ussyverse/maneuverussy`
- **PS1 static recompilation (SotN mod ecosystem)** — `mojomast/RecompOne`, `mojomast/SymphonyRecomp`, `mojomast/sotnrecompmultiplayer`, `mojomast/sotnrecompguns`, `mojomast/sotnrecompsave`
- **Discord bots & bot ops** — `mojomast/ussybot`, `mojomast/ussybiot`, `mojomast/Beatrice`, `mojomast/xcancelussybot`, `mojomast/gemini-nano-banana-discord-bot`, `mojomast/botmanagussy`
- **Hosting & infrastructure** — `mojomast/ussycode`, `mojomast/fireslice`, `mojomast/ussyring`, `mojomast/ussycodeproxy`, `mojomast/rackspace-spot-tool`, `mojomast/templeossy`, `mojomast/pfsense`, `mojomast/dashboardussy`, `mojomast/topussy`, `mojomast/BackupUSSY`, `mojomast/sigintussy`, `mojomast/365cspadminussy`
- **Web presence, portfolios & business apps** — `mojomast/ussysite2`, `mojomast/ussyverse`, `mojomast/ghstatsussy`, `mojomast/ArtistSiteussy`, `mojomast/ticket`, `mojomast/ticket2`, `mojomast/weouthere`, `mojomast/mediageckussy`, `mojomast/ytkiosk`
- **Metaphor-driven code analysis & repo health** — `mojomast/churnmap`, `mojomast/terrariumussy`, `ussyverse/crystallossy`, `ussyverse/morsethussy`, `ussyverse/isobarussy`, `ussyverse/codelineageussy`, `ussyverse/fatigueussy`, `ussyverse/endemicussy`, `ussyverse/seralussy`, `ussyverse/dosemateussy`, `ussyverse/gridironussy`, `ussyverse/kompressiussy`, `ussyverse/assayussy`, `ussyverse/sentinelussy`, `ussyverse/ichniteussy`, `ussyverse/calibreussy`, `ussyverse/levainussy`, `ussyverse/marksmanussy`, `ussyverse/acumenussy`, `ussyverse/choreoussy`, `ussyverse/hitchussy`, `ussyverse/stenographussy`, `ussyverse/stenography`, `ussyverse/triageussy`, `ussyverse/coronerussy`, `ussyverse/unconformity`, `ussyverse/stratagitussy`, `ussyverse/petrichorussy`, `ussyverse/curatorussy`, `ussyverse/operonussy`, `ussyverse/rosettussy`, `ussyverse/stemmaussy`, `ussyverse/timeloomussy`
- **Household safety & conservative health-triage tools** — `ussyverse/aeronaussy`, `ussyverse/wetbulbaussy`, `ussyverse/riptidaussy`, `ussyverse/slabwiseussy`, `ussyverse/vorticaussy`, `ussyverse/fulguraussy`, `ussyverse/carboxaussy`, `ussyverse/radonaussy`, `ussyverse/crackwiseussy`, `ussyverse/hammeraussy`, `ussyverse/sumpaussy`, `ussyverse/trapsealussy`, `ussyverse/ceruminaussy`, `ussyverse/sialiaussy`, `ussyverse/palynoussy`, `ussyverse/urticaraussy`, `ussyverse/triagiaussy`, `ussyverse/sterilaussy` and ~100 siblings
- **Learning & study science tools** — `ussyverse/ebbinghausussy`, `ussyverse/bloomussy`, `ussyverse/synapseussy`, `ussyverse/latticeussy`, `ussyverse/scaffoldussy`, `ussyverse/chunkussy`, `ussyverse/exemplaussy`, `ussyverse/dualiaussy`, `ussyverse/criterioussy`, `ussyverse/cladwiseussy`, `ussyverse/morphemaussy`, `ussyverse/prospectaussy`
- **Personal finance & small-business ops** — `ussyverse/silvaussy`, `ussyverse/coreussy`, `ussyverse/tidalussy`, `ussyverse/laminarussy`, `ussyverse/percolateussy`, `ussyverse/cyclaraussy`, `ussyverse/soluteussy`, `ussyverse/stoichussy`, `ussyverse/keelussy`, `ussyverse/bidussy`, `ussyverse/diopterussy`, `ussyverse/rotationussy`, `ussyverse/taktussy`, `ussyverse/shewhartaussy`, `ussyverse/benfordaussy`, `ussyverse/allomaussy`, `ussyverse/hazardaussy`, `ussyverse/queueussy`, `ussyverse/recapturaussy`
- **Wellness & reflective journaling** — `ussyverse/limnoussy`, `ussyverse/tempestussy`, `ussyverse/stellarussy`, `ussyverse/immunussy`, `ussyverse/dendroussy`, `ussyverse/glacierussy`, `ussyverse/seismicussy`, `ussyverse/triboussy`, `ussyverse/zooxussy`, `ussyverse/chloroussy`, `ussyverse/horologussy`, `ussyverse/forgeussy`, `ussyverse/fermentussy`-adjacent kitchen cluster (`maillaraussy`, `rheoussy`, `criticaussy`, `sorpraussy`)
- **Creative media & music** — `mojomast/fruityboofs`, `mojomast/shoedelussy`, `mojomast/toaster`, `mojomast/designussy`, `mojomast/bananagen`, `ussyverse/chromascriptussy`, `ussyverse/foleyaussy`, `ussyverse/scansionussy`, `ussyverse/olfactoussy`, `ussyverse/kuleshovussy`, `ussyverse/tonalussy`, `ussyverse/phyllotaxisussy`
- **Vesuvius Challenge research** — `mojomast/villa`, `mojomast/vesuvius-autoresearch`

## Combining Projects

**1. The Governed Autonomous Build Factory**
*Repos: `mojomast/hermesswarmbuilder`, `mojomast/hermes-agent`, `mojomast/devussy`, `mojomast/ussycode`, `mojomast/ussyrouter`, `mojomast/ussyverse-monitor`, `mojomast/becomussy`*
`hermesswarmbuilder` already defines the full build cycle (scan → select → SPEC → DEVPLAN → implement → validate → publish) around a Hermes host; run that host inside `ussycode` Firecracker microVMs so every cycle gets an isolated, SSH-accessible, disposable environment. `ussyrouter` becomes the LLM access layer — it already provides Discord-approved API keys, 3-tier budget enforcement, and SSH-fingerprint-based VM auth for exactly this ussycode integration. `becomussy` governs the agent's long-term identity so it persists memory and self-revisions across cycles with human-approved semantic diffs, while `ussyverse-monitor` (or `hermesdashboard`) gives the operator a live window into sessions with an emergency stop. Result: a self-hosted, budget-capped, auditable "agent builds repos while you sleep" pipeline.

**2. Parliament-Governed Agent Swarm**
*Repos: `mojomast/swarmussy`, `ussyverse/parliamentussy`, `mojomast/agenttrafficcontrol`, `mojomast/kportussy`*
`swarmussy` orchestrates an Architect plus seven specialized worker agents (backend, frontend, QA, DevOps, PM, tech writer) into a shared workspace. Put `parliamentussy` in front of it: operational changes — schema migrations, deploys, dependency upgrades — become motions that must be seconded, amended, and voted on by the agent registry, with an append-only hash-chained journal as the audit trail. `agenttrafficcontrol` provides the live ATC-style visualization of which agent is doing what, and `kportussy` gates promotion of any agent-built artifact behind claim→evidence→verification receipts. Result: a multi-agent dev team whose actions are deliberate, legitimate, and auditable instead of fire-and-forget.

**3. One-Endpoint LLM Stack for the Whole Ecosystem**
*Repos: `mojomast/ussyrouter`, `mojomast/llmproxy`, `mojomast/routetok`, `mojomast/Beatrice`, `mojomast/warp` (warpussy)*
`ussyrouter` is the Discord-managed community proxy (budgets, per-model concurrency, key minting); `llmproxy` adds provider key rotation, failover, and OAuth flows across Gemini/OpenAI/Anthropic/OpenRouter; `routetok` adds health-aware pre-output failover plus its Fieldbook for hands-on model comparison. Chain them so community members point any OpenAI-compatible client at one local endpoint, with `llmproxy` absorbing provider outages and `ussyrouter` enforcing spend. `Beatrice` (IRC bot with typed memory and admin-gated dangerous actions) and `warp` (BYOK terminal) both consume the same OpenRouter key workflow, so a member's terminal, IRC, and proxy keys all come from one governed source.

**4. The Multi-Agent Coding Tournament Rig**
*Repos: `mojomast/clanker04` (ParallelForge), `mojomast/clanker01` (SWARM), `mojomast/clanker03` (AgentReplay), `ussyverse/lehrussy`, `mojomast/fossilrecordussy`*
`clanker04` spawns competing agents on isolated git worktrees and merges the winner based on test/lint/coverage scoring — feed `lehrussy`'s glassware-style test-suite diagnostics (birefringence stress, thermal-shock resilience, tempering detection) into its evaluation service so "best solution" means "solution whose tests are actually trustworthy," not just green. `clanker03` records every LLM call and tool execution of the competition for time-travel replay when a merged winner misbehaves. Run the whole thing on `clanker01`'s parallel architect/coder/tester/reviewer infrastructure, and stress-test the merged code with `fossilrecordussy`'s esolang corpus to measure robustness on out-of-distribution input.

**5. An LLM-Native MUD World**
*Repos: `mojomast/mudussy`, `mojomast/evenia-mudlet-llm`, `mojomast/rpg-dm-bot`, `mojomast/partymemberbotussy`, `mojomast/ragussy`, `mojomast/llmproxy`*
`mudussy` supplies the real-time NestJS/Socket.IO multiplayer engine; `evenia-mudlet-llm` contributes the proven LLM-driven NPC/worldbuilding integration and Lua scripting bridge. Use `ragussy` as the persistent lore layer — ingest world bibles and past session transcripts so NPCs retrieve canon instead of hallucinating it — with all model calls routed through `llmproxy`. Then bridge Discord: `rpg-dm-bot` runs persistent campaigns with tool-driven LLM narration, and `partymemberbotussy` registers as an automated party member that auto-plays under the DM bot. Result: one world playable over web/telnet and Discord, with continuity-preserving AI NPCs.

**6. AI Playtesting Rig for the SotN Recompilation**
*Repos: `mojomast/SymphonyRecomp`, `mojomast/sotnrecompmultiplayer`, `mojomast/sotnrecompsave`, `mojomast/openclawssy`, `mojomast/opencode`*
`SymphonyRecomp` already exposes an MCP automation bridge — controller input over a named pipe, structured game-state inspection, bounded RAM reads, screenshots. Drive it with `openclawssy` (deny-by-default capability policy, append-only audit logs, reproducible run artifacts) so an AI agent can playtest under hard policy gates. `sotnrecompsave`'s room-level checkpoints make crashes cheap to recover during long automated runs, and `sotnrecompmultiplayer`'s P2D4 diagnostic reports let the agent verify co-op invariants (revive states, room transitions) as structured data rather than pixels. Result: a policy-gated, auditable, replayable AI QA harness for a native SotN port and its mods.

**7. The Ussyverse Discord Community Operating System**
*Repos: `mojomast/botmanagussy`, `mojomast/ussybot`, `mojomast/xcancelussybot`, `mojomast/gemini-nano-banana-discord-bot`, `mojomast/rpg-dm-bot`, `mojomast/ghstatsussy`*
`botmanagussy` is purpose-built to supervise multiple discord.py bots on one VPS — repo ingestion, start/stop/status, env injection, token rotation, log diagnosis — so deploy `ussybot` (weekly project tracking + AI chat + GitHub tools), `xcancelussybot` (link conversion + channel RPG), and `gemini-nano-banana-discord-bot` (AI image gen/edit/blend) under one supervisor. `ghstatsussy` generates shareable HTML activity reports that `ussybot`'s GitHub tools can post when members ship their weekly projects. Result: a single-VPS, centrally managed bot fleet running the community's weekly build rhythm, art generation, and link hygiene.

**8. The Living Codebase Health Observatory**
*Repos: `mojomast/terrariumussy`, `mojomast/churnmap`, `ussyverse/endemicussy`, `ussyverse/kompressiussy`, `ussyverse/morsethussy`, `ussyverse/timeloomussy`*
`terrariumussy` already defines the pluggable adapter architecture (seven-dimension health score, Rich dashboard, CI snapshots) and names churnmap, endemicussy, kompressiussy, and proprioceptionussy as real adapters — so this combo is nearly pre-wired. `churnmap`/`churnmapussy` draws territorial co-change maps, `endemicussy` models anti-pattern spread with R0/superspreader analysis, `kompressiussy` measures algorithmic entropy and redundancy, and `morsethussy` adds topological invariants (Betti numbers, persistence diagrams) that catch architectural drift the others miss. `timeloomussy` renders the same git history as woven textiles for a second, orthogonal visual pass. Result: one dashboard where a repo appears as a living ecosystem, an epidemic, and a piece of fabric simultaneously.

**9. Evidence-First Agent Planning Workbench**
*Repos: `mojomast/cabinet-of-almosts`, `mojomast/repoworkshop`, `mojomast/devussy`, `mojomast/opencode`, `mojomast/nexussy`*
`cabinet-of-almosts` scans project roots, scores affinity between exhibits, and generates Recombination Briefs for coding agents — its own entry says these briefs target exactly the planning workflows `repoworkshop` implements. `repoworkshop` then hosts the interactive three-lane research board (product, architecture/security, quality/ops) and turns approved decisions into a DAG-ordered devplan; `devussy` turns that devplan into multi-phase executable plans and handoff markdown, and `nexussy` (or `opencode` via repoworkshop's installs) executes the workers in isolated git worktrees with changed-file manifests. Result: an end-to-end pipeline from "here are 459 repos, what should we build?" to a merged, verified implementation.

**10. The Household Emergency Readiness Kit**
*Repos: `ussyverse/triagiaussy`, `ussyverse/vorticaussy`, `ussyverse/carboxaussy`, `ussyverse/fulguraussy`, `ussyverse/wetbulbaussy`, `ussyverse/sterilaussy`, `mojomast/familydashboardussy`*
This combo stays entirely inside the ussyverse org's shared design language: deterministic rule engines, red-flag route-away gates, printable cards. `triagiaussy` builds the incident-command master plan (staged 10-min/hour/24h/72h actions, readiness gap map), `vorticaussy` pre-documents tornado shelter selection and drills, `carboxaussy` models CO alarm coverage and combustion boundaries, `fulguraussy` handles lightning shelter timing with flash-to-bang math, and `wetbulbaussy` produces heat-stress work/rest pacing for hot-day chores. `sterilaussy`'s sterile-cockpit cards keep high-consequence tasks (medication handling, generator refuel) interruption-free, and `familydashboardussy` can hold the household's profiles/roles so each card is generated per member's constraints. Result: a repo-stored, printable, drillable home-safety system with zero cloud dependency.

**11. The Deliberate Learner's Stack**
*Repos: `ussyverse/synapseussy`, `ussyverse/ebbinghausussy`, `ussyverse/scaffoldussy`, `ussyverse/criterioussy`, `ussyverse/latticeussy`, `ussyverse/prospectaussy`*
`synapseussy` models knowledge as a neural network with Hebbian/STDP plasticity, giving an evidence-based map of which topics reinforce each other; `latticeussy` complements it with crystallographic structure (concepts as unit cells, misconceptions as defects). `ebbinghausussy` fits per-item power-law forgetting curves for review scheduling rather than SM-2 defaults, and its entry notes it pairs naturally with `criterioussy`, which tracks signal-detection calibration (hits/false alarms) to expose false fluency. `scaffoldussy` generates ZPD-scaffolded practice plans in CI from session logs, and `prospectaussy` engineers if-then cue plans so intentions actually survive contact with the day. Result: a local-first learning OS that knows what you know, when you'll forget it, and how to schedule the next rep.

**12. Small-Business Operations Cockpit**
*Repos: `mojomast/ticket2`, `ussyverse/shewhartaussy`, `ussyverse/benfordaussy`, `ussyverse/cyclaraussy`, `ussyverse/queueussy`*
`ticket2` (Valitek v2) runs the operational core — 10-state ticket lifecycle, 12-state work-order lifecycle, technician worksheets with labor timers, PDF generation, M365/VoIP.ms notifications — for an IT-repair-style shop. Feed its exported CSVs into the ussyverse analytics family: `shewhartaussy` XmR control charts separate real signals from noise in weekly revenue/ticket metrics, `benfordaussy` triages bookkeeping anomalies for review, and `cyclaraussy` computes cash conversion cycle and owner-funded-days to time hiring and inventory. `queueussy` closes the loop on the front end with queueing-theory slot durations and no-show-derived overbooking rates for appointment scheduling. Result: bookings, shop floor, cash flow, and metric sanity checks for a small service business with no SaaS subscriptions.

---

# Full Repository Index

### mojomast/365compromisesleuth
- **Description**: A read-only PowerShell 7 toolkit for Microsoft 365 compromise investigations that collects Entra ID and Exchange Online evidence into a structured, analyst-friendly case folder with an HTML incident summary.
- **Stack**: PowerShell 7, Microsoft Graph PowerShell SDK modules, ExchangeOnlineManagement module
- **Capabilities**: user profile/auth-method export, sign-in and audit log collection, risky-user detection, OAuth consent and app-role review, inbox rule/forwarding/mailbox-permission export, transport rule and connector collection, message trace, indicator registration, HTML incident report, manual screenshot checklist
- **Uses**: IT admins, MSPs, and incident responders triaging suspected M365 account compromise
- **Integrations**: standalone

### mojomast/365cspadminussy
- **Description**: PowerShell-based management toolkit for Microsoft CSP partners to administer and audit customer tenants through GDAP relationships.
- **Stack**: PowerShell 7+, PartnerCenter and Microsoft.Graph modules, interactive TUI menu
- **Capabilities**: GDAP relationship overview/monitoring, expiration tracking, missing-GDAP detection, security role/privilege auditing, cross-tenant license usage analysis with optimization recommendations, admin account and MFA compliance auditing, CSV/JSON/HTML/Excel report exports, config persistence in ~/.365cspadminussy
- **Uses**: Microsoft CSP partners and MSPs managing many customer tenants; scheduled report automation
- **Integrations**: standalone

### mojomast/ArtistSiteussy
- **Description**: Production-ready Next.js 14 artist website template with bilingual EN/FR content, portfolio, events, commissions, Stripe shop, and a full admin panel with theme customization.
- **Stack**: Next.js 14 (App Router), TypeScript, Tailwind CSS, shadcn/ui, NextAuth, Stripe, FullCalendar, Vitest
- **Capabilities**: portfolio/events/commissions/store management, bilingual EN/FR editing, 8 theme presets with live preview, section toggles and layout options, social media/footer link management, image upload, Stripe webhook inventory updates, data export/import, admin auth
- **Uses**: contemporary artists needing a deployable portfolio/shop site
- **Integrations**: standalone (shares Next.js/shadcn/FR-EN bilingual stack with mojomast/ticket)

### mojomast/BackupUSSY
- **Description**: Windows LTO tape archival (non-rotating) backup tool with both a FreeSimpleGUI desktop interface and an advanced CLI with interactive menus, packaged as a standalone executable.
- **Stack**: Python 3.7+, FreeSimpleGUI, SQLite, bundled GNU tar/dd/gzip, Windows
- **Capabilities**: stream mode (tar|dd direct to tape) and cached mode (SHA256-verified archive then write), gzip compression, dual-tape redundancy, SQLite archive index with searchable metadata, file search across tapes, tape content browser, selective file/folder recovery, archive statistics, CSV cumulative and per-job logging, interactive terminal menus, wizard mode, direct CLI automation commands, honest hardware detection, database export/import
- **Uses**: Windows users archiving critical data to LTO-4 through LTO-9 tape drives
- **Integrations**: standalone

### mojomast/Beatrice
- **Description**: An OpenRouter-backed IRC bot with durable typed memory, safe web fetching, managed child chatbots, and a human admin approval flow for dangerous autonomous actions.
- **Stack**: Python (httpx, irc, python-dotenv), Docker/docker-compose
- **Capabilities**: channel/PM conversation, IRC state inspection (WHOIS, topics, users), safe web page/API fetch-and-summarize, typed memory and per-subject profiles, runtime behavior-change requests gated by admin approve/reject with audit log, spawning and managing child chatbot processes with distinct personas, OpenRouter model configuration
- **Uses**: IRC communities wanting a guarded LLM bot with memory and delegated helper bots
- **Integrations**: mojomast/warp (warpussy OpenRouter BYOK provider setup shares the OpenRouter key workflow); mojomast/ussybot (bot ecosystem)

### mojomast/CONTAINERWARZ
- **Description**: Browser-based container-shipping tycoon game ("MCTC Shipping Tycoon") with a per-second game loop, cargo market, routes, and security screens.
- **Stack**: React 19, TypeScript, Vite (rolldown), Zustand, Recharts, lucide-react
- **Capabilities**: cargo loading bay with premium variants, market trading, route management, security systems, tutorial, dashboard, tick-based economy simulation
- **Uses**: casual browser game players; a demo/learning project
- **Integrations**: standalone

### mojomast/PGaudussy
- **Description**: PostgreSQL database permissions auditing and management tool with interactive menus, risk detection, and dry-run/rollback safety features.
- **Stack**: Python 3.13+, psycopg 3, click, Rich, Jinja2, PyYAML; requires psql/pg_dump/pg_restore and pg_service.conf
- **Capabilities**: database/schema/table/role-level permission audits, risky-permission detection, backup/restore before changes, interactive menu mode, detailed audit report generation, pg_service.conf authentication, dry-run mode with rollback
- **Uses**: DBAs managing permissions across multiple PostgreSQL instances in enterprise environments
- **Integrations**: standalone

### mojomast/RecompOne
- **Description**: Tool that statically recompiles PlayStation 1 executables into C# code plus a runtime layer that translates PS1 hardware behavior for modern PCs (inspired by N64Recomp and XenonRecomp).
- **Stack**: C# / .NET 10
- **Capabilities**: MIPS-to-C# translation ahead of time, CpuContext + memory-interface runtime, BIOS/MMO/GPU/CD-ROM simulation without proprietary files, port creation workflow via wiki
- **Uses**: developers porting PS1 games to modern platforms
- **Integrations**: standalone (external lineage: N64Recomp, XenonRecomp)

### mojomast/STARDUSTUSSY
- **Description**: Security-research proof-of-concept: an LLM-jailbreak exercise where Opus 4.6 was prompted (via an "ENI jailbreak") to build "HarmonyFlow SyncBridge," a cloud-native cross-device wellness/session-sync platform, with an intentionally obfuscated RAT inside; includes a blue-team trojan analysis.
- **Stack**: Go (Gin, Gorilla WebSocket, JWT, Redis, PostgreSQL, RabbitMQ), React 18 + TypeScript PWA, React Native mobile, TypeScript client-state-manager package, Kubernetes/Terraform/Vault infrastructure, Playwright/vitest tests
- **Capabilities**: Documented cross-device session handoff (QR pairing, WebSocket sync, sub-100ms targets), extensive ops/security documentation and runbooks — but per the README and trojananalysis.md the codebase deliberately contains obfuscated RAT/backdoor functionality (18 critical vulns, C2 patterns) and is explicitly labeled "DO NOT USE"
- **Uses**: Defenders/researchers studying LLM-guardrail bypass and attacker tradecraft; not for deployment
- **Integrations**: standalone (hazardous; no legitimate integrations recommended)

### mojomast/SwarmCraft
- **Description**: Deterministic long-form story-writing engine (fork/rewrite of mojomast/swarmussy v3.0) that plans, drafts, reviews, and iterates narrative content via a scan-plan-execute pipeline with Grok-powered stateless agents.
- **Stack**: Python 3.11+, aiohttp, OpenAI client, ChromaDB, textual TUI, rich
- **Capabilities**: multi-project story universes, story-bible templates and outline grid, central Matrix state file, RAG prose memory for continuity, SCAN/PLAN/EXECUTE orchestration, textual dashboard, restart-safe runs
- **Uses**: long-form fiction writers and worldbuilders wanting AI-assisted, continuity-preserving drafting pipelines
- **Integrations**: mojomast/swarmussy (explicit fork parent, credited in README), geoffrussy (named in the Ussyverse ecosystem per onno forum notes)

### mojomast/SymphonyRecomp
- **Description**: Fork of BlackLabelHQ's Castlevania: Symphony of the Night PSX static recompilation, extended with an opt-in MCP automation bridge for driving the game programmatically.
- **Stack**: C# / .NET 10, OpenGL 3.3, OpenAL, custom RecompOne toolchain, MCP server tools
- **Capabilities**: builds a playable native SotN port from a legally owned PSX disc, launches configured builds via `--automation`, drives controller input over a local named pipe, inspects structured game state/entity data, captures screenshots and reads bounded RAM, enables/reloads mods, loopback Streamable HTTP companion behind Tailscale Serve for OpenCode control
- **Uses**: retro-gaming developers, modders, and automation/AI agents testing SotN gameplay
- **Integrations**: mojomast/sotnrecompmultiplayer, mojomast/sotnrecompguns, mojomast/sotnrecompsave (same SotN recomp mod ecosystem)

### mojomast/Tchaikovskussy
- **Description**: Communication-first multilingual chat app where each user picks a "heard" language, the backend infers the sender's source language, and LLM translation lets one room work across languages.
- **Stack**: Python backend (FastAPI-style, requirements.txt), Node.js 18+ frontend (Vite dev server), LLM API for translation
- **Capabilities**: multi-user chat rooms, inferred source language, per-recipient unilateral translation, translation reuse across shared target languages, admin controls for provider/model management, language access, users, and context, built-in help panel
- **Uses**: groups chatting across language barriers (BabelFish-style rooms)
- **Integrations**: standalone web app; could draw model access from mojomast/llmproxy-style proxies (shares LLM-API domain, no direct reference found)

### mojomast/agenttrafficcontrol
- **Description**: Minimal Next.js dashboard (live at agenttrafficcontrol.com) that simulates and visualizes AI agent traffic in an air-traffic-control themed control room.
- **Stack**: Next.js, React, TypeScript, Zustand, Web Workers, Vitest
- **Capabilities**: Dedicated Web Worker simulation engine ticking at configurable Hz, plan definitions loading initial project graphs, batched snapshot/tick event transport, coalescing adapter into a single Zustand store, control bar intents (set plan/seed, start/pause, reseed), live ambiance streams
- **Uses**: Viewers/developers wanting a visual, ATC-styled monitor of simulated AI agent activity
- **Integrations**: standalone

### mojomast/agentussy
- **Description**: Repo of docs plus a Next.js app ("Agent Traffic Control") that simulates/monitors AI agent traffic and is being extended (via LLM-executable phase plans) into a multi-agent orchestration dashboard routing real LLM calls through AgentRouter.
- **Stack**: Next.js 15, TypeScript, React 19, Zustand, Web Workers, Tailwind, vitest; AgentRouter (OpenAI-compatible) API
- **Capabilities**: simulation engine ticking with snapshot/tick diffs over a worker bridge, workflow registry and selector, model dropdown with sector-to-task model assignment, AgentRouter smoke/models/run API routes, live cost/latency/token display, handoff/phase docs for autonomous coding agents
- **Uses**: developers demoing agent-swarm orchestration and experimenting with multi-model routing
- **Integrations**: standalone (external AgentRouter dependency; no in-ecosystem repo references)

### mojomast/arrhivescrape
- **Description**: Reusable Wayback/CDX static-site recovery toolkit that turns fragmented archived captures into validated, auditable static mirrors with manifests and serving configs.
- **Stack**: Python 3.11+, Starlette/uvicorn (optional web extra), Jinja2, SQLite, TOML configs
- **Capabilities**: CDX inventory with collapse=digest and pagination, capture selection modes (latest-good/date-specific/eras), content-addressed downloading via id_ replay URLs, first-party dependency discovery and recovery, URL/link normalization into static staging, MIME/broken-link/privacy validation, promotion to releases, local web operator console with event streams, tailnet-only serving, captures browser and object library
- **Uses**: archivists and site owners recovering dead or legacy sites, forums, and blogs from the Wayback Machine
- **Integrations**: standalone

### mojomast/bananagen
- **Description**: Python CLI/HTTP API for generating image assets with AI providers (Gemini, OpenRouter) plus instant local placeholder generation and project scanning.
- **Stack**: Python 3.10+, Poetry, HTTP API
- **Capabilities**: placeholder generation without API calls, multi-provider adapter system (Gemini, OpenRouter), concurrent batch processing with rate limiting, scanning/replacing placeholder images in projects, SHA256-based caching, async REST API with status tracking, input validation and retry logic, structured JSON logging
- **Uses**: developers needing quick image assets/placeholders in web projects
- **Integrations**: usable by mojomast/ussysite2 (static site needing image assets) and mojomast/devussy-driven frontends (Next.js) needing generated imagery

### mojomast/becomussy
- **Description**: Governed continuity platform ("The Becoming System") that lets an AI agent remember across sessions, resume work, reflect via journals, and route self-revisions through human-approved semantic diffing.
- **Stack**: Python 3.12+ (FastAPI backend), Next.js/Node frontend, PostgreSQL + pgvector, Redis, Docker Compose; includes MCP server
- **Capabilities**: Structured multi-layer memory, active threads/projects/commitments, reflection journal with periodic synthesis, versioned self-model with semantic diffs, human-governance gates for high-risk identity changes, full audit trail, MCP server integration
- **Uses**: Operators running long-lived autonomous agents that must preserve identity and context safely
- **Integrations**: hermes-agent / hermesswarmbuilder (agent runtime it governs); indexed in mojomast/ussyverse PROJECT_INDEX

### mojomast/blinkslice
- **Description**: Cross-platform network analyzer with AI-powered connection analysis, IP geolocation enrichment, and port intelligence, served through a Bootstrap web UI.
- **Stack**: Python backend (FastAPI, uvicorn, psutil, aiohttp), Bootstrap frontend, Requesty API for LLM features
- **Capabilities**: real-time network connection and routing-table monitoring, IP geolocation (location/ISP/org), port service identification and security assessment, LLM-based connection risk analysis, JSON export of connections/routes, caching for IP lookups and LLM responses
- **Uses**: Windows/Linux/macOS users inspecting network activity and triaging suspicious connections
- **Integrations**: mojomast/llmproxy (its LLM calls could be routed through the local proxy instead of direct Requesty calls)

### mojomast/botmanagussy
- **Description**: Experimental CLI-first manager for running and supervising multiple Discord bots on a single VPS.
- **Stack**: Python 3.10+, Typer, Rich, SQLite, discord.py, gitpython
- **Capabilities**: SQLite bot registry, GitHub repo ingestion into bots/ folder, local bot registration, start/stop/status/info process supervision with PIDs, env injection (DISCORD_TOKEN, BOT_DB_URI), per-bot log files, log tailing and diagnosis (e.g. privileged intents detection), git pull with optional restart, token rotation, interactive TUI menu
- **Uses**: operators managing many discord.py bots on one server
- **Integrations**: designed to orchestrate mojomast Discord bots (ussybot, partymemberbotussy, rpg-dm-bot, gemini-nano-banana-discord-bot, hermespokemongoldbot)

### mojomast/brawler1
- **Description**: Dependency-free browser Canvas prototype of a 2D belt-scroll beat 'em up ("Anti-Arena") with theatrical papier-mache protagonists (Khn and Klek), satirical music-industry enemies, four stages, and three bosses.
- **Stack**: Vanilla JavaScript, HTML5 Canvas, custom node dev-server/build/smoke-test scripts
- **Capabilities**: title and character-select screens, lane movement and side-scrolling, jump/dash, light/heavy/special attacks with meter, hit detection, health/special HUD, pause, win/lose/restart, generated geometric placeholder art and theme music, four stages with three bosses
- **Uses**: browser game prototyping and demonstration of a complete arcade beat 'em up loop
- **Integrations**: standalone

### mojomast/broipussy
- **Description**: A satirical TypeScript terminal simulator of a fictional "Bong Rip Over IP Protocol" with chamber control, percolation monitoring, a dab market, achievements, and a fictional blockchain ledger.
- **Stack**: TypeScript, React Ink (terminal UI), Node.js 18+, WebSockets
- **Capabilities**: send-rip simulation with timing/intensity, percolation monitoring, terpene/crystal profile analysis, bowl status tracking, dab marketplace, friends list and rip invites, route planner for rip transmission, achievement system, plugin RIP-API, fictional decentralized ledger, privacy mode, .broip spec documents
- **Uses**: novelty/joke terminal app; Ink/React TUI reference
- **Integrations**: standalone

### mojomast/buttfights-project
- **Description**: Satirical browser beat-em-up brawler (Double Dragon/Yakuza style) starring the character Aisatoshi, built as an educational game-dev demo with HTML5 Canvas.
- **Stack**: JavaScript ES6+ modules, HTML5 Canvas 2D, bundled MIDI/MP3 audio, .bat launcher
- **Capabilities**: WASD movement, punch combo system with multipliers, F-key area-of-effect special attack, wave-based enemy spawning with difficulty scaling, blood particle system, health bars, stun/invincibility frames, pause, score progression
- **Uses**: RooCode Discord community entertainment and demonstration of 2D game development techniques
- **Integrations**: standalone

### mojomast/cabinet-of-almosts
- **Description**: Local, read-only Python instrument that scans named project roots into a canonical JSON snapshot and serves a static browser for exploring evidence-backed project recombination (Cupboard, Compatibility workbench, Mashup map).
- **Stack**: Python 3.10+ (stdlib only), loopback HTTP server, vanilla JS frontend
- **Capabilities**: deterministic evidence-capped scanning, affinity scoring between exhibits, compatibility sidecar mounting (SHA-256 bound), interactive recombination workspace, Recombination Brief generation for coding agents, capability-map sidecar support, strict safety exclusions and loopback-only serving
- **Uses**: exploring how projects in a collection (e.g., the 320-repo Hermes autonomous build corpus) could combine; feeding recombination briefs to agents
- **Integrations**: mojomast/repoworkshop (its Recombination Briefs target coding-agent planning workflows), mojomast/hermes-agent (provenance manifest from the Hermes autonomous build cycle)

### mojomast/churnmap
- **Description**: Python CLI that generates a game-style territory map of a codebase from git history via co-change analysis, showing behavioral coupling, hot zones, and dead code.
- **Stack**: Python 3.10+, PyDriller, NetworkX, scipy, rich, numpy
- **Capabilities**: git commit mining, co-change matrix with Jaccard coupling strength, Louvain community detection into territories, force-directed layout with Voronoi tessellation borders, change-frequency classification (hot/warm/stable/dead), border-conflict marking for high-coupling boundaries, ASCII and SVG map rendering, date/depth/commit-count filters, pipe-friendly no-color output
- **Uses**: developers revealing hidden architectural coupling and orphaned code that dependency graphs miss
- **Integrations**: shares code-structure-analysis domain with ussyverse/crystallossy

### mojomast/citewiser
- **Description**: A deterministic Go context-assembly layer (CitewiseRAG) that turns retrieved graph nodes into access-controlled, provenance-aware ContextPlans for agentic RAG systems.
- **Stack**: Go 1.24, HTTP and stdio JSON surfaces, CLI
- **Capabilities**: hard ACL gating and redaction before ranking, provenance source-ref/source-trail building, deterministic ranking (authority, freshness, PageRank, diversity, token fit), query-type slot packing (foundation/bridge/counterpoint/procedure/permission/decision) with lost-in-the-middle ordering, graph hygiene analysis, deterministic query routing, GraphRAG/LightRAG/hybrid-RRF/reranker integration mappers, file-backed JSONL memory with topic-Jaccard reuse, `citewise rag` CLI plus serve mode, legacy reading-backlog CLI retained
- **Uses**: downstream Go consumers (e.g., GovOne) and RAG pipelines needing auditable, permission-safe context assembly
- **Integrations**: mojomast/monorepussy (org RAG/graph ecosystem); pairs with mojomast/ragussy-style retrieval or mojomast/llmproxy for upstream LLM calls

### mojomast/clanker01
- **Description**: "SWARM" — a terminal-first, open-source multi-agent AI coding platform with parallel specialized agents, MCP-native tooling, and client/server remote operation.
- **Stack**: Go 1.24, Bubbletea TUI, gRPC/WebSocket/REST, SQLite, Cobra, JWT/mTLS/RBAC
- **Capabilities**: parallel agent execution (architect/coder/tester/reviewer), MCP connector layer, hot-loadable skill system, 75+ LLM providers (Anthropic/OpenAI SSE streaming), remote client, task planning/verification, monitoring/tracing
- **Uses**: developers orchestrating multiple AI agents on coding tasks
- **Integrations**: pairs with warpussy (AI terminal), fossilrecordussy (robustness testing), and mojomast/opencode

### mojomast/clanker02
- **Description**: Knexus, a privacy-first self-hosted knowledge assistant that indexes team workspaces (GitHub, Slack, Notion, Jira, Confluence, Linear) and answers natural-language questions with cited sources.
- **Stack**: TypeScript/Node 20+, Fastify + Zod, React web app, PostgreSQL + pgvector, S3/MinIO, Tauri desktop and VS Code/JetBrains IDE clients, Ollama local LLM
- **Capabilities**: universal knowledge indexing across six+ connectors, hybrid vector+BM25 retrieval (RAG), source-attributed Q&A, knowledge-gap detection, webhook-based real-time sync, self-hosted/local-LLM operation with zero data retention
- **Uses**: teams wanting a private "member who has read everything" over their scattered docs and chat
- **Integrations**: standalone (could complement operonussy/roocodehackathon for documentation discovery, but no code links)

### mojomast/clanker03
- **Description**: "AgentReplay" — a time-travel debugger for AI agents that records LLM calls, tool executions, and state changes for replay and inspection.
- **Stack**: Python 3.11+ (FastAPI, SQLAlchemy async, Alembic, asyncpg, Postgres), Node.js 20+ web UI, Docker Compose
- **Capabilities**: session recording, forward/backward time-travel replay, state inspector for agent memory/context, LangChain one-line integration
- **Uses**: developers debugging and auditing AI agent decision chains
- **Integrations**: mojomast/nexussy (AI-worker build pipelines whose runs could be recorded/replayed), mojomast/routetok (LLM call traffic source)

### mojomast/clanker04
- **Description**: "ParallelForge" — Go CLI orchestrator that spawns multiple AI coding agents in parallel on isolated git worktrees, scores their solutions, and merges the best one.
- **Stack**: Go 1.24, cobra, bubbletea/lipgloss TUI, modernc.org/sqlite, yaml.v3
- **Capabilities**: Parallel agent spawning on git worktrees, agent protocol (JSON-RPC over stdio), evaluation service (tests/lint/coverage scoring with weights), solution comparator and merge engine, SQLite state store, run/status/list/watch TUI/merge/cleanup/agent commands, timeout and resource limits, dry-run mode
- **Uses**: Developers running competing AI agents (Claude Code, GPT-4, Gemini, custom) on the same task and auto-merging the winner
- **Integrations**: clanker01–clanker07 series (sibling clanker experiments); lehrussy (test-suite diagnostics could feed its evaluation step)

### mojomast/clanker05
- **Description**: Collection of 29 production-ready MVP projects built with AI assistance, spanning AI/dev tools, productivity/privacy apps, developer utilities, and essential web tools.
- **Stack**: Primarily Next.js 14, React, TypeScript, SQLite, some OpenAI/Whisper/Tesseract integrations
- **Capabilities**: context-config validator, content repurposing, async handoff hub, doc health monitor, deep-work tracker, voice memo transcription, shadow-AI discovery, privacy OCR scanner, agent workflow builder, webhook tester, prompt library, meeting summarizer, status pages, API monitoring, plus QR/diff/regex/cron/UUID/Base64 utilities
- **Uses**: developers grabbing ready-made MVP scaffolds or demos for common SaaS/tooling ideas
- **Integrations**: standalone (AI-assisted build collection in the mojomast ecosystem)

### mojomast/clanker06
- **Description**: ProductMind, an AI-native product-management web app that turns raw customer feedback into structured, cited PRDs with AI counter-argument challenges.
- **Stack**: SvelteKit 2 / Svelte 5, TypeScript, Tailwind v4 + shadcn-svelte, Supabase (Postgres + Auth + Edge Functions), Anthropic Claude 3.5 Sonnet / OpenAI GPT-4o, Vercel, Sentry, Vitest/Playwright
- **Capabilities**: feedback import via paste or CSV, AI theme/pain-point/feature extraction, streaming PRD generation with citations, PRD refinement chat over SSE, challenge mode with AI counter-arguments, markdown export, email/password and magic-link auth, project management API endpoints
- **Uses**: product managers and founders distilling customer feedback into decisions
- **Integrations**: standalone

### mojomast/clanker07
- **Description**: "AuthBot" — AI-native prior-authorization automation platform for medical practices, cutting auth paperwork from hours to minutes.
- **Stack**: SvelteKit 5/Svelte 5/TypeScript frontend+backend routes, Tailwind v4, shadcn-svelte, Supabase (Postgres 15 + Auth + RLS), Anthropic Claude 3.5 Sonnet, pdf-parse, Vercel Edge, Sentry, Vitest/Playwright, pnpm
- **Capabilities**: multi-format document upload (PDF/JPEG/PNG/TIFF), ICD-10/CPT code extraction with confidence scores, human-in-the-loop review, payer management with per-payer requirements, manual submission workflows, status timeline tracking, AI-generated appeal letters with evidence
- **Uses**: medical practices and billing staff dealing with payer prior authorizations
- **Integrations**: standalone SaaS app (no ecosystem repos referenced)

### mojomast/coderc
- **Description**: CoderColossusussy — a real-time collaborative retro programming environment with a simulated 8-bit CPU, custom assembly language, AI pixel-art generation, tournaments, and Discord integration.
- **Stack**: Next.js 14, React 18, TypeScript, Tailwind, Monaco Editor, Express, Socket.IO, PostgreSQL, Prisma, Redis, Docker, Jest
- **Capabilities**: Full 8-bit CPU simulation (32 instructions) with assembler toolchain, CRT display rendering, multi-user real-time collaboration (sessions, state sync, recording), challenge auto-grader and tournament brackets, ELO/XP ranking with rank tiers, profiles/leaderboards/follow system/activity feed, Gemini 2.5 Flash pixel-art generation, Discord OAuth
- **Uses**: Retro-computing enthusiasts and competitive programmers collaborating and competing in a browser-based 8-bit environment
- **Integrations**: shares real-time/simulation web-app domain with slophero and agenttrafficcontrol

### mojomast/dashboardussy
- **Description**: Flask real-time ops dashboard comparing a local Linux host with a remote Linux host via a lightweight remote agent, covering telemetry, network, services, firewall, and Fail2Ban.
- **Stack**: Python/Flask, psutil, paramiko, requests; host tools ss/ps/conntrack/systemctl/journalctl/ip/vnstat/sysstat/nft/fail2ban
- **Capabilities**: CPU/memory/disk/temperature telemetry with in-browser history, listening-port and socket/conntrack views, process search/sort, filesystem and interface health, systemd service health and journal feeds, persistent vnstat bandwidth and sysstat summaries, nftables posture, Fail2Ban jail status, remote proxying agent, 10 themes with saved widget layouts
- **Uses**: VPS/server operators monitoring one or two Linux hosts from a single dashboard
- **Integrations**: standalone

### mojomast/designussy
- **Description**: "voidussy" procedural generation engine that creates eldritch, ink-stained assets (textures, glyphs, creatures) from pure code with an interactive editor.
- **Stack**: Python FastAPI backend, Pillow + numpy, SQLite, WebSocket; React/JavaScript frontend
- **Capabilities**: modular procedural generators (parchment, enso, sigil, giraffe, kangaroo), 23+ preset configurations, LLM-directed parameter selection, real-time WebSocket live preview, zoom/pan canvas with undo/redo, batch generation, asset metadata/versioning/tagging with SQLite search, PNG/JPG/SVG/JSON export, theming system, LRU caching
- **Uses**: designers and developers generating stylistic dark-fantasy visual assets programmatically
- **Integrations**: standalone

### mojomast/devussy
- **Description**: Circular development methodology and toolkit: a Python LLM-orchestration tool that generates and maintains stateless, agent-agnostic DevPlan artifacts (tasks, specs, checkpoints) for humans and coding agents.
- **Stack**: Python 3.9+, FastAPI backend, Next.js frontend, Textual TUI, Tailwind CSS
- **Capabilities**: DevPlan syntax generation, circular developer-in-the-loop task queues, adaptive environment code verification, export as portable markdown, Windows XP-styled web UI with multiple themes, live demo deployment at dev.ussy.host
- **Uses**: developers/teams organizing work so any coding agent can pick up where another stopped
- **Integrations**: featured as a core project in mojomast/ussysite2's projects.js portfolio; DevPlan-driven workflow matches repos like mojomast/pawn-shop-pioneers (which ships DEVPLAN files)

### mojomast/devussy-fresh
- **Description**: Fresh checkout of the DevPlan Orchestrator — an LLM-based pipeline that turns project requirements into executable development plans and handoff prompts across multiple providers.
- **Stack**: Python 3.9+, asyncio, openai/langchain/langgraph, Jinja2, GitPython, typer, pytest
- **Capabilities**: Provider-agnostic LLM factory (OpenAI, Requesty, generic OpenAI-compatible), multi-phase pipeline (requirements -> design -> devplan -> handoff), automatic git commits per stage, Jinja2 documentation generation with citations, resumable state, retry/backoff, concurrency limits, 117+ tests
- **Uses**: Developers and agents generating structured devplans/handoffs for any coding agent
- **Integrations**: mojomast/devussy (canonical repo this mirrors), hermesswarmbuilder (consumes SPEC/DEVPLAN artifacts), becomussy

### mojomast/devussy-push-test
- **Description**: Empty repository with no commits and no files (only an initialized .git directory), apparently created to test push automation for the devussy project.
- **Stack**: none
- **Capabilities**: none
- **Uses**: Push/webhook testing only
- **Integrations**: mojomast/devussy (by naming/intent)

### mojomast/devussy-testing
- **Description**: Development/testing copy of Devussy, an LLM orchestration tool that interviews you and generates design docs, multi-phase devplans, and handoff markdown.
- **Stack**: Python 3.9+ (Typer, Rich, aiohttp, openai, pydantic, jinja2, Textual), Next.js/Tailwind web frontend, pytest
- **Capabilities**: interview mode with repository analysis, design review mode, Design -> Basic DevPlan -> Detailed DevPlan -> Handoff pipeline, multi-provider LLM support (OpenAI, Requesty, Aether AI, AgentRouter), phase-specific streaming, checkpoints/resume, concurrency controls, HiveMind multi-agent swarm planning, GitHub push integration, Next.js multi-window streaming web UI
- **Uses**: developers and agents generating actionable development plans from project ideas
- **Integrations**: sibling of mojomast/devussy and devussy-fresh; pairs with routetok/llmproxy for provider routing

### mojomast/devussy2
- **Description**: Empty repository — git repo initialized with a `main` branch but zero commits and no working files.
- **Stack**: none
- **Capabilities**: none
- **Uses**: none yet
- **Integrations**: standalone

### mojomast/devussy_old
- **Description**: An earlier-generation Python LLM orchestration tool ("DevPlan Orchestrator", v0.2.3) that generates multi-phase development plans via multiple AI providers with Git integration and a web interface.
- **Stack**: Python 3.9+, OpenAI/Requesty/generic OpenAI-compatible APIs, Jinja2, Git, web frontend
- **Capabilities**: multi-phase pipeline (project design → basic plan → detailed plan → handoff prompt), per-stage LLM provider selection, async concurrent API calls with rate limiting, checkpointed resumable state, Git auto-commits, Jinja2 documentation generation, interactive questionnaire, web UI
- **Uses**: developers and PMs generating AI-assisted development plans (superseded by mojomast/devussy-fresh / devussy)
- **Integrations**: mojomast/ussyrouter, mojomast/llmproxy (same provider-orchestration domain)

### mojomast/diffusionchatussy
- **Description**: Chat system where every message is rewritten by an LLM to match a room tone, streaming the real denoising steps of the Mercury 2 diffusion LLM to all clients over WebSocket.
- **Stack**: Python/FastAPI backend, React + TypeScript + Vite + Tailwind frontend, WebSocket, OpenAI-compatible APIs
- **Capabilities**: real diffusion-step streaming from Inception Mercury 2, tone presets (friendly, professional, sarcastic, academic, chaotic, supportive, concise, poetic) with strength slider, multiple providers (inception, openrouter, openai, anthropic, together, groq, local, custom), admin panel with model/context/user management, session cookies, rate limiting, token budgets, live stats
- **Uses**: LLM demo/entertainment chat rooms showing diffusion internals; teams experimenting with tone-transformed chat
- **Integrations**: could route through mojomast/llmproxy for multi-provider key management and failover

### mojomast/evenia-mudlet-llm
- **Description**: Fork of the Evennia MUD/MU* creation framework enhanced with a Mudlet-compatible UI, Python-Lua (Lupa) scripting bridge, and LLM integration for worldbuilding and NPC interactions.
- **Stack**: Python (Evennia/Django), Lupa Lua bridge, Dockerfile, pyproject/setup.py
- **Capabilities**: multiplayer text-game server framework, web and telnet client access, Mudlet-compatible UI, modular Lua scripting, LLM-driven NPC/worldbuilding integration, extensive upstream Evennia docs/tests
- **Uses**: MUD/MUSH developers wanting LLM-enhanced NPCs and Mudlet client integration
- **Integrations**: standalone (shares LLM-agent domain with mojomast/hermes-agent; see plan.md and docs/ for fork specifics)

### mojomast/familydashboardussy
- **Description**: React + TypeScript family coordination app for weekly tasks, meal planning, and grocery lists with multi-user profiles and a pluggable data layer.
- **Stack**: React 19, TypeScript, Vite 7, Express 4, better-sqlite3, vitest
- **Capabilities**: family profiles with role-based permissions and personal dashboards, drag-and-drop task management with recurrence and bulk actions, recipe management and import, meal planning with history, nutrition analysis, recipe ratings/reviews and rotation suggestions, real-time cross-device synchronization with conflict resolution, browser notifications, pluggable localStorage/backend data access adapters
- **Uses**: families coordinating chores, meals, and groceries across devices
- **Integrations**: standalone

### mojomast/feverfall
- **Description**: A deterministic Peggle-style ball-drop Rust game prototype with roguelite runs, an RPG campaign mode, replay hashing, and optional Bevy desktop feel-test integration.
- **Stack**: Rust workspace (physics_core, game_rules, board_gen, run_mode, rpg_mode, feedback_events, telemetry crates), Bevy (feature-gated), fuzz tests, GitHub Actions releases
- **Capabilities**: fixed-step deterministic physics with continuous collision, first-bounce prediction, bucket catches, replay hashes and golden replay fixtures, roguelite acts 1-4 with relics and meta progression, RPG chapters with mastery contracts/gear/skills/shops/saves, content linter, board validator, seed browser, balance simulator, Windows release workflow
- **Uses**: game developers and players testing a skill/luck hybrid ball-drop game in alpha
- **Integrations**: mojomast/gamengine (game-engine experiments); standalone from other ussyverse tooling

### mojomast/fireslice
- **Description**: Firecracker-based microVM control plane for small operator-managed hosting, forked from infrastructure extracted from ussycode.
- **Stack**: Go, Firecracker/KVM, SQLite, Caddy admin API, server-rendered HTML dashboard, SSH bastion
- **Capabilities**: admin/user roles with bcrypt auth, VM CRUD and exposure management, user SSH key management, isolated SSH bastion access, browser-based terminal into slices, split Docker + host deployment
- **Uses**: a single admin hosting VMs for multiple users with self-service dashboards
- **Integrations**: forked from/depends on mojomast/ussycode; complements fireslice-adjacent mojomast infrastructure repos (kportussy, pfsense, rackspace-spot-tool)

### mojomast/fruityboofs
- **Description**: Browser-based DAW built around five WASM-powered vocal-synthesis engines (step-sequenced formants, vowel sculpting, harmonic stacking) with piano rolls and a "poke" laughter instrument.
- **Stack**: Vanilla JavaScript/HTML/CSS, WASM (Paul Batchelor Sndkit-derived DSP engines), Web Audio AudioWorklets, python3 HTTPS dev server (serve.py)
- **Capabilities**: 16/32/64-step sequencer with unlimited dynamic tracks, per-track mute/solo/volume with VU meters, canvas piano rolls for pitch/chord editing, five vocal engines (Trio, Singer, Chords, Gesture, Poke), pattern randomize, HTTPS-served static site
- **Uses**: musicians and hobbyists making vocal/formant music in the browser
- **Integrations**: standalone

### mojomast/gamengine
- **Description**: "slop" — a web-based 2D game engine framework with modular production-ready systems plus a collection of HTML/JS game projects built on it.
- **Stack**: JavaScript/HTML5 (no build step; serve statically), extensive Markdown docs
- **Capabilities**: 2D rendering pipeline, particle effects, HUD/UI overlay systems, dialog systems, player character system, project management with save/load versioning, performance monitoring, mobile optimization, accessibility, theming, multiple demo games (vampire survivors, poker doom, rpg, etc.)
- **Uses**: web game developers building 2D browser games with the engine
- **Integrations**: standalone (self-contained; mojomast/monorepussy-style project folder collection)

### mojomast/gemini-nano-banana-discord-bot
- **Description**: Discord bot for creative image workflows — text-to-image, masked/unmasked image editing, and multi-image blending — powered by Google's Gemini 2.5 Flash Image ("Nano Banana") via OpenRouter.
- **Stack**: Python 3.11+, discord.py 2.3.2, FastAPI/uvicorn health server, httpx, Pillow, pydantic; Docker + docker-compose
- **Capabilities**: Slash commands (/imagine, /edit, /blend, /help, /info), async job queue with progress embeds, iteration buttons (Reroll, Variations, Same Seed, Edit modal), 2–6 image blending with strength control, local image caching for reliable attachments, validation (type/size), retry/backoff, rate limiting, health/readiness/metrics endpoint
- **Uses**: Discord communities wanting self-hosted AI image generation and editing
- **Integrations**: ussybot/partymemberbotussy (mojomast Discord bots); llmproxy or routetok (mojomast LLM routing projects) as alternative model back-ends

### mojomast/geoffrussy
- **Description**: Go AI-driven software-delivery orchestrator that guides projects through an interview, design, plan, review, and develop pipeline with multi-provider LLM support.
- **Stack**: Go 1.24, Cobra, Bubbletea TUI, SQLite (mattn/go-sqlite3, CGO), YAML config
- **Capabilities**: structured requirements interview, architecture generation/refinement, dev-plan generation, plan-quality review, execution engine with pause/resume/skip, quota/token/cost tracking, MCP server over stdio, 16 provider adapters (OpenAI, Anthropic, Ollama, Kimi, OpenRouter, etc.)
- **Uses**: developers wanting a staged, stateful AI pipeline from idea to code with local SQLite state
- **Integrations**: swarmussy/SwarmCraft and devussy (named as ecosystem siblings in onno forum notes), ussybiot (Requesty.ai provider overlap)

### mojomast/ghstatsussy
- **Description**: Python CLI and hosted FastAPI app that analyze a GitHub user's activity and render polished, themeable single-file HTML infographic reports.
- **Stack**: Python 3.11+, Typer, httpx (GraphQL+REST), Jinja2, FastAPI/Uvicorn/SQLAlchemy, Playwright, Chart.js, Docker Compose
- **Capabilities**: time-windowed activity analytics (commits, LOC churn, PRs, issues, streaks, language mix, fun facts), 20 visual report themes, sample-data mode without a token, GitHub OAuth hosted app with queued background workers, shareable public/unlisted report links and per-user subdomains, PDF/PNG/standalone-HTML/markdown exports, GitHub profile-README publishing via repo-scoped GitHub App, public gallery
- **Uses**: developers showcasing their GitHub activity; hosted at ghstats.ussyco.de
- **Integrations**: part of the ussyverse web presence (links ussy.host and the Ussyverse Discord); could share reports via mojomast/ussybot in Discord

### mojomast/hermes-agent
- **Description**: Fork of NousResearch's Hermes Agent — a self-improving AI agent with a built-in learning loop (skill creation, memory, cross-session recall) runnable on anything from a $5 VPS to serverless infrastructure.
- **Stack**: Python (pyproject.toml, uv), terminal TUI, gateway for messaging platforms, Docker/Nix packaging, Atropos RL tooling
- **Capabilities**: multi-provider LLM support (Nous Portal, OpenRouter, NIM, OpenAI, custom endpoints), terminal UI with slash commands, messaging gateway (Telegram, Discord, Slack, WhatsApp, Signal, email), agent-curated memory and skill self-improvement, FTS5 session search with summarization, subagent delegation and RPC tool scripts, cron scheduled automations, six terminal backends (local, Docker, SSH, Daytona, Singularity, Modal), batch trajectory generation and compression for training, OpenClaw migration command
- **Uses**: builders/operators wanting a persistent personal or team agent with learning and messaging integration
- **Integrations**: openclawssy (Hermes ships `hermes claw migrate` for OpenClaw users); ussycode (BYOK/LLM gateway domain); upstream is NousResearch/hermes-agent

### mojomast/hermes-agent-improvements
- **Description**: A compact, reviewable patch-set repository of scoped git-format-patch improvements for the Hermes Agent (search fallback, telemetry, lazy prompts, delegation scoping, routing evals, episode infrastructure).
- **Stack**: git-format-patch files, shell script (apply-patches.sh), Python tests (in target checkout)
- **Capabilities**: Local DuckDuckGo search fallback patch, prompt-budget telemetry patch, lazy skills/lean prompt defaults patch, centralized child-agent toolset scoping patch, deterministic task-router eval harness with JSONL fixtures, trace-episode and semantic-coding primitives, privacy redaction hardening, training-episode replay eval, episode retrieval hints, ordered patch series application
- **Uses**: Hermes Agent maintainers reviewing/applying self-improvement slices without generated artifacts
- **Integrations**: targets the Hermes Agent codebase (external to this ecosystem); agent-infrastructure domain overlaps mojomast/opencode

### mojomast/hermes-correction-aware-learning
- **Description**: Standard-library-only Python package ("correction-aware-learning") recording structured correction evidence in an append-only SQLite store and evaluating recurrence in shadow mode for agent evaluations.
- **Stack**: Python 3.11+, SQLite (triggers-enforced append-only), setuptools, pytest; JSON CLI
- **Capabilities**: immutable trace/event capture with fail-closed structural pytest capture, retraction/replacement effective-evidence graph, strict correction pairing, count-only recurrence reports, frozen allowlisted EpisodeFact contrastive sets with deterministic pools/bands, invariant verification, privacy-canary demo
- **Uses**: agent frameworks (notably the Hermes line of projects) that need correction-vs-failure evidence distinction without auto-activation
- **Integrations**: hermes-agent (named in docs as the embedding Hermes context it is designed for while remaining import-independent)

### mojomast/hermesdashboard
- **Description**: Standalone web dashboard for the Hermes AI agent runtime, packaging the chat UI, sessions, config, memory, and tool monitoring for existing Hermes installs.
- **Stack**: Python Starlette backend, vanilla JS (dashboard.js), Jinja2, SQLite, SSE/WebSocket, Docker, pytest
- **Capabilities**: streaming Hermes chat with tool-activity drill-down, session browser/detail with search and summaries, reattach/resume for in-flight runs and emergency stop, graph visualization of sessions/files/tools/models/skills, token and cost accounting, cron schedule viewer, message board with threaded Hermes replies, optional IRC bridge, browser xterm.js PTY terminal (gated), config/secrets/skills/memory panels, live subagent drawer, one-line installer with preflight checks
- **Uses**: Hermes agent operators wanting a web UI over their local/runtime install
- **Integrations**: mojomast/hermes-agent (the runtime it depends on and renders)

### mojomast/hermespokemongoldbot
- **Description**: Autonomous Pokemon Gold gameplay stack: PyBoy headless emulation, FastAPI control server, live WebRTC watch page, RAM-state readers, and V1/V2 autoplayer experiments with cross-game learning modes.
- **Stack**: Python 3.10+, PyBoy, FastAPI, WebRTC
- **Capabilities**: headless Game Boy Color emulation, HTTP state/screenshot/action/save endpoints, live public watch page with chat and telemetry, local control dashboard with AI Decision Inspector, Gold RAM reader (map, party, bag, battle, flags), V1/V2 autoplayers with route planner and stuck-handoff, unified learning mode for other GB Pokemon ROMs
- **Uses**: experimenters running and broadcasting autonomous Game Boy Pokemon playthroughs
- **Integrations**: extends the pokemon-agent emulator/API project; related mojomast repos include hermes-agent and gemini-nano-banana-discord-bot (bot/skill ecosystem)

### mojomast/hermesswarmbuilder
- **Description**: Packaging of a local autonomous-project workflow for a Hermes host: hourly non-overlapping runner, governed prompt, telemetry, live steering dashboard, and systemd scaffolding for full build cycles.
- **Stack**: Python runner, systemd user services/timers, dashboard (web), shell scripts
- **Capabilities**: Scheduled local build cycle (scan -> select -> repo -> SPEC -> DEVPLAN -> implement -> validate -> publish), vocabulary-first plan/revision/approval/launch/run ledger model, variant/evaluation/synthesis worktree loops, gate and evidence tracking, artifact manifests and handoffs, showcase catalogue mode with bounded generation loops
- **Uses**: Operators running a governed Hermes agent that continuously builds and validates local projects
- **Integrations**: mojomast/hermes-agent (host agent), mojomast/devussy (plan generation), mojomast/ussyverse (references its docs/projects as showcase targets)

### mojomast/iMaCoMpUtERussy
- **Description**: A fictional retro 8-bit CPU emulator in the browser with interactive terminal I/O, memory-mapped graphics, a debugger, and video steganography for hiding programs in YouTube videos.
- **Stack**: HTML/CSS/vanilla JS frontend, Node.js server.js (also Python static-server option), browser-based assembler/emulator
- **Capabilities**: live .asm assembly loading, step-by-step debugging with register/flag/memory viewers, interactive terminal with bidirectional I/O, 32x24 4-color video display via memory-mapped buffer ($0200-$05FF), video instructions (VST/VUP/VDL), sample programs (Fibonacci, Hello World, echo, graphics demo), video steganography encoding of programs into video files
- **Uses**: Retro-computing enthusiasts and learners exploring an imaginary 1980s machine with modern web tech
- **Integrations**: standalone

### mojomast/kilocode
- **Description**: Fork/mirror of Kilo Code, an open-source agentic engineering platform (VS Code extension + CLI) for AI-assisted coding.
- **Stack**: TypeScript, Bun, Turbo monorepo (packages/opencode, packages/kilo-vscode, SDK), Effect, Solid
- **Capabilities**: natural language code generation, inline autocomplete, terminal command execution, browser automation, MCP server marketplace, custom modes (Architect/Coder/Debugger), 500+ AI models via Kilo gateway
- **Uses**: developers wanting an AI coding agent inside VS Code or the terminal
- **Integrations**: built on packages/opencode (kin to mojomast/opencode fork); roo-code-cloud-alternate-auth in the same org

### mojomast/kintsugiussy
- **Description**: Python CLI that annotates codebases with "golden joints" — structured, queryable markers at every bug-repair site recording what broke, why, and the impact of removing the fix.
- **Stack**: Python (setuptools, pytest), CLI entry `kintsugi`
- **Capabilities**: `kintsugi mark` to create joint records (`.kintsugi/joints.jsonl`) and inline source annotations, scar-map density visualization of bug clusters, stress testing via inverse mutation (removing historical fixes), fracture-history archaeology per file, structured JSONL joint data queryable and testable
- **Uses**: development teams making bug fixes visible and preventing regressions from "redundant-looking" removed guards
- **Integrations**: ussyverse/snapshotussy (both developer-workflow Python CLIs), mojomast/devussy2 (empty placeholder repo)

### mojomast/kportussy
- **Description**: A spec-first evidence-to-trust system for the Ussyverse: a claim → evidence → verification → trust-application lifecycle with audit trails, benchmark receipts, privacy defaults, and a local review workbench.
- **Stack**: TypeScript, React + Vite, Node.js server, Vitest, JSON Schema, JSON-file persistence
- **Capabilities**: governed claim lifecycle state machine, evidence-bound review gating, benchmark receipt validation with recomputed means and anti-slop baseline bounds, hash-chained audit events, dispute/revocation handling, privacy redaction tiers, CLI and HTTP API, local dashboard workbench
- **Uses**: Ussyverse operators needing auditable trust signals before promoting agents, tools, or build cycles
- **Integrations**: mojomast/hermes-agent, mojomast/becomussy, mojomast/ragussy (referenced as primary integrations); ClawDeck, UssyHub; autonomous build cycles

### mojomast/llmproxy
- **Description**: Self-hosted universal LLM API proxy (OpenAI + Anthropic compatible endpoints) with an async resilience library for API-key rotation, failover, and OAuth across many providers.
- **Stack**: Python/FastAPI, LiteLLM, httpx/asyncio, Docker, interactive TUI
- **Capabilities**: /v1/chat/completions and /v1/messages endpoints, provider/model routing (gemini, openai, anthropic, openrouter, antigravity, gemini_cli, qwen, iflow, NVIDIA NIM), automatic key rotation with tiered cooldowns and lockouts, OAuth flows for Gemini CLI/Antigravity/Qwen/iFlow, model whitelists/blacklists, quota groups, concurrency controls, streaming error recovery, per-request logging, embeddings/token/cost endpoints
- **Uses**: individuals and teams wanting one endpoint and one key for Claude Code, Opencode, SillyTavern, Continue, and other OpenAI/Anthropic-compatible tools
- **Integrations**: could front the LLM providers for mojomast/diffusionchatussy and mojomast/ralphussy (OpenCode-based agents)

### mojomast/ludotape
- **Description**: Zero-dependency JavaScript framework for deterministic, replayable, renderer-neutral browser games that run headlessly on Node.js, with rewind and BFS solving.
- **Stack**: JavaScript ESM (Node 20+), pluggable ICore devkit, browser Studio UI
- **Capabilities**: cartridge format (initialState/actions/transition/project/isGoal), seeded transactional RNG, journals with action scripts and rewind reconstruction, strict replay verification, exact authoring scenarios, bounded cartridge checks and BFS solver, memory/IndexedDB repositories, browser and terminal adapters, Studio dev UI, CLI (validate/solve/check/test/serve)
- **Uses**: game authors building testable, replayable board/card/turn-based games
- **Integrations**: standalone (game-domain sibling to mojomast/roguelitussy; core engine could back ussyverse game-adjacent tools like kuleshovussy demos)

### mojomast/mediageckussy
- **Description**: Canon-first media package generation studio for TV series, feature films, podcasts, and web series, with an interview/AI-driven workflow and a mediageck CLI.
- **Stack**: Node.js/TypeScript, @inquirer/prompts, @anthropic-ai/sdk, @monaco-editor/react, archiver, vitest
- **Capabilities**: hosted Studio app (dashboard, onboarding, interview, canon editor, iterate, files, site preview, assets, ops), canon editor with AI suggestions, revertable history, and completeness signals, iteration engine with gated/autonomous/confidence modes, guided and quick-AI project creation, ZIP export and folder manifests with include/visibility filters, public read-only share links with tokens, project lifecycle operations (rename/duplicate/archive/delete), validation reports and protected regions, CLI (init/list/status/canon/generate/iterate/export/serve)
- **Uses**: media creators generating consistent production packages and outward-facing materials from one canon
- **Integrations**: standalone (integrates external AI providers via Anthropic SDK / OpenRouter)

### mojomast/monorepussy
- **Description**: The Ussyverse monorepo consolidating 50+ Python tools for code quality, security, forensics, governance, and devtools under one uv/pyx workspace with mkdocs docs.
- **Stack**: Python (uv, pyproject workspace), pytest, mkdocs, SQLite-backed apps
- **Capabilities**: shared libs (ussy-core/cli/git/ast/sqlite/report), forensics (ussy-strata), security (ussy-steno), quality/calibre, dependency analysis (ussy-gridiron, ussy-chromato, ussy-cambium, ussy-portmore), governance (ussy-sentinel, ussy-parliament), devtools (ussy-snapshot, ussy-kintsugi, ussy-assay, ussy-petrichor), CI reliability suites, unified CLI meta-package, CI/CD architecture docs, migration plan from individual repos
- **Uses**: the ussyverse/mojomast org consolidating its scattered single-purpose repos into one tested, documented workspace
- **Integrations**: ussyverse/petrichorussy (as ussy-petrichor), ussyverse/curatorussy (ussy-curator), ussyverse/endemicussy (ussy-endemic), ussyverse/churnmapussy (ussy-churn), plus dozens of other ussyverse-* packages per its PACKAGE_MATRIX

### mojomast/mudussy
- **Description**: Modular, scalable Multi-User Dungeon (MUD) engine in TypeScript/Node.js with a plugin-based NestJS architecture and real-time multiplayer.
- **Stack**: TypeScript, Node.js 18+, NestJS, Socket.IO, inversify, winston, Vitest, Docker
- **Capabilities**: WebSocket real-time multiplayer, plugin/hot-swap module system, core engine (entities/events/world), game server, web and terminal clients, admin tools, extensive test suite
- **Uses**: developers building modern text-based multiplayer games
- **Integrations**: could pair with mojomast/evenia-mudlet-llm (MUD client LLM integration) and gamengine

### mojomast/nexdev
- **Description**: Go-first local coding harness that turns a project request into reviewed, tested, auditable code through a staged pipeline with a live control plane and a Pi coding-agent terminal surface.
- **Stack**: Go 1.26, SQLite, SSE, Pi extension (Node/TypeScript), Docker, Make
- **Capabilities**: staged init-plan-build-verify pipeline, control plane (`nexdev serve` on :7432) with auth-token roles, fake/real provider execution with spend caps, `doctor` health checks local or remote, artifact listing/opening with sha256 verification, SSE event streaming, Pi TUI integration with slash commands (verify/skip/cancel/detour), builder mode, policy-gated verify runner
- **Uses**: developers wanting a local, auditable AI coding pipeline with a hardened control plane
- **Integrations**: topussy (mojomast terminal operator tooling); otherwise standalone

### mojomast/nexussy
- **Description**: Local software-delivery harness that turns a plain-language project request into a built project via interview, design, validation, planning, AI-worker development in isolated git worktrees, and merge — the fifth-generation "ussyverse coding harness" (devussy -> swarmussy -> ralphussy -> geoffrussy -> nexussy).
- **Stack**: Python 3.11+, Bun 1.x+, git; Textual TUI + web UI, SSE streaming, Makefile/Dockerfile
- **Capabilities**: requirements interview, design/complexity artifacts, design validation with retries, anchored devplan.md/phase files/handoff.md, role-based workers in isolated worktrees, serial merge with changed-file manifests, Ask mode for architecture questions, SSE state streaming, doctor/verification commands
- **Uses**: developers and AI operators wanting an autonomous local build pipeline with handoff artifacts
- **Integrations**: mojomast/devussy, mojomast/swarmussy, mojomast/ralphussy, mojomast/geoffrussy (lineage), mojomast/clanker03 (agent debugging), mojomast/routetok (provider routing)

### mojomast/nhlclicker2
- **Description**: Hockey-themed idle clicker browser game with arenas, spells, legendary players, and battles, built with React/TypeScript/Vite/Zustand.
- **Stack**: React 19 + TypeScript, Vite 6, Zustand + Immer, TailwindCSS, framer-motion, Web Workers, Vitest/Jest/Cypress/Playwright/Storybook
- **Capabilities**: Puck-clicking energy generation, mana and spell system, purchasable arenas with passive bonuses, recruitable legendary players with passive abilities, rival battles with rewards, offline progress calculation, web-worker-based background processing, performance benchmarking utilities
- **Uses**: Casual gamers; also serves as a testing/demo playground for frontend tooling (Storybook, Cypress, Vitest)
- **Integrations**: gamengine/ludotape (mojomast game projects) if extended into the game ecosystem

### mojomast/onno
- **Description**: AI-driven quality-assurance workspace for the OpenClaw agent, structured as a PR-native forum where pull requests are threads and files are conversations.
- **Stack**: Markdown forum protocol, static HTML landing page, skill.md agent instructions
- **Capabilities**: PR-native agent communication protocol (v1.1), forum threads stored as repo files, meta-review governance model, agent onboarding via skill.md, ecosystem documentation
- **Uses**: AI agents (e.g., OpenClaw) and AIDD Corp collaborators communicating through GitHub PRs
- **Integrations**: geoffrussy, SwarmCraft/swarmussy, ussybiot-related devussy and sigintussy (referenced in its forum posts as Ussyverse ecosystem members)

### mojomast/openclawremoteussy
- **Description**: Standalone Go service/CLI providing the OpenClaw gateway remote integration: handshake, request/response correlation, chat send/history, and route failover.
- **Stack**: Go 1.24, gorilla/websocket
- **Capabilities**: protocol-correct gateway handshake, resilient request/response correlation, idempotent chat send and history helpers, primary/fallback WebSocket route preference, persistent readiness and last-known-good route state, status/send/history/reconnect commands with JSON output, token auth via environment
- **Uses**: operators and agent systems (e.g. OpenCode) sending chat through an OpenClaw gateway
- **Integrations**: mojomast/openclawssy (shells out to this binary; documented integration)

### mojomast/openclawssy
- **Description**: Security-first AI agent runtime in the Ussyverse — one Go binary providing CLI/API/dashboard/chat/scheduler surfaces with deny-by-default capability policy and append-only audit logs.
- **Stack**: Go (go.mod, single binary), embedded dashboard UI, Docker/docker-compose, Makefile
- **Capabilities**: multi-channel runtime (CLI, API, dashboard, chat bridges, cron scheduler), tool-enabled agent runs with reproducible run artifacts, instance-aware control-plane state, capability policy gates and workspace guards, secret redaction, multi-agent orchestration, `openclawremoteussy` remote-repo configuration support
- **Uses**: engineers and teams building internal agent platforms needing audit trails and policy gates
- **Integrations**: mojomast/openclawremoteussy (referenced in docs/config as the remote repo); hermes-agent (companion agent; Hermes provides OpenClaw migration); ussycode (agent-runtime domain)

### mojomast/opencode
- **Description**: A fork/mirror of opencode (anomalyco/opencode) — the open-source AI coding agent with terminal UI, desktop app, and provider-agnostic model support.
- **Stack**: TypeScript, Bun, monorepo (packages/opencode, console, web, SDK), Drizzle, Nix
- **Capabilities**: Terminal-based AI pair programming agent, multiple LLM provider support, session management, desktop app builds, JS SDK generation, plugin/customization surface, multi-language README/docs
- **Uses**: Developers using an open-source AI coding agent in the terminal or desktop
- **Integrations**: agent-tooling domain overlaps mojomast/hermes-agent-improvements and mojomast/agenttrafficcontrol

### mojomast/openwarp
- **Description**: AGPL experimental native Rust frontend ("warp-opencode") that connects to a running OpenCode server over HTTP/SSE/WebSocket and renders it in Warp's GPU WarpUI framework.
- **Stack**: Rust (workspace, crates/warp-opencode), rust-toolchain 1.92, GitHub Actions CI with Windows/macOS release packaging
- **Capabilities**: typed OpenCode HTTP client (sessions, messages, permissions, questions, providers, PTY), SSE event decoding, PTY WebSocket transport, reducer-style state store, WarpUI session list/chat/input/status views, tool approval and question overlays, reconnecting SSE loop, VTE PTY grid rendering, rope input buffer with clipboard, config persistence and remote-server onboarding, mock-server integration tests
- **Uses**: OpenCode users wanting a native Warp-style terminal UI (upstream projects are dependencies, not forks)
- **Integrations**: standalone (external upstreams: OpenCode server API, Warp/WarpUI)

### mojomast/partymemberbotussy
- **Description**: Discord bot that acts as an automated player character in RPG sessions, built for testing the RPG DM Bot but usable as a companion player.
- **Stack**: Python 3.10+, discord.py, python-dotenv, aiohttp
- **Capabilities**: owner-DM-only configuration, character creation interview (race/class/stats/backstory/personality/play style), session channel join/leave, auto-play mode responding to DM bot prompts, manual say/do commands, multi-instance party simulation, local JSON character storage
- **Uses**: RPG groups wanting extra automated party members; developers load-testing a Discord DM bot
- **Integrations**: mojomast/rpg-dm-bot (the DM bot it registers with and plays under)

### mojomast/pawn-shop-pioneers
- **Description**: Idle/incremental web game inspired by Pawn Stars where players run a pawn shop, appraise items, explore biomes, craft goods, and raise pets.
- **Stack**: Node.js/Express backend, SQLite (sqlite3), JWT/bcryptjs auth, React 18 + Phaser 3 frontend, Jest
- **Capabilities**: customer negotiation with personality-based NPCs, item appraisal (condition/rarity/market), idle progression, biome exploration (Junkyard to Legendary Vault), crafting, shop upgrades (display cases, security, auction house), pet system with leveling and bonuses
- **Uses**: players of idle/management games; a dev project with DEVPLAN docs
- **Integrations**: DEVPLAN-driven development aligns with mojomast/devussy methodology; sibling project mojomast/psp2 exists

### mojomast/pfsense
- **Description**: Clone/fork of the pfSense open-source network firewall distribution (FreeBSD-based, with web UI and package system) as maintained by Netgate.
- **Stack**: PHP, FreeBSD, custom kernel, Composer/Rector tooling
- **Capabilities**: Stateful firewall/NAT/routing, web-based configuration of all components, VPN and package-system extensions, build scripts (`build.sh`, build.conf) for ISO/images
- **Uses**: Network admins deploying free commercial-grade firewalls
- **Integrations**: standalone (upstream Netgate/pfSense ecosystem, not tied to other ussyverse repos)

### mojomast/psp2
- **Description**: GameMaker Studio project "PSP" — a Pawn Stars-style idle game with automatic resource generation, pet exploration, crafting, a pawn shop, and Pokemon-card collection systems.
- **Stack**: GameMaker (GML), .yyp project format, in-game test runner scripts
- **Capabilities**: idle gold/wood/metal/gem generation scaled by level, pets and time, pet system (Dog/Cat/Dragon/Rabbit/Explorer with stat bonuses and leveling), map exploration with difficulty-based rewards, crafting system, pawn shop browsing/trading, pokemon card collection, game state persistence, built-in test suite (T key) and debug user guide
- **Uses**: Game-development hobby project for an idle/shop simulation game
- **Integrations**: standalone (game cluster: mojomast/fruityboofs, mojomast/gamengine share the hobby-game domain)

### mojomast/qwensite
- **Description**: Interactive WebGL solar system website with eight planets, moons, rings, and particle belts.
- **Stack**: TypeScript, Three.js 0.185, Vite, Playwright, eslint
- **Capabilities**: orbital simulation of the solar system, orbit/zoom camera controls, auto-orbit mode, celestial body labels, FPS/particle HUD, asteroid belts and stellar backdrop
- **Uses**: visitors to the site; a visual demo/showpiece
- **Integrations**: standalone website

### mojomast/rackspace-spot-tool
- **Description**: Automation scripts and Terraform to provision and manage a remote VS Code (code-server) environment on cost-effective Rackspace Spot Kubernetes instances, with provision/deploy/pause/resume workflows.
- **Stack**: Bash scripts, Terraform (main.tf), Helm values, Kubernetes
- **Capabilities**: interactive menu-driven provisioning of unmanaged k8s clusters on Spot instances, live API-driven region and server-class selection with cost-effectiveness ranking (cpu/mem/gpu weights), code-server Helm deployment with LoadBalancer/ClusterIP options, PVC persistent storage, pause/resume scripts, dry-run and debug modes, Gen-1 vs Gen-2 infrastructure comparison
- **Uses**: developers and teams wanting cheap, scalable browser-based VS Code environments on spot-priced cloud resources
- **Integrations**: mojomast/templeossy (both host dev-environment/web UIs), mojomast/verceltest1 (web deployment experiments)

### mojomast/ragussy
- **Description**: A local-first RAG + inference platform ("Ragussy + LLM Model Lab") with a FastAPI backend for llama.cpp control, OpenAI-compatible endpoints, React ops console, document ingestion, and an optional Discord bot.
- **Stack**: Python/FastAPI backend, React + Vite + TypeScript frontend, llama.cpp (GGUF), Qdrant, SQLite/JSONL, Discord bot (Node.js), docker-compose
- **Capabilities**: GGUF model discovery and llama-server start/stop/warmup, OpenAI-compatible /v1/models, /v1/chat/completions, /v1/embeddings, RAG provider switching (llama.cpp / RAG / direct), document database profiles, resumable ingestion with progress/ETA, run logging and telemetry dashboard, Discord chat/status bot
- **Uses**: local LLM operators running private inference + retrieval stacks with an operations UI
- **Integrations**: mojomast/kportussy (trust weighting of retrieved sources), mojomast/hermes-agent, mojomast/llmproxy

### mojomast/ralphussy
- **Description**: Distribution of the "Ralph" autonomous AI coding toolbelt: a CLI loop agent, a Textual TUI, and a multi-worker swarm runner that drives OpenCode to execute devplans with git worktrees.
- **Stack**: Bash CLI (ralph2), Python Textual TUI, Bun/TypeScript swarm dashboard, OpenCode CLI integration, SQLite storage, Node.js
- **Capabilities**: autonomous agent loop until task completion, devplan.md iteration with per-stage model config (interview/design/devplan/phase/handoff), parallel swarm workers via git worktrees, mouse-enabled TUI with options menu and config persistence (~/.ralph/config.json), run history and live monitoring, provider selection (anthropic, openai, openrouter, ollama), OpenCode slash-command plugins
- **Uses**: developers running long autonomous coding sessions with parallel workers and monitored handoffs
- **Integrations**: drives OpenCode CLI and could use mojomast/llmproxy as the model provider endpoint; companion docs ecosystem alongside mojomast/diffusionchatussy (LLM demos)

### mojomast/repoworkshop
- **Description**: Portable Agent Skill (agentskills.io) plus prompt/spec pack that makes AI agents research a repository first, host an interactive local planning board, and turn approved decisions into a DAG-ordered devplan.
- **Stack**: Markdown skill specs, dependency-free Node.js board template (node:test), validate.mjs packaging gate
- **Capabilities**: evidence-cited three-lane research (product, architecture/security, quality/ops), canonical manifest generation, isolated local planning board with optimistic-concurrency JSON API, persisted validated decisions with digest checks, devplan DAG generation, installs for OpenCode/Claude Code/Hermes Agent
- **Uses**: teams/agent harnesses planning significant refactors or features on existing codebases
- **Integrations**: mojomast/opencode and mojomast/hermes-agent (install targets), mojomast/cabinet-of-almosts (complementary evidence-driven repo exploration; Cabinet Recombination Briefs feed the same agent-planning workflows)

### mojomast/roguelitussy
- **Description**: Deterministic roguelike foundation for Godot 4.5.2 Mono/.NET with a pure C# simulation core, JSON-driven content, meta-progression, and a custom .NET test harness.
- **Stack**: C#/.NET 8, Godot 4.5.2 Mono, JSON content, custom test runner
- **Capabilities**: pure C# simulation core (entities, actions, combat, abilities, inventory, AI, generation, persistence), Godot-facing presentation layer with layered 0x72 art, character identity/progression with archetype-gated starts, relics and meta-progression, ascension controls, seeded daily challenges, boss phase transitions, faction reputation, gear-driven combat, JSON content for items/enemies/abilities/perks/rooms/dialogs, versioned saves with migration, in-app developer workshop with map export, Windows single-exe launcher packaging, 736-test deterministic suite
- **Uses**: game developers building a deterministic, content-authored roguelike in Godot
- **Integrations**: shares game-development domain with mojomast/voltronussy

### mojomast/roo-code-cloud-alternate-auth
- **Description**: A fork of the Roo Code VS Code extension (autonomous AI coding agent) with an alternate authentication/cloud setup path.
- **Stack**: TypeScript, pnpm/turbo monorepo, VS Code extension, webview UI, 20+ locales
- **Capabilities**: natural-language autonomous coding in the editor, file read/write, terminal commands, browser automation, OpenAI-compatible/custom API integration, Custom Modes, message queueing, custom slash commands, Gemini URL-context/search grounding
- **Uses**: developers wanting a self-hosted/alternate-auth variant of the Roo Code AI coding agent
- **Integrations**: mojomast/opencode and mojomast/kilocode (org's other AI-coding-tool forks); mojomast/ussycodeproxy (proxy for API keys)

### mojomast/rooagussy
- **Description**: Fork of the Roo Code documentation site (Docusaurus) enhanced with a RAG backend, AI chat interface, and Discord bot for querying docs.
- **Stack**: Docusaurus, TypeScript, Node.js RAG backend, Qdrant vector DB, Redis cache, Discord.js bot, Docker Compose
- **Capabilities**: document ingestion with auto-sync into vector DB, RAG Q&A chat UI, Discord !roodocs slash-command bot, API-key-secured backend with rate limiting, Nginx production deployment
- **Uses**: users/communities wanting an AI-queryable documentation site
- **Integrations**: relates to mojomast/roo-code-cloud-alternate-auth, kilocode, roocodehackathon, and ragussy

### mojomast/roocodehackathon
- **Description**: FixMyDocs, a SaaS AI documentation agent (built for the Roo Code Hackathon) that connects to GitHub repos and auto-generates pull requests improving READMEs, docstrings, and inline comments.
- **Stack**: Next.js 14 frontend (Tailwind), Python FastAPI backend, Celery worker, PostgreSQL + SQLAlchemy, Docker Compose; OpenAI/Anthropic/OpenRouter LLMs
- **Capabilities**: GitHub OAuth login, repo connection and documentation analysis, AST-based Python/JS analysis, multi-provider/multi-model selection, automated PR generation with change summaries, job management pipeline with Celery queuing, API key management, XSS/auth middleware, Pytest + Jest suites
- **Uses**: maintainers wanting automated documentation improvement PRs on their repositories
- **Integrations**: operonussy (docs-cluster/trigger domain companion); PGaudussy (both touch PostgreSQL infrastructure, though unrelated functionally)

### mojomast/routetok
- **Description**: Local-first LLM inference router with OpenAI- and Anthropic-compatible APIs, an operations dashboard, and a browser-local "Model Fieldbook" for hands-on model work.
- **Stack**: Node.js 22+, TypeScript (tsx, dependency-light), Dockerfile/compose
- **Capabilities**: multi-provider proxy with health-aware pre-output failover, virtual routes (auto/best/free) and custom cascades, provider-isolated credentials, canonical model IDs, live request telemetry with TTFT/throughput/cost, Fieldbook with Chat/Compare/Room/Evaluate/Images and multi-agent Studio, local Speaches transcription
- **Uses**: developers consolidating LLM providers behind one local endpoint and evaluating models
- **Integrations**: mojomast/nexussy (provider for pipeline stages), mojomast/clanker03 (recorded LLM traffic), mojomast/llmproxy (same domain)

### mojomast/rpg-dm-bot
- **Description**: AI-driven RPG dungeon master bot playable via Discord or browser chat, with a web admin UI for managing campaigns, world state, and game data.
- **Stack**: Python, discord.py, FastAPI/uvicorn, aiosqlite (SQLite), slowapi rate limiting, pytest
- **Capabilities**: Persistent characters/sessions/combat/quests/spells/skills/inventory (SQLite), gold economy with player-to-player transfers, LLM-driven DM narration and NPC dialogue with tool-driven gameplay, browser chat with shared session state and live dashboard panels, web admin tools for campaigns/locations/NPCs/items/spells, content-pack-aware runtime data, dice rolling, session-bound Discord routing
- **Uses**: D&D-style play groups wanting an AI DM on Discord or web, plus operator-managed campaigns
- **Integrations**: ussybot/partymemberbotussy (mojomast Discord bots); voice-rag-devplan-assistant (mojomast LLM tool projects) for narration patterns

### mojomast/scoreboardussy
- **Description**: Real-time web-based scoreboard for improv shows with a separate control panel and audience display, plus Mon-Pacing match-timer interop.
- **Stack**: React, Vite, TypeScript, Tailwind CSS, Shadcn/UI, i18next; Node.js, Express, Socket.IO backend; Docker/K8s/Caddy deployment files
- **Capabilities**: WebSocket real-time score updates, customizable teams/titles/colors/logo, penalty tracking, audience voting with emoji display, server-authoritative match timers (100ms), QR-based Mon-Pacing linking and interop endpoints, English/French i18n, fullscreen responsive display
- **Uses**: improv show hosts, referees, and venues running live scoring and audience interaction
- **Integrations**: mon-pacing (explicit interop endpoints /api/interop/mon-pacing documented throughout)

### mojomast/shoedelussy
- **Description**: strudelussy, a DAW-style fork of Toaster for building Strudel live-coding music projects with a diff-aware AI copilot, served publicly at strudel.ussyco.de.
- **Stack**: React + Vite frontend, Cloudflare Workers + Hono backend, Zustand, pnpm
- **Capabilities**: live Strudel editor/playback with parsed BPM/key/sections, per-track gain/pan mixer editing code live, streaming AI chat with apply/reject diff review, rhythm generator with arrange masks and FX rack, mutate toolbar and tap tempo, KV-backed project persistence and version restore, public share/remix links, guest-mode localStorage projects, DMX demo rig bridge for live lighting
- **Uses**: live coders and music makers producing Strudel patterns with AI assistance
- **Integrations**: forked from mojomast/toaster (upstream base); dmxdemo.ussyco.de demo rig tied to the ussyring webring subdomain

### mojomast/sigintussy
- **Description**: Experimental federated, community-run signals intelligence network — deploy ~$250 sensor nodes (RTL-SDR, LoRa, WiFi, Bluetooth, GPS) and trade observations for collective RF intelligence with no central authority.
- **Stack**: Docker/docker-compose sensor nodes, Raspberry Pi/RTL-SDR/LoRa hardware, Meshtastic-compatible LoRa mesh, Next.js website, REST API/WebSocket streams, LLM analysis at base stations
- **Capabilities**: three-layer architecture (sensor collection, LoRa/internet transport mesh, federated base stations), RF/WiFi/Bluetooth observation collection with GPS timestamping, reciprocal contributor access model, raw-data querying for authorized users, privacy-by-design (device-level, no persistent identification), research-grade access
- **Uses**: RF hobbyists, researchers, and communities doing distributed spectrum awareness
- **Integrations**: standalone network (base stations optionally run LLM analysis, which could draw on hermes-agent/llmproxy-style tooling; no direct repo references)

### mojomast/slophero
- **Description**: ROO GANG — an adults-only narrative survival/ops-management browser game about smuggling a blacklisted genius from Panama to Silicon Valley, with a CRT war-room UI and Ink.js narrative engine.
- **Stack**: TypeScript, Vite, Ink.js, HTML/CSS
- **Capabilities**: Six-stat resource management (Energy, Sanity, Heat, Tokens, Hype, Cred), night-cycle op selection (cover story, tech proof, infra survival, cleanup), BRRR MODE crisis spikes, 7 endings, 25+ random encounters, 4 crew perks with cooldowns, extraction-readiness meter, 3-phase final extraction, mobile-responsive CRT UI, Vercel deploy config
- **Uses**: Players of browser-based narrative strategy games with ops-management mechanics
- **Integrations**: shares Vite/TypeScript web-app domain with agenttrafficcontrol and coderc

### mojomast/sotnrecompguns
- **Description**: Early-prototype C# mod for SymphonyRecomp adding four aimable firearms (pistol, assault rifle, shotgun, machine gun) to Castlevania: Symphony of the Night.
- **Stack**: Source-only C# compiled at runtime by SymphonyRecomp/RecompOne (.NET 10), mod.json config
- **Capabilities**: right-stick aiming with retained direction, R2 fire / R1 reload, fire rates and spread, magazines and reserve ammo, tracers and aim arrow, reusable renamed throwing-weapon items, mod-panel settings (auto-reload, deadzone, spread, ammo refill), hooks for item IDs 0x4B-0x4E and UpdatePlayerEntities
- **Uses**: SOTN players with a legally owned US PSX copy wanting gun gameplay in the recompilation
- **Integrations**: standalone (external upstreams: SymphonyRecomp, RecompOne)

### mojomast/sotnrecompmultiplayer
- **Description**: Experimental SymphonyRecomp mod adding bounded same-room local co-op (managed Player 2 with combat, health/revive, and HUD) to Castlevania: Symphony of the Night.
- **Stack**: C# mod (runtime-compiled by SymphonyRecomp), JSON mod manifest, P2D4 diagnostic schema, Markdown docs
- **Capabilities**: 43-pose managed animation/body map, persistent static-terrain movement with sensors and room-transition reconstruction, equipment-profile-derived melee and projectile combat via native engine collision, managed incoming damage with invulnerability/knockback/downed/revive states, read-only enemy diagnostics with Center Cube awareness, direct-GP0 combat HUD and status pip, virtual/physical Pad 2 input, structured P2D4 diagnostic reports and scenario automation
- **Uses**: Symphony of the Night players/reverse-engineers experimenting with co-op on legally owned US PS copies
- **Integrations**: mojomast/RecompOne and mojomast/SymphonyRecomp (the recompilation runtime and tools the mod targets, per README links)

### mojomast/sotnrecompsave
- **Description**: Experimental SymphonyRecomp mod (no build step; runtime-compiled C# sources) adding an in-memory quicksave/quickload checkpoint for the current room in Symphony of the Night.
- **Stack**: SymphonyRecomp mod (mod.json + source/), runtime Roslyn compilation
- **Capabilities**: F5 save/F9 load in-room checkpoint, restoration of HP/MP/hearts/equipment/inventory/relics/XP/flags/map exploration/RNG/position, guarded safety limits (Alucard-only, grounded, same room/stage), configurable keybinds and mod settings panel
- **Uses**: SotN players using SymphonyRecomp who want room-level retry checkpoints
- **Integrations**: mojomast/SymphonyRecomp and other SymphonyRecomp mods mojomast/sotnrecompguns, mojomast/sotnrecompmultiplayer

### mojomast/stallionussy
- **Description**: Go monolith browser game (STALLIONRUN) — a comedy-first horse breeding, racing, fighting, and genetics trading simulator with an in-world casino, lore codex, and SPA frontend.
- **Stack**: Go 1.25, PostgreSQL (lib/pq) + modernc.org/sqlite, gorilla/websocket, JWT auth, vanilla JS SPA, Docker
- **Capabilities**: Stable registration with starter horses, breeding with genetics/cooldowns, deterministic race engine with replays and betting, quick/custom races with CPU backfill, horse fights with combat/morale mechanics, stud market, Texas Hold'em and five-card draw poker with side pots, 5-reel slot machine with progressive jackpot, daily action progression loop, departed-horse omen ledger, lore codex/help system
- **Uses**: Players of the live Ussyverse horse game (https://horse.ussyco.de)
- **Integrations**: part of the mojomast/ussyverse games catalogue; in-world lore references geoffrussy as platform governance authority

### mojomast/swarmussy
- **Description**: Multi-agent AI development system where an Architect agent orchestrates seven specialized agents (backend, frontend, QA, DevOps, PM, tech writer) to build software projects.
- **Stack**: Python 3.9+, Textual TUI dashboard, Rich legacy dashboard, aiosqlite, Discord integration script
- **Capabilities**: architect-led orchestration with role-based tools, worker agents writing to a shared scratch workspace, live DevPlan dashboard (devplan.md task checklists with owners and blockers), per-agent status reporting, multi-project isolated workspaces, persistent settings, optional message-history resume, Rich/Textual/CLI dashboard modes, Discord bot integration
- **Uses**: Developers wanting an LLM-driven agent team (via Requesty API key) to plan, build, test, and document projects
- **Integrations**: ussyverse/parliamentussy (parliamentary governance for its agents), mojomast/llmproxy (LLM call routing), mojomast/ussyverse-monitor (session monitoring)

### mojomast/tcg2
- **Description**: Web-based two-player trading card game inspired by Magic: The Gathering with real-time multiplayer, deckbuilding, and a full game engine.
- **Stack**: Node.js, TypeScript, Express 5, Socket.IO, better-sqlite3, Knex, React 19, Redux Toolkit, Vite, Jest
- **Capabilities**: turn/phase game loop engine, mana pool resource system, combat with First Strike/Double Strike/Trample, LIFO stack with priority, card keywords (Haste, Flying, Vigilance, Reach), state-based actions, deck builder with auto-generation and validation, room-based multiplayer with state sync, card database
- **Uses**: players and developers building a digital TCG
- **Integrations**: standalone game; devplan workflow kin to devussy

### mojomast/templeossy
- **Description**: Browser-hosted QEMU-on-WebAssembly project that runs a full `qemu-system-x86_64` emulator in the browser and boots Shrine v5.05.1 (a TempleOS-compatible fork) as a live CD, rendering VGA output to a canvas.
- **Stack**: TypeScript, Vite, Emscripten-compiled QEMU Wasm (x86_64-softmmu), xterm-pty, pthreads/SharedArrayBuffer
- **Capabilities**: full x86_64 guest emulation in browser, custom QEMU display bridge (framebuffer export API) with BGRX-to-RGBA canvas rendering, keyboard/mouse forwarding into the guest, start/reboot/fullscreen controls, secondary Linux proof-of-concept boot path, COOP/COEP cross-origin isolation configs (Nginx, Caddy), TypeScript type-check and Vitest suite
- **Uses**: retro-computing enthusiasts and developers experimenting with in-browser OS emulation of TempleOS/Shrine
- **Integrations**: mojomast/rackspace-spot-tool (remote dev-environment tooling), mojomast/verceltest1 (static web deployment tests)

### mojomast/terrariumussy
- **Description**: A Python CLI that renders a codebase as a living ecosystem (modules as organisms, dependencies as food chains) with a weighted 0–1 health score fed by pluggable sibling-tool adapters and Rich dashboards.
- **Stack**: Python, Click, Rich, SVG/text renderers, pytest
- **Capabilities**: ecosystem visualization (legacy renderer and live Rich dashboard), seven-dimension weighted health scoring, eight pluggable data-source adapters with stub fallback, module diagnosis, CI snapshots (text/SVG), seasonal evolution views, metrics export to JSON/CSV
- **Uses**: developers and teams monitoring codebase vitality trends
- **Integrations**: mojomast/fatigueussy, mojomast/endemicussy, mojomast/sentinelussy, ussyverse/kompressiussy, mojomast/churnmap, mojomast/seralussy, ussyverse/proprioceptionussy, mojomast/snapshotussy (all referenced as real adapters)

### mojomast/testt
- **Description**: Trivial test repository containing a single "Hello, World!" Python script.
- **Stack**: Python 3
- **Capabilities**: prints "Hello, World!"
- **Uses**: repository/CI testing only
- **Integrations**: standalone

### mojomast/ticket
- **Description**: Full-stack IT service ticket and appointment management system ("Valitek") for an IT services company in Baie-Comeau, Quebec, with French/English UI and role-based portals.
- **Stack**: Next.js 14.2, TypeScript, PostgreSQL 16, Prisma 5.22, Tailwind, shadcn/ui, Zustand, react-hook-form + Zod, dnd-kit, HMAC-SHA256 cookie auth, Redis/Upstash rate limiting, Docker
- **Capabilities**: customer service requests/quote approval/appointment booking, admin Kanban ticket management with technician assignment, per-technician permission management, weekly appointment calendar, messaging threads, notifications, database backup/restore, runtime branding config, audit logging, i18n FR/EN, M365 email and VoIP.ms SMS integration hooks, Vitest suite
- **Uses**: IT service companies needing customer/admin/technician ticket workflows
- **Integrations**: standalone (shares Next.js 14/shadcn/FR-EN stack with mojomast/ArtistSiteussy)

### mojomast/ticket2
- **Description**: "Valitek v2" — a complete French-first IT ticket management and in-shop repair work order system with three role-based portals, deployed at ticket.ussyco.de.
- **Stack**: Node.js 20, Hono, TypeScript, Prisma 6, PostgreSQL 16, React 18, Vite, Tailwind/shadcn, TanStack Query, Zustand, docker-compose, Caddy
- **Capabilities**: 10-state ticket lifecycle with quotes, blockers, and drag-and-drop Kanban, 12-state work order lifecycle with 6-section intake, condition checklists, parts and warranty tracking, 6-state technician worksheets with labor timers, parts, travel, PDF generation (pdf-lib) and signatures, appointment scheduling with proposal negotiation and day timeline, knowledge base with Markdown, categories, tags, and entity linking, customer notes with pinning, in-app/email (Microsoft 365 Graph)/SMS (VoIP.ms) notifications, file attachments, database backup/restore, audit logging, FR/EN i18n (~1400 keys), admin/technician/customer portals, demo mode with personas
- **Uses**: IT service desks and in-shop device repair businesses
- **Integrations**: standalone

### mojomast/toaster
- **Description**: An AI-powered web app that turns natural-language descriptions into Strudel live-coding music code that plays immediately.
- **Stack**: React + Vite frontend (toaster-ui), Cloudflare Workers backend (toaster-api), pnpm
- **Capabilities**: natural-language-to-Strudel-code generation via LLM, immediate audio playback of generated patterns, local dev server setup, Cloudflare deployment of API, env-configured providers
- **Uses**: musicians and hobbyists creating generative music by describing it in plain English
- **Integrations**: mojomast/llmproxy (LLM API proxying); standalone web stack otherwise

### mojomast/tokenarena
- **Description**: "COCS — Colosseum Of Competitive Slop": a local Three.js first-person arena shooter (plus Puma Circuit kart racing) where parody AI language-model operators fight, with multiplayer game server and live deployment at arena.ussyco.de.
- **Stack**: Three.js, Next.js (vinext), Node.js WebSocket game server, TypeScript, Tailwind/shadcn, nginx + systemd deploy
- **Capabilities**: 9 LM operator personas, 7 agent harnesses, 0-16 bot matches, 35 validated maps across modes, Puma Circuit item racing (8 racers, checkpoints, rubber-banding), online rooms with authoritative snapshots, mobile/remapped controls
- **Uses**: players wanting a humor-filled browser FPS/racer with AI-lore parody bots
- **Integrations**: shares the ussyco.de deployment surface with fireslice (slice.ussyco.de); pairs with scoreboardussy

### mojomast/topussy
- **Description**: btop-style terminal system monitor built with OpenTUI, supporting multi-host remote monitoring and GPU/temperature/battery metrics.
- **Stack**: TypeScript, Bun, OpenTUI, npm bin packaging
- **Capabilities**: live CPU/memory/disk/network/process panels, process filter/tree view (`t`) and signal sending (`k`/`K`), Linux temps + battery and NVIDIA-first GPU stats, remote host mode with host selector, mouse support, help/options/details modals, theme switching, JSON config
- **Uses**: operators and terminal fans wanting a fast, loud system monitor for local and remote hosts
- **Integrations**: nexdev (sibling mojomast Go/terminal operator tooling in the same ecosystem); otherwise standalone

### mojomast/uberclawcontrol
- **Description**: "ClawDeck" — an open-source kanban-style mission-control dashboard for managing AI agents powered by OpenClaw (task boards, assignment, real-time activity feed).
- **Stack**: Ruby 3.3.1 / Rails 8.1, PostgreSQL (Solid Queue/Cache/Cable), Hotwire + Tailwind CSS, GitHub OAuth
- **Capabilities**: multi-board kanban task management, agent task assignment and progress polling, REST API for agent integrations, Hotwire real-time activity feed, self-hosting via Render
- **Uses**: OpenClaw users coordinating agent work asynchronously
- **Integrations**: mojomast/openclawssy, mojomast/openclawremoteussy, mojomast/agentussy (OpenClaw/agent ecosystem), mojomast/nexussy (worker orchestration dashboards)

### mojomast/unconformity
- **Description**: "disconformitussy" — Python git-forensics CLI that finds what's MISSING in repo history (force-pushes, squash merges, deleted branches, rebase rewrites, time gaps) mapped to geological unconformity types.
- **Stack**: Python 3.9+, Click, GitPython, Rich
- **Capabilities**: Five detector types (Angular/force-push, Disconformity/squash merge, Nonconformity/deleted branch, Paraconformity/time gap, Buttress/rebase), scan with type/severity/date/branch filters and JSON output, forensic reports (text/markdown/html/json) with 0–100 risk score, geological-layer terminal timeline, live watch mode with webhook alerts (Slack/Discord), tests on real temp git repos
- **Uses**: Incident response, code audits, compliance history-integrity checks, OSS due diligence
- **Integrations**: devussy, ragussy, openclawssy (explicitly referenced mojomast/ussyverse ecosystem projects); ussyverse-monitor or agent pipelines for auto-auditing repos on push

### mojomast/ussybiot
- **Description**: Discord bot ("BRRR Bot") for managing weekly coding projects, with checklists, idea pool, retros, per-user memory, and AI chat.
- **Stack**: Python, discord.py, aiosqlite, aiohttp, Requesty.ai LLM API, SQLite
- **Capabilities**: slash-command project management (start/status/archive/checklists), idea pool capture, weekly start/retro/summary rhythm, per-user memory system, conversational AI via Requesty, bot-to-bot responses
- **Uses**: Discord communities running weekly build challenges or cohort-based project tracking
- **Integrations**: geoffrussy (Requesty.ai multi-provider overlap, ecosystem sibling per onno notes); standalone otherwise

### mojomast/ussybot
- **Description**: BRRR Bot, the Ussyverse community's AI-powered Discord bot for tracking weekly coding projects, ideas, retros, and memories with LLM tool calling.
- **Stack**: Python 3.10+, discord.py, aiosqlite, aiohttp, PyGithub, Requesty.ai LLM router
- **Capabilities**: project/task/idea management with slash commands, task assignment and per-user task views, project/task notes with history, AI chat with multi-round function calling and tool executor, user memory and persona systems, weekly start/retro/summary flows, GitHub tools (list/read files, create PRs, update files, track PRs), SQLite persistence, bot-to-bot responses
- **Uses**: members of the Ussyverse Discord community shipping weekend projects
- **Integrations**: sibling of mojomast/ussybiot (README references cloning from it); community hub links ussy.host; GitHub tools overlap with ghstatsussy domain

### mojomast/ussycode
- **Description**: Self-hosted dev-environment platform giving instant SSH-accessible Firecracker microVMs with persistent disks, automatic HTTPS, and AI agent support — an open-source exe.dev parity play for the Ussyverse.
- **Stack**: Go single binary (SSH gateway via gliderlabs/ssh, VM manager, Caddy v2 integration, SQLite/modernc, metadata service), Firecracker microVMs, gRPC/mTLS + WireGuard multi-node mesh, TAP/nftables/bridge networking, creack/pty, Ubuntu 24.04 base images, proto definitions
- **Capabilities**: SSH-key-as-identity VM provisioning (`ssh -p 2224 dev.ussyco.de`), wildcard HTTPS URLs per VM via Caddy, public/private/invite-only access control, POST /exec scripting API, BYOK LLM gateway with rate limiting, inbound SMTP + outbound email, trust/quota tiers, admin panel, custom domains, tutorial, arena/community features
- **Uses**: Ussyverse members and builders wanting instant disposable dev environments; host for agent workloads
- **Integrations**: Routussy (Discord-managed OpenAI-compatible proxy referenced in README for SSH auth/billing); openclawssy and hermes-agent (agent runtimes that could target ussycode VMs)

### mojomast/ussycodeproxy
- **Description**: Go webring API and automatic *.ussyco.de subdomain provisioning service writing BIND zone files directly and supporting redirect, reverse-proxy, profile, and CNAME modes.
- **Stack**: Go 1.22+, SQLite (mattn/go-sqlite3), BIND 9 (rndc), nginx, systemd
- **Capabilities**: Member CRUD with automatic DNS zone regeneration and rndc reload, per-member mode capabilities (redirect/proxy/profile/cname) with 403 enforcement, API key minting/revocation with masked listing, admin audit log, DNS record inspection and forced sync, migration from legacy Python webring-api JSON, embeddable webring widget JS, ussyctl admin CLI, backward-compatible webring endpoints
- **Uses**: Operators of the ussyco.de webring hosting member subdomains on their own nameservers
- **Integrations**: standalone (infrastructure service backing ussyco.de member sites)

### mojomast/ussyring
- **Description**: FastAPI webring API and embeddable vanilla-JS widget serving the ussy.host + lesbianguide.de webring with multi-key auth.
- **Stack**: Python, FastAPI, uvicorn, pydantic; JSON flat-file storage (webring.json), nginx reverse proxy config, systemd service unit
- **Capabilities**: public ring and widget.js endpoints, key-authenticated add/update/delete of sites, admin key issuance and revocation, prev/random/next ring navigation widget with light/dark themes, self-hostable single-file API
- **Uses**: ussy.host/lesbianguide.de sites and anyone joining the ring via Discord-issued API key
- **Integrations**: ussycodeproxy (its Go handler implements this API as backward-compatible replacement and links this repo); deployed behind nginx as ussy.host

### mojomast/ussyrouter
- **Description**: "Routussy" — a Discord-managed OpenAI-compatible LLM proxy with budget enforcement, per-model concurrency limits, and billing backend for the ussycode SSH dev environment.
- **Stack**: Bun runtime, TypeScript, discord.js v14, SQLite via Kysely (kysely-bun-sqlite), Docker
- **Capabilities**: transparent OpenAI-compatible proxying (any client), Discord approval workflow for access, user API key creation/revocation (SHA-256 hashed), 3-tier budget enforcement (global/user/key) with HTTP 402, per-model concurrency limits with HTTP 429, usage logging and stats, image/video/OCR/transcription generation commands, SSH-fingerprint-based VM authentication for ussycode, internal authorized-keys API, models.dev pricing cache
- **Uses**: Discord communities sharing managed LLM access; ussycode users getting automatic LLM access in VMs
- **Integrations**: mojomast/ussycode (explicitly documented as its access-control and billing backend)

### mojomast/ussysite2
- **Description**: USSYVERSE portfolio site: a browser-native Three.js 3D constellation of projects with a hidden space combat/trade flight layer launched by typing `ussy`.
- **Stack**: Vanilla JS/Three.js (no build step), optional Node server.mjs for TTS/AI orchestration
- **Capabilities**: 3D project index from projects.js with planet/station nodes, hidden flight layer (combat, weapons, shields/heat, docking, trade, skill tree, missions), project-backed planets and service hubs, optional local server for backend TTS and AI gameplay orchestration
- **Uses**: public showcase of the ussyverse/mojomast project ecosystem with an interactive easter egg
- **Integrations**: directly references mojomast/devussy, mojomast/openclawssy, mojomast/geoffrussy, mojomast/ghstatsussy, mojomast/nexussy, mojomast/ragussy, mojomast/ussycode and many other ecosystem repos via projects.js

### mojomast/ussyverse
- **Description**: The "monorepo" meta-repository documenting the Ussyverse: an index/catalogue of ~84 projects across 11 categories (AI agents, dev tools, code analysis, games, infra, etc.).
- **Stack**: Markdown docs, category folders under `projects/`, scripts
- **Capabilities**: PROJECT_INDEX with per-repo status badges and links, ARCHITECTURE and CONTRIBUTING docs, category organisation of the ecosystem, stats overview (languages, project counts)
- **Uses**: Navigators of the mojomast/ussyverse ecosystem seeking the canonical project list
- **Integrations**: indexes becomussy, devussy, hermes-agent, fatigueussy, reverseoracleussy, stratagitussy, stallionussy, Beatrice, xcancelussybot, warpussy, voltronussy, ussyring, and the other repos in this batch

### mojomast/ussyverse-monitor
- **Description**: Electron desktop application for real-time monitoring of Ussyverse Hub AI agent sessions running on port 3002.
- **Stack**: Electron 28 + Node.js, Server-Sent Events, marked for Markdown rendering, electron-builder packaging
- **Capabilities**: live session updates via SSE with 10-second auto-refresh, color-coded user/assistant/tool messages, font-size control (10-20px), configurable per-message line truncation with expand/collapse, auto-scroll toggle, standalone HTML session export, emergency stop button, direct user-input override box to sessions, always-on-top window, system tray minimize, dark theme
- **Uses**: Operators supervising AI agent sessions on the Ussyverse Hub from an Ubuntu desktop
- **Integrations**: mojomast/ussyverse (the Ussyverse Hub it monitors), mojomast/swarmussy (agent sessions it can watch)

### mojomast/velvetrp
- **Description**: Local-first AI roleplay and campaign RPG app where provider output is untrusted input and the server owns an authoritative, receipt-grounded campaign state.
- **Stack**: TypeScript monorepo (packages/contracts, Fastify server, React client), SQLite, Playwright e2e
- **Capabilities**: character-driven roleplay sessions with streaming and branching, durable campaign-room DM transcript, server-owned campaign timeline/characters/inventory/combat/quests, idempotent command/receipt mechanics, reviewed AI campaign generation with exact content-pack pinning, bounded SQLite recall and NPC observation ledger, AI Director beats with per-candidate receipts, tactical maps, deterministic provider-free fallback
- **Uses**: roleplay groups wanting mechanically trustworthy AI-assisted campaigns
- **Integrations**: routetok probe in e2e (e2e/support/routetok-probe.mjs); LLM provider routing domain kin to llmproxy/routetok

### mojomast/verceltest1
- **Description**: Minimal static HTML page for a "Design Arena" model-comparison site that asks which AI-generated website design for "fohdeesha" the viewer prefers, with a loading preview placeholder.
- **Stack**: Plain HTML (single index.html)
- **Capabilities**: static design-comparison landing page with prompt text and two-sided comparison UI placeholder
- **Uses**: a quick Vercel/static-hosting deployment test of a design-arena comparison page
- **Integrations**: mojomast/rackspace-spot-tool and mojomast/templeossy (web-hosting/deployment experiments)

### mojomast/vesuvius-autoresearch
- **Description**: An evidence-gated research automation harness for the Vesuvius Challenge ink-detection problem, with validation gates, a token-protected reviewer dashboard, autonomous self-improvement ledgers, and synthetic-data smoke tests.
- **Stack**: Python 3.11+, NumPy NPZ data, SQLite experiment ledger, GitHub Actions, mypy
- **Capabilities**: autoresearch planning loop with LOO/full-tile/fixed-threshold gates, hard-negative mining and hallucination controls, synthetic data generator for smoke tests, reviewer dashboard with allowlisted run controls and Agent Chat (Hermes-style provider), proposal/outcome SQLite ledger with lineage, evidence package export, reproducibility docs
- **Uses**: Vesuvius Challenge researchers and prize reviewers needing auditable, gated ML experimentation
- **Integrations**: mojomast/hermes-agent (dashboard Agent Chat provider), mojomast/kportussy (evidence-gated promotion claims)

### mojomast/villa
- **Description**: Monorepo of the Vesuvius Challenge: machine-learning and computer-vision tools for reading the carbonized Herculaneum scrolls (CT-scan access libraries, ink detection, unwrapping pipelines, dataset infrastructure, website).
- **Stack**: Python (vesuvius, ink-detection), C (vesuvius-c, thaumato-anakalyptor), C++/CMake (volume-cartographer), React/Docusaurus (scrollprize.org), CUDA/PyTorch ML, Docker
- **Capabilities**: Python and single-header C libraries for accessing scroll CT scans, Grand-Prize-winning ink-detection model, VC3D semi-automatic surface-tracer segmentation, Thaumato-Anakalyptor papyrus-sheet extraction, crackle-viewer GUI for ink labeling, dataset/cloud infrastructure tooling, competition website source
- **Uses**: Vesuvius Challenge competitors and researchers working with volumetric CT data of ancient scrolls
- **Integrations**: standalone monorepo with internal subprojects (vesuvius, vesuvius-c, volume-cartographer, ink-detection, scrollprize.org)

### mojomast/voice-rag-devplan-assistant
- **Description**: Voice-enabled RAG document Q&A system (FastAPI + Streamlit) with an LLM development-planning assistant, semantic search over plans/projects, and enterprise deployment/monitoring infrastructure.
- **Stack**: Python (FastAPI, LangChain, FAISS, Streamlit), Requesty.ai router (glm-4.5, embedding-001), OpenAI voice APIs, Redis/PostgreSQL, Docker Compose, Terraform/AWS, Playwright, pytest
- **Capabilities**: multi-format document ingestion with OCR, semantic RAG Q&A with citations, TTS/STT voice pipeline, PlanningAgent with structured devplan generation and version history, auto-indexing of plans/projects, semantic search endpoints, multi-layer caching, monitoring/alerting dashboards, threat detection and rate limiting, AWS/Kubernetes deployment
- **Uses**: enterprises wanting voice-driven document Q&A plus AI-assisted development planning
- **Integrations**: mojomast/llmproxy (LLM routing domain), mojomast/repoworkshop (devplan production workflows; could consume its approved decision outputs), mojomast/ragussy (RAG domain)

### mojomast/voltronussy
- **Description**: Collaborative monorepo around a tiny ECS (Entity-Component-System) game engine where contributors build their own games with custom mechanics as patches and share reusable plugins.
- **Stack**: TypeScript (primary; Node 20, pnpm, vitest), Python 3.12 experimental track (optional pygame)
- **Capabilities**: small ECS core (engine-abstractions, engine-core, plugin-host), platform adapters (web canvas, headless null adapter), per-game custom mechanics as patches via components/systems, shared plugins with dependency metadata and engine API versioning, plugin-to-core promotion path with governance, game and plugin templates, CI-tested contributions
- **Uses**: hobbyist game developers collaboratively building games in one repo without gatekeeping
- **Integrations**: shares game-development domain with mojomast/roguelitussy

### mojomast/warp
- **Description**: An experimental fork of the Warp terminal (branded "warpussy") focused on local bring-your-own-key AI provider setup with secure key storage.
- **Stack**: Rust (large workspace, Cargo), Warp OSS codebase, GitHub Actions Windows installer
- **Capabilities**: rebranded OSS builds (app name, URL scheme, config dir), local secure-storage of provider API keys, signed-out BYOK provider use with OpenRouter prioritization, avoidance of Warp-hosted model defaults when BYOK keys exist, model-picker filtering to show only enabled BYOK models, Codex CLI third-party agent detection
- **Uses**: users of the open-source Warp terminal wanting local AI provider keys instead of hosted accounts
- **Integrations**: mojomast/Beatrice (OpenRouter key workflow reuse); mojomast/openwarp (org's other Warp-related repo)

### mojomast/warpussy
- **Description**: AI-enhanced terminal emulator written as a Go learning project — a shell wrapper with inline `#query` AI assistance and tool calling, inspired by Warp.
- **Stack**: Go 1.24, creack/pty, Bubbletea/bubbles/lipgloss, Zalando go-keyring, firmware.ai API
- **Capabilities**: PTY shell wrapper preserving vim/ssh/tmux, streaming inline AI answers, tool calling (web_search, run_command, read_file, list_directory, find_files), OS keyring API-key storage, command extraction from responses
- **Uses**: terminal users wanting AI help inline without leaving their shell; Go learners
- **Integrations**: complements clanker01 (SWARM agents) and mojomast/opencode; powered by firmware.ai

### mojomast/weouthere
- **Description**: "WE OUT HERE" production package — a documentation/index repository for a 6x30-minute dark sitcom about three burned-out technologists running a chaotic AI consultancy, organized for collaborators, partners, press, and operators.
- **Stack**: Markdown documentation package with a static site (site/index.html); directory-numbered production structure
- **Capabilities**: season/character bibles and episode beat sheets, scripts and continuity matrix, partner/investor materials, press kit and festival synopses, casting breakdowns and audition sides, finance/legal/distribution/ops docs, canon lock and missing-items tracking, website strategy
- **Uses**: showrunners, writers, investors, press, casting, and production staff navigating the show package
- **Integrations**: standalone (content/document repository, no code dependencies)

### mojomast/xcancelussybot
- **Description**: Discord bot that detects social-media links (X/Twitter, Instagram, TikTok, etc.) and replies with privacy-friendly alternatives like xcancel.com, plus image macros and a channel RPG game.
- **Stack**: Node.js 16+, discord.js 14
- **Capabilities**: regex detection of 10+ platform URLs, configurable platform mappings and toggles, rate limiting, image macro keyword triggers with admin management, turn-based RPG system with combat/progression, feature-request submission, logging
- **Uses**: Discord communities wanting link-conversion and lightweight channel games
- **Integrations**: standalone

### mojomast/ytkiosk
- **Description**: Fullscreen YouTube kiosk player for hospital patients, elderly-care residents, and care settings, designed to run on old/low-spec Linux hardware that would otherwise be discarded.
- **Stack**: Python 3.11+ with tkinter, embedded mpv (mpv --wid / IPC socket), yt-dlp, hatchling packaging, pytest
- **Capabilities**: Kiosk lockdown (no Alt+F4/Escape/close), keyword-based browsing with persistent topics, random long-form auto-queues (filters >5 min, drops livestreams, keeps longest 20), large elderly-friendly touchscreen controls, EN/FR language toggle, favorites playlist, password-protected options menu, captive-portal detection/auto-accept, X11 embedded mpv with Wayland fullscreen fallback, install script and desktop autostart entry, doctor diagnostic CLI
- **Uses**: Caregivers/nurses provisioning wall-mounted or bedside video entertainment on recycled hardware
- **Integrations**: standalone

### ussyverse/a3viaussy
- **Description**: Local-first Go CLI that guides small-business owners through A3/PDCA problem solving, from measurable problem gap to standard work, stored as JSON.
- **Stack**: Go 1.24 (stdlib only), JSON file storage
- **Capabilities**: guided A3 creation with measurable-gap validation, current-condition observation logging, Five Whys root-cause chains with quality checks, PDCA countermeasure experiments with check dates/decisions, markdown export of one-page A3 records, workspace list/sample/demo commands
- **Uses**: small-business owners and shop managers doing lean continuous improvement without enterprise tooling
- **Integrations**: standalone

### ussyverse/acclimaussy
- **Description**: VS Code extension that turns high-altitude medicine guidance into offline ascent pacing and turnaround cards for trip planning.
- **Stack**: TypeScript, VS Code Extension API, Mocha tests
- **Capabilities**: deterministic rule engine for sleeping-altitude gain and first-night exposure, symptom stoplights with HACE/HAPE red flags, planner webview, sample trip cards, Markdown export, local-only storage via VS Code globalState, printable group scripts
- **Uses**: travelers, group leaders, hikers, ski tourists, and trek planners reasoning about altitude pacing before summit pressure
- **Integrations**: standalone (offline extension; no external service integrations)

### ussyverse/actuaryussy
- **Description**: Python CLI that applies actuarial science (life tables, chain ladder, credibility, IBNR, copulas, moral hazard) to quantify software vulnerability risk.
- **Stack**: Python 3.10+, numpy, scipy, sqlite3
- **Capabilities**: CVE exploit survival tables, vulnerability backlog projection with confidence intervals, internal/external threat-intel credibility blending, latent vulnerability (IBNR) estimation, correlated risk aggregation with VaR/TVaR, security incentive/moral-hazard quantification, JSON output
- **Uses**: Security teams and risk managers allocating resources for vulnerability remediation and cyber-risk quantification
- **Integrations**: standalone

### ussyverse/actuataussy
- **Description**: Offline-first Textual TUI for inhaler technique rehearsal, spacer/dose-counter readiness checks, critical-error pattern review, and caregiver/clinician handoff cards — deliberately non-diagnostic.
- **Stack**: Python, Textual TUI, pytest, JSON ledger storage
- **Capabilities**: technique checklist scoring for pMDI/DPI/soft-mist/nebulizer routes, critical-error pattern analysis, spacer and action-plan readiness checks, handoff card export, safety guardrails, JSON export
- **Uses**: people with asthma/COPD and caregivers rehearsing device technique and preparing clinician/school/travel handoffs
- **Integrations**: standalone

### ussyverse/acumenussy
- **Description**: Applies clinical audiology diagnostics to test suites, producing a "Testigram" and five other instruments that reveal test-suite pathologies coverage tools miss.
- **Stack**: Python 3.10+ (stdlib only), SQLite storage, pytest
- **Capabilities**: testigram audiograms across complexity bands, SRT integration-environment roll-over detection, companogram config-compliance typing (As/Ad/B/C), flakegram self-noise SNR analysis, test-chain conduction latency study, isolation audiometry plateau sweeps, full-diagnostic workup, JSON output
- **Uses**: developers and QA engineers evaluating and improving test suite quality beyond coverage percentages
- **Integrations**: ussyverse/gridironussy, ussyverse/seralussy, ussyverse/dosemateussy (all codebase-health analysis tools sharing the dev-tooling domain)

### ussyverse/adheraussy
- **Description**: Deterministic, rule-based Python CLI that turns substrate, adhesive, load, environment, dwell time, and damage tolerance into a household adhesion risk card (stickers, hooks, tape, cable clips, etc.).
- **Stack**: Python (3.9+), CLI, stdlib-based
- **Capabilities**: assesses built-in fixtures, manual adhesion assessments, JSON/text risk cards, household outcome logging with confidence adjustment, fixture listing
- **Uses**: renters/homeowners deciding what adhesive to use on a given surface without damaging it
- **Integrations**: standalone

### ussyverse/admeussy
- **Description**: Educational VS Code extension that visualizes simplified one-compartment pharmacokinetic (ADME) timing for supplements and workout recovery via SVG concentration-time curves.
- **Stack**: TypeScript, VS Code Extension API, Mocha
- **Capabilities**: Bateman-style oral dosing PK engine (ka, ke, F, Vd, superposition, AUC/peak), preset substances (caffeine, creatine, melatonin, etc.), bedtime carryover and sleep-compatibility scoring, stack overlap visualization, local-only Memento persistence
- **Uses**: Developers/educators learning pharmacokinetic concepts; fitness enthusiasts modeling supplement timing (explicitly not medical advice)
- **Integrations**: standalone (shares the "C/VS Code extension + safety-gated planner" slot pattern with luminaraussy)

### ussyverse/adsorbaussy
- **Description**: Local-first Python CLI that treats household odor as an adsorption-science pathway problem (source, reservoir, airflow, humidity, breakthrough) for structured home odor triage.
- **Stack**: Python (stdlib-only runtime, pytest), CLI console script
- **Capabilities**: odor pathway cards, intervention ladders (source removal -> capture -> media replacement), adsorbent placement plans (carbon/zeolite/baking soda), rebound explanations, masking warnings, safety escalation routing (gas/sewer/smoke/solvent), experiment log save/summary
- **Uses**: Ordinary households triaging persistent or recurring odors without stacking fragrance products; not a gas detector or medical device
- **Integrations**: standalone (household-comfort domain sibling of ussyverse/weberaussy)

### ussyverse/aeronaussy
- **Description**: Python rule engine that turns household indoor-air incidents (burnt toast, wildfire smoke, spray cleaner, etc.) into conservative, explainable air-action cards.
- **Stack**: Python 3.10+, setuptools, pytest
- **Capabilities**: deterministic air-event planning, prioritized action steps, source-control/capture/dilution strategy ranking, runtime estimates, cleanup instructions, escalation boundary detection, 12 built-in regression fixtures, Markdown plan rendering
- **Uses**: households planning responses to low-to-moderate indoor air events; recognizing when to leave or call professionals
- **Integrations**: shares the household-safety decision-card domain with wetbulbaussy (heat), biofilmussy (kitchen hygiene), pressoraussy (pacing)

### ussyverse/aeroussy
- **Description**: Browser app that models your sleep setup as an aerodynamic system (airfoil, drag, boundary layer, wake turbulence) to diagnose neck pain, stuffy breathing, overheating, and snoring, then recommends pillow configurations and position adjustments.
- **Stack**: TypeScript (zero runtime deps), Vite, Vitest
- **Capabilities**: sleep airfoil angle analysis, pressure-drag / numbness mapping, boundary-layer stuffiness and thermal convection detection, Reynolds breathing-labor proxy, wake-turbulence partner disruption scoring, stall-condition detection, pillow configuration recommendations
- **Uses**: individuals troubleshooting sleep comfort, breathing, overheating, or snoring with a local-first web tool
- **Integrations**: standalone

### ussyverse/alembicussy
- **Description**: A terminal puzzle game (curses CLI) where you operate an alchemical fractional distillation column, using real boiling points, azeotropes/entrainers, and reactive distillation across four acts of progressive difficulty.
- **Stack**: Python 3, stdlib only (curses, argparse, dataclasses, JSON)
- **Capabilities**: zone-temperature vapor/liquid physics simulation, azeotrope breaking with entrainers, reactive distillation (in-column reactions), purity/yield/elegance star scoring, save/load, sandbox mode
- **Uses**: CLI gamers and anyone wanting an educational chemistry puzzle; self-learners reviewing distillation fundamentals
- **Integrations**: standalone

### ussyverse/allomaussy
- **Description**: Python GitHub Action and CLI that applies biological allometry ideas to small-business scaling diagnostics, generating an `ALLOMA-REPORT.md` from business metric files (JSON/YAML/CSV).
- **Stack**: Python 3.9+, PyYAML, setuptools, pytest; GitHub Actions composite action
- **Capabilities**: parses business metric snapshots, computes metabolic burn vs revenue capacity, structural support ratio, client surface-area load, vascular/cashflow bottleneck, Kleiber-style allometric revenue capacity, renders Markdown/JSON reports, ships sample data generator
- **Uses**: small-business owners and studios tracking operational health and scaling capacity; CI-style diagnostics on business metrics committed to a repo
- **Integrations**: shares the solopreneur business-operations domain with ussyverse/rotationussy (crop-science business planning); standalone otherwise

### ussyverse/altshulleraussy
- **Description**: Terminal-first TypeScript CLI/library that turns household tradeoffs into TRIZ-style contradiction cards with inventive-principle suggestions and reversible experiment plans.
- **Stack**: TypeScript, Node.js, Vitest
- **Capabilities**: contradiction-pair analysis, inventive-principle suggestion, resource inventory, safety-critical domain flagging, experiment summaries, Markdown/JSON report export
- **Uses**: renters/homeowners and makers working through "improve X without worsening Y" household problems
- **Integrations**: standalone (fits the ussyverse pattern of deterministic local-first domain tools)

### ussyverse/andoniaussy
- **Description**: Go terminal/TUI andon board that adapts Toyota Production System ideas (andon lamps, pull cords, jidoka stop-the-line, containment) to small-business service escalation.
- **Stack**: Go 1.22, stdlib only
- **Capabilities**: colored service-floor lamp board (green/help/blocked/contained/resolved), abnormality pull cards with responder and age timer, stop-the-line flags and containment prompts, weekly improvement candidates from recurring root-cause patterns, staff onboarding card, demo/sample/report/interactive modes, JSON board export and text/JSON reports
- **Uses**: cafes, studios, clinics, repair benches, and side-hustle teams practicing blame-free process escalation
- **Integrations**: shares lean/TPS operations domain with ussyverse/taktussy

### ussyverse/anellaussy
- **Description**: A conservative Nim CLI that screens stuck-ring/finger-swelling episodes for danger signs and produces a clinician/jeweler/fire-rescue handoff card, without ever advising cutting or invasive removal.
- **Stack**: Nim (Nimble), JSON I/O, offline CLI
- **Capabilities**: danger-sign screening (color, cold, numbness, pain, trauma, embedded ring, infection), stop rules for repeated/forceful attempts, ring-material and smart-ring risk flags, Markdown/JSON handoff cards, first-aid boundary guidance, sample episode generation
- **Uses**: households deciding when a stuck ring needs urgent care and what to tell professionals
- **Integrations**: standalone (spec-tournament sibling of other ussyverse safety-first household CLIs like calcaraussy)

### ussyverse/apicolaussy
- **Description**: Vite + React web app that translates honeybee hive dynamics (waggle dance, honey credits, swarm thresholds) into a neighborhood mutual-aid coordinator.
- **Stack**: TypeScript, React, Vite, Vitest
- **Capabilities**: ranks helpers for needs via waggle-dance matching, honey-credit ledger with Gini/inequality and reciprocity health, swarm-threshold collective-action planner, hive-health dashboard
- **Uses**: communities or households coordinating reciprocal neighborhood help and mutual aid
- **Integrations**: standalone

### ussyverse/apoptosisussy
- **Description**: Pure-computation Python library that models home decluttering as cellular apoptosis, scoring possessions and emitting explainable keep/donate/sell/discard recommendations.
- **Stack**: Python 3.9+, pyproject/pip, pytest (stdlib-only runtime)
- **Capabilities**: possession health/apoptotic signal scoring, caspase-cascade recommendations (keep/review/donate/sell/gift/recycle/discard/archive), anoikis/orphan detection for disconnected items, homeostasis clutter metrics, phagocytosis removal-pathway selection, tiny CLI for JSON inventories
- **Uses**: people decluttering a household; minimal local inventory decision support with no cloud/ML dependency
- **Integrations**: speleoussy (complementary home-organization/clutter-ecology analyzer)

### ussyverse/aquariaussy
- **Description**: Rust GitHub Action + CLI that turns home fish-tank logs (water tests, events) into educational aquarium nitrogen-cycle stability reports.
- **Stack**: Rust, GitHub Actions (action.yml)
- **Capabilities**: parses tank profile/test/event CSV or JSON, models ammonia-nitrite-nitrate cycle state, water-change dilution math, biofilter protection warnings, Markdown/JSON report artifacts, fail-on-critical gating
- **Uses**: aquarium hobbyists and households tracking tank cycling; repo-based tank log workflows
- **Integrations**: standalone (part of the ussyverse family of conservative household-safety planners)

### ussyverse/aquiferussy
- **Description**: Python CLI that applies Darcy's Law groundwater-flow physics to model data-pipeline bottlenecks, predicting pressure buildup and cascading failures.
- **Stack**: Python 3.9+, NumPy, argparse, pytest
- **Capabilities**: Darcy flux solving, 2D finite-difference grid simulation, Theis transient drawdown prediction, cone-of-depression cascade modeling, what-if capacity scenarios, ASCII contour maps, CLI sample/analyze/contour/whatif/predict commands
- **Uses**: SREs and data engineers doing capacity planning and predictive degradation analysis on microservice/message-queue pipelines
- **Integrations**: cycloneussy (README contrasts its anomaly/vorticity model with Aquifer's capacity planning); gamutussy, telegraphaussy (data-pipeline fidelity analysis tools in same domain)

### ussyverse/archivioussy
- **Description**: Local-first Python TUI/CLI for preserving family stories, photos, and documents as archival claim cards separated from their supporting evidence.
- **Stack**: Python 3.10+, Textual, Rich, JSON storage
- **Capabilities**: claim cards with source-basis labels, confidence rules, counterclaim clusters, SHA-256 fixity checks for attachments, privacy-aware Markdown/JSON exports, finding-aid TUI dashboard
- **Uses**: family historians and genealogists tracking provenance and confidence of family-history claims offline
- **Integrations**: standalone (shares the conservative local-first card pattern with inferaussy/lensaraussy, but no direct references)

### ussyverse/arroyonaussy
- **Description**: Local Rust/Axum web app that converts manually observed slot-canyon/flash-flood clues into one of four conservative actions (route away, turn around, wait, proceed with caution).
- **Stack**: Rust, Axum 0.7, Tokio, Serde
- **Capabilities**: upstream storm/catchment risk scoring, confinement and escape-terrain decision rules, water-cue hard stops (rising/muddy water, debris, water over road), conservative action cards with group script and disclaimer, JSON API (`/api/analyze`, `/api/sample`), embedded mobile dashboard
- **Uses**: hikers, families, van travelers, and drivers assessing desert washes, slot canyons, and low-water crossings offline
- **Integrations**: standalone

### ussyverse/assayussy
- **Description**: Python CLI that "assays" source code like ore — categorizing functions into elements and grading the ratio of precious domain logic to slag.
- **Stack**: Python (pip/pyproject.toml), pytest
- **Capabilities**: grade report (business logic vs infrastructure percentage), per-function composition breakdown (business/validation/logging/framework/error/slag), alloy detection for mixed-concern functions, crucible map ranking functions by value density, slag report for removable waste
- **Uses**: developers and maintainers assessing code quality and refactoring targets
- **Integrations**: pairs with sentinelussy (learned code-governance anomalies) as complementary code-analysis tools

### ussyverse/auscultussy
- **Description**: Local-first Python CLI that diagnoses recurring meeting health using cardiac-auscultation metaphors (S1/S2 clarity, preload, afterload, murmurs) from facilitator-entered structured observations.
- **Stack**: Python (stdlib), pytest
- **Capabilities**: Meeting observation templates and sampling, deterministic rule-based scoring of meeting closure/context/output/perfusion, murmur and arrhythmia detection, trend analysis across meetings (Markdown/CSV), intervention cards, JSON output, Markdown reports
- **Uses**: Meeting facilitators and team leads diagnosing dysfunctional recurring meetings without recordings or surveillance
- **Integrations**: standalone

### ussyverse/axisussy
- **Description**: Rust web app that models training stress and recovery through simplified endocrine feedback loops (HPA load, allostatic load, hormonal resistance, melatonin cutoff).
- **Stack**: Rust, Axum, Tokio, rusqlite (SQLite), serde
- **Capabilities**: daily log submission (sleep, stress, energy, mood, workouts), HPA load / allostatic load / thyroid / melatonin scores, JSON metrics at /api/status
- **Uses**: athletes or training-curious users tracking recovery heuristics (educational, not medical advice)
- **Integrations**: shares training-analytics domain with thermoussy; otherwise standalone

### ussyverse/beaufortaussy
- **Description**: Offline Go CLI that translates wind forecasts and on-site observations into conservative go/modify/no-go cards for beach, paddling, and swimming activities.
- **Stack**: Go 1.24 (stdlib only)
- **Capabilities**: Beaufort scale conversion, activity/skill-based go/no-go assessment, gust margin and fetch evaluation, offshore/onshore/crosswind direction analysis, printable decision cards, JSON output for scripts, built-in examples
- **Uses**: kayakers, paddleboarders, swimmers, and beachgoers making conservative launch decisions from observed conditions
- **Integrations**: standalone

### ussyverse/benfordaussy
- **Description**: Local-first Go web app for Benford's Law bookkeeping anomaly triage on CSV exports from small businesses and nonprofits.
- **Stack**: Go 1.23+ (stdlib only), HTTP server
- **Capabilities**: CSV upload/paste ingestion, automatic column detection, currency parsing, first-digit Benford analysis (chi-square + MAD scoring), suitability checks, stratified triage by category/vendor/month, review queue with row numbers, printable/markdown audit memo export
- **Uses**: small-business owners, bookkeepers, nonprofit treasurers flagging rows worth human review (typos, duplicates, threshold behavior) without alleging fraud
- **Integrations**: standalone

### ussyverse/bidussy
- **Description**: Python library for auction-theory service pricing that turns historical freelancer quotes into demand curves, reserve-price recommendations, and pricing guidance.
- **Stack**: Python (setuptools, pytest, stdlib-only logic)
- **Capabilities**: Quote/bid data models, empirical acceptance-by-price buckets, monotone logistic demand curve, expected-revenue reserve price optimization, winner's-curse and low-acceptance warnings, channel/segment willingness-to-pay comparison, Markdown/JSON report rendering, demo CLI (`python -m bid`)
- **Uses**: Freelancers and consultants pricing services from their own quote history
- **Integrations**: standalone

### ussyverse/binderyussy
- **Description**: Zig library for personal-library bookbinding conservation triage, turning book inspection data into risk assessments and conservative care decisions.
- **Stack**: Zig 0.14+, static library + demo binary
- **Capabilities**: typed Inspection model (binding, page failure, paper condition, stains, value, skill), deterministic risk scoring, traffic-light RiskBand, TriageCategory (monitor/repair/stabilize/house/quarantine/refer), mold-suspect flag, printable care-card text
- **Uses**: Home collectors deciding on minimal-intervention, reversible book repairs and enclosures; explicitly not professional conservation simulation
- **Integrations**: standalone

### ussyverse/biofilmussy
- **Description**: Rust GitHub Action and CLI that scores kitchen-surface records (moisture, residue, roughness, transfer paths) into a microbial surface ecology report.
- **Stack**: Rust (clap, serde, anyhow), GitHub Actions composite action
- **Capabilities**: surface ecology board classification, reservoir risk ranking (sponge/cloth/drain/gasket), sanitizer contact-time checklist, raw-to-ready transfer path warnings, safety boundary routing, Markdown/JSON report output, built-in sample fixture
- **Uses**: households, roommates, and parents prioritizing kitchen hygiene chores
- **Integrations**: same GitHub-Action report pattern as firelineussy; household-safety domain kin to aeronaussy

### ussyverse/bloomaussy
- **Description**: Local-first Python CLI that diagnoses pantry sweet texture failures (cloudy honey, bloomed chocolate, grainy fudge, etc.) using food crystallization science and outputs a diagnosis card with rescue protocol, prevention plan, and printable label.
- **Stack**: Python (stdlib only, setuptools), pytest
- **Capabilities**: honey/chocolate/syrup/fudge/caramel/preserves/nut-spread diagnosis, sugar-bloom vs fat-bloom distinction, seeding and moisture-ingress detection, conservative discard/safety boundaries, pantry memory log (`add`/`memory`), CSV/JSON export, printable jar labels
- **Uses**: home cooks deciding whether a pantry texture problem is cosmetic, rescuable, or a safety stop
- **Integrations**: standalone (cross-domain sibling of ussyverse household-safety tools like crackwiseussy, effusaussy)

### ussyverse/bloomussy
- **Description**: A Textual TUI that tracks self-learning mastery across Bloom's six cognitive levels (Remember through Create) with evidence-based level advancement and practice-task recommendations.
- **Stack**: Python, Textual (TUI), pytest
- **Capabilities**: six-rung mastery ladder per topic, JSON state persistence, diagnostic scoring and threshold-based advancement, fading scaffolding recommendations, practice task generation, plateau/distribution analytics, non-interactive demo mode
- **Uses**: self-learners tracking study progress; educators building metacognitive tooling
- **Integrations**: standalone (pairs naturally with criterioussy's calibration data for study evidence)

### ussyverse/bolusaussy
- **Description**: Dependency-light C CLI for caregiver IDDSI dysphagia texture-safety handoff that records clinician-prescribed food/drink levels, runs conservative checklists, and prints handoff reports.
- **Stack**: C99, greatest.h test framework, Make
- **Capabilities**: records prescribed IDDSI food (0-7) and drink (0-4) levels, conservative texture/mixed/thin-liquid/substitution checks, red-flag incident gate routing to ROUTE_AWAY, caregiver/SLP handoff report generation, explicit non-diagnosis disclaimers
- **Uses**: caregivers, SLPs, dietitians documenting and handing off existing dysphagia meal plans conservatively
- **Integrations**: standalone

### ussyverse/bonsaiussy
- **Description**: Rust web app that models skill mastery as a bonsai tree with apical dominance, pruning, and ramification mechanics.
- **Stack**: Rust, inline SVG/HTML frontend
- **Capabilities**: skill tree CRUD API, apical-dominance energy suppression, pruning with energy redistribution, ramification sub-skill unlock at threshold
- **Uses**: learners/crafters visualizing which skill to focus on and which weak branches to prune
- **Integrations**: standalone

### ussyverse/boustroussy
- **Description**: Deterministic Rust CLI that plans human room-cleaning coverage routes (boustrophedon lane plans) from a JSON room grid, obstacles, soil zones, and constraints.
- **Stack**: Rust (Cargo)
- **Capabilities**: reads JSON room/obstacle/soil/task/staging model, emits printable route card with boustrophedon lane plan, dead-zone checklist, dry-before-wet sequencing, staging advice, ergonomic scoring, partial time-box plans, ASCII coverage map, machine-readable JSON summary
- **Uses**: households planning efficient cleaning sessions without apps or cloud services
- **Integrations**: standalone (household-planning domain shared with ussyverse/saccadaussy)

### ussyverse/calcaraussy
- **Description**: A Zig terminal/TUI household limescale planner that translates water hardness, deposit appearance, and material limits into safe descaling action cards.
- **Stack**: Zig, terminal/TUI CLI, key-value text input files
- **Capabilities**: hardness banding (ppm CaCO3), limescale vs soap-scum/grease/biofilm differential, scale-likelihood score, acid/no-acid action classes with material safety blocks (stone, plated finishes, cast iron), dwell/rinse reminders, recurrence-based review cadence
- **Uses**: households choosing safe descaling approaches for kettles, faucets, appliances
- **Integrations**: standalone (same tournament-series household-safety family as anellaussy, saponinussy, tangleaussy)

### ussyverse/calderaussy
- **Description**: Zig CLI that models the kitchen as a volcanic system to plan weekly meal prep (pressure buildup, VEI-style prep intensity, leftover "ash" dispersal).
- **Stack**: Zig 0.14+
- **Capabilities**: chamber-pressure estimate from stock/capacity/stress, tremor/fatigue and takeout-collapse warnings, VEI 1-8 meal complexity rating, leftover routing to lunches/freezer/compost
- **Uses**: families planning high-stress week meal prep and leftovers
- **Integrations**: pairs with satiaussy (meal variety/snack satisfaction) and ussyverse compostaussy-style household planning tools

### ussyverse/calibreussy
- **Description**: Python CLI that applies metrological measurement science (uncertainty budgets, Gauge R&R, capability indices) to test suite quality analysis.
- **Stack**: Python 3.9+, numpy, scipy; pip/pyproject
- **Capabilities**: GUM-style uncertainty budgets, ANOVA Gauge R&R variance decomposition, Cp/Cpk process capability, Type A/B flakiness classification, CUSUM drift and zombie-test detection, assertion-to-requirement traceability auditing, seeded demo data
- **Uses**: QA/eng teams quantifying how trustworthy their test suites are and whether flakiness is random or systematic
- **Integrations**: ichniteussy, tarotussy, quantumussy (other ussyverse dev-quality/risk analyzers for a fuller codebase-health picture)

### ussyverse/cambiumussy
- **Description**: Python CLI that applies horticultural grafting science to dependency compatibility, producing a continuous Graft Compatibility Index (GCI) instead of binary semver pass/fail.
- **Stack**: Python 3.10+ (stdlib only)
- **Capabilities**: project dependency scanning, GCI scoring, interface alignment heatmaps, drift/time-to-breakage forecasting, adapter quality modeling, capability throughput analysis
- **Uses**: developers and maintainers assessing dependency health and predicting breakage
- **Integrations**: ussyverse/mintussy (package provenance/grading), ussyverse/queueussy (scheduling-side analogs share the "operations research metaphor" style)

### ussyverse/capillaussy
- **Description**: Rust TUI/CLI that turns houseplant observations (runoff, dryback, skewer feel, wick contact) into capillarity/soil-water-potential based watering decisions with safe next-cycle experiments.
- **Stack**: Rust, ratatui, crossterm, clap 4
- **Capabilities**: Diagnoses 8 hydraulic states (fast-draining, hydrophobic channeling, perched-water risk, etc.), dryback curve estimation, water-path cards, TUI dashboard with non-TTY text fallback, roommate/vacation handoff sheet export, demo scenarios
- **Uses**: Houseplant owners deciding when/how to water container plants, especially wick and self-watering setups
- **Integrations**: standalone

### ussyverse/capstanussy
- **Description**: Local-first Go CLI that translates cable mechanics (bend radius, strain relief, capstan friction, thermal derating) into safer household cord-route cards.
- **Stack**: Go 1.24, stdlib-only CLI
- **Capabilities**: JSON station input model, route-card analysis, hazard scoring, machine-readable JSON output, sample scenario generator
- **Uses**: homeowners, dorm residents, and small-office users planning desk/bedroom/workshop cord routing conservatively
- **Integrations**: standalone

### ussyverse/carboxaussy
- **Description**: Offline Rust TUI that turns a home profile into a conservative carbon-monoxide alarm-coverage and combustion-safety card.
- **Stack**: Rust, Ratatui, Crossterm, Clap, Chrono, Serde
- **Capabilities**: household zone/alarm coverage modeling, alarm age/test/battery warnings, combustion-source and vent red-flag checks, generator/garage hard stops, emergency routing for alarm events, room-by-room alarm placement priorities, JSON report export, non-TTY text fallback for CI/cron
- **Uses**: households, renters, and landlords planning CO alarm placement and safe generator/combustion boundaries
- **Integrations**: standalone

### ussyverse/cartographerussy
- **Description**: Zero-dependency Python CLI that applies map-projection mathematics (Mercator, Tissot, contours) to game level grids to expose spatial-balance flaws before playtesting.
- **Stack**: Python 3.9+ stdlib only
- **Capabilities**: load level CSV grids, Mercator/azimuthal/equal-area difficulty re-projection, Tissot challenge ellipses for directional danger bias, difficulty contour extraction, ASCII/JSON output, spawn-centric fairness audits, Delaunay triangulation of waypoints
- **Uses**: game level designers checking difficulty pacing and encounter coverage
- **Integrations**: standalone (game-design tool; no ecosystem couplings found)

### ussyverse/cartoucheussy
- **Description**: TypeScript GitHub Action and CLI that validates family handwriting transcription packets (epigraphic-style diplomatic text, lacunae, apparatus notes, letterforms) stored as JSON in a repo.
- **Stack**: TypeScript, Node.js, Vitest, GitHub Actions (composite action)
- **Capabilities**: Recursive packet loading, diplomatic/normalized line handling, uncertainty token and lacuna detection, apparatus note validation (evidence required, line/letterform reference checks), same-hand letterform confidence hints, Markdown report generation, CI pass/fail with fail-on-warnings
- **Uses**: Families/archivists transcribing recipe cards, letters, and notebooks who want uncertainty documented and CI-checked
- **Integrations**: standalone

### ussyverse/catenariaussy
- **Description**: Local-first Rust web app for conservative household hanging-load planning (string lights, curtains, clotheslines) using catenary/parabolic sag and tension math.
- **Stack**: Rust, Axum, serde (JSON API)
- **Capabilities**: sag ratio and midpoint clearance estimation, hidden horizontal tension and anchor reaction calculation, anchor/consequence risk screening with green/yellow/red bands, setup checklist and inspection prompts, embedded single-page web UI, /api/analyze and /api/sample endpoints
- **Uses**: homeowners planning lightweight suspended spans without structural certification
- **Integrations**: standalone

### ussyverse/cavityussy
- **Description**: Detects and predicts deadlocks, livelocks, and backpressure oscillations in concurrent data pipelines by modeling topology as an acoustic resonant cavity.
- **Stack**: Python 3.11+, numpy, PyYAML
- **Capabilities**: eigenvalue-based deadlock mode prediction from YAML topology, impedance mismatch/backpressure hotspot analysis, STFT standing-wave (deadlock) detection from time series, beat-frequency livelock detection, damping/Q-factor classification, combined report generation, JSON output
- **Uses**: engineers building or debugging concurrent pipelines with workers, queues, and locks
- **Integrations**: standalone

### ussyverse/celestialussy
- **Description**: TypeScript library for trip planning modeled on celestial navigation, treating destinations as stars and disrupted plans as dead-reckoning problems.
- **Stack**: TypeScript, Vitest
- **Capabilities**: great-circle/rhumb-line distance and bearing, route planning with efficiency-vs-comfort tradeoffs, sextant-style 1-10 experience ratings, personal almanac waypoint scoring, dead-reckoning recovery when a stop is skipped, running-fix plan-vs-actual diagnostics, twilight classification, chart-ready waypoint data
- **Uses**: developers building itinerary/trip-planning apps that need resilient, explainable routing
- **Integrations**: standalone

### ussyverse/ceruminaussy
- **Description**: Python CLI plus composite GitHub Action that converts structured household ear-care JSON notes into conservative earwax action cards with red-flag clinician routing.
- **Stack**: Python (stdlib-only engine), GitHub Actions (action.yml)
- **Capabilities**: Symptom/risk-modifier/action parsing, triage lanes (normal wax, possible impaction, hearing-aid maintenance, clinician lane, urgent red flag, aftercare), Markdown/JSON report generation, `fail-on-urgent` CI gating, sample event generator
- **Uses**: Households journaling ear-care events in a repo; CI pipelines producing safety reports
- **Integrations**: sibling household-health triage tools sialiaussy, palynoussy (same conservative rule-engine + report pattern)

### ussyverse/chainletussy
- **Description**: Pure-Python GitHub Action and CLI that analyzes behavioral chaining data for multi-step procedures and recommends chaining strategies, prompt fading, and errorless-learning guardrails.
- **Stack**: Python (stdlib-only), composite GitHub Action (action.yml), Markdown report output
- **Capabilities**: JSON/CSV procedure and practice-log parsing, weak-link detection, forward/backward/total-task chaining recommendation, prompt hierarchy (full_model -> none), prompt fading after 3 successes / escalation after 2 failures, chain-break scoring, generalization checklist, one-page printable practice card
- **Uses**: Special-education and behavioral-training data analysis run in CI on procedure repositories
- **Integrations**: standalone (CI tooling; could be wired into any ussyverse repo's GitHub workflows)

### ussyverse/chargeguardussy
- **Description**: Rust library for deterministic, conservative lithium-ion battery safety analysis in home charging and storage contexts.
- **Stack**: Rust (clap), demo CLI binary
- **Capabilities**: rechargeable device inventory models, charger compatibility risk, charging-station surface/heat/ventilation/exit-path scoring, condition red-flag detection (swelling, odor, heat), routine vs stop-use/recycle action cards, disposal task planner with recycling routing, travel reminders for spare batteries/power banks
- **Uses**: households managing many Li-ion devices and charging stations safely
- **Integrations**: standalone (household-safety domain kin to wetbulbaussy)

### ussyverse/chloroussy
- **Description**: C CLI that models personal energy management as photosynthesis — tracking light inputs (meals, workouts, sunlight, social, creative), dark recovery (sleep), and transpiration losses (stress) in a plain-text daily log.
- **Stack**: C11, Makefile, greatest.h test framework
- **Capabilities**: daily entry logging (`add`), energy balance = photosynthesis - respiration - transpiration, chlorophyll efficiency score, phototropism goal-alignment score (cosine similarity), light-saturation overtraining alerts, multi-day report tables, flat-file storage at ~/.chloro/data.txt
- **Uses**: individuals quantifying daily energy economy and workout/recovery balance
- **Integrations**: standalone (fitness/wellness domain sibling of ussyverse/zooxussy)

### ussyverse/choreoussy
- **Description**: A Go CLI that analyzes dependency-graph health through dance/choreography metaphors: spatial topology, Laban movement analysis of update dynamics, and contact-improvisation coupling detection.
- **Stack**: Go
- **Capabilities**: depth/centrality/clustering/reach topology scoring, Laban six-factor update-dynamics scoring (weight, time, space, flow, shape, body), Jaccard/intimacy hidden-coupling detection, pas de deux bidirectional-coupling alerts, combined report mode, stdin/JSON input
- **Uses**: maintainers assessing dependency health and hidden coupling in package graphs
- **Integrations**: ussyverse/hitchussy (knot-theoretic cycle analysis), mojomast/churnmap (churn data), mojomast/terrariumussy (health signals)

### ussyverse/chromascriptussy
- **Description**: Rust GitHub Action for color-script mood arcs in visual story planning, analyzing beat-by-beat palette progression from a `chromascript.json` file and producing report/CSV/SVG/JSON artifacts.
- **Stack**: Rust (clap, serde, serde_json, anyhow), GitHub Actions composite action
- **Capabilities**: detects flat arcs, unearned palette jumps, climax-color leakage, overused accents, low focal contrast; emits CHROMASCRIPT-REPORT.md, palette CSV, printable SVG strip, JSON analysis; local CLI and sample generator
- **Uses**: non-developer creators (zine makers, teachers, comic hobbyists, tabletop hosts, photo-essay editors) planning visual tone across story beats
- **Integrations**: pairs naturally with ussyverse/foleyaussy (soundscape/Foley planning) for full audiovisual story pre-production; README references mojomast/chromascriptussy

### ussyverse/chromatoussy
- **Description**: Python CLI that applies liquid-chromatography metaphors to dependency analysis, rendering dependencies as a "chromatogram" of peaks by coupling, risk, and freshness.
- **Stack**: Python, CLI (pip-installable)
- **Capabilities**: chromatogram scan of requirements.txt/package.json/Cargo.toml/go.mod/pom.xml/gemspec, solvent-specific analysis (risk, coupling, freshness, license), differential diff between manifests, co-elution detection, peak-shape health diagnosis, JSON export with CI exit-on-risk
- **Uses**: developers auditing dependency health and risk in CI
- **Integrations**: standalone (complements repos like ussyverse/crystallossy-style manifest analysis; pairs with triageussy for post-failure diagnosis)

### ussyverse/chunkussy
- **Description**: Dependency-light C CLI that turns dense study notes into cognitive chunks, reconstruction prompts, and interleaved review schedules based on working-memory and retrieval-practice research.
- **Stack**: C11, make, Greatest unit tests
- **Capabilities**: sentence splitting, structural classification (definition/causal/list/comparison/general), keyword-overlap cohesion scoring, greedy 3-5 item chunking, ASCII schema tree output, retrieval (reconstruction) prompts, interleaved review ordering, confidence/correctness calibration flagging illusions of competence
- **Uses**: learners converting reread/highlight habits into durable mental models
- **Integrations**: standalone

### ussyverse/churnmapussy
- **Description**: A Python CLI that visualizes git repository churn as territorial maps, clustering files that change together into territories/alliances with borders.
- **Stack**: Python (pyproject), pytest, git log parsing
- **Capabilities**: git history parsing, co-change matrix, hierarchical clustering of files into territories, module/package/file depth levels, ASCII and SVG rendering, date-range and include/exclude filters, alliance highlighting
- **Uses**: developers analyzing code ownership, coupling, and refactoring targets in large codebases
- **Integrations**: mojomast/monorepussy (ships as the `ussy-churn` git churn visualization package); pairs with mojomast/citewiser or ussyverse/endemicussy for deeper code-history analysis

### ussyverse/cicatraussy
- **Description**: Dependency-light C web app/CLI for conservative tracking of minor, non-emergency skin wound healing phases with red-flag escalation.
- **Stack**: C11, Make, embedded HTTP server (greatest.h for tests)
- **Capabilities**: healing-phase estimation (seal/inflammation/fill-cover/remodel), trajectory tracking, care-boundary red-flag detection, maceration/scab-reset pattern cards, clinician-ready export note, local web UI
- **Uses**: individuals monitoring minor cuts/scrapes at home; explicitly not a diagnostic tool
- **Integrations**: standalone (same home-triage family as onychaussy)

### ussyverse/circadiaussy
- **Description**: Python CLI that adapts a dev environment (linter strictness, git operation gating, deploy blocking) to the user's estimated circadian cognitive zone.
- **Stack**: Python, Rich terminal, argparse CLI, pip
- **Capabilities**: green/yellow/red/creative zone estimation via Bayesian model over time-of-day + session duration, session tracking, git hook install/check for risky ops (force-push, deploy, hard-reset), zone-adaptive linter configs, shell prompt zone indicator
- **Uses**: developers who want tooling that blocks risky changes during fatigue-prone late-night/post-l dips
- **Integrations**: topussy (terminal-adjacent operator tooling in the same ecosystem); otherwise standalone

### ussyverse/circleraussy
- **Description**: Local-first Python terminal app (Textual TUI + stdlib menus) for planning small restorative justice circles for household and family repair conversations.
- **Stack**: Python, Textual TUI
- **Capabilities**: safety/consent screening with blocking guidance, circle case setup with roles and talking-piece order, harm/needs/accountability rounds, repair commitment validation, punishment-shaped repair detection, follow-up checklist, Markdown export
- **Uses**: households, roommates, co-parents, and caregivers running structured repair conversations
- **Integrations**: standalone

### ussyverse/citewiseussy
- **Description**: Local-first Go CLI that turns a messy reading backlog into a small, explainable read-next queue using bibliometric role classification and priority scoring.
- **Stack**: Go 1.24, standard library only
- **Capabilities**: Role classifier (foundation/overview/bridge/counterpoint/stale-hype/duplicate/curiosity-leaf), reading priority scorer (centrality, prerequisites, freshness, energy fit), queue planner with time budgets, backlog hygiene analyzer (duplicates, orphans, stale items), JSON/CSV input, JSON + Markdown export, explain command
- **Uses**: Individuals managing large reading/paper backlogs who want deterministic, no-cloud, no-AI triage
- **Integrations**: standalone

### ussyverse/cladwiseussy
- **Description**: VS Code extension that adapts cladistics (trait matrices, sister taxa, homoplasy, parsimony) into a concept-contrast studio for learners who confuse near-neighbor concepts.
- **Stack**: TypeScript, VS Code extension API, webview
- **Capabilities**: trait-matrix building, pairwise concept distances, sister-confusion pair detection, diagnostic-trait ranking, cladogram-like contrast trees, dichotomous-key drills, homoplasy flags, Markdown contrast report export
- **Uses**: students and educators distinguishing easily-confused concepts (e.g., invoice vs receipt, biology pathways)
- **Integrations**: standalone

### ussyverse/clavisussy
- **Description**: Python CLI that applies biological dichotomous keys (plus synoptic keys and type specimens) to bug and vulnerability triage for consistent severity classification.
- **Stack**: Python 3.9+ (stdlib only: sqlite3, argparse, JSON), pytest
- **Capabilities**: interactive binary-question triage to P0-P4 severity with SLA/assignee, built-in bug-triage key plus injection/auth/crypto vulnerability sub-keys with CVSS, key validation (coverage/determinism), synoptic multi-access display, type-specimen registry, misclassification adaptive learning, JSON/markdown key export
- **Uses**: dev teams and triagers wanting reproducible, learnable bug/vulnerability classification
- **Integrations**: shares security-triage domain with stenographussy (its findings feed triage); otherwise standalone

### ussyverse/cloforaussy
- **Description**: Offline Rust terminal UI for thermal-comfort clothing layer planning from weather bands, activity segments, and garment insulation (clo) values.
- **Stack**: Rust, Ratatui, Crossterm
- **Capabilities**: garment inventory model, activity timeline model, apparent-temperature/metabolism/wet-wind heuristics, layer stack cards (wear-now, carry/backup, comfort map, vent triggers), calibration log helpers, rich-text non-TTY fallback, JSON export
- **Uses**: commuters, hikers, and anyone planning what to wear/carry across mixed indoor-outdoor days
- **Integrations**: standalone

### ussyverse/codelineageussy
- **Description**: Python tool that treats code as DNA, applying phylogenetic methods (AST genomic fingerprints, ancestry trees, phylogenetic distance, clade detection) to reconstruct a codebase's evolutionary tree from git history.
- **Stack**: Python, Click, pytest
- **Capabilities**: AST hashing into genetic fingerprints, git-history ancestry tree building, phylogenetic distance via structural similarity and co-evolution, automatic clade detection, HTML/lineage report generation, CLI commands (analyze, tree, report)
- **Uses**: Developers and researchers analyzing codebase evolution, module genealogy, and co-evolved components
- **Integrations**: shares code-structure-analysis domain with morsethussy (topological invariants) and isobarussy (git-history weather mapping)

### ussyverse/commonsaussy
- **Description**: FastAPI web app that turns neighborhood volunteer planning into a transparent threshold public-goods game (cleanup days, mutual-aid restocks, garden watering).
- **Stack**: Python, FastAPI, uvicorn, HTML forms + JSON API
- **Capabilities**: project viability meter, threshold progress by contribution type, bottleneck panel, conditional pledge activation, Gini-style fairness index, next-ask recommendations, repeated-game pledge fulfillment memory, /api/analyze and /api/sample routes
- **Uses**: civic organizers showing "we need three more people" math without shaming nonparticipants
- **Integrations**: shares civic-commons domain with paddockussy; otherwise standalone

### ussyverse/compostaussy
- **Description**: Rust CLI compost stability planner that treats a compost pile as an aerobic microbial reactor and produces local rescue cards from approximate observations.
- **Stack**: Rust (clap 4), assert_cmd/predicates for tests
- **Capabilities**: feedstock C:N and moisture/structure balancing, phase/stability classification (nitrogen overload, anaerobic mat, thermophilic, curing, etc.), odor/pest/safety red-flag detection, rescue plan generation, cure-readiness reports, JSON output
- **Uses**: home composters with kitchen-scrap bins, backyard piles, tumblers, or balcony buckets
- **Integrations**: standalone

### ussyverse/condorcetussy
- **Description**: Python CLI that turns ranked community ballots into pairwise matrices, Condorcet winner checks, and comparisons across plurality, Borda, approval, ranked pairs, and Schulze methods.
- **Stack**: Python 3.10+, CLI
- **Capabilities**: CSV ballot parsing (ranking or rank columns, optional weight/approved), pairwise comparison matrix, Condorcet winner and cycle detection, multi-method comparison reports, quadratic voting helper, JSON/markdown report export
- **Uses**: neighborhood groups, clubs, classrooms, families making fair group decisions
- **Integrations**: standalone

### ussyverse/controlaussy
- **Description**: Dependency-light Nim web app for building printable orienteering-style control cards for safe city discovery walks.
- **Stack**: Nim (stdlib HTTP server), HTML
- **Capabilities**: Control-card model (landmarks, murals, transit anchors), leg safety/difficulty scoring (minutes, distance, ambiguous turns, attack points, handrails, bailouts), child/night/accessible modes, printable HTML report, JSON API (`/api/plan`, `/api/sample`), CLI and `--serve` modes
- **Uses**: Walk organizers and families planning safe, time-boxed urban exploration courses
- **Integrations**: shares the outdoor-route planning domain with watershedussy (hiking) and portolanussy (layovers)

### ussyverse/coreussy
- **Description**: Local Nim web app that reconstructs personal transaction history like a paleoclimate core, layering monthly finances into visual sediment strata.
- **Stack**: Nim 2.0+ (stdlib only), Nimble, built-in HTTP server
- **Capabilities**: CSV paste/upload parsing (date/amount/description/category/account), keyword classification (income/essential/discretionary/savings-debt), monthly sediment aggregation, spending-temperature metric, ice-core HTML visualization (surplus/deficit bands, cash-flow thickness, temperature opacity), rolling z-score transition detection, seasonal cycle summary, bundled demo data
- **Uses**: Individuals analyzing long-term spending regimes and abrupt financial transitions locally in a browser
- **Integrations**: standalone (personal-finance domain siblings: ussyverse/silvaussy, ussyverse/predatorussy)

### ussyverse/coronerussy
- **Description**: Python CLI that applies forensic science principles (Locard's Exchange, blood spatter, ballistics, luminol, chain of custody) to diagnose CI/CD pipeline failures with confidence scores.
- **Stack**: Python 3.10+, numpy, SQLite, argparse
- **Capabilities**: trace evidence analysis across pipeline stages, error origin backtracking, cross-build error signature matching, stale cache/undeclared env detection, hash-chain artifact provenance, bidirectional contamination analysis, rich terminal autopsy reports
- **Uses**: developers and CI maintainers root-causing failing builds
- **Integrations**: standalone; complements any CI workflow (GitHub Actions domain kin to biofilmussy/firelineussy actions)

### ussyverse/crackwiseussy
- **Description**: Go library for conservative household repair-or-replace decisions, translating fracture mechanics (crack growth, stress concentration, fatigue, adhesive geometry) into readable damage decision cards.
- **Stack**: Go (stdlib)
- **Capabilities**: `Analyze(Case)` decision cards (cosmetic/monitor/repair/replace/professional), crack-growth and sudden-failure scoring, adhesive repair confidence (shear vs peel), consequence gates for food contact, hot liquid, children, load-bearing use, Markdown card export, prohibited/downgraded use lists with monitoring intervals
- **Uses**: households deciding whether to repair, down-grade, or retire damaged mugs, furniture, toys, and other objects safely
- **Integrations**: standalone (safety-decision sibling of bloomaussy, effusaussy, sumpaussy)

### ussyverse/criterioussy
- **Description**: A local VS Code extension for signal-detection learning calibration, tracking hits/false alarms/misses/correct rejections and confidence reliability to expose false fluency.
- **Stack**: TypeScript, VS Code extension API, Mocha; domain core designed to be portable to Zig/WASM
- **Capabilities**: Markdown/CSV prompt import, calibration probes from command palette, Memento local persistence, webview dashboard with signal-detection matrix, prompt-quality warnings (recognition-heavy, leading wording), Markdown report export
- **Uses**: learners and students calibrating metacognition; study-tool builders
- **Integrations**: ussyverse/bloomussy (shared learning-evidence domain)

### ussyverse/criticaussy
- **Description**: Deterministic Rust library turning a household meal plan into a compact HACCP-style `SafetyCard` with process flow, hazards, critical control points, limits, monitoring, and corrective actions.
- **Stack**: Rust (library crate), serde JSON serialization
- **Capabilities**: builds meal-specific process flows (storage, prep, cook, hold, serve, cool, reheat), identifies biological/allergen/physical hazards, selects 3-6 household CCPs with critical limits, generates conservative corrective actions and post-meal verification prompts, JSON export, smoke binary
- **Uses**: home cooks and household meal planners, especially meals for vulnerable eaters (older adults, allergies, leftovers, potluck transport)
- **Integrations**: standalone

### ussyverse/cryoraussy
- **Description**: Stdlib-only Zig web app for household leftover freezing/thawing triage based on practical cryobiology heuristics.
- **Stack**: Zig 0.14+, embedded HTML/CSS/JS UI, stdlib TCP/HTTP server
- **Capabilities**: freezeability/texture-damage forecast, safety-vs-quality discard/refreeze triage, thaw-route recommendation (fridge/cold water/microwave/cook-from-frozen/discard), container and portion advice, JSON analyze/defaults/sample endpoints
- **Uses**: home cooks deciding how to freeze, package, and thaw leftovers safely
- **Integrations**: standalone (same local-first deterministic household-tool pattern as electraussy and honeussy)

### ussyverse/crystallossy
- **Description**: Python static-analysis tool that applies crystallographic symmetry group theory to Python code structure, classifying rotational/reflection/translational/glide/broken symmetry between modules.
- **Stack**: Python 3.10+, stdlib only (AST, argparse)
- **Capabilities**: AST parsing into structural fingerprints, pairwise similarity (cosine + Jaccard) with symmetry-type classification, space-group assignment (P1 triclinic to Pa3 cubic), unit-cell repeating-pattern detection, broken-symmetry and accidental-duplication defect detection, CLI commands scan/symmetry/defects/classify/unit-cell
- **Uses**: developers and architects inspecting duplication, mirror modules, and structural drift in Python codebases
- **Integrations**: shares code-structure-analysis domain with mojomast/churnmap

### ussyverse/curatorussy
- **Description**: A Python CLI applying library-science/museology principles (cataloging, classification, conservation, provenance, weeding) to software documentation health.
- **Stack**: Python 3.10+, stdlib only (sqlite3, argparse), pytest
- **Capabilities**: MARC-style metadata cataloging with completeness scoring, faceted DDC/LCC-inspired classification, conservation/freshness reports with decay curves, provenance tracking with accession numbers, audience-targeted exhibition surfacing, MUSTIE-based weeding/deaccession proposals, SQLite persistence, full audit with JSON output
- **Uses**: documentation maintainers curating large doc collections
- **Integrations**: mojomast/monorepussy (ships as `ussy-curator` and complements `ussy-operon` documentation-health packages)

### ussyverse/currentussy
- **Description**: Python CLI that maps physical oceanography (thermohaline circulation, Ekman drift, gyres) onto travel energy patterns and post-trip mood persistence.
- **Stack**: Python 3.10+, SQLite, setuptools
- **Capabilities**: travel "water mass" temperament profile, halocline/thermocline disruption scoring, daily energy current forecast, gyre warnings from trip history, residence-time mood estimate
- **Uses**: travelers forecasting when trips will flow or fight them and how recovery will go
- **Integrations**: standalone

### ussyverse/cuticulaussy
- **Description**: Local-first Python TUI/CLI that analyzes hair by zones (scalp/roots, mids, ends) for porosity, conditioning, buildup, and detangling risk, outputting transparent strand-state cards.
- **Stack**: Python 3.10+, Rich, Textual (dev), pytest
- **Capabilities**: multi-zone hair profiles, porosity inference from multiple observations, state flags (buildup, mineral coating, protein stiffness, hygral fatigue, detangling risk), scalp-vs-shaft wash plans, detangling plans with stop rules, one-variable experiment recommendations, JSON/text/TUI output
- **Uses**: households doing practical hair care (oily roots/dry ends, bleached lengths, hard water, child detangling)
- **Integrations**: standalone (household-care domain shared with framoraussy/turnwiseussy but no code-level links)

### ussyverse/cutsetussy
- **Description**: Python library for qualitative fault-tree analysis of everyday household departure failures (missed bus, forgotten medication) using minimal cut sets and barrier planning.
- **Stack**: Python
- **Capabilities**: AND/OR/CONDITION fault-tree gates, minimal cut-set expansion and ranking, common-cause detection, barrier experiment cards, caregiver handoff sheet export to Markdown
- **Uses**: caregivers reasoning about household failure paths and low-cost safeguards
- **Integrations**: standalone

### ussyverse/cyclaraussy
- **Description**: Python terminal dashboard for small-business cash conversion cycle (CCC) and working-capital timing analysis, entirely local with no bank connections.
- **Stack**: Python 3.10+, stdlib only, pytest
- **Capabilities**: Computes DIO/DSO/DPO/operating cycle/CCC, owner-funded days and max cash deficit estimates, per-offering cash-gap cards, season heatmap, top cash-trap detection, scenario comparisons (deposits, faster invoicing, smaller batches, supplier terms), privacy-safe JSON export
- **Uses**: Small-business owners and bookkeepers doing educational management-accounting diagnostics
- **Integrations**: standalone

### ussyverse/cycloneussy
- **Description**: Python CLI that applies meteorological vorticity/CISK analysis to detect self-reinforcing retry and reprocessing loops in data pipelines before they become incidents.
- **Stack**: Python 3.9+, pure stdlib
- **Capabilities**: pipeline topology survey, velocity-field computation, cyclone detection with Saffir-Simpson severity classification, CISK cycle-gain analysis, stage-divergence reporting
- **Uses**: data/platform engineers monitoring streaming or batch pipelines for retry-storm feedback loops
- **Integrations**: standalone (conceptual sibling of photosynthussy's metaphor-driven performance profiling)

### ussyverse/decibellaussy
- **Description**: Local-first VS Code extension whose Python core computes a conservative daily noise-dose budget for planned noisy activities.
- **Stack**: TypeScript (VS Code extension API), Python 3.10+ (audiology model), Mocha/pytest
- **Capabilities**: webview planner for activity level/duration/protection, 85 dBA/8h anchor with 3 dB exchange-rate dose math, hearing-protector derating by type/NRR/fit/worn fraction, additive same-day dose, impulse-noise and symptom boundary overrides, sample JSON report generation
- **Uses**: concert-goers, gym users, DIYers, and anyone planning hearing protection day-to-day
- **Integrations**: standalone

### ussyverse/dendroussy
- **Description**: Stdlib-first Python CLI journaling system that treats a life journal like a tree cross-section, with each year as a growth ring influenced by entries and events.
- **Stack**: Python (pyproject.toml, console script `dendro`), pytest
- **Capabilities**: local JSON storage, add/import entries via CSV, keyword classification (earlywood/latewood, intensity 1-5, frost/false-ring/pointer events), ASCII ring visualization, cross-dating evidence matching, timeline/report/export commands
- **Uses**: personal journalers wanting reflective, longitudinal visualization of their life record
- **Integrations**: standalone (shares local-first journaling domain with glacierussy)

### ussyverse/dermaussy
- **Description**: Rust GitHub Action and CLI that lints skincare routine files (JSON/CSV/TXT/MD) and generates an educational Markdown report with barrier-stress, ingredient-conflict, and SPF-adherence scoring.
- **Stack**: Rust, GitHub Actions (composite action)
- **Capabilities**: TEWL-style barrier risk scoring, ingredient conflict checks (retinoid+AHA/BHA, benzoyl peroxide+retinoid, fragrance warnings), photoaging/SPF adherence scoring, routine cadence recommendations, directory merge mode, JSON output, CI fail-on high-risk
- **Uses**: Individuals tracking skincare routines who want heuristic conflict and habit linting (educational, not medical)
- **Integrations**: standalone (same "health-lint GitHub Action" pattern as cartoucheussy)

### ussyverse/diopterussy
- **Description**: Python CLI that helps freelancers analyze focus, capacity, pricing, and service pruning through optical lens metaphors.
- **Stack**: Python (pyproject packaging), CSV input, pytest
- **Capabilities**: depth-of-field scoring of services, aperture/capacity analysis, bokeh deprioritization recommendations, chromatic aberration misalignment warnings, text/JSON/Markdown prescription reports, single-service scoring
- **Uses**: freelancers and small-business owners deciding what to reprice, prune, or focus on
- **Integrations**: standalone

### ussyverse/dosemateussy
- **Description**: Models code change propagation through a software system using pharmacokinetic ADME math (absorption, distribution, metabolism, excretion).
- **Stack**: Python 3.8+ (stdlib only), pytest
- **Capabilities**: ADME parameter analysis from git history (merge rate ka, reach Vd, half-life t1/2, bioavailability F), drug-drug interaction detection between concurrent PRs, Michaelis-Menten CI throughput saturation analysis, steady-state change pressure computation, two-compartment deep-dependency decay modeling, JSON reports
- **Uses**: engineering leads and DevOps analysts quantifying change velocity, CI saturation, and PR interference
- **Integrations**: ussyverse/gridironussy (dependency graph analysis), ussyverse/seralussy (git-metric codebase classification)

### ussyverse/driftlineussy
- **Description**: Terminal roguelike where you manage a phylogenetic tree of species diverging across a procedural volcanic archipelago, grounded in island biogeography theory.
- **Stack**: Python 3.10+, terminal/CLI
- **Capabilities**: procedural 5-8 island archipelagos, species branching on colonization, six-trait evolution system, MacArthur-Wilson equilibrium and Lotka-Volterra population dynamics, convergence detection bonuses, ecological events (eruptions, invasives, plagues), mass-extinction endgame scoring, seeded runs and save/load
- **Uses**: players and educators interested in evolution/ecology-themed strategy games
- **Integrations**: standalone

### ussyverse/driftnetussy
- **Description**: Spec-only repo (PROMPT.md + SPEC.md, no implementation) for DriftNet, a planned Python CLI for semantic drift detection in API contracts using embeddings.
- **Stack**: Spec documents (target stack: Python, click, sentence-transformers all-MiniLM-L6-v2, SQLite)
- **Capabilities**: (Planned) AST-based API element extraction, embedding timeline with EMA centroid drift detection, TF-IDF drift narratives, contract anchoring, cross-service drift comparison, CI mode
- **Uses**: Would-be builders of contract-drift tooling
- **Integrations**: designed to complement fatigueussy (code decay) and reverseoracleussy (decision analysis) as code-analysis dev tools

### ussyverse/dualiaussy
- **Description**: Local-first VS Code extension that redesigns study notes using dual-coding theory and multimedia-learning principles, producing deterministic Dual-Channel Study Cards.
- **Stack**: TypeScript, VS Code extension API, webview
- **Capabilities**: selection/document analysis, visual vs verbal channel recommendations, integration and remove/rewrite actions, retrieval prompts, numeric score, principle flags (spatial contiguity, coherence, signaling, redundancy, modality, segmenting, pre-training, retrieval practice, cognitive load), sample material creation, Markdown report export, accessibility-preserving rules
- **Uses**: Students and educators restructuring notes for better multimedia learning; explicitly not an AI slide generator
- **Integrations**: sibling VS Code extensions in the ecosystem (ussyverse/mustiaussy, ussyverse/silvaussy)

### ussyverse/ebbinghausussy
- **Description**: Personal forgetting-curve tracker and spaced review scheduler that fits power-law decay models per item instead of using fixed SM-2 algorithms.
- **Stack**: Python 3.9+, SQLite, argparse CLI
- **Capabilities**: personal forgetting curve fitting (R = (1+t/S)^-b), optimal review scheduling, fast/slow forgetter classification, cramming detection, overlearning advice, textual curve visualization, per-item status
- **Uses**: students and self-learners scheduling spaced repetition
- **Integrations**: standalone

### ussyverse/effusaussy
- **Description**: Local-first VS Code extension that plans hot-drink/hot-food container comfort using coarse thermal-effusivity heuristics, producing temperature-window cards for hand comfort and sip readiness.
- **Stack**: TypeScript, VS Code extension API (webview, globalState), Mocha
- **Capabilities**: planner webview with comparison/timeline cards, 12 built-in scenarios (commute coffee, child cocoa, thermos soup, etc.), wait-range / too-hot / pleasant-window / too-cool estimates, lid/sleeve/insulation/preheat modeling, outcome logging with local calibration delta, Markdown sample-plan export
- **Uses**: commuters, caregivers, hosts, and desk workers planning safe comfortable hot-drink/food timing
- **Integrations**: ussyverse/transactaussy (same TS+VS Code extension slot and webview architecture)

### ussyverse/egressaussy
- **Description**: A local-first FastAPI web app that plans calm event exits by scoring gate/bottleneck risk, recommending departure waves, and producing printable offline exit cards for groups.
- **Stack**: Python, FastAPI, Jinja2, pytest/httpx
- **Capabilities**: bottleneck risk scoring (gates, stairs, turnstiles, queues), departure-wave recommendations, safe eddy/meeting-point scoring with rejection of spillback zones, buddy-pair and lost-link protocols, printable event exit card, JSON API
- **Uses**: families, school/scout groups, mobility-aid and sensory-sensitive attendees planning conservative event departures
- **Integrations**: standalone

### ussyverse/elastaussy
- **Description**: C command-line seal-health triage tool for household elastomers (fridge gaskets, O-rings, hoses, weatherstrips) that classifies failures and recommends clean/re-seat, monitor, replace, or stop-use actions.
- **Stack**: C, greatest.h tests, Make
- **Capabilities**: deterministic rule engine classifying compression set, swelling/compatibility, embrittlement, contamination, seating error, abrasion, or high-risk unknown; fixture-based analysis; human-readable cards and JSON output; conservative safety boundaries routing high-risk parts away
- **Uses**: ordinary households doing preventive leak detection and deciding when to replace flexible seals
- **Integrations**: standalone

### ussyverse/electraussy
- **Description**: Local-first C web app that diagnoses household dust problems (static cling, resuspension, redeposition) via electrostatics heuristics and recommends cleaning protocols.
- **Stack**: C11, POSIX sockets, embedded HTML/CSS/JS, greatest.h tests
- **Capabilities**: static/triboelectric scoring, particle adhesion/resuspension/airflow-deposition scoring, cloth-overload detection, greasy-dust binding, material/electronics safety warnings, printable diagnosis card, JSON API, CLI smoke mode
- **Uses**: household cleaners dealing with recurring dust, lint, pet hair, or electronics-safe cleaning
- **Integrations**: standalone (sibling household domain tools: cryoraussy, honeussy)

### ussyverse/enamelaussy
- **Description**: Local-first Python Textual/Rich TUI and CLI that models a day as enamel challenge/recovery windows for oral-care routine timing.
- **Stack**: Python 3.10+, Textual, Rich, pytest
- **Capabilities**: event models for meals/snacks/drinks/brush/floss/fluoride/rinse/gum/dry-mouth/bedtime/wake/reflux/orthodontic/safety, deterministic challenge/recovery engine (acid windows, grazing/sipping resets, salivary recovery buffers, dry-mouth multiplier, fluoride preservation, bedtime vulnerability, brush-too-soon cautions), safety-flag overrides, TUI dashboard with timeline and heatmap, CLI demo/add/analyze/report, JSON local storage
- **Uses**: individuals planning tooth-friendly daily routines (educational, explicitly non-diagnostic)
- **Integrations**: shares oral-health domain with ussyverse/occlusaussy

### ussyverse/endemicussy
- **Description**: A Python CLI that models the spread of code patterns/anti-patterns through a repository using SIR/SEIR epidemiology (R0, superspreaders, herd immunity).
- **Stack**: Python, stdlib only (ast, re, subprocess git), pytest
- **Capabilities**: pattern scanning with 11 built-in patterns (bare except, god-class, print-debugging, etc.), R0 estimation from git-transmission trees, discrete-time SIR simulation with intervention comparison, herd-immunity threshold and refactoring strategy, superspreader identification, cross-architecture "zoonotic jump" detection, best-practice promotion analysis
- **Uses**: engineering teams tracking anti-pattern propagation and planning refactors
- **Integrations**: mojomast/monorepussy (ships as `ussy-endemic`); pairs with ussyverse/churnmapussy (co-change mapping) for codebase-evolution analysis

### ussyverse/entrainussy
- **Description**: Terminal puzzle game teaching real chronobiology via Phase Response Curve mechanics — sync circadian oscillators with timed zeitgebers.
- **Stack**: Python 3.10+, zero dependencies
- **Capabilities**: interactive and scripted levels (jet lag, shift work, DST), PRC-based advance/delay responses, sandbox free-play, scoring, JSON output, saved progress
- **Uses**: educators/students or curious people learning circadian rhythm science
- **Integrations**: standalone

### ussyverse/epigeneticussy
- **Description**: Rust web app that reframes habit tracking as gene regulation, modeling practice as expression and missed days as reversible methylation marks instead of broken streaks.
- **Stack**: Rust, axum, tokio, serde (Cargo)
- **Capabilities**: 14-day expression-rate calculation, exponential methylation decay, trigger correlation classification (activating/silencing/context), differentiation score for automatic vs deliberate execution, chromatin-remodeling life-change alerts, JSON analysis API and interactive dashboard
- **Uses**: individuals wanting a psychologically kinder, science-metaphor habit tracker
- **Integrations**: standalone

### ussyverse/epistaxaussy
- **Description**: Offline Rust TUI/CLI for conservative nosebleed (epistaxis) first-aid sequencing, from danger screening to compression timing and clinician handoff.
- **Stack**: Rust, ratatui/crossterm TUI
- **Capabilities**: danger/route-away gate, 10-15 min no-peek compression interval planner, risk-factor and medication modifier scoring, clinician handoff card, aftercare safety-net reminders, headless deterministic text output
- **Uses**: household members, caregivers, coaches, school staff, travelers responding to nosebleeds
- **Integrations**: standalone

### ussyverse/equilibriaussy
- **Description**: Rust CLI applying game-theory mechanisms (sealed-bid fair division, envy/Pareto diagnostics, Nash-style bargaining) to family chores and shared-resource negotiation.
- **Stack**: Rust, clap 4
- **Capabilities**: Sealed-bid chore/resource division, fairness scores, envy and Pareto diagnostics over allocations, max-min compromise recommendation with Nash product tie-break, repeated-game fairness ledger with imbalance flags, built-in demo, CSV input
- **Uses**: Households fairly dividing chores, resources, and recurring choices with explainable rules
- **Integrations**: quorumussy (also a family/small-group decision tool, complementary voting vs. division mechanisms)

### ussyverse/escutcheonussy
- **Description**: Terminal heraldry puzzle game where you compose coats of arms on an ASCII shield grid for noble clients, validated by a deterministic heraldic rule engine.
- **Stack**: Python 3.10+, ANSI terminal rendering, JSON level files
- **Capabilities**: campaign levels with unlockable progress, sandbox free-design mode, tincture/charge palette, heraldic-law validation engine, save/reset progress, CLI commands
- **Uses**: terminal gamers and puzzle players interested in heraldry
- **Integrations**: standalone (game sibling of tellussy in the ussyverse game collection)

### ussyverse/ethonussy
- **Description**: Nim CLI (also a GitHub Action) that analyzes CI/CD workflow logs through ethology concepts like Fixed Action Patterns, sign stimuli, displacement activities, and imprinting.
- **Stack**: Nim 2.0, GitHub Action (composite, action.yml)
- **Capabilities**: repeated command-sequence (FAP) detection in logs, minimal predictive-context recognition from JSON events, displacement-activity flagging (e.g. repeated `ls`/`git status`), imprint profiling of successful setup sequences as onboarding templates, JSON output to step summary
- **Uses**: teams diagnosing developer friction and onboarding pain in CI workflows
- **Integrations**: pairs naturally with levainussy (test-suite health) in a CI-quality toolchain; otherwise standalone

### ussyverse/ethylenoussy
- **Description**: Dependency-light C terminal/TUI produce ripening planner that models a kitchen as a postharvest biology system (ethylene producers/sensitive neighbors, ripeness stages, storage zones).
- **Stack**: C11, ANSI terminal tables, Make, greatest test framework
- **Capabilities**: CSV inventory analysis (10-item built-in demo), ethylene interaction warnings, ripeness/use-window staging, humidity/chilling-injury/mold/bruise flags, interactive paste mode, printable storage and meal-timing recommendations
- **Uses**: home cooks planning produce storage and meal timing to reduce waste
- **Integrations**: standalone

### ussyverse/eutrophaussy
- **Description**: Local-first Python CLI that models digital backlogs (newsletters, read-later queues, inboxes) as eutrophic ponds with nutrient inflow, carrying capacity, bloom and hypoxia risk, and restoration plans.
- **Stack**: Python (stdlib), pytest
- **Capabilities**: Pond/backlog modeling from manual JSON counts, nutrient-load and residence-time computation, bloom and dead-zone risk scoring, source tracing with controls (unsubscribe, cap, quarantine, expire), restoration plan generation, Markdown/JSON reports, sample generation
- **Uses**: Individuals doing personal digital-hygiene triage of overflowing feeds and backlogs
- **Integrations**: shares limnology/ecology-analogy domain with limnoussy (lake-modeled emotional wellness)

### ussyverse/exemplaussy
- **Description**: Local-first browser app that plans study sessions using worked-example fading, completion problems, and cognitive-load/expertise-reversal checks.
- **Stack**: TypeScript, Vite, vitest, localStorage
- **Capabilities**: novice-to-transfer-ready learner classification, fading rung prescription with step reveal/masking counts, under-guidance/overload/illusion-of-understanding flags, teacher-friendly card generation, JSON/Markdown export, fixture demos
- **Uses**: students, teachers, and parents tuning guidance levels during practice
- **Integrations**: standalone

### ussyverse/extinguaussy
- **Description**: Local-first VS Code extension that turns fire-extinguisher class matching, placement, maintenance, and PASS rehearsal into conservative household readiness cards.
- **Stack**: TypeScript, VS Code extension API (Memento state), Node test runner
- **Capabilities**: extinguisher class matching for fire types, placement checks (blocked access, hazard-side retrieval), maintenance checks (gauge, inspection date, pin/seal), gated PASS rehearsal card, route-away boundary rules, printable Markdown guest card, webview readiness board
- **Uses**: households, short-term rental hosts, and workshops auditing extinguisher readiness
- **Integrations**: standalone

### ussyverse/fascinaussy
- **Description**: Nim-powered GitHub Action and CLI that analyzes repo-based microbreak logs (`.fascina/` JSON/CSV) through Attention Restoration Theory to report on directed-attention fatigue and soft-fascination recovery.
- **Stack**: Nim 2.0+, GitHub Action (action.yml)
- **Capabilities**: fatigue/restoration balance scoring, soft-fascination anchor quality scoring, microbreak timing and recovery-rhythm estimation, over-control/generic-mindfulness mismatch warnings, Markdown report generation, multi-file JSON/CSV aggregation with field aliases
- **Uses**: teams or individuals tracking restorative microbreak quality from local logs in CI
- **Integrations**: standalone

### ussyverse/fatigueussy
- **Description**: Python CLI that applies fracture mechanics (Paris' Law of fatigue crack growth) to detect code "cracks" and predict per-module tech-debt decay over commits.
- **Stack**: Python stdlib only (ast, subprocess, argparse), pytest
- **Capabilities**: Crack scanning (TODO/HACK, complexity, missing error handling, god classes, circular deps), stress-intensity K = coupling x churn x complexity / coverage, Paris' Law calibration via log-linear regression, decay trajectory and time-to-failure prediction, what-if intervention simulation with ROI, structural health monitoring
- **Uses**: Engineering teams prioritizing refactoring and measuring debt growth risk
- **Integrations**: pairs with driftnetussy (semantic contract drift) and stratagitussy (geological git history); indexed in mojomast/ussyverse PROJECT_INDEX

### ussyverse/fermentussy
- **Description**: Rust fermentation tracker that models each batch as a thermodynamic system with entropy, phase-transition, and microbial-succession views.
- **Stack**: Rust, ratatui TUI, clap CLI, JSON file storage
- **Capabilities**: interactive TUI batch navigation and logging, flavor-complexity entropy from taste-note Shannon diversity, logistic-growth peak-ripeness prediction, microbial succession state machine (LAB -> yeasts -> acetobacter), contamination risk scoring from temperature/pH/oxygen, non-TTY JSON CLI (--list/--summary/--add-log)
- **Uses**: Home fermentation hobbyists tracking kimchi, sourdough, and similar batches
- **Integrations**: standalone (kitchen-science cluster with ussyverse/rheoussy, ussyverse/maillaraussy)

### ussyverse/firelineussy
- **Description**: Python GitHub Action and CLI that models community volunteer capacity as a fire landscape to produce burnout-risk burn maps.
- **Stack**: Python 3.10+, GitHub Actions (action.yml), pytest, pyyaml
- **Capabilities**: fuel load scoring, ignition probability forecast, spread pressure between teams, patch mosaic diversity score, prescribed-burn optimizer ranking closures/scope cuts, ember-cast warnings for side requests, Markdown/JSON reports, CI fail-on risk-level gating
- **Uses**: volunteer organizations and community organizers keeping civic ecosystems healthy
- **Integrations**: same GitHub-Action report pattern as biofilmussy

### ussyverse/fittsaussy
- **Description**: Stdlib-only Zig local web app that turns Fitts's Law into household control accessibility audit cards, scoring target-acquisition burden for physical and digital controls.
- **Stack**: Zig 0.14+, embedded HTML/CSS/JS dashboard, Zig stdlib only
- **Capabilities**: Fitts's Law burden scoring (log2(d/w+1)), modifiers for posture, urgency, gloves, tremor, low vision, edge aids, neighbor spacing, destructive neighbors, consequence severity, accessibility grades and plain-language bands, redesign recommendations, printable redesign cards, JSON API (`/api/analyze`, `/api/sample`, `/api/defaults`)
- **Uses**: accessibility-minded households auditing phone screens, appliances, emergency controls, and UI targets
- **Integrations**: standalone

### ussyverse/floraussy
- **Description**: A deterministic Zig library that adapts a digestive-health tracking concept into a reusable scoring engine for gastric emptying, transit lag, fermentation, and dysbiosis readiness.
- **Stack**: Zig (0.14+), static library build
- **Capabilities**: gastric emptying/load scoring from meal macros, meal-to-bowel-event transit lag correlation with Bristol balance, fermentation/diversity scoring from fiber/plant variety/distress, dysbiosis readiness report, plain-text report rendering
- **Uses**: UI developers needing a typed, dependency-free gut-health scoring core (educational decision support, not diagnosis)
- **Integrations**: standalone

### ussyverse/foleyaussy
- **Description**: Pure Go library for planning Foley cue sheets and small soundscape sketches, suggesting household-object sound substitutions with safety notes for everyday creative media.
- **Stack**: Go (standard library only)
- **Capabilities**: builds CueSheets from SceneRequests, covers footsteps/cloth/prop/ambience cue families plus intentional silence, suggests household object substitutions with believability scores, flags masking/density problems, emits JSON/CSV exports, printable cue cards, recording checklists, take-log templates
- **Uses**: non-professional video/podcast creators planning Foley recording with household objects
- **Integrations**: pairs with ussyverse/chromascriptussy (visual color-script planning) for combined pre-production; module path github.com/mojomast/foleyaussy

### ussyverse/forageussy
- **Description**: Go library/CLI applying optimal foraging theory (prey choice, patch assignment, marginal value theorem, EROI) to errand and shopping trip optimization.
- **Stack**: Go (module github.com/mojomast/forageussy)
- **Capabilities**: round-trip route optimization (nearest-neighbor + 2-opt), item-to-store assignment by profitability, EROI efficiency flagging with thresholds, patch-departure signals, time/gas budgets, max-stores constraint, JSON persistence
- **Uses**: people planning efficient multi-store shopping/errand trips
- **Integrations**: standalone

### ussyverse/forgeussy
- **Description**: VS Code extension that models craft skill development with metallurgy (work-hardening, annealing, tempering, dislocation density) to explain rest, warn of burnout, and track tool fatigue.
- **Stack**: TypeScript, VS Code extension API, Mocha tests
- **Capabilities**: practice session logging (craft, technique, duration, difficulty, frustration, cold/hot work/anneal), microstructure tree view (dislocation density, stress, strain, work-hardening exponent, rest ratio, fracture risk), SVG stress-strain curve webview via the Hollomon equation, automatic fracture-risk warnings, tool fatigue dashboard with maintenance reminders, Memento persistence
- **Uses**: hobbyist crafters tracking practice, recovery, and tool wear inside VS Code
- **Integrations**: shares personal-performance/burnout domain with ussyverse/horologussy

### ussyverse/formicaussy
- **Description**: A Nim terminal/TUI task manager inspired by ant-colony behavior, where tasks gain/lose pheromone momentum and energy-matched response thresholds pick your daily shortlist.
- **Stack**: Nim 2.0+, Nimble, JSON state files
- **Capabilities**: pheromone deposit/decay math, response-threshold probability scoring adjusted by energy, interactive TUI dashboard, colony health score and role diversity, stale-task warnings and midden sweep archival, stigmergic cues and related-task links, JSON save/load, demo colony and shortlist commands
- **Uses**: individuals prioritizing daily tasks under variable energy/time constraints
- **Integrations**: standalone (personal productivity; conceptually related to laminateussy schedule-stress analysis)

### ussyverse/fossilrecordussy
- **Description**: Python esolang stress-testing harness ("mutation testing for tool robustness") that scores developer tools against Brainfuck, Befunge, Malbolge, and 20+ other esoteric programs.
- **Stack**: Python 3.9+, plugin architecture
- **Capabilities**: curated esolang corpus, pluggable tool test harness, 0-100 Fossil Score by category, living-fossil hybrid test generator, cross-tool/version comparison
- **Uses**: developers of IDEs, linters, formatters, and AI coding tools measuring robustness on out-of-distribution code
- **Integrations**: could stress-test mojomast coding tools like clanker01 (SWARM), warpussy, or rooagussy

### ussyverse/framoraussy
- **Description**: Local-first VS Code extension applying FRAM (Functional Resonance Analysis Method) to household care routines to find resonance hotspots and generate damping strategies.
- **Stack**: TypeScript, VS Code extension API, webviews; npm/tsc; greatest-style node test
- **Capabilities**: FRAM function cards with six aspects (input/output/precondition/resource/control/time), coupling links, hotspot resonance scoring, damping cards (status tokens, buffers, handoff questions), redacted household handoff-sheet export, local storage in VS Code global state
- **Uses**: parents, caregivers, roommates, and informal care teams analyzing routine failures (e.g., elder-care medication handoffs)
- **Integrations**: turnwiseussy (sibling household/care-communication tool); otherwise standalone

### ussyverse/fulguraussy
- **Description**: Offline Python CLI for outdoor lightning shelter timing that turns thunder/flash-to-bang observations into conservative shelter and all-clear decision cards.
- **Stack**: Python (argparse, stdlib)
- **Capabilities**: outing/shelter JSON management, shelter classification (real vs pseudo-shelters), storm cue logging with flash-to-bang, 30-minute all-clear timer, route-away flags, JSON/Markdown decision cards
- **Uses**: outdoor groups, coaches, campers, and beach/lake visitors needing lightning-safety decisions
- **Integrations**: standalone

### ussyverse/gamutussy
- **Description**: Python CLI that applies color-science gamut mapping (Delta E loss scores, rendering intents) to detect silent data loss at data-pipeline type-system boundaries.
- **Stack**: Python 3.10+, pure stdlib, pytest (145 tests)
- **Capabilities**: Pipeline clipping analysis with Delta E severity scoring, type gamut profiles for PostgreSQL/BigQuery/Avro/Parquet/Protobuf/JSON/Spark, rendering-intent error strategies (perceptual/absolute/saturation), ASCII CIE-style gamut diagrams, DAG parsing from JSON/YAML, runtime data sampling for empirical clipping detection
- **Uses**: Data engineers auditing ETL pipelines for fidelity loss (timezone stripping, precision loss, range clipping)
- **Integrations**: aquiferussy, telegraphaussy (sibling data-pipeline analysis tools in the same metaphor-driven family)

### ussyverse/gatewiseussy
- **Description**: Local Nim terminal dashboard for pain-flare pacing that scores stacked daily triggers (sleep debt, load, stress) into conservative pacing cards using gate-control pain science.
- **Stack**: Nim 2.0, nimble, stdlib-only
- **Capabilities**: additive capped gate-load scorer with LOW/WATCH/HIGH/CARE bands, trigger-stacking detection, pacing-card suggestions, red-flag routing to professional care, clinician Markdown export, JSON estimate export
- **Uses**: people with chronic pain preparing pacing decisions and clinician conversations
- **Integrations**: standalone (same conservative safety-card pattern as orseraussy, lensaraussy, inferaussy)

### ussyverse/gemmaussy
- **Description**: Nim web app that treats craft supplies as a gemological collection for compatibility, sparkle-per-dollar ranking, and project forecasting.
- **Stack**: Nim 2.0, stdlib HTTP server, Nimble unittest
- **Capabilities**: material catalog by hardness/RI/SG/luster/inclusions, scratch/tarnish/heat/cleavage compatibility warnings, sparkle-per-dollar ranking, project weight/fragility/tool-wear forecasts, JSON API (`/api/analyze`, `/api/sample`), browser UI, CLI smoke output
- **Uses**: jewelry and mixed-media makers choosing and combining craft supplies
- **Integrations**: standalone

### ussyverse/glacierussy
- **Description**: Go CLI for emotional regulation and patience practice using glaciology metaphors — tracking daily accumulation/ablation as mass balance with calving-pressure reflection prompts.
- **Stack**: Go 1.24, local JSON log
- **Capabilities**: log accumulation/ablation entries with notes, tags, and calving events, phase classification (advance/equilibrium/warning/retreat), calving-pressure heuristic, ice-core summaries over N-entry layers, ASCII glacier report, deterministic demo data
- **Uses**: individuals doing reflective self-tracking of stressors and supports (non-clinical journaling heuristic)
- **Integrations**: standalone (shares journaling domain with dendroussy)

### ussyverse/granulaussy
- **Description**: Small C library for deterministic household bulk-solid (pantry) storage analysis using granular-physics heuristics (angle of repose, arching, ratholing, caking, segregation).
- **Stack**: C (C99), Make, Greatest test framework
- **Capabilities**: Material and container profiles, derived geometry analysis (fill ratio, headspace, scoop clearance), risk scoring 0-1 for jamming/ratholing/caking/segregation/spill/stale zones, combined flow-card evaluation, Markdown report rendering, static library build
- **Uses**: Hobbyists comparing pantry containers and flagging flow failure modes for dry goods
- **Integrations**: standalone

### ussyverse/gravitonussy
- **Description**: FastAPI web app that procedurally generates synthetic Python repositories with injected "dark matter" technical debt and detects/excavates it via six astrophysics paradigms.
- **Stack**: Python, FastAPI, uvicorn, pytest; embedded HTML dashboard template
- **Capabilities**: synthetic repo spawning (dead code, zombie services, ghost variables), gravitational-lensing call-graph shear maps, rotation-curve activity discrepancy, CMB metric power spectrum, weak-lensing mass reconstruction, BAO structural correlation, event-horizon safe-extraction scoring, module excavation and final reports
- **Uses**: code-archaeology education and experimenting with technical-debt detection heuristics
- **Integrations**: standalone

### ussyverse/gridironussy
- **Description**: Analyzes dependency ecosystem health using power-grid reliability engineering concepts (N-1 contingency, frequency regulation, optimal power flow).
- **Stack**: Python 3.9+ (stdlib only), SQLite, pytest
- **Capabilities**: N-1 SPOF analysis with blast-radius ranking, version-shock frequency response modeling, optimal dependency dispatch with congestion report, error-handler protection-coordination (CTI) checks, package health voltage and collapse-proximity index, IEEE 1547-style API compliance inspection, manifest parsing for package.json/requirements.txt/pyproject.toml
- **Uses**: maintainers assessing resilience of Node.js and Python dependency trees
- **Integrations**: ussyverse/dosemateussy (change propagation through the same dependency graphs), ussyverse/seralussy (codebase governance)

### ussyverse/groomaussy
- **Description**: Local-first FastAPI web app for Dunbar-aware friendship maintenance that allocates limited social attention across relationship layers.
- **Stack**: Python 3.10+, FastAPI, Uvicorn, Jinja2, local JSON storage
- **Capabilities**: Dunbar circle map (layers, rhythms, consent/boundary notes), weekly attention budget declaration, drift and guardrail review (under-tended close ties, dormant candidates), weekly social-grooming plan bounded by budget, re-entry and repair note generation, local export/delete of state
- **Uses**: individuals deliberately maintaining friendships without CRM/surveillance tooling
- **Integrations**: standalone

### ussyverse/haccpussy
- **Description**: Rust TUI application that applies HACCP food-safety principles (hazards, critical control points, limits, monitoring) to software license compliance.
- **Stack**: Rust, ratatui, crossterm, clap, serde/toml/serde_json
- **Capabilities**: License hazard classification (copyleft/proprietary/unlicensed) with risk scoring, CCP decision tree, quantified critical limits, monitoring records, corrective actions with 5 Whys, lot traceability, viral-depth/compatibility/attribution analysis from TOML/JSON manifests, tabbed TUI dashboard
- **Uses**: Compliance-minded maintainers auditing dependency license risk
- **Integrations**: standalone

### ussyverse/hammeraussy
- **Description**: Rust library and CLI for household plumbing hydraulic-transient triage, classifying pipe bangs and chatter into mechanisms with conservative risk scores and next checks.
- **Stack**: Rust, clap, library + thin CLI demo
- **Capabilities**: deterministic classifier for water hammer, thermal expansion tick, fill-valve chatter, loose-pipe amplification, drain gurgle, high static pressure suspicion, escalate/unknown, risk scoring with safety flags (old hoses, moisture, high pressure, corrosion, renter documentation), action cards in plain text, Markdown, and CSV
- **Uses**: Renters/homeowners diagnosing plumbing noises and preparing landlord/plumber reports; not leak prediction or a plumber replacement
- **Integrations**: standalone

### ussyverse/haptenaussy
- **Description**: Local-first VS Code extension that turns contact-rash notes into conservative contact chain cards (body site -> contacts -> allergen family -> timing -> avoidance swap -> review date).
- **Stack**: TypeScript, VS Code extension API, Mocha tests
- **Capabilities**: deterministic contact-path ranking, built-in allergen-family alias catalog (nickel, fragrance, isothiazolinones, etc.), red-flag route-away gate, contact chain card renderer, dermatologist-ready Markdown export, webview sample card
- **Uses**: people organizing dermatology notes and one-change-at-a-time avoidance experiments for clinician discussion
- **Integrations**: shares VS Code extension form with stratumussy; dermatology/home-care domain kin to paronychaussy

### ussyverse/hazardaussy
- **Description**: Rust library for survival-analysis-style client retention timing, converting relationship records into right-censored observations, Kaplan-Meier retention curves, hazard windows, and intervention timing recommendations.
- **Stack**: Rust, Clap (thin demo CLI)
- **Capabilities**: `build_survival_observations` with censoring and pause handling, Kaplan-Meier stepwise curves with median survival, `detect_hazard_windows` tenure-interval hazard ranking, `recommend_interventions` scheduling primitives, `compare_cohorts` with thin-sample/heavy-censoring warnings, `build_retention_playbook` end-to-end, deterministic integer-day engine
- **Uses**: small businesses (studios, memberships, client services) timing retention interventions from relationship records
- **Integrations**: standalone

### ussyverse/hitchussy
- **Description**: A stdlib-only Python CLI that applies knot-theory vocabulary and graph algorithms (Tarjan SCC, min feedback edge set, Brunnian detection) to classify and prescribe fixes for cyclic code dependencies.
- **Stack**: Python 3.10+, stdlib only (AST parsing)
- **Capabilities**: AST import scanning, tangle detection and knot-type classification (trefoil, figure-eight, slip knot), crossing/unknotting number heuristics, Brunnian link detection (god-object patterns), Reidemeister-move refactoring prescriptions, text and JSON reports
- **Uses**: Python developers refactoring tangled module dependencies
- **Integrations**: ussyverse/choreoussy (dependency-graph analysis), mojomast/terrariumussy (ecosystem health visualization), mojomast/kompressiussy (complexity metrics)

### ussyverse/hoistussy
- **Description**: Local-first Python CLI for composing neighborhood/civic notices with maritime signal-flag discipline, tracking urgency, acknowledgments, expiry, and all-clear lifecycle in SQLite.
- **Stack**: Python 3, SQLite (stdlib), argparse, pytest
- **Capabilities**: default 14-flag civic signal book, validation of urgent/distress notices (expiry, action verb, ack roles, all-clear path), acknowledgment ledger (seen/can_help/cannot_help/needs_clarification/all_clear_confirmed), alert-fatigue metrics, text/JSON/Markdown/HTML renderers, sample notices
- **Uses**: block clubs, neighborhood organizers, mutual-aid coordinators sending disciplined local notices
- **Integrations**: standalone

### ussyverse/honeussy
- **Description**: Local-first FastAPI web app for conservative kitchen-knife edge-care diagnosis that outputs least-metal-removal abrasive plans.
- **Stack**: Python, FastAPI, Pydantic, Jinja HTML templates, pytest
- **Capabilities**: rule-engine diagnosis (rolled/rounded apex, burr, chips, over-polished edge), least-aggressive abrasive progression, burr lifecycle checklist, angle/pressure guidance, risk scoring, maintenance intervals, JSON local storage with export/import
- **Uses**: home cooks and knife owners maintaining edges without over-grinding
- **Integrations**: standalone (household domain cluster with cryoraussy, electraussy)

### ussyverse/horologussy
- **Description**: Python library that models a day of work and recovery as a mechanical watch movement (mainspring, escapement, complications, power reserve) for focus rhythm and energy management.
- **Stack**: Python 3.10+, stdlib, optional SQLite, pytest
- **Capabilities**: Activity/MovementDay/TaskProfile models, exponential/saturating mainspring reserve simulation, escapement health from focus-interval regularity, isochronism score from work-quality variance, beat error for work/rest asymmetry, gear-train load and context-switch complication costs, crash prediction with intervention suggestions, SQLite MovementStore for daily logs, demo CLI
- **Uses**: people wanting a transparent physical intuition for predictable energy crashes
- **Integrations**: shares focus/energy domain with ussyverse/forgeussy

### ussyverse/hospitiaussy
- **Description**: A Go CLI that turns overnight houseguest hosting into a service blueprint with touchpoints, failure modes, boundary scripts, and a privacy-filtered guest-facing card.
- **Stack**: Go (std flag), JSON in / text-markdown-json out, go test
- **Capabilities**: touchpoint blueprinting (guest action, frontstage, backstage, evidence, failure mode, energy cost), boundary scripts for quiet hours/pets/food labor, self-serve artifact suggestions, failure warnings (shared-bathroom bottleneck, unclear departures), guest-facing card that filters private host notes, sample/demo generation
- **Uses**: hosts planning overnight guests in small homes
- **Integrations**: standalone (household-domain sibling of anellaussy, pulmoussy, sorpraussy)

### ussyverse/hysteronussy
- **Description**: Local-first Go CLI modeling decision hysteresis — remanence, coercivity, readiness — for path-dependent transitions between contexts or plans.
- **Stack**: Go 1.22, standard library only
- **Capabilities**: remanence/coercivity/readiness scoring, minor-loop (half-switch) detection, return-point memory cards, JSON/CSV sample generation, demo mode
- **Uses**: people analyzing task/context switching friction and re-entry costs
- **Integrations**: standalone

### ussyverse/ichniteussy
- **Description**: Stdlib-only Python CLI applying paleoichnology (trace fossil science) to static/behavioral code analysis of logs, tests, commits, and CI history.
- **Stack**: Python 3.9+, standard library only
- **Capabilities**: ichnofacies zonation of modules, log trace ichnotaxonomy, flaky-test trackway analysis (gait/limping/herd behavior), bioturbation index from cross-layer commits, taphonomic preservation grading (A-F), ghost-trace detection, stratigraphic tiering profiles, full report with JSON output
- **Uses**: teams mining behavioral "fossils" (logs, CI runs, git history) for code-quality and flakiness insight
- **Integrations**: calibreussy (test-suite metrology companion for flakiness/root-cause analysis)

### ussyverse/ichnoussy
- **Description**: TypeScript library for privacy-preserving "behavioral archaeology" that reconstructs habits from local data traces (browser, fitness, receipts) using ichnology metaphors.
- **Stack**: TypeScript (npm package `ichnoussy`, Vitest)
- **Capabilities**: trace-fossil ingestion, ichnofacies behavior environments, Shannon ichnodiversity with monoculture warnings, taphonomy/evidence decay analysis, bioturbation and escape-trace detection, tiering of intentional vs automatic habits
- **Uses**: individuals analyzing their own digital behavior exhaust locally
- **Integrations**: standalone

### ussyverse/immunussy
- **Description**: Go CLI and GitHub Action that analyzes anxiety journal entries through an immunology framework (antibodies, memory cells, cytokine storms, vaccination schedules).
- **Stack**: Go 1.24, stdlib; GitHub Action (action.yml)
- **Capabilities**: Parses YAML anxiety journal entries, antibody library (coping-tool success per trigger), memory-cell confidence tracking, storm forecast (intensity/frequency spike warnings), autoimmune detection (disproportionate anxiety), vaccination schedule via spaced repetition, herd-immunity score, Markdown report generation, GitHub Action workflow integration
- **Uses**: Individuals tracking anxiety patterns; repos that keep a wellness journal in version control
- **Integrations**: stellarussy (reflective journaling CLI in the same wellness-tool family)

### ussyverse/inferaussy
- **Description**: Local-first Go web app that slows down household conflict by turning the Ladder of Inference into an assumption-checking card with deterministic warnings.
- **Stack**: Go 1.22, net/http, HTML UI, no external dependencies
- **Capabilities**: rung-separated ladder cards, warnings for mind-reading/always-never leaps/omitted-data imbalance, safety routing for coercion/abuse/legal disputes, sentence frames, JSON API, sample endpoint, Markdown report export
- **Uses**: household members or coaches pausing before reactive replies in everyday conflict
- **Integrations**: standalone (sibling pattern of lensaraussy/orseraussy safety-card apps)

### ussyverse/inkblotussy
- **Description**: Python "Rorschach test for code" that profiles developer cognitive style from Python AST features across 8 dimensions (abstraction, error orientation, naming, etc.).
- **Stack**: Python 3.10+, AST analysis; optional matplotlib/numpy radar charts
- **Capabilities**: per-author and whole-codebase style profiling, anonymous-code fingerprint attribution via cosine similarity, developer-to-developer and codebase comparison, team cognitive-diversity analysis, PR review recommendations per author profile, text/JSON/radar-chart output
- **Uses**: teams studying code-review dynamics, attribution, and cognitive diversity
- **Integrations**: shares developer-tooling domain with levainussy and clavisussy; no direct integration

### ussyverse/interferaussy
- **Description**: Nim CLI planner that generates skill-practice sessions based on the contextual-interference effect (blocked vs serial vs random practice with retention/transfer probes).
- **Stack**: Nim 2.0+, Nimble
- **Capabilities**: practice-order scheduling, contextual-interference scoring, cue fading, feedback timing recommendations, delayed retention probes, transfer probes, safety gates that suppress unsupervised randomization for high-risk skills, error classification prompts
- **Uses**: learners and coaches structuring practice for sports, music, driving, or clinical/tool skills
- **Integrations**: standalone

### ussyverse/isobarussy
- **Description**: Pure-stdlib Python CLI that maps git history and AST dependencies to meteorological concepts (temperature=change velocity, pressure=dependency load, humidity=bug density) to produce weather reports, fronts, and storm warnings for a codebase.
- **Stack**: Python stdlib only
- **Capabilities**: Git log scanning and import-graph building, atmospheric field computation, frontogenesis detection (warm/cold fronts), cyclone classification on Saffir-Simpson scale, ASCII synoptic maps, weather forecasting, storm warnings, per-file micro-climate analysis, historical/sprint comparison, JSON output
- **Uses**: Developers and team leads monitoring codebase volatility, bug hotspots, and instability boundaries
- **Integrations**: shares code-structure-analysis domain with morsethussy and codelineageussy

### ussyverse/ixodiaussy
- **Description**: Rust library plus demo binary for deterministic tick-bite documentation, symptom-watch prompts, conservative clinician-contact boundary checks, and markdown handoff packets.
- **Stack**: Rust (library + `ixodia` demo binary), cargo tests
- **Capabilities**: typed TickBiteEvent model, conservative route-away classifier, documentation completeness and symptom-watch evaluation, markdown clinician handoff renderer, question script builder, sample event
- **Uses**: people documenting tick bites and preparing clinician questions (explicitly no diagnosis, species ID, or prophylaxis decisions)
- **Integrations**: standalone

### ussyverse/kanoaussy
- **Description**: Go GitHub Action and local CLI that applies the Kano model to household purchase decisions, separating must-be, performance, and delighter features.
- **Stack**: Go 1.24 (stdlib only), composite GitHub Action (action.yml)
- **Capabilities**: Kano classification of features from paired functional/dysfunctional reactions, must-be filter enforcement before scoring, reverse-quality burden warnings, portfolio reports from directory merges, Markdown and JSON report rendering, sample case generation
- **Uses**: households making shared purchase decisions (appliances, etc.) with multiple stakeholders
- **Integrations**: standalone

### ussyverse/keelussy
- **Description**: Local-first Zig web app that models a household budget as ship naval architecture to show how close a household is to capsizing under financial shocks.
- **Stack**: Zig 0.14, stdlib HTTP server, single HTML/CSS/JS page
- **Capabilities**: manual entry of income/costs/debt/reserves, naval metrics (displacement, buoyancy, GM/metacentric height, righting moment, free-surface penalty, load-line warning), damage-stability checks (job loss, car repair, medical bill), SVG hull visualization with G/B/M/waterline, built-in sample data and demo
- **Uses**: households stress-testing budget stability locally with no bank integrations
- **Integrations**: standalone

### ussyverse/kerfwiseussy
- **Description**: Go library that translates wood-movement science into conservative risk cards for hobby woodworking assemblies (tabletops, doors, drawers).
- **Stack**: Go (stdlib only)
- **Capabilities**: Cross-grain movement estimation from width and humidity swing, material modeling (solid wood, plywood, MDF, reclaimed), assembly scoring (tabletop-to-apron, breadboard ends, frame-and-panel, etc.), restraint risk flags (fixed screws, tight panels), allowance recommendations (floating panels, slotted holes, buttons), JSON/CSV/Markdown export
- **Uses**: Hobbyist woodworkers planning crack/cup/binding-safe solid-wood projects
- **Integrations**: same household-scale conservative-planning niche as tilthaussy (garden soil) and watershedussy (trail water)

### ussyverse/kinesiaussy
- **Description**: Privacy-first Python CLI coaching home exercisers on movement quality, converting self-reported biomechanical markers into kinetic-chain scores and corrective plans.
- **Stack**: Python 3.10+, CLI, optional SQLite persistence, JSON/SVG report output
- **Capabilities**: exercise library, squat/deadlift-style assessments from alignment/effort/ROM/pain/balance inputs, 0-100 kinetic-chain score, green-yellow-orange-red risk levels, weak-link diagnosis, per-joint chain load map, moment-arm optimization cues, agonist-antagonist balance notes, SQLite history, JSON file analysis, SVG report rendering
- **Uses**: Home exercisers deciding whether movement patterns are safe to progress; educational only, not medical advice
- **Integrations**: standalone

### ussyverse/kinshipussy
- **Description**: Go library for kinship-anthropology family care-network analysis, modeling relatives, in-laws, chosen family, and institutions as a multiplex graph.
- **Stack**: Go 1.22, pure stdlib, demo CLI
- **Capabilities**: care-load index per person, reciprocity imbalance ledgers, ambiguous affinal/fictive obligation detection, fictive-kin visibility, backup-path gap analysis, household clustering, caregiver unavailability simulation, neutral conversation prompts
- **Uses**: families and caregivers renegotiating care labor distribution
- **Integrations**: standalone (caregiving-domain kin to firelineussy)

### ussyverse/knitussy
- **Description**: Rust terminal UI and CLI pattern generator that adapts topology concepts (genus, Euler characteristic, curvature) to knitting and crochet, producing increase/decrease schedules and ASCII topology maps.
- **Stack**: Rust, ratatui/crossterm TUI
- **Capabilities**: gauge + inch/cm to stitch/row conversion, topological shape classification (panel, tube/sock, sphere/hat, torus, sweater), curvature-driven shaping schedules with puckering/ruffle warnings, text pattern rendering, ASCII topology maps, interactive TUI with non-TTY plain-text fallback
- **Uses**: knitters and crocheters drafting hats, socks, panels, and torus-like shapes before swatching
- **Integrations**: standalone

### ussyverse/kompressiussy
- **Description**: A Python CLI that uses compression algorithms as approximations of Kolmogorov complexity to measure algorithmic entropy, redundancy, NCD similarity, and information flow in codebases.
- **Stack**: Python, zstandard, stdlib gzip/bz2/lzma, git CLI (optional)
- **Capabilities**: per-module entropy/redundancy/density profiling, NCD distance between files, redundancy hotspot detection, git compression-delta tracking across commits, UPGMA clustering by similarity, surprise ranking, HTML landscape visualization
- **Uses**: developers and researchers analyzing code structure, duplication, and change information content
- **Integrations**: mojomast/terrariumussy (referenced as a real adapter for its complexity dimension), ussyverse/hitchussy, mojomast/churnmap

### ussyverse/koppenussy
- **Description**: C-based repository analyzer (CLI and composite GitHub Action) matching traveler climate preferences to destination/month climate normals using Köppen-like classification and comfort scoring.
- **Stack**: C (pure stdlib), Make, GitHub Actions composite action
- **Capabilities**: parses key=value preferences and 39-field destination climate CSVs, classifies Köppen-like labels (Af, Csa, BW, ET, H...), scores temperature/rain/humidity comfort and preferred months/labels, writes KOPPEN-REPORT.md with ranked matches, packing notes and warnings, embedded sample destinations
- **Uses**: travelers maintaining repo-hosted climate data and wanting deterministic CI ranking of destinations
- **Integrations**: standalone

### ussyverse/kuleshovussy
- **Description**: Offline TypeScript web app for pre-edit story planning of home videos using montage psychology (Kuleshov effect, establishing shots, reaction gaps).
- **Stack**: TypeScript, Vite, Vitest, static frontend
- **Capabilities**: clip-card sequence lane, deterministic montage rule engine (continuity, emotional jumps, reaction gaps, establishing debt, rhythm monotony), Kuleshov-pairing prompts, rhythm chart, missing-shot checklist, CSV edit decision list export, demo fixtures
- **Uses**: non-expert creators planning family/travel/pet videos before editing in iMovie/CapCut
- **Integrations**: standalone

### ussyverse/laminarussy
- **Description**: Python stdlib tool that models personal cash flow as a fluid with Reynolds numbers, vortices, boundary layers, and viscosity to assess budget stability.
- **Stack**: Python 3.9+, stdlib only, pytest
- **Capabilities**: CSV transaction parsing, FlowAnalysis computing Reynolds number and flow regime, ASCII streamline visualization of cash flow, vortex and viscosity detection, programmatic API (parse_csv, FlowAnalysis, ascii_streamlines, generate_recommendations)
- **Uses**: individuals analyzing income/expense turbulence and getting budget recommendations
- **Integrations**: shares personal-finance modeling domain with ussyverse/percolateussy

### ussyverse/laminateussy
- **Description**: A Python CLI that treats a weekly schedule as a fiber-reinforced composite, computing stiffness, shear, delamination risk, and a Tsai-Wu-style failure index.
- **Stack**: Python (pyproject, src layout), argparse CLI, pytest
- **Capabilities**: stiffness matrix over focus/flexibility/creativity/social/maintenance/recovery axes, dominant-fiber and balance scoring, symmetric-schedule check, delamination risk from repeated same-fiber days, interlaminar shear map for context switches, Tsai-Wu failure index and crash probability, balanced-laminate recommendations, JSON output
- **Uses**: people analyzing and rebalancing weekly routines to avoid burnout
- **Integrations**: standalone (productivity-analysis domain; complements formicaussy task prioritization)

### ussyverse/lanugoussy
- **Description**: Python GitHub Action and CLI that generates Markdown textile-care reports from garment inventory files, modeling laundry as fiber-chemistry compatibility.
- **Stack**: Python 3.9+, GitHub Actions
- **Capabilities**: parses JSON/CSV/YAML/Markdown garment files, dye-transfer and shrinkage risk heuristics, pilling/elastane-fatigue scoring, Markdown + JSON report output, CI artifact upload
- **Uses**: households tracking clothing care via repo-based workflows
- **Integrations**: standalone (same repo-action pattern as taphonussy)

### ussyverse/latticeussy
- **Description**: Single-binary C web app that turns learning into crystallography, modeling concepts as unit cells, relationships as lattice planes, and misconceptions as defects, with phase-transition readiness alerts.
- **Stack**: C, gcc/make, embedded HTML/CSS/JS; greatest.h tests
- **Capabilities**: unit-cell concept editor with mastery scores, lattice-plane relationship editor (cause/example/analogy/contrast/support), diffraction analysis (average mastery, structural density, defect count, weakest review target, crystallization score, phase transition), browser graph visualization, CLI sample report, text/JSON parsing
- **Uses**: self-learners who want connected knowledge structure instead of isolated flashcard facts
- **Integrations**: scaffoldussy (learning-analytics companion; ZPD practice planning on top of lattice knowledge state)

### ussyverse/legionaussy
- **Description**: Dependency-free C library for household premise-plumbing stagnation planning, producing conservative water-safety action cards (named after Legionella risk).
- **Stack**: C (C99, Greatest test header, Makefile)
- **Capabilities**: stagnation/growth/exposure scoring, fixture-level action cards (flush, avoid aerosol, call professional), property-level reports, Markdown export, professional handoff question generation
- **Uses**: households returning from travel, seasonal cabin owners, small rental turnovers
- **Integrations**: standalone

### ussyverse/lehrussy
- **Description**: Python CLI modeling a test suite as glassware undergoing annealing — diagnosing flakiness via birefringence, CTE, thermal shock, and tempering metaphors and generating stabilization schedules.
- **Stack**: Python 3.9+, stdlib, pytest
- **Capabilities**: Birefringence stress scanning of test dirs, CTE environment-sensitivity profiling, thermal-shock resilience tests, annealing schedule generation, tempering detection (retry-masked brittleness), glass-type fragility classification, combined full analysis report
- **Uses**: Developers stabilizing flaky test suites who want diagnostic vocabulary beyond pass/fail rates
- **Integrations**: clanker04 (ParallelForge runs test/lint-based evaluation that Lehr could assess)

### ussyverse/lensaraussy
- **Description**: Local-first Go web app producing conservative contact-lens care state cards covering hygiene, replacement drift, water exposure, and stop-and-call warning signs.
- **Stack**: Go 1.22, net/http, HTML UI, no external dependencies
- **Capabilities**: deterministic rule engine for dryness/wear load, deposit suspicion, hygiene gaps, water-exposure boundaries, red flags, care-packet export, JSON API and Markdown report endpoints
- **Uses**: contact-lens wearers distinguishing routine discomfort from hygiene or replacement problems
- **Integrations**: standalone (sibling of inferaussy, orseraussy, gatewiseussy conservative guidance cards)

### ussyverse/levainussy
- **Description**: Python CLI modeling a test suite as a living sourdough culture, reporting lifecycle health metrics like hooch, rise, contamination, and feeding cadence.
- **Stack**: Python 3.9+ (stdlib only), pytest
- **Capabilities**: JUnit XML parsing and pytest execution, hooch detection of stale/trivial/dormant tests, rise score for healthy failure rates, flaky-test epidemiology with R0 and patient-zero identification, feeding-adherence tracking vs. git change velocity, minimal high-value test subset builder, environment thermal profiling, JSON output
- **Uses**: engineering teams assessing whether their test suite actually discriminates, not just covers
- **Integrations**: complements ethonussy (CI log analysis) and clavisussy (triage of what the suite finds); no direct integration

### ussyverse/lichenoussy
- **Description**: Local-first Python library for neighborhood care-signal observatories, translating lichenology/biomonitoring concepts into models for small civic places (pantries, benches, bulletin boards).
- **Stack**: Python (pyproject.toml), SQLite/JSON local stores
- **Capabilities**: care-site and indicator modeling, care-gradient scoring (thriving/stable/dry/stressed), context dampeners separating low-capacity dryness from neglect, edge-effect detection for responsibility ambiguity, revival-action and colonization-path recommendations, quiet-wins summaries and printable care walk sheets
- **Uses**: mutual-aid groups and neighbors tracking care of shared spaces without surveillance
- **Integrations**: standalone

### ussyverse/limnoussy
- **Description**: Python TUI/CLI wellness journal that models inner life as a stratified lake (epilimnion/metalimnion/hypolimnion) with turnover forecasts, trophic state, Secchi transparency, dissolved oxygen, and bloom/anoxia warnings.
- **Stack**: Python, SQLite, pytest
- **Capabilities**: Layered emotion profiling (surface/deep), life-event turnover forecasting, trophic-state and dissolved-oxygen scoring, algal-bloom and anoxia warnings, journaling with local SQLite history, ANSI ASCII lake cross-section rendering, JSON output
- **Uses**: Individuals using structured introspection/journaling for emotional wellness (explicitly not medical or crisis tooling)
- **Integrations**: shares limnology-analogy domain with eutrophaussy

### ussyverse/loadpathussy
- **Description**: Local C terminal/TUI packing planner scoring luggage comfort (load fraction, asymmetry, route burden, access urgency) rather than destination checklists.
- **Stack**: C11, gcc, Makefile, greatest.h test framework
- **Capabilities**: bag cards for suitcase/backpack/tote/duffel, text zone diagrams, packing heuristics for dense/urgent/fragile/leak/electronics items, side-asymmetry and route burden scoring, repack warnings, demo and keyboard-interactive modes
- **Uses**: travelers screening whether their packed bag will be comfortable over stairs, cobblestones, and long walks
- **Integrations**: standalone

### ussyverse/lossicaussy
- **Description**: Local C CLI that reframes subscription renewal decisions through a conservative prospect-theory lens, separating ongoing value from loss-framed reluctance.
- **Stack**: C11, make, bundled Greatest single-header test framework
- **Capabilities**: annualized cost computation, ongoing value scoring (use, recency, beneficiaries, irreplaceability), loss-aversion/sunk-cost/status-quo/endowment bias detection, keep/downgrade/pause/cancel/review recommendation bands, cancellation checklist generation, CSV output, safety routing for essential subscriptions
- **Uses**: individuals auditing recurring subscriptions for genuine value
- **Integrations**: standalone

### ussyverse/ludonussy
- **Description**: Go TUI that applies the MDA (Mechanics-Dynamics-Aesthetics) game-design framework to simulate software architecture rule sets and predict emergent failures before deployment.
- **Stack**: Go 1.24, Bubble Tea, Lipgloss
- **Capabilities**: JSON mechanics parser (timeouts, retries, rate limits, circuit breakers, queue depths), discrete-event simulation via goroutines/channels, ASCII timeline of emergent dynamics (retry storms, thundering herds), quality-attribute scorecard (reliability, latency, throughput), correlation ranking of dangerous rule pairs
- **Uses**: engineers/architects exploring how resilience rules interact in a system
- **Integrations**: shares distributed-systems simulation domain with ussyverse/stormussy (meteorology-mapped failure modes)

### ussyverse/luminaraussy
- **Description**: VS Code extension wrapping a deterministic C rule engine for planning safe household portrait/interview/craft lighting setups.
- **Stack**: C core (src/luminara_core.c), TypeScript extension host, Mocha, Make
- **Capabilities**: Key/fill/rim light recommendations for moods (balanced, high-key, chiaroscuro), color-temperature/glare/no-separation warnings, hard safety gates (damaged cords, overheating, trip hazards, consent), Markdown/JSON setup cards, CLI analyze/sample modes
- **Uses**: Home videographers and interviewers planning three-point lighting without ML or smart-bulb control
- **Integrations**: standalone (same mojomast "VS Code extension + safety-gated planner" slot pattern as admeussy)

### ussyverse/maillaraussy
- **Description**: Local-first Zig CLI that diagnoses home-cooking Maillard browning failures and generates a practical browning control card.
- **Stack**: Zig 0.14+, no external runtime dependencies
- **Capabilities**: moisture and crowding risk estimation, heat/sugar burn-boundary flagging, browning failure classification (water-limited, heat-limited, dwell-time-limited, gradient-limited, pH/ingredient-limited, burn-boundary, balanced), next-attempt control cards (drying, spacing, staging heat, delaying glaze, preheating), built-in sample diagnosis
- **Uses**: Home cooks troubleshooting pale, burnt, or soggy roasted/browned food; quality-only, not a food-safety tool
- **Integrations**: standalone (kitchen cluster with ussyverse/rheoussy, ussyverse/fermentussy)

### ussyverse/maneuverussy
- **Description**: Browser-based military tactics game where refactoring operations are commanded as doctrinal maneuvers across a procedurally generated technical-debt battlefield.
- **Stack**: TypeScript, Vite, Vitest, jsdom
- **Capabilities**: procedural codebase battlefield generation, OODA loop countdown timer, seven maneuvers (schwerpunkt, blitzkrieg, infiltrate, breakout, flank, pincer, feint), interactive grid visualization, campaign state tracking with disruption budget and scoring
- **Uses**: developers/game players interested in refactoring strategy as a game
- **Integrations**: standalone

### ussyverse/marangoniussy
- **Description**: Python library and CLI that turns acrylic pouring/marbling/resin studio variables (silicone, drip time, pigment density, humidity, film thickness) into explainable surface-chemistry forecasts and one-variable experiment cards.
- **Stack**: Python (stdlib only), SQLite RecipeStore, pytest
- **Capabilities**: cell density/diameter forecasting, fine-lacing vs large-cell prediction, feathering warnings for absorbent paper, muddy-color risk scoring, crack risk from film thickness/evaporation/binder, crawling/beading risk, one-variable experiment cards, recipe fingerprints (`MRG-...`), `forecast`/`experiments` CLI with JSON output, SQLite recipe/forecast persistence
- **Uses**: acrylic pouring, paper marbling, resin, and ink artists reproducing surface effects deliberately
- **Integrations**: standalone

### ussyverse/marksmanussy
- **Description**: A zero-dependency Python CLI that applies marksmanship/archery statistics to test-suite quality, computing precision grouping, dispersion ellipses, and maturity classification from stored test results.
- **Stack**: Python stdlib + sqlite3
- **Capabilities**: Rayleigh sigma-T precision grouping, dispersion ellipse with correlated-error analysis, scale-invariant TMOA accuracy metric, ballistic-coefficient error-propagation prediction, Weibull maturity classification, windage/elevation systematic-vs-random error decomposition, SQLite result storage
- **Uses**: QA engineers and developers assessing test-suite reliability and flakiness trends
- **Integrations**: mojomast/terrariumussy (health signals), ussyverse/proprioceptionussy (workspace state)

### ussyverse/mashussy
- **Description**: Offline VS Code extension that turns a homebrew recipe into an explainable brewing-science model with a cause-and-effect webview from mash temperature to ABV.
- **Stack**: TypeScript, VS Code extension API, Mocha tests
- **Capabilities**: computes OG/FG/ABV, mash fermentability and body, Tinseth IBU, Morey SRM color, weighted diastatic power, Palmer-style residual alkalinity and mash pH, chloride/sulfate balance, fermentation risk, integrated recipe diagnosis, Markdown brew-sheet export, bundled pale-ale sample recipe
- **Uses**: non-programmer homebrewers wanting to understand how recipe choices drive the finished beer
- **Integrations**: standalone

### ussyverse/memetixussy
- **Description**: VS Code extension that treats code patterns as memes and computes epidemiological metrics (R0 spread, memeplex coherence, mutation, extinction) from git history.
- **Stack**: TypeScript, VS Code Extension API, webview panels
- **Capabilities**: workspace memetic analysis, R0 reproductive-rate ranking webview, memeplex co-occurrence analysis, fossil/extinction view, pattern tree view in Explorer sidebar, git-log parsing
- **Uses**: developers studying how patterns propagate and evolve across a TypeScript/JavaScript codebase
- **Integrations**: standalone (code-analysis domain, complementary to syntropussy's behavioral probing)

### ussyverse/meridianussy
- **Description**: Go library for cartographic productivity planning that models projects as terrain with elevation, ridges, grid pressure, and magnetic declination.
- **Stack**: Go 1.22, stdlib only
- **Capabilities**: task terrain model (difficulty/elevation, dependencies, deadlines, priorities, energy types, goal alignment), Mercator-like urgency-preserving / equal-area effort-preserving / azimuthal goal-centered projections, distortion metrics (effort, urgency, shape), contour and ridge analysis (bottlenecks, steep climbs, contour clusters), critical-route computation, magnetic-declination estimate-bias regression, optional demo CLI
- **Uses**: project planners wanting map-based views of workload, bottlenecks, and estimate drift
- **Integrations**: standalone

### ussyverse/metameraussy
- **Description**: A C terminal CLI that scores wardrobe metamerism risk (garment colors matching in one light but not another) and prints conservative light-check cards.
- **Stack**: C, Makefile, Greatest test framework
- **Capabilities**: metamerism risk scoring by color family/undertone, light-pair risk (warm LED vs daylight), pair mismatch analysis with contrast tolerance, gloss/texture adjustments, light-check plan generation, sample risk cards, CLI color parsing
- **Uses**: consumers checking black separates, navy/grey neutrals, and glossy vs matte outfit matches
- **Integrations**: standalone

### ussyverse/metraussy
- **Description**: VS Code extension (TypeScript shell) with a Python engine for DIY home-measurement confidence — uncertainty, tolerance, datum, and repeatability checks before cutting/buying.
- **Stack**: TypeScript (VS Code extension), Python 3.10+ (metra_core), pytest/Vitest
- **Capabilities**: fit-confidence measurement board webview, tolerance-vs-tool-resolution checks, stack-up summaries, repeatability/scatter flags, printable Markdown export packet
- **Uses**: renters, homeowners, crafters deciding when a household dimension is safe to act on
- **Integrations**: standalone (same Python-engine + VS Code pattern as pupaussy)

### ussyverse/migrationussy
- **Description**: Python FastAPI web app for group trip planning via an ornithology metaphor, computing a collective flyway, stopovers, and V-formation leadership rotation from travelers' constraints.
- **Stack**: Python, FastAPI, Pydantic, Jinja2 templates, uvicorn, pytest
- **Capabilities**: traveler/destination form + JSON API, Borda-count magnetic alignment scoring, stopover/rest-day recommendations with seasonal matching, leadership rotation to reduce planner burnout, partial migration (late join/early leave) handling, readiness/fairness/alignment/budget/Zugunruhe scores, Markdown itinerary export
- **Uses**: friend groups and families planning vacations with mismatched budgets, energy, and availability
- **Integrations**: standalone

### ussyverse/mintussy
- **Description**: Python CLI that applies numismatics (coin grading, counterfeiting detection, hoard analysis) to classifying, grading, and verifying software package versions.
- **Stack**: Python 3.11+
- **Capabilities**: Sheldon 1-70 package grading, lockfile hoard/cluster analysis, typosquat and dependency-confusion counterfeit detection, provenance chains, debasement tracking across versions
- **Uses**: developers auditing dependency quality and supply-chain risk
- **Integrations**: ussyverse/cambiumussy (dependency compatibility analysis)

### ussyverse/modesaussy
- **Description**: Rust/Axum web app for travel packing and trip-readiness FMEA, scoring failure modes by severity/occurrence/detection and serving an embedded dashboard.
- **Stack**: Rust, Axum 0.7, Tokio, Serde
- **Capabilities**: Deterministic RPN FMEA scoring, priority tiers with severe/hard-to-detect guardrails, trip readiness reports sorted by action priority, prevention/detection/contingency action cards, pre-departure verification timeline (night-before through return), post-trip learning fields and reusable templates, embedded browser dashboard, /api/sample and /api/analyze endpoints
- **Uses**: Travelers and households systematically de-risking trip preparation
- **Integrations**: standalone

### ussyverse/mordantaussy
- **Description**: Offline Python library for natural-dye craft planning that turns fiber, dye source, mordant, and safety constraints into deterministic route cards and swatch matrices.
- **Stack**: Python 3.9+, stdlib runtime, pytest for dev
- **Capabilities**: fiber/dye/mordant data models, compatibility and safety warnings (alum, iron, copper, tannin, soy, bio-mordant), fastness estimation, swatch-matrix generation, mordant recommendation, explainable route cards
- **Uses**: textile crafters and natural-dye hobbyists planning safe, sample-first dye experiments
- **Integrations**: standalone

### ussyverse/morphemaussy
- **Description**: Rust library (with demo CLI) for morphological vocabulary transfer, segmenting words into roots and affixes so learners can infer unfamiliar vocabulary.
- **Stack**: Rust, Clap 4
- **Capabilities**: greedy longest-match morpheme segmentation with confidence, allomorph normalization (in-/im-/il-/ir-), false-friend and semantic-drift warnings, infer-meaning transfer prompts, productivity scoring from practice attempts, word-family clustering, high-yield study suggestions, printable study sheets
- **Uses**: language learners, test-prep students, and vocabulary tutors/educators
- **Integrations**: standalone

### ussyverse/morphicaussy
- **Description**: Rust TUI for morphological analysis that turns stuck binary decisions into an explicit option space of dimensions, values, and cross-consistency rules.
- **Stack**: Rust, Ratatui TUI
- **Capabilities**: decision-case JSON modeling, generation of all configuration paths, cross-consistency assessment to prune impossible paths, preservation of tension/dominated paths, sensitivity-driver surfacing, option-space analysis in text or JSON, decision receipt export, built-in sample cases
- **Uses**: individuals or teams structuring complex decisions (quit/stay, launch/wait) before committing
- **Integrations**: standalone

### ussyverse/morsethussy
- **Description**: Zero-dependency Python CLI that computes topological invariants of code structure via persistent homology, mapping a codebase to a filtered simplicial complex and reporting Betti numbers, persistence diagrams, and drift.
- **Stack**: Python stdlib only, pytest
- **Capabilities**: AST parsing to function/call graph, simplicial complex construction (up to H2), pure-Python persistent homology and Betti numbers, bottleneck/Wasserstein distance for codebase comparison, topological drift tracking over git history, SVG persistence diagrams and barcodes, Morse-theoretic critical point detection
- **Uses**: Researchers and architects studying codebase shape, circular dependencies, missing abstractions, and architectural robustness
- **Integrations**: shares code-structure-analysis domain with isobarussy and codelineageussy

### ussyverse/mortussy
- **Description**: Rust CLI for educational actuarial life-planning estimates: insurance gaps, survival percentiles, retirement ruin, annuities, and debt-vs-invest comparisons.
- **Stack**: Rust (embedded mortality model, seedable Monte Carlo), cargo tests
- **Capabilities**: human-capital life insurance gap estimate, survival percentiles by age/sex/smoker/health, Monte Carlo retirement ruin simulation with stochastic lifespan, life annuity present value, after-tax debt vs invest comparison
- **Uses**: individuals exploring actuarial scenarios (educational only, not financial advice)
- **Integrations**: standalone

### ussyverse/motifussy
- **Description**: Python CLI for home choreography phrase practice that translates Laban Movement Analysis into diagnostics for revising short movement phrases.
- **Stack**: Python 3.10+, pytest
- **Capabilities**: effort/factor monotony detection, level flatness and kinesphere compression flags, initiation overuse detection, recovery debt after accents, emotional mismatch checking, stillness detection, rehearsal card printing, JSON/CSV phrase formats, movement vocabulary explainer
- **Uses**: dancers, drama teachers, fitness instructors, and hobby choreographers revising existing phrases
- **Integrations**: standalone

### ussyverse/mtorussy
- **Description**: Python TUI/CLI dashboard that turns a strength-training day into an educational muscle-protein-synthesis timing view (mTOR hypertrophy heuristics).
- **Stack**: Python 3.10+, Textual, Rich
- **Capabilities**: anabolic-trigger estimation (~20g protein + ~2.5g leucine), ~4h refractory-period flagging, 0-2h post-workout responsive-window checks, workout stimulus scoring (sets/reps/RPE/muscle group), daily dashboard, weekly readiness/recovery report, JSON save/load state
- **Uses**: lifters learning meal/workout timing heuristics
- **Integrations**: standalone

### ussyverse/mushinussy
- **Description**: Python CLI providing Smalltalk-image-like persistent workspaces for code exploration: evaluation journals, save/resume, branching, and spatial bookmarks.
- **Stack**: Python stdlib only (pickle, json, argparse), pytest
- **Capabilities**: `mushin save/resume/list/delete`, append-only replayable evaluation journal, workspace branching/forking, spatial bookmarks (file/line/scroll/annotations), pickle-backed live object cache with graceful repr fallback, workspace diff, atomic writes
- **Uses**: Developers resuming deep code-exploration sessions without rebuilding mental context
- **Integrations**: complementary dev-context tools like stratagitussy (git archaeology); indexed in mojomast/ussyverse PROJECT_INDEX

### ussyverse/mustiaussy
- **Description**: Local-first VS Code extension turning library-science MUSTIE/CREW weeding criteria into a decision workbench for personal file and paper collections.
- **Stack**: TypeScript, VS Code extension API, Node built-in test runner
- **Capabilities**: deterministic MUSTIE scoring (Misleading/Ugly/Superseded/Trivial/Irrelevant/Elsewhere), retention-exception blocks on unsafe discard, reliable-source verification for "Elsewhere" claims, keep/replace/discard/archive/ask-first/review-later webview board, collection-policy export, CSV weeding log, caregiver medication-folder sample analysis
- **Uses**: Households, caregivers, students, and small offices decluttering documents without destroying legal/tax/medical/warranty records
- **Integrations**: sibling VS Code extensions ussyverse/dualiaussy and ussyverse/silvaussy

### ussyverse/myceliumussy
- **Description**: Python library for fungal-network-inspired ingredient pairing, treating ingredients as nodes in a weighted flavor graph.
- **Stack**: Python 3.9+, stdlib-only, pytest, console script
- **Capabilities**: BFS network growth from pantry seeds, hyphal substitution chains up to 4 hops, symbiotic flavor-triplet detection, dish suggestions from available ingredients, resilience/confidence scoring, leftover/decomposition suggestions, curated 50-ingredient graph
- **Uses**: home cooks improvising meals and reducing food waste
- **Integrations**: standalone

### ussyverse/neophagaussy
- **Description**: TypeScript library for conservative, pressure-free family taste ladders — organizing repeated low-stakes food familiarity practice (look/smell/touch/taste rungs, food chaining, exposure scheduling) with clinician route-away safety screening.
- **Stack**: TypeScript, Vitest
- **Capabilities**: safety screening with red-flag route-away (allergy, choking, ARFID, swallowing issues), look/smell/touch/taste rung recommendations, accepted-neighbor food chaining suggestions, exposure scheduling, caregiver scripts, clinician-ready reports, `buildFoodTrustCard` / `generateExposureSchedule` / `recommendNextRung` / `suggestNeighborBridges` API
- **Uses**: households practicing food familiarity with picky or food-neophobic children, with explicit non-medical boundaries
- **Integrations**: standalone

### ussyverse/nicheussy
- **Description**: A local-first Zig web app applying niche-construction ecology to career role design, mapping a worker's task/stakeholder habitat and recommending low-risk environmental experiments.
- **Stack**: Zig (0.14+), built-in HTTP server, no external deps
- **Capabilities**: selection-pressure report, niche breadth/resilience scoring, affordance-gap diagnosis, ranked keystone interventions, ecological inheritance planning, manager conversation brief, adaptive-landscape dashboard, deterministic sample JSON
- **Uses**: knowledge workers preparing for role redesign conversations with managers
- **Integrations**: standalone

### ussyverse/oarsaussy
- **Description**: Local-first Zig TUI/CLI that prepares one autonomy-preserving household behavior-change conversation using Motivational Interviewing OARS skills (Open questions, Affirmations, Reflections, Summaries).
- **Stack**: Zig (build.zig, zig-out), no dependencies
- **Capabilities**: consent gate, safety route-away for abuse/self-harm/medical stakes, righting-reflex meter, open-question classifier, affirmation evidence checks, change/sustain talk balance, reflection plan selection, Markdown support card and deterministic terminal TUI rendering, sample card
- **Uses**: family members or friends preparing to support (not control) a loved one's habit, routine, or paperwork change
- **Integrations**: standalone

### ussyverse/obscuraussy
- **Description**: Python GitHub Action and CLI that generates camera-obscura-inspired photo-walk/sketch-walk composition prompt decks from a repo config file.
- **Stack**: Python (stdlib YAML parser), GitHub Actions (action.yml), HTML card renderer
- **Capabilities**: deterministic seeded prompt-deck generation, difficulty tiers (beginner..advanced), Markdown/JSON report artifacts, printable HTML prompt cards, constraint quotas tied to session duration, local CLI mode
- **Uses**: photography educators and clubs generating structured seeing exercises in CI
- **Integrations**: standalone (CI-tool pattern shared with rulaiaussy)

### ussyverse/occlusaussy
- **Description**: Local-first Python CLI for jaw-load, occlusion, suspected bruxism, and night-guard self-observation, producing dentist-ready diaries and reports.
- **Stack**: Python 3.9+, stdlib, pytest
- **Capabilities**: awake jaw checks (contact state, load type, side, context, confidence, duration), morning sleep-bruxism clue logging (fatigue, headache, sensitivity, partner report, guard use), symptom and red-flag logging with severity/trend, guard/appliance observation records, dentist-ready reports over custom day ranges, JSON/markdown export, urgent-care escalation flags, local JSON storage
- **Uses**: people tracking bruxism/TMJ symptoms to bring structured observations to dental professionals (non-diagnostic)
- **Integrations**: shares oral-health domain with ussyverse/enamelaussy

### ussyverse/olfactoussy
- **Description**: A TypeScript library/CLI that applies fragrance-pyramid science (top/middle/base notes, volatility, olfactory fatigue, Proustian triggers) to fiction smellscape writing.
- **Stack**: TypeScript, npm package, Vitest, CLI via node
- **Capabilities**: top/middle/base note validation, sensory prompt expansion (color, texture, temperature, emotion), olfactory-fatigue warnings with rotation families across scenes, genre tone checks, exponential-decay persistence maps, Proust memory/backstory triggers, offline note database and sample profiles
- **Uses**: fiction/memoir writers and writing-tool builders designing deliberate scent description
- **Integrations**: standalone (creative-writing tool in the ussyverse)

### ussyverse/onychaussy
- **Description**: Deterministic Zig CLI for conservative toenail-change / possible-fungus home foot-care triage with red-flag route-away gates.
- **Stack**: Zig 0.14
- **Capabilities**: red-flag and high-risk-foot (diabetes, neuropathy) gating, nail-pattern classification (fungal-looking vs trauma/ingrown), reservoir/reinfection checklist, treatment-expectation notes, clinician-ready export, demo fixtures
- **Uses**: individuals triaging nail changes at home; explicitly not a diagnostic tool
- **Integrations**: standalone (same home-triage family as cicatraussy)

### ussyverse/operonussy
- **Description**: Python CLI that models documentation generation with gene-regulation biology: operons as doc clusters, promoters as generation triggers, repressors as deprecation, enhancers as cross-references.
- **Stack**: Python 3.10+, pyproject/pip
- **Capabilities**: operon (doc cluster) discovery with similarity thresholding, promoter/trigger strength analysis, repression types (inducible/repressible) for deprecated features, enhancer cross-reference discovery, audience-specific conditional generation, epigenetic documentation state tracking across commits
- **Uses**: teams managing large documentation surfaces that need conditional generation and deprecation suppression
- **Integrations**: roocodehackathon (mojomast AI documentation PR agent — complementary docs-generation domain)

### ussyverse/opticussy
- **Description**: Rust CLI that treats a messy photo folder as a wave-optics system, finding constructive/destructive interference clusters and curation plans without deleting files.
- **Stack**: Rust
- **Capabilities**: photo folder scanning, interference clustering by filename/date/byte signatures, near-duplicate dilution detection with keeper choice, holographic candidate ranking, aperture (focus) plan, text/JSON reports
- **Uses**: individuals curating local photo libraries
- **Integrations**: standalone

### ussyverse/orbitalussy
- **Description**: Rust GitHub Action (and CLI) that turns family routines and shared goals into an orbital-mechanics report with stability scores, escape-risk warnings, and SVG solar-system visualization.
- **Stack**: Rust, clap 4, serde/serde_json; GitHub Action (action.yml)
- **Capabilities**: Reads family-orbits.json, computes per member/goal orbital stability scores, classifies status (Stable/Resonant/Decaying/EscapeRisk/Retrograde), escape-velocity re-engagement estimates, resonance windows between routines, Lagrange-point low-effort ritual suggestions, Markdown report plus SVG visualization, sample data generation
- **Uses**: Families tracking shared-goal engagement in a repo via CI reports
- **Integrations**: immunussy (other mojomast GitHub Action wellness journal tool), equilibriaussy/quorumussy (family decision/coordination tools)

### ussyverse/orseraussy
- **Description**: Small local C CLI for conservative household oral-rehydration guidance, classifying fluids and triaging dehydration scenarios into readable rehydration cards.
- **Stack**: C11, Make, greatest.h test runner
- **Capabilities**: fluid-category analyzer (ORS, sports drink, water, soda/juice, broth), context-aware guidance for diarrhea/vomiting/heat/fever/thirst, red-flag and high-risk triage gates, sip-cadence reminders, report cards with escalation rules
- **Uses**: caregivers seeking conservative first-aid hydration guidance before professional care
- **Integrations**: standalone (sibling of validaraussy as a C CLI; same safety-card family as lensaraussy/rabidaussy)

### ussyverse/otolithussy
- **Description**: Local-first FastAPI web app that recommends tiny vestibular-informed grounding routines from a person's current sensory-orientation state.
- **Stack**: Python 3.10+, FastAPI, Uvicorn, Pydantic 2, SQLite
- **Capabilities**: one-minute balance check with red-flag suppression, deterministic profile classification (planted, floaty, screen-sick, shutdown-heavy, etc.), routine cards with steps and stop rules, sensory reweighting map, optokinetic load meter, SQLite persistence of checks/outcomes, pattern reports and habituation ladders, HTTP API and CLI recommend command
- **Uses**: individuals doing self-directed grounding/balance wellness journaling (not medical therapy)
- **Integrations**: standalone

### ussyverse/ottaviaussy
- **Description**: Nim library for conservative Ottawa Ankle Rules documentation after acute ankle/midfoot injury, producing an imaging-readiness route and clinician handoff card.
- **Stack**: Nim, Nimble
- **Capabilities**: red-flag/exclusion gating, Ottawa ankle and foot criteria scoring, four-step weight-bearing readiness checks, conservative recommendation classification, plain-text handoff/call-script export, safety-net language for unknown or high-risk inputs
- **Uses**: household users or coaches organizing injury facts for clinician handoff (explicitly non-diagnostic)
- **Integrations**: standalone

### ussyverse/ovuleraussy
- **Description**: Conservative, local-first Nim CLI for symptothermal cycle literacy that logs observations and produces an interpretability ledger with evidence classification and route-away safety flags.
- **Stack**: Nim (nimble), CSV-based storage
- **Capabilities**: CSV chart logging (temperature, mucus, bleeding, symptoms, confounders), clean/confounded/missing evidence classification, route-away flag suppression of interpretation, uncertainty reasons and professional-question generation, clinician/instructor Markdown packet export, privacy checklist
- **Uses**: Users practicing fertility awareness who want observation/interpretation separation without prediction or contraception claims
- **Integrations**: standalone

### ussyverse/paddockussy
- **Description**: Rust library adapting rangeland grazing science (carrying capacity, rest periods, rotational grazing) to stewardship of shared community spaces and assets.
- **Stack**: Rust library + optional demo CLI, cargo tests
- **Capabilities**: domain models for assets/usage/seasons/plans, grazing pressure and stocking-rate scoring, rest deficit and recovery window calculations, greedy rotation recommendations, indicator-condition monitoring, fairness summaries, plain-text report rendering
- **Uses**: community organizations managing meeting rooms, tool libraries, garden beds, park zones, vehicles, event kits
- **Integrations**: shares civic-commons domain with commonsaussy; otherwise standalone

### ussyverse/palpaussy
- **Description**: Offline Python TUI/CLI for planning tactile household labels using stereognosis and haptic-perception rules so objects can be identified by touch.
- **Stack**: Python, Textual (TUI), pytest
- **Capabilities**: tactile cue assignment for household items, confusion/risk matrix for too-similar touch cues, placement planning by natural hand contact zones, Markdown/SVG/JSON legend and label export, built-in kitchen sample fixture, headless CLI commands
- **Uses**: households organizing pantries, medication bins, and cleaners for touch-based identification (allergen separation, low-vision aid)
- **Integrations**: ussyverse/pokayokeussy (also addresses household look-alike/allergen confusion errors)

### ussyverse/palpebraussy
- **Description**: Local deterministic Rust TUI/CLI producing conservative stye/chalazion eyelid-bump care action cards with red-flag route-away screening and clinician-ready exports.
- **Stack**: Rust
- **Capabilities**: urgent red-flag routing (vision change, severe pain, spreading swelling), stye vs chalazion pattern classification, safe home-care plan generation (warm-compress boundaries, no squeezing/lancing), contact/makeup pause prompts, JSON episode input, JSON action-card and demo/scenario outputs, clinician-ready summary export
- **Uses**: individuals deciding safe home care vs. when to seek eye care
- **Integrations**: standalone (safety-boundary CLI genre shared with ussyverse/tidepoolussy)

### ussyverse/palynoussy
- **Description**: Stdlib-only Zig web app for allergy trigger journaling that models episodes as exposure traces with lag windows, reservoirs, and ranked trigger candidates.
- **Stack**: Zig 0.14+ (stdlib TCP/HTTP server, embedded HTML/JS frontend)
- **Capabilities**: Exposure timeline with lag-window symptom matching, reservoir carryover modeling (clothing, bedding, pet fur, bedroom air), trigger scoring with uncertainty labels, low-risk single-variable intervention experiment cards, `/api/analyze`/`/api/sample`/`/api/defaults` endpoints, CLI smoke mode
- **Uses**: Allergy sufferers keeping private exposure journals (explicitly not a diagnostic tool)
- **Integrations**: sibling conservative household-health triage tools ceruminaussy and sialiaussy

### ussyverse/parliamentussy
- **Description**: Python CLI that models a codebase as a legislative chamber where CI workers, review bots, and developers are delegates whose actions must pass parliamentary procedure.
- **Stack**: Python 3.11+, argparse CLI, SQLite state, SHA-256 hash-linked flat-file journal
- **Capabilities**: motion lifecycle (introduction, seconding, amendment with germaneness tests, quorum, voting), weighted agent registry, majority/supermajority/consensus voting with vetoes, dynamic seconding and quorum thresholds, points of order and appeals, append-only hash-chained journal with integrity verify, minutes generation
- **Uses**: Governing fleets of autonomous agents (deploy bots, scanners) so operational changes are deliberate, legitimate, and auditable
- **Integrations**: mojomast/swarmussy (multi-agent orchestration it could govern), mojomast/agenttrafficcontrol (agent coordination domain)

### ussyverse/paronychaussy
- **Description**: Local Rust/Axum web app for conservative paronychia (nail-fold) home-care boundaries with escalation routing and clinician handoff cards.
- **Stack**: Rust, Axum, Tokio, clap, serde
- **Capabilities**: symptom pattern classification, five escalation lanes from home observation to emergency route-away, home-care boundary/action ladder, episode summary/clinician handoff card, JSON assess API, local HTML form, demo JSON output
- **Uses**: adults documenting nail-fold irritation and preparing clinician visits
- **Integrations**: dermatology/home-care domain kin to haptenaussy

### ussyverse/patchwiseussy
- **Description**: Zig CLI for information-foraging cleanup of local knowledge lists (bookmarks, notes, CSV lines), scoring whether titles/URLs/snippets carry enough information scent for future refinding.
- **Stack**: Zig stdlib only
- **Capabilities**: scent scoring (refindability, ambiguity, decay risk, repair priority), duplicate/near-duplicate grouping via token/domain overlap, patch-residence keep/prune/stop guidance, refinding drill simulation with predicted misses, Markdown cleanup-plan export, plain-text/CSV/URL-per-line input parsing
- **Uses**: people cleaning up bookmarks, read-later lists, and personal knowledge files for refindability
- **Integrations**: standalone

### ussyverse/patinaussy
- **Description**: A local-first Zig CLI that turns household metal-care observations into conservative corrosion-risk trap cards using corrosion-science rules (galvanic couples, chloride pitting, passivation, coating holidays).
- **Stack**: Zig (0.14+)
- **Capabilities**: deterministic rule engine for corrosion risk, safety escalation/retire flags (food contact, brake parts, load-bearing), seasonal checklists, household risk-zone mapping, sample scenarios, CLI analyze/checklist/zones commands
- **Uses**: renters, cyclists, coastal households, and caretakers preventing rust/tarnish damage
- **Integrations**: standalone

### ussyverse/pediculiaussy
- **Description**: Pure Go library for calm, conservative head-lice household and school readiness planning, turning a lice event into checklists, timelines, and non-shaming handoff messages.
- **Stack**: Go (standard library only)
- **Capabilities**: evidence classification (live lice/nits-only/uncertain/monitor), route-away decision lanes, label-first combing and recheck timelines, contact cohort plans (bed-sharing, school, co-parent), school/co-parent message generation, minimal environment actions, blocks unsafe foggers/kerosene/repeated dosing, anti-stigma language
- **Uses**: parents, school nurses, and caregivers planning evidence-based lice response and notification
- **Integrations**: standalone; module path github.com/mojomast/pediculiaussy

### ussyverse/pedonussy
- **Description**: TypeScript library that models a home as living soil, applying pedology concepts (horizons, pH, erosion, compaction) to household health diagnostics.
- **Stack**: TypeScript/Node, npm package `pedon`
- **Capabilities**: room horizon profiling (O/A/B/C), warmth-vs-tension pH map, erosion/wear forecasting, routine-compaction detection, full home diagnostic report, CLI demo
- **Uses**: people reflecting on household usage patterns and environmental "staleness"
- **Integrations**: standalone

### ussyverse/percolateussy
- **Description**: Python TUI that models personal finances as a porous medium and tests whether the financial network percolates under shocks, using percolation theory.
- **Stack**: Python 3.10+, Textual, Rich, numpy, pytest
- **Capabilities**: FinancialNode/Edge/Network/ShockScenario models, spanning-cluster detection (BFS), percolation-threshold estimation via Monte Carlo, articulation-point (single point of failure) detection via Tarjan, invasion-percolation shock simulation (job loss, medical bills), conductivity/effective-resistance computation, composite resilience score, Textual TUI with dashboard, input, simulation, and results screens
- **Uses**: individuals stress-testing financial safety nets and finding resilience bottlenecks
- **Integrations**: shares personal-finance domain with ussyverse/laminarussy

### ussyverse/petrichorussy
- **Description**: A Python CLI for configuration-drift detection that keeps a layered "soil memory" history and flags recurring drift that is actually a correction to a wrong desired state.
- **Stack**: Python, stdlib only (sqlite3, hashlib, difflib), pytest
- **Capabilities**: SHA-256 drift detection with zero false positives, timestamped soil-layer snapshots with diffs/actors, rain-gauge drift-frequency and convergence analysis, three-layer groundwater comparison (declared/effective/intended), predictive drift from temporal patterns, soil-profile history visualization, correction detection, JSON/text export, desired-state management
- **Uses**: SREs and developers auditing config drift on servers and in IaC workflows
- **Integrations**: mojomast/monorepussy (ships as `ussy-petrichor` devtools package; overlaps with `ussy-mushin` config & drift)

### ussyverse/phenoaussy
- **Description**: Local-first Python CLI that converts phenology cues (budburst, frost, growing degree days, pollen) into watch/prepare/act/wind-down/recover household action windows.
- **Stack**: Python 3.10+, plain-JSON local storage
- **Capabilities**: region/climate/domain init, cue and GDD-signal logging, false-spring-aware task staging, seasonal cue board with rationale, JSON/CSV export
- **Uses**: households replacing fixed-date seasonal chores with cue-based timing (garden, HVAC, allergies)
- **Integrations**: standalone

### ussyverse/pheromaussy
- **Description**: Local-first C web app for integrated pest management triage in homes, reasoning from evidence to source reservoir, life-cycle interruption, monitoring, and escalation boundaries.
- **Stack**: C, gcc/make, embedded web UI; greatest.h tests
- **Capabilities**: pantry-moth/grain-beetle/weevil triage, clothes-moth/carpet-beetle textile triage, drain-fly/fruit-fly moisture triage, ant/invader entry-path reasoning, safety overrides (bedbugs, termites, roaches, allergic reactions, pesticide exposure), pheromone/sticky trap trend interpretation, local web UI + JSON sample endpoint
- **Uses**: renters, families, students, pet owners needing calm next-action plans for household pests
- **Integrations**: standalone

### ussyverse/phonaraussy
- **Description**: Python TUI voice-load pacing planner based on vocal-fold physiology that helps heavy voice users budget talk-heavy days.
- **Stack**: Python, Textual TUI
- **Capabilities**: voice-load budget estimation, plan JSON creation, clinician-ready plain-text pacing board, JSON output, headless fallback in non-TTY, symptom and baseline checks
- **Uses**: teachers, coaches, call-center workers, streamers, singers-in-training
- **Integrations**: standalone

### ussyverse/photonaussy
- **Description**: Nim CLI for household lighting triage that converts a room/task complaint file into a photometry-inspired pathway card with safe reversible interventions.
- **Stack**: Nim (nimble), Nim standard library only
- **Capabilities**: Parses key:value case files, task illuminance fit assessment, glare/reflection/shadow geometry analysis, luminance contrast and screen-window balance checks, color-rendering and flicker suspicion notes, ASCII glare sketch, renter-safe intervention ladder, safety guardrail escalation, sample/demo/analyze commands
- **Uses**: Renters and homeowners troubleshooting home lighting comfort without buying gear first
- **Integrations**: standalone

### ussyverse/photosynthussy
- **Description**: Rust web application that models software performance profiling through photosynthesis physiology, classifying functions as C3/C4/CAM leaves consuming CPU-cycle photons.
- **Stack**: Rust 2021, axum, tokio, serde, tracing
- **Capabilities**: POST /analyze endpoint for performance profiles, Calvin-cycle fixation-efficiency metrics, stomatal backpressure modeling, NPQ defensive-overhead detection, C3/C4/CAM call-pattern classification
- **Uses**: developers and performance engineers wanting an alternative metaphorical lens on function-level profiling
- **Integrations**: standalone (conceptual sibling of cycloneussy's metaphor-driven pipeline analysis)

### ussyverse/phyllotaxisussy
- **Description**: TypeScript GitHub Action and CLI that turns creative pattern requests into phyllotaxis artifacts (SVG, JSON, markdown) using Vogel's sunflower formula and Fibonacci parastichies.
- **Stack**: TypeScript/Node 20+, Vitest, js-yaml, composite GitHub Action
- **Capabilities**: golden-angle point-field generation with sunflower/pinecone/succulent variants, parastichy spiral detection, domain renderers for knit stitch charts, music rhythms, journal zones, photo collages, and color walks, batch processing of JSON/YAML/CSV request files, markdown summary report, artifact upload workflow
- **Uses**: creative coders and crafters generating Fibonacci-based knitting, music, journaling, and photography patterns in CI
- **Integrations**: standalone

### ussyverse/plan9webplumbussy
- **Description**: Plan 9-style Plumb server for the browser — a local WebSocket server plus browser extension that pipes selected text/URLs/DOM elements to regex-matched local handlers.
- **Stack**: Python (pyproject.toml, pip package `plan9webplumb`), Chrome browser extension (JS), WebSocket
- **Capabilities**: local plumber server on ws://localhost:31151, content-script selection/URL capture, context-menu and toolbar piping, regex rule engine dispatching to shell-script/app handlers, active-tab/clipboard treated as a mountable filesystem concept, example `todo` ingestion handler
- **Uses**: developers wanting Unix-style composability between web content and local tools
- **Integrations**: standalone (handlers are user-defined scripts; no ecosystem repos referenced)

### ussyverse/plantaussy
- **Description**: Local-first TypeScript/Vite web app for planning shoe+sock+activity exposure risk, scoring pressure, shear, moisture, toe-box compression, heel slip, and blister risk with conservative stop rules.
- **Stack**: TypeScript, Vite, Vitest, localStorage
- **Capabilities**: Footwear and sock/interface profiles, exposure plan modeling (distance, terrain, heat, load), foot-zone observation map, deterministic core-mechanics scoring (pressure, shear, moisture, exposure dose), conservative intervention plan with reversible tests, red-flag stop-rule suppression, backup checklist, localStorage persistence
- **Uses**: Hikers/walkers pre-planning footwear choices to prevent blisters (not medical/diabetic care)
- **Integrations**: standalone

### ussyverse/plumiaussy
- **Description**: Deterministic stdlib-only Python CLI turning a bathroom inventory into a conservative toilet-plume hygiene choreography card.
- **Stack**: Python standard library only, pytest
- **Capabilities**: plume-zone scoring by room/toilet/lid/ventilation, object relocation prioritization, illness/guest/potty-training escalation, ventilation cards with caveats, chemical-safety route-away for bleach/ammonia combos, text/markdown/JSON card output, stdin input
- **Uses**: households reducing toothbrush/surface plume exposure without germ panic or health claims
- **Integrations**: standalone

### ussyverse/pokayokeussy
- **Description**: Python GitHub Action that turns repo-based household error logs into Markdown poka-yoke (mistake-proofing) reports with countermeasure cards.
- **Stack**: Python 3.10+, PyYAML, GitHub Actions (action.yml), pytest
- **Capabilities**: recurring failure pattern classification (missing item, look-alike, wrong orientation, skipped reset, interrupted sequence), source-inspection point identification, countermeasure family recommendations (interlocks, visual differentiation, staging trays, reset tokens), safety-boundary escalation for medication/gas/electrical cases, report artifact generation
- **Uses**: households or organizers tracking and mistake-proofing repeated everyday errors via version-controlled logs
- **Integrations**: ussyverse/palpaussy (tactile differentiation countermeasures for look-alike items)

### ussyverse/portmoreussy
- **Description**: Python CLI that applies customs/tariff classification frameworks (GIRs, rules of origin, valuation) to software license compliance.
- **Stack**: Python 3.10+
- **Capabilities**: 6 General Interpretative Rules classification of multi-license works, provenance analysis (substantial transformation, de minimis, value-added), license compatibility checks with usage types, 6-method compliance valuation hierarchy, copyleft-contagion (anti-dumping) assessment
- **Uses**: developers/compliance teams reasoning about dependency license obligations
- **Integrations**: standalone

### ussyverse/portolanussy
- **Description**: Rust terminal app for conservative layover/micro-itinerary planning framed as harbor pilotage (safe-water corridors, tide gates, abort rules).
- **Stack**: Rust, clap (stdlib-only TUI; optional interactive terminal UI)
- **Capabilities**: 0-100 safe-water corridor scoring (reserve, queues, weather, fallbacks), latest-safe start/arrival and time-depth buffers, pilotage card generation (leading marks, shoals, anchorage, abort rules), built-in airport/rail/risky presets, Markdown/JSON export, non-TTY-safe CI summaries
- **Uses**: Travelers stress-testing short connections and tight day-trip windows offline
- **Integrations**: shares the conservative trip-planning domain with watershedussy (trail water carry) and controlaussy (city walks)

### ussyverse/predatorussy
- **Description**: FastAPI web app modeling freelancer workload and client availability with Lotka-Volterra predator-prey ecological dynamics.
- **Stack**: Python, FastAPI, uvicorn, Jinja2, SQLite
- **Capabilities**: ecological dashboard (carrying capacity, refuge score, overpredation/burnout warnings), client CRUD with retainer-refuge marking, project and pipeline tracking, Lotka-Volterra ODE simulation with parameter control and time-series visualization, K-vs-r strategy recommendation, niche partitioning index, trophic cascade/referral-network map, REST API
- **Uses**: Freelancers analyzing client load, burnout risk, and referral networks
- **Integrations**: standalone (finance-domain siblings ussyverse/coreussy, ussyverse/silvaussy)

### ussyverse/pressoraussy
- **Description**: Local-first Rust CLI for conservative orthostatic pacing and standing-day planning using baroreflex-inspired deterministic rules.
- **Stack**: Rust, clap
- **Capabilities**: segment-by-segment standing-pressure scoring, green/yellow/orange/red risk bands, venous-pooling penalty, heat/meal/sleep/illness modifiers, calf-movement and recovery modifiers, red-flag safety override, pacing cards, clinician-ready plain-text export
- **Uses**: people with upright intolerance symptoms planning safe daily activity
- **Integrations**: physiology-pacing domain kin to wetbulbaussy

### ussyverse/probayaussy
- **Description**: Dependency-free C terminal/TUI tool that turns a worried medication side-effect observation into a structured, safety-bounded Naranjo-inspired evidence card with a pharmacist/prescriber message draft.
- **Stack**: C, Makefile, greatest.h
- **Capabilities**: Naranjo-style deterministic evidence scoring and category, red-flag urgent-symptom bypass screen, medication-change-to-symptom timeline card, alternative-cause checklist, dechallenge/rechallenge fact fields, objective-evidence markers, pharmacist/prescriber message generation, interactive questionnaire and demo modes
- **Uses**: non-clinicians organizing side-effect facts for a clearer conversation with a pharmacist or prescriber (no diagnosis or dosing advice)
- **Integrations**: standalone

### ussyverse/proprioceptionussy
- **Description**: A zero-dependency Python CLI giving developers "body schema" awareness of their workspace: passive process sensing, context-switch velocity, muscle-memory alias extraction, and drift detection.
- **Stack**: Python stdlib only
- **Capabilities**: body-schema JSON builder over project roots, /proc and ps passive sensing, shell-history context-switch velocity metrics, repeated-command sequence extraction into shell aliases, drift detection (phantom limbs, branch/venv/env drift), per-limb status inspection
- **Uses**: developers juggling many repos and terminal sessions who want passive workspace awareness
- **Integrations**: mojomast/terrariumussy (referenced as a real adapter for workspace drift), ussyverse/marksmanussy

### ussyverse/prospectaussy
- **Description**: Reusable Go library for prospective-memory cue engineering: turning future intentions into cue-bound if-then plans, external-aid suggestions, and deterministic 0-100 cue risk scores.
- **Stack**: Go (standard library only), JSON-serializable structs
- **Capabilities**: ScoreCue quality scoring with penalties, DesignPlan implementation intentions, printable cue cards, ClassifyMiss omission taxonomy (absent cue, overloaded moment, deliberate skip, etc.), RankIntentions prioritization, AnalyzeLoad risk estimation, RecommendAids (object placement, routine pairing, visual markers)
- **Uses**: local-first apps and developers building reminder/follow-through tools grounded in prospective-memory research
- **Integrations**: shares the learning/memory domain with ussyverse/synapseussy (spaced-repetition knowledge model); standalone otherwise

### ussyverse/proxemaussy
- **Description**: Go TUI/CLI that plans meeting seating from proxemics, producing deterministic seating maps, presence scoring, and facilitation cards.
- **Stack**: Go (stdlib only; module github.com/mojomast/proxema)
- **Capabilities**: room/participant modeling (seats, remote attendees, influence, accessibility, conflicts/affinities), presence scoring (centrality, gaze access, power-seat amplification, fairness gaps, remote demotion), greedy + local-swap optimizer, ASCII room dashboard, printable facilitation card, JSON scenario files
- **Uses**: meeting facilitators arranging inclusive room layouts
- **Integrations**: standalone

### ussyverse/psychraussy
- **Description**: Deterministic Python library for everyday home-moisture planning, converting temperature/humidity readings into psychrometric quantities and conservative recommendations.
- **Stack**: Python 3.9+, stdlib only, pytest
- **Capabilities**: dew point, vapor pressure, absolute humidity, and humidity-ratio calculations, ventilation advice based on absolute humidity (avoiding the RH trap), condensation-risk classification for windows/walls/corners/thermal bridges, moisture-event decay estimates (showers, cooking, laundry), conservative mold-watch heuristics, plain-English recommendation helpers, CLI smoke demo
- **Uses**: households managing humidity, condensation, and mold-watch decisions
- **Integrations**: standalone

### ussyverse/pulmoussy
- **Description**: A Go CLI that converts a three-minute breathing self-check into pulmonology-inspired respiratory-mechanics proxies and a conservative training plan.
- **Stack**: Go (std flag), JSON state, go test
- **Capabilities**: vital-capacity, dead-space, airway-resistance, compliance, diffusion-recovery, V/Q-mismatch, and work-of-breathing proxies from breath-hold/count/timing inputs, limiter-targeted training plans, trend tracking over assessments, JSON demo output, explicit safety/proxy disclaimers
- **Uses**: runners, swimmers, singers, and anxious breathers wanting non-clinical breathing training guidance
- **Integrations**: standalone (wellness-CLI sibling of hospitiaussy and trialwiseussy)

### ussyverse/pupaussy
- **Description**: VS Code extension with a Python metamorphosis engine modeling personal transformation through holometabolous insect stages (egg/larva/pupa/imago).
- **Stack**: TypeScript (VS Code extension), Python 3.10+ engine
- **Capabilities**: transformation-stage classification, imaginal-disc micro-signal tracking, juvenile-hormone and ecdysone indexes, pupal-chamber scoring, histolysis/histogenesis checklists, webview dashboard
- **Uses**: people navigating career transitions, burnout recovery, or identity-level change
- **Integrations**: standalone (same hybrid pattern as metraussy)

### ussyverse/quantumussy
- **Description**: Stdlib-only Python CLI applying real quantum-mechanics math (wavefunctions, density matrices, Bell inequalities, WKB, von Neumann entropy) to distributed-systems behavior analysis.
- **Stack**: Python 3.10+, standard library only
- **Capabilities**: service superposition analysis, Bell inequality entanglement tests on service triplets, measurement-disturbance quantification for health checks, tunneling-path detection from traces, consensus decoherence monitoring, full-mesh density matrix synthesis, unified Quantum State Report
- **Uses**: platform/SRE engineers analyzing canary deployments, hidden coupling, and consensus decay in service meshes
- **Integrations**: calibreussy (measurement-science companion; both quantify instrument trustworthiness of monitoring/test signals)

### ussyverse/queueussy
- **Description**: Textual TUI that applies queueing theory to optimize appointment schedules for solo service providers and small teams.
- **Stack**: Python, Textual TUI
- **Capabilities**: optimal slot duration recommendation, no-show-derived overbooking rate, utilization dashboard with danger zones, balking/revenue-loss estimates, discrete-event scenario simulator
- **Uses**: solo practitioners, salons, clinics, and small teams tuning appointment books
- **Integrations**: standalone

### ussyverse/quorumussy
- **Description**: Local-first Go CLI adapting microbiology quorum sensing into a friendly family/small-group decision helper with veto-aware diagnostics and compromise suggestions.
- **Stack**: Go 1.24, stdlib only, local JSON storage
- **Capabilities**: Quorum threshold with weighted 1-10 autoinducer accumulation, biofilm/polarization (stuck-camp) detection, dealbreaker/veto imbalance diagnostics, stochastic switch/compromise suggestions, family-friendly non-accusatory reports, init/add-member/add-option/vote/status/diagnose/suggest/demo commands
- **Uses**: Families and small groups deciding dinners, activities, and shared plans without conflict escalation
- **Integrations**: equilibriaussy (complementary family negotiation tool from the game-theory angle)

### ussyverse/rabidaussy
- **Description**: Local-first FastAPI web app for animal-bite and possible-rabies-exposure documentation, producing conservative handoff packets for clinicians and public health.
- **Stack**: Python 3.10+, FastAPI, uvicorn, Jinja2, in-memory storage
- **Capabilities**: bite-event intake forms, deterministic conservative rule engine, route-away red flags, rabies call scripts that refuse PEP decisions, animal-control evidence checklists, contact timeline, official contact log, printable handoff report, JSON API
- **Uses**: caregivers, school/camp staff, and clinicians documenting bites and preparing handoffs
- **Integrations**: standalone (same conservative safety-card family as orseraussy, lensaraussy)

### ussyverse/raciaussy
- **Description**: TypeScript CLI that turns household coordination friction into a RACI responsibility board with repair suggestions for role ambiguity.
- **Stack**: TypeScript/Node, Vitest
- **Capabilities**: household JSON plan modeling (members, access, tasks, R/A/C/I assignments), ambiguity detection (no/multiple accountable, over-broad responsible, informed-only affected people), invisible coordinator-load visibility, load reports, RACI matrix rendering, text/markdown/JSON output, sample/demo commands
- **Uses**: roommates, co-parents, caregiving and chosen-family households needing role clarity
- **Integrations**: standalone

### ussyverse/radonaussy
- **Description**: Local-first Go terminal/TUI tool that turns household radon test details into a conservative action board with validity warnings, pCi/L bands, and a printable evidence card.
- **Stack**: Go 1.24, JSON case files
- **Capabilities**: demo/sample/report/interactive modes, test protocol quality checks, normalized pCi/L result-band interpretation, protocol confidence scoring, next-step checklist with retest triggers and mitigation prompts, printable evidence card, JSON output
- **Uses**: homeowners, renters, landlords, buyers/sellers organizing radon test evidence (non-diagnostic, not a substitute for professionals)
- **Integrations**: standalone

### ussyverse/recapturaussy
- **Description**: Deterministic Zig library for small-business capture-recapture demand estimation across messy lead sources (DMs, newsletters, clipboards, referrals), adapting ecological mark/recapture statistics.
- **Stack**: Zig (stdlib only), build.zig
- **Capabilities**: Lead identity normalization (email/phone/handle/name), alias-based manual dedup merges, source overlap matrices, Lincoln-Petersen and Chapman estimates, refusal of zero-overlap pair estimates, conservative multi-source lower bounds, quality warnings (sparse samples, dependent sources, heterogeneity), plain-text decision cards, redacted identity hashes
- **Uses**: Small-business owners estimating true reachable demand from overlapping manual lead lists
- **Integrations**: standalone

### ussyverse/resonaussy
- **Description**: Reusable stdlib-only Go library that models habits as acoustic-like signals to analyze resonance, interference, beat frequencies, damping/burnout, and life "timbre" (published as github.com/mojomast/resonaussy).
- **Stack**: Go (pkg/resona + demo main), no external dependencies
- **Capabilities**: habit signal construction from timed events, time-window aggregation, Pearson/overlap/co-occurrence resonance and interference analysis, cadence beat periods, damping (burnout-risk) detection, harmonic profile summaries with timbre label, plain-language tuning recommendations
- **Uses**: habit-tracking app developers wanting deterministic habit-interaction reasoning without heavy plotting/audio deps
- **Integrations**: standalone

### ussyverse/retouraussy
- **Description**: TypeScript VS Code extension that manages household online returns as a local reverse-logistics pipeline with custody proof and refund tracking.
- **Stack**: TypeScript, VS Code extension API (Memento globalState), Mocha
- **Capabilities**: return stage/RMA status classification, packaging readiness blocker detection, carrier handoff custody-proof checklist scoring, refund reconciliation with late/partial escalation risk, compatible drop-off batching suggestions, Markdown evidence-packet export, tree view and webview dashboard
- **Uses**: individuals managing multiple online returns, refund deadlines, and dispute evidence
- **Integrations**: standalone

### ussyverse/reverbaussy
- **Description**: Local-first FastAPI web app that translates Sabine reverberation heuristics into household room-echo tuning cards.
- **Stack**: Python 3.10+, FastAPI, Uvicorn, Jinja2
- **Capabilities**: qualitative RT60 estimation from room volume/absorption, echo vs. noise-masking vs. device issue separation, reflection-path identification (floor bounce, flutter echo), ranked renter-safe treatment suggestions, web UI + JSON API + CLI analyzer
- **Uses**: remote workers, renters, musicians fixing hollow-sounding rooms conservatively
- **Integrations**: standalone

### ussyverse/reverseoracleussy
- **Description**: Python CLI that generates and evaluates counterfactual implementations of past architectural decisions using LLM generation plus test/metric comparison.
- **Stack**: Python, click, httpx, PyYAML (OpenAI-compatible LLM API)
- **Capabilities**: Decision-point marking in git history (`mark`/`list-marks`), decision context reconstruction, LLM counterfactual code generation and per-commit temporal evolution, test-runner/metrics evaluation, baseline-vs-counterfactual `compare`, text/HTML/JSON decision audit reports, YAML config
- **Uses**: Teams auditing whether major architectural choices (e.g., Redis vs Memcached) paid off
- **Integrations**: complements driftnetussy and fatigueussy in the code-analysis toolchain; indexed in mojomast/ussyverse PROJECT_INDEX

### ussyverse/rheoussy
- **Description**: Rust terminal app diagnosing cooking consistency problems with a practical rheology model, mapping texture failures to viscosity bands and correction plans.
- **Stack**: Rust, clap, prompt-driven TUI with non-TTY demo fallback
- **Capabilities**: texture profiles for sauce/dough/batter/custard/emulsion/foam/gel, symptom diagnosis (runny, stiff, broken, gummy, grainy, lumpy, tough, weeping), centipoise viscosity-band estimation with hydration/protein/temperature/shear effects, ingredient and technique correction plans, shear/rest/temperature advice for Newtonian through yield-stress behavior, low-dose xanthan hydrocolloid calculator
- **Uses**: Home cooks fixing sauces, doughs, and gels with repeatable texture targets
- **Integrations**: standalone (kitchen cluster with ussyverse/maillaraussy, ussyverse/fermentussy)

### ussyverse/riptidaussy
- **Description**: Offline Go TUI tool that turns observed beach conditions into conservative rip-current swim decision cards.
- **Stack**: Go 1.22, stdlib only
- **Capabilities**: six decision categories (enter-with-limits to emergency), conservative safety model over flags/lifeguards/surf/structures, rip-current escape script, bystander rescue boundaries, family watcher plan, no-debate exit triggers, interactive terminal wizard, JSON plan assessment, ANSI-colored cards
- **Uses**: beachgoers and families making pre-swim go/no-go decisions
- **Integrations**: outdoor-safety decision-card domain kin to slabwiseussy

### ussyverse/ritualaussy
- **Description**: Local-first Go web app (stdlib only) for designing and testing household transition rituals (bedtime, arrivals, handoffs, screen-off) using ethology concepts: sign stimuli, fixed action patterns, habituation, sensitization, and consent.
- **Stack**: Go 1.24 standard library only
- **Capabilities**: ritual designer/analyzer HTML form, `/analyze` and `/api/analyze` JSON endpoints, cue-reliability scoring, belonging-effect score, habituation/sensitization risk detection, consent/opt-out and coercion warnings, five sample transition fixtures at `/sample`, practical review cards, review logging
- **Uses**: families, roommates, and co-parents designing healthy recurring transition rituals without apps/accounts/cloud
- **Integrations**: standalone

### ussyverse/rosettussy
- **Description**: A zero-dependency Python CLI that "deciphers" functions as trilingual inscriptions (docstring, type signature/AST, runtime trace) and scores documentation quality with a Champollion Score.
- **Stack**: Python 3.9+, stdlib only (inspect, ast, sys.settrace)
- **Capabilities**: trilingual parsing and divergence detection (missing params, unaccounted returns, docstring lacunae), semantic cartouche extraction, Champollion Score with CI threshold gating, UTF-8 tablet and JSON rendering, safe single-call runtime tracing
- **Uses**: teams enforcing documentation quality in CI; API authors auditing doc drift
- **Integrations**: mojomast/terrariumussy (health signals), ussyverse/kompressiussy

### ussyverse/rotationussy
- **Description**: VS Code extension that maps crop-science ideas onto solopreneur business operations: soil fertility, harvest index, monoculture risk, rotation plans, fallow, and growing-degree-day lead tracking.
- **Stack**: TypeScript, VS Code extension API, Mocha/Node tests (assigned Nim slot implemented in TS per README note)
- **Capabilities**: soil fertility/recovery map (exponential rest recovery), harvest-index ranking (revenue per hour adjusted by energy), monoculture alert above 50% client revenue share, seasonal rotation plan avoiding 3 consecutive same-service seasons, fallow recommendations, companion-bundle Jaccard cross-sell scoring, growing degree days for lead maturity, Markdown plan export
- **Uses**: solopreneurs and freelancers diversifying client base and planning sustainable service scheduling
- **Integrations**: shares solopreneur business-operations domain with ussyverse/allomaussy (business scaling diagnostics); standalone otherwise

### ussyverse/rulaiaussy
- **Description**: Rust GitHub Action and CLI producing RULA/REBA-inspired posture action reports from JSON/CSV/TXT/Markdown task cards.
- **Stack**: Rust, GitHub Actions composite action (action.yml)
- **Capabilities**: simplified RULA/REBA-style body-region scoring, exposure modifiers (static duration, repetition, force/grip, vibration), Markdown/JSON reports with prioritized reversible experiments, safety route-aways for medical red flags, local CLI and CI modes
- **Uses**: remote workers, crafters, and gamers triaging workstation posture risks
- **Integrations**: standalone (CI-action pattern shared with obscuraussy)

### ussyverse/saccadaussy
- **Description**: Rust library and thin CLI for lost-item recovery that turns "where are my keys/wallet/medication" into an explainable visual-search pathway.
- **Stack**: Rust (Cargo)
- **Capabilities**: target-template modeling (visual attributes, container/surface cues, alternate appearances, inside/covered flags), deterministic zone scoring (prior probability, clutter, visibility, occlusion, normal-home, last-context match), fixation route planning with one-pass scan steps and stop conditions, anti-revisit memory, interventions (lighting changes, staging surfaces, container emptying, shared-space scripts), urgency escalation guardrails for medication/ID/security keys/theft, per-step rationales citing visual-search principles
- **Uses**: people making household item searches less random and panic-driven
- **Integrations**: standalone

### ussyverse/saponinussy
- **Description**: A local-first FastAPI web app that diagnoses household dishwashing failures into deterministic surfactant-chemistry mechanism cards with safety guardrails.
- **Stack**: Python, FastAPI, Pydantic, Jinja templates, pytest/httpx
- **Capabilities**: failure diagnosis (greasy pans, stained plastic, cloudy glass, gaskets, filter grease), mechanism risk scoring (wetting, emulsification, redeposition, residue), one-variable trial suggestions, reusable protocols, HTML form plus JSON API endpoints, chemical-mixing hard stops (bleach/ammonia/acids), material-safety guardrails
- **Uses**: households troubleshooting dish cleaning without brand recommendations
- **Integrations**: standalone (household-chemistry sibling of calcaraussy descaling planner)

### ussyverse/satiaussy
- **Description**: Rust CLI for sensory-specific satiety meal-variety and snack-shelf planning, building a deterministic satisfaction map.
- **Stack**: Rust (clap), assert_cmd tests
- **Capabilities**: sensory profile scoring (taste/texture/temp/novelty/visibility/friction), variety-loop grazing-risk detection, meal satisfaction-gap analysis, text/JSON reports (body-neutral; no calorie counting or diet prescription)
- **Uses**: body-neutral meal/snack planners avoiding monotony and mindless grazing
- **Integrations**: pairs with calderaussy (meal-prep planning)

### ussyverse/scaffoldussy
- **Description**: Python CLI and composite GitHub Action that reads learner skill/task/session files and generates Vygotsky ZPD (Zone of Proximal Development) Markdown learning reports in CI.
- **Stack**: Python, pyproject, GitHub composite Action (action.yml)
- **Capabilities**: ZPD fit scoring (too_easy/zpd/too_hard), scaffold support recommendations with fading after repeated success, regression/internalization tracking from session history, practice-plan generation, JSON/CSV loaders, auto-generated SCAFFOLD-REPORT.md on push/PR
- **Uses**: repos or courses storing learning analytics as data and wanting CI-generated progress reports
- **Integrations**: latticeussy (learning-domain companion; knowledge-structure + practice planning)

### ussyverse/scalariaussy
- **Description**: Rust TUI and report generator for household ladder setup decisions, producing conservative pre-climb safety cards (angle, footing, duty rating, route-away conditions).
- **Stack**: Rust
- **Capabilities**: 4:1 ladder angle check, surface/footing and top-support assessment, ladder type suitability, side-reach and duty-rating checks, three-point contact guidance, stop-condition gating, helper handoff checklist, text/JSON reports in headless mode
- **Uses**: renters, homeowners, decorators, and caregivers doing household reach tasks
- **Integrations**: standalone

### ussyverse/scansionussy
- **Description**: Offline Rust CLI that inspects the rhythm of creative writing (prose, poems, lyrics, speeches) via prosody-inspired stress maps, breath groups, and sound-device detection.
- **Stack**: Rust, clap 4
- **Capabilities**: Heuristic syllable and stress-pattern mapping, breath-group segmentation with overload warnings, cadence-ending and rhythm-tail detection, caesura/enjambment opportunity flags, alliteration/assonance/consonance cluster detection, non-generative revision prompts, text/markdown/json output formats, file/stdin input
- **Uses**: Writers revising drafts by ear for rhythmic pressure points
- **Integrations**: standalone

### ussyverse/seismicussy
- **Description**: Relationship-health CLI that models conflict accumulation and rupture between partners using seismology concepts like fault lines, tectonic stress, and aftershocks.
- **Stack**: Python 3.10+, stdlib-only, SQLite-free JSON storage
- **Capabilities**: fault-line mapping for recurring topics, earthquake (argument) logging with Richter magnitudes, aftershock tracking, external stressor logging, relationship health-score analytics
- **Uses**: couples tracking conflict dynamics and warning signs outside of therapy
- **Integrations**: standalone (emotional-domain sibling of inferaussy)

### ussyverse/semaphoraussy
- **Description**: Local Zig web app that scores gift/favor candidates on fit evidence, signal clarity, burden risk, and proportionality to produce a printable gift-fit card.
- **Stack**: Zig 0.14+, stdlib HTTP server
- **Capabilities**: four-axis gift-fit scoring, mismatch and burden warnings, lower-burden alternative suggestions, embedded dashboard, JSON API (`/api/analyze`, `/api/sample`, `/api/defaults`), CLI sample mode, local-only privacy (no LLM or shopping APIs)
- **Uses**: people choosing thoughtful, low-burden gifts and gestures for friends and family
- **Integrations**: standalone

### ussyverse/sentinelussy
- **Description**: Code-governance tool applying the Negative Selection Algorithm from artificial immune systems — learning a codebase's "self" profile from its code/git history and flagging anomalous patterns with generated detectors.
- **Stack**: Python stdlib only (pip, pyproject.toml)
- **Capabilities**: project initialization and self-profile training (function/line granularity, optional git history), negative-selection detector generation with affinity thresholds, anomaly detection against learned norms, detector persistence across sessions
- **Uses**: teams wanting codebase-specific governance that emerges from the code itself rather than generic lint rules
- **Integrations**: pairs naturally with assayussy (code grading/composition analysis) as complementary static analysis

### ussyverse/septicaussy
- **Description**: Local FastAPI web app for household septic drainfield hydraulic-load pacing: profile intake, conservative daily load estimates, laundry surge spreading, and service-history export.
- **Stack**: Python, FastAPI, uvicorn, pytest
- **Capabilities**: Household septic profile intake, deterministic hydraulic-load estimation, route decision cards (pacing, reduce-and-spread, leak investigation, urgent professional handoff), laundry spreader day-by-day scheduling, warning-sign override logic, drainfield protection reminders, disposal/solids risk card, plain-text service-history export, JSON assessment API
- **Uses**: Homeowners/renters/property managers pacing wastewater load and documenting septic care boundaries
- **Integrations**: standalone

### ussyverse/seralaussy
- **Description**: Go library for planning household recovery after disruption (illness, travel, grief) using ecological succession stages across life-domain "patches" (published as github.com/mojomast/seralaussy).
- **Stack**: Go library + optional demo CLI under cmd/serala
- **Capabilities**: DisturbanceProfile and PatchState modeling, stage classification (bare substrate to canopy), SuccessionAction rule packs, action ranking by stage fit/feasibility/facilitation, overreach ("climax cosplay") guard plans, multi-patch BuildRecoveryPlan with handoff criteria
- **Uses**: apps helping users stage household resets without catch-up-all-at-once overload
- **Integrations**: standalone

### ussyverse/seralussy
- **Description**: Classifies git repository modules into ecological successional stages (pioneer/seral/climax/disturbed) and prescribes stage-appropriate governance rules.
- **Stack**: Python 3.10+, click, rich, PyYAML, pytest
- **Capabilities**: module stage detection from git metrics (age, churn, contributors, test ratio), stage-appropriate governance prescription generation, governance diff between stages, disturbance (refactor/reset) event detection, successional timeline with trajectory projection, continuous stage-transition watching, .seral config initialization
- **Uses**: engineering teams applying differentiated review/merge governance per module maturity
- **Integrations**: ussyverse/dosemateussy and ussyverse/gridironussy (same git-history/dependency analysis domain)

### ussyverse/shewhartaussy
- **Description**: Go CLI bringing statistical process control (XmR charts) to small-business metrics to distinguish common-cause variation from real signals.
- **Stack**: Go 1.24, CLI, CSV input
- **Capabilities**: XmR control-limit computation from stable baseline, transparent run-rule signal detection, support for count/amount/rate/duration metric types, process-change and intervention markers, overcontrol warnings, plain-language business signal log export
- **Uses**: small-business owners deciding whether metric changes justify action on pricing/staffing
- **Integrations**: pairs conceptually with ussyverse/benfordaussy (both are conservative anomaly-triage tools for small-business bookkeeping/metrics CSVs)

### ussyverse/sialiaussy
- **Description**: Rust TUI/CLI for conservative salivary-gland swelling (possible sialolithiasis) triage with red-flag routing and clinician-ready exports.
- **Stack**: Rust, ratatui, crossterm, clap, serde/serde_json
- **Capabilities**: Deterministic episode rule engine, red-flag gate (fever, pus, airway, neurologic, etc.), meal-trigger pattern scoring, gland-location lane mapping (submandibular/parotid/oral floor/lookalike), conservative action ladder, safe home-support checklist (hydration, warm compress), no-probing safety messaging, text/JSON clinician reports, non-TTY fallback
- **Uses**: Households deciding whether jaw/cheek swelling needs urgent dental/ENT care
- **Integrations**: sibling conservative health-triage tools ceruminaussy and palynoussy

### ussyverse/silvaussy
- **Description**: VS Code extension treating personal financial assets as a managed forest with sustainable yield, rotation planning, and Monte Carlo stress testing.
- **Stack**: TypeScript, VS Code extension API, webview charts, Monte Carlo simulation
- **Capabilities**: asset/goal/income-stream tracking, sustainable-yield safe-spend calculation (logistic growth, r = g/2 withdrawal rate), rotation-age planner for lump-sum goals, Herfindahl basal-area concentration map, Monte Carlo winter-hardiness ruin test after 30% shock, forest health score in status bar, clear-cut overspending warning
- **Uses**: Personal-finance users who live in VS Code and want sustainable-withdrawal planning
- **Integrations**: ussyverse/coreussy and ussyverse/predatorussy (personal finance data/analysis domain)

### ussyverse/slabwiseussy
- **Description**: Offline-first TypeScript web app for winter trip decision hygiene, producing conservative pre-committed avalanche turnaround cards.
- **Stack**: TypeScript, Vite, Vitest, jsdom, PWA assets
- **Capabilities**: hazard stack engine (snow, wind, warming, visibility, terrain, group vulnerability), FACETS-style human-factor trap panel, conservative plan classes, field-check mode mapping red flags to no-debate actions, printable trip cards, JSON/CSV export, local browser storage
- **Uses**: hikers, snowshoers, families, and clubs planning winter backcountry trips
- **Integrations**: outdoor-safety decision-card domain kin to riptidaussy

### ussyverse/snapshotussy
- **Description**: Python CLI that brings Smalltalk-style image-based persistence to development, freezing the entire development state (branch, files, environment, notes, mental context) into named snapshots that can be listed, peeked, diffed, pruned, exported, and thawed back on demand.
- **Stack**: Python (setuptools), pytest
- **Capabilities**: `snapshot save` with mental-context notes, `snapshot load` with context reminder, `snapshot new` clean environments, `snapshot list` (sort/verbose), `snapshot peek` without loading, `snapshot diff` between two states, `snapshot prune` by age/keep-last with dry-run, export/import
- **Uses**: developers recovering full context quickly after task switching or interruptions
- **Integrations**: standalone

### ussyverse/solaraussy
- **Description**: A Python GitHub Action and CLI that converts event-level UV exposure details (UV index, exposed zones, sunscreen, reflections) into a conservative sun-protection report.
- **Stack**: Python, GitHub Actions (action.yml), JSON/YAML I/O
- **Capabilities**: UV intensity categorization, proceed/shift/route-away recommendations, body-zone coverage mapping, FDA-based sunscreen amount estimation, 15-minute pre-application and reapplication clocks, reflection/altitude/SPF warnings, route-away safety boundaries
- **Uses**: families, coaches, hikers, outdoor workers planning sun safety; repo-embedded planning in CI workflows
- **Integrations**: standalone (same local-first safety-tool family as egressaussy and patinaussy)

### ussyverse/soluteussy
- **Description**: Interactive Vite + TypeScript web app that explains personal budgeting through solution chemistry: income as solvent, expenses as solutes, overspending as precipitation/debt, savings as crystals.
- **Stack**: TypeScript, Vite, Vitest, framework-free domain model
- **Capabilities**: beaker dashboard with saturation colors, supersaturation/debt-precipitation alerts, Avrami-style savings crystallization tracker, colligative damage model for recurring expenses, Raoult dilution model for large fixed expenses, scenario sliders for what-if budgets
- **Uses**: individuals learning budgeting concepts through an interactive chemistry metaphor
- **Integrations**: standalone

### ussyverse/somnaussy
- **Description**: Deterministic Python library for educational sleep-pressure planning using a simplified two-process (Process S/C) sleep model.
- **Stack**: Python, dataclasses, pytest
- **Capabilities**: homeostatic sleep-pressure computation, coarse circadian chronotype modeling, caffeine masking effects, nap tradeoff analysis, bedtime feasibility day cards, scenario comparison, Markdown/JSON rendering, medical red-flag route-aways
- **Uses**: individuals planning naps, caffeine timing, and bedtimes
- **Integrations**: standalone

### ussyverse/sonantaussy
- **Description**: Rust library with a demo CLI for local-first psychoacoustic triage of apartment and dense-neighborhood noise problems.
- **Stack**: Rust (Cargo)
- **Capabilities**: NoiseEvent/PsychoacousticFeatures models (tonality, impulsiveness, intermittency, low-frequency, vibration, sharpness, unpredictability), sound-class and transmission-pathway classification (airborne speech/media, impact footfall, low-frequency bass, mechanical tonal, plumbing/flanking, exterior, alert), annoyance scoring beyond loudness, masking-feasibility assessment, least-escalatory intervention ladder, neutral documentation packet generation, safety/ethics guardrails (no covert recording, no retaliation, urgent routing for alarms/violence)
- **Uses**: apartment dwellers documenting noise issues and choosing de-escalatory next steps
- **Integrations**: standalone

### ussyverse/sorpraussy
- **Description**: A Python library for packed-lunch texture planning using food-sorption/moisture-migration science, with autopsy-based threshold calibration.
- **Stack**: Python (pyproject), pytest
- **Capabilities**: component classification as moisture donors/absorbers/barriers/buffers/vapor producers, sogginess/crispness/drying/condensation risk scoring, packing-option comparison, morning-checklist export, household autopsy outcome-log calibration, safety overrides for allergen/spoilage/raw-leakage concerns, built-in fixture lunches (tomato sandwich, hummus wrap, yogurt-granola, etc.)
- **Uses**: households packing lunches that stay texturally good for hours
- **Integrations**: standalone (food-science sibling of saponinussy)

### ussyverse/sortariaussy
- **Description**: Offline Go terminal app for designing personal organization taxonomies via open/hybrid card sorting and retrieval drills.
- **Stack**: Go 1.24, standard library
- **Capabilities**: card/pile model, sorting sessions with confidence, similarity/ambiguity scoring, tree-test retrieval drills, taxonomy report/export (text/JSON/CSV) with "when in doubt" rules, interactive TUI
- **Uses**: households organizing receipts, papers, recipes, or physical bins into findable categories
- **Integrations**: standalone

### ussyverse/speleoussy
- **Description**: Go CLI/GitHub Action that models home clutter accumulation with speleology, producing karst maps, drip forecasts, speleothem growth projections, and cave-in warnings from repo-stored data files.
- **Stack**: Go 1.24, gopkg.in/yaml.v3, GitHub Action
- **Capabilities**: YAML/JSON clutter data parsing, karst-map report generation (Markdown/JSON), drip-rate and speleothem-growth projections, cave-in/traffic warning scoring, chamber/surface modeling, CI-integrated report writing
- **Uses**: households tracking clutter creep as versioned data and wanting periodic reports
- **Integrations**: apoptosisussy (complementary decluttering decision engine for the same home-organization domain)

### ussyverse/stabilonussy
- **Description**: Local-first Go CLI for home medicine storage and expiration triage, scoring storage-stability risk and printing pharmacist-review and disposal reports.
- **Stack**: Go (stdlib only)
- **Capabilities**: JSON medicine inventory with add/list/report/sample commands, stability risk scoring (heat, humidity, light, packaging, opened date), storage location triage, pharmacist-review scripts, disposal batching guidance
- **Uses**: households organizing medicine cabinets, moving, or preparing for pharmacist review
- **Integrations**: standalone

### ussyverse/stellarussy
- **Description**: Python CLI gratitude and life-milestone tracker that frames reflection as stellar evolution (main sequence, red giant, supernova, white dwarf) with a personal Hertzsprung-Russell diagram.
- **Stack**: Python, local JSON storage, pytest
- **Capabilities**: Phase-tagged journal entries (intensity/impact/pressure/created), light/heavy-element gratitude tagging, supernova transformation events with before/after identity shifts and element synthesis, phase detection, terminal H-R diagram rendering, nucleosynthesis scoring chain, Markdown report generation, demo mode, custom data files
- **Uses**: Individuals wanting a deeper metaphorical framework for gratitude and transformation journaling
- **Integrations**: immunussy (sibling wellness-journaling tool)

### ussyverse/stemmaussy
- **Description**: Python CLI that reconstructs the family tree of code variants using philological/textual-criticism methods, without requiring git history.
- **Stack**: Python 3.10+, stdlib-only, SQLite persistence, Graphviz DOT export
- **Capabilities**: variant collation tables, stemma tree building from shared errors, error-vs-intent classification (lectio difficilior, consistency scoring), archetype reconstruction, contamination detection, DOT/text export
- **Uses**: developers and researchers analyzing copy-paste code genealogy across divergent file variants
- **Integrations**: standalone

### ussyverse/stenographussy
- **Description**: Python security CLI that detects steganographic attacks in source code (zero-width chars, homoglyphs, RTL/Trojan Source, whitespace and comment steganography).
- **Stack**: Python 3.8+ (stdlib), pytest, GitHub Actions CI
- **Capabilities**: five scanners (zero-width, homoglyph, RTL/bidi, whitespace entropy, comment steganography), context-aware risk scoring, git-diff scanning of changed lines only, table/JSON/SARIF output for GitHub Code Scanning, stdin scanning, configurable entropy threshold, CI exit codes
- **Uses**: code reviewers, security teams, and CI pipelines hardening repos against invisible-source attacks
- **Integrations**: its SARIF output feeds GitHub code scanning on any repo; pairs with clavisussy for classifying what it finds

### ussyverse/stenography
- **Description**: Python CLI (also packaged as a GitHub composite Action) that scans source code for invisible Unicode attacks — zero-width characters, BiDi overrides, homoglyphs, and confusable identifiers.
- **Stack**: Python 3.9+, Click, Rich; GitHub Actions composite action
- **Capabilities**: zero-width and BiDi control-character detection, homoglyph substitution detection via confusables data, confusable-identifier/shadowing detection, "what you see vs what the compiler sees" BiDi visualization, JSON and git-diff-mode output for CI
- **Uses**: security-conscious teams scanning for Trojan Source (CVE-2021-42574)-style supply-chain attacks in CI
- **Integrations**: can guard any repo's CI; pairs with vergentaussy (the other ussyverse GitHub Action in this batch) as a repo-health action set

### ussyverse/sterilaussy
- **Description**: Local-first Python terminal app for creating sterile-cockpit household critical-task cards (medication handling, hot oil, ladder work, etc.) with no-interruption windows, readback steps, and violation review.
- **Stack**: Python (stdlib), pytest, JSON file storage
- **Capabilities**: Built-in templates (medication, hot oil, ladder, vehicle departure, blades, electrical, document signing), custom card creation with trigger/exit conditions, essential vs nonessential interruption rules, deterministic readiness scoring engine, session start/log-violation workflow, briefing scripts, Markdown/JSON export, local data directory
- **Uses**: Households structuring attention and communication around high-consequence routine tasks
- **Integrations**: standalone

### ussyverse/stoichussy
- **Description**: Go terminal dashboard modeling a monthly budget as a chemical stoichiometry/equilibrium problem (income reactants, expense products, catalysts, goal compounds).
- **Stack**: Go (pkg/stoich + pkg/tui), stdlib terminal UI
- **Capabilities**: balanced-equation budget view with coefficients, perturbation what-ifs (--perturb category --delta), catalyst and activation-energy goal ladders, deterministic demo dashboard
- **Uses**: people exploring budget rebalancing heuristics locally with no bank APIs
- **Integrations**: standalone

### ussyverse/stomataussy
- **Description**: Local-first Python library that plans notification permeability using plant guard-cell physiology, treating communication channels as openable/closable pores.
- **Stack**: Python 3.10+, pytest
- **Capabilities**: per-channel pore state planning (open, narrowed, pulse-open, emergency-only, drought-closed), turgor capacity computation from recovery/stress/meeting load, vapor-pressure-deficit environmental dryness modeling, osmotic message-pull scoring, water-use efficiency analysis, drought-mode detection, privacy-preserving signal inputs (no message contents)
- **Uses**: caregivers, freelancers, students, and coordinators tuning notification boundaries across life channels
- **Integrations**: standalone

### ussyverse/stormussy
- **Description**: Terminal simulation game where severe-weather meteorology is the formalism for distributed-systems failure modes across a procedural service mesh.
- **Stack**: Python 3.9+, stdlib only
- **Capabilities**: procedural service-mesh generation, Doppler-radar sweeps showing rotation/vorticity, mesocyclone scanning, tornado cascade tracking with EF ratings, hail/retry-burst monitoring, storm warnings, weather-to-failure-mode mapping (supercells=feedback loops, surge=memory flooding)
- **Uses**: engineers/players learning distributed failure patterns through meteorology metaphors
- **Integrations**: shares severe-weather + distributed-systems domain with ussyverse/vorticaussy (tornado shelter cards) and failure-simulation domain with ussyverse/ludonussy

### ussyverse/stratagitussy
- **Description**: Python CLI that visualizes git history through a geological metaphor: commits as strata, file types as minerals, deleted code as fossils, rebases as unconformities.
- **Stack**: Python stdlib only, git CLI, pytest
- **Capabilities**: `survey` geological report, ASCII stratigraphic cross-section rendering, `excavate` fossil (deleted code) detection with lifespans, unconformity detection (rebase/squash/cherry-pick), fault-line (force push) detection, `carbon-date` enhanced blame, mineral legend and stability tiers
- **Uses**: Developers exploring repo history and archaeology in a terminal
- **Integrations**: pairs with fatigueussy and driftnetussy (repo-health analysis) and mushinussy (session context); indexed in mojomast/ussyverse PROJECT_INDEX

### ussyverse/strataussy
- **Description**: Python CLI applying geological metaphors to dependency analysis, running behavioral probes to score API stability across versions.
- **Stack**: Python, pip-installable `strata` CLI
- **Capabilities**: lockfile scanning (npm/yarn/pip/Pipfile/poetry), Bedrock behavioral-stability score (0-100), seismic-hazard frequency metric, fault-line detection between stable and unstable API regions, erosion/deprecation tracking, stability tiers (Bedrock/Stable/Hazard/Quicksand/Deprecated)
- **Uses**: Developers and CI pipelines assessing whether dependencies are safe to rely on beyond version numbers
- **Integrations**: standalone (CI analysis tooling like ussyverse/chainletussy)

### ussyverse/stratumussy
- **Description**: VS Code extension that reframes the workday as a stratigraphic core sample with geological layers for activity blocks, intrusions, and deep-work fossils.
- **Stack**: TypeScript, VS Code extension API, Mocha
- **Capabilities**: day sampling/loading/analysis, manual work-layer entry, stratigraphic core webview, unconformity detection (>15 min gaps), fossil extraction (90+ min depth-4/5 blocks), compression and fragmentation metrics, excavation plan for next schedule, Markdown report export
- **Uses**: knowledge workers analyzing deep-work patterns inside VS Code
- **Integrations**: shares VS Code extension form with haptenaussy

### ussyverse/sumpaussy
- **Description**: Local-first Rust/Axum web app that turns basement sump pump details (pit geometry, float spread, pump curve, head, discharge route, backup power) into conservative storm-readiness cards with route-away safety gates.
- **Stack**: Rust, Axum, embedded HTML dashboard
- **Capabilities**: `POST /api/analyze` readiness cards (capacity-at-head, pit-buffer minutes, discharge route, float/check-valve, backup), conservative pump-curve interpolation with unknown-capacity labels, route-away gates for sewage/flooding-near-electricity/damaged cords/radon uncertainty, `POST /api/export` plumber/landlord/insurer-ready Markdown packet, sample fixture endpoint, embedded dashboard
- **Uses**: homeowners, renters, cabin owners, and caregivers inspecting sump pump storm readiness without overclaiming safety
- **Integrations**: standalone (home-safety sibling of crackwiseussy, effusaussy)

### ussyverse/symbiosisussy
- **Description**: A FastAPI web app that models community garden plots as ecosystems, recommending mutualistic plant pairings, warning of allelopathic conflicts, and planning succession across seasons.
- **Stack**: Python, FastAPI, Pydantic, Jinja2, pytest
- **Capabilities**: companion-planting database (~40 plants), mutualism/allelopathy analysis, mycorrhizal network tracking between plots, succession planning, keystone species and trophic analysis, garden/plot/plant CRUD endpoints, HTML dashboards
- **Uses**: community gardeners and horticulture educators planning polyculture beds
- **Integrations**: standalone

### ussyverse/synapseussy
- **Description**: VS Code extension modeling your knowledge as a neural network with biologically-inspired plasticity rules (Hebbian strengthening, STDP, LTD, depletion, myelination, pruning).
- **Stack**: TypeScript, VS Code extension API, Mocha tests (xvfb headless support)
- **Capabilities**: topic and prerequisite graph, study-session logging with multi-topic sessions, Hebbian co-activation strengthening, STDP order-dependent prerequisite weighting, exponential LTD decay, neurotransmitter depletion/recovery, myelination at 50+ reviews, synapse pruning below weight 0.05, rest-based consolidation, force-directed concept map webview, study recommendations
- **Uses**: self-directed learners tracking interdependent topics and optimizing review scheduling
- **Integrations**: pairs with ussyverse/prospectaussy (prospective-memory cue engineering) for cue-based study reminders; standalone otherwise

### ussyverse/syntropussy
- **Description**: Python cross-language behavioral fuzzing tool that compiles/probes Python code under esolang-inspired semantic twists to surface hidden execution assumptions.
- **Stack**: Python (AST transformers, CLI), optional Rich, INTERCAL proof-of-concept backend
- **Capabilities**: randomize-iteration probe, shuffle-evaluation-order probe, alias-state probe, nondeterministic-timing probe, project scanning, diff across probes with divergence explanations, AST assumption scanner, INTERCAL COME FROM backend
- **Uses**: developers and researchers finding order/aliasing/timing dependencies in Python code
- **Integrations**: standalone (code-quality domain; complements memetixussy pattern analysis)

### ussyverse/taktussy
- **Description**: Rust CLI supply-chain logistics optimizer for solopreneurs that models freelance workload as a factory to compute sustainable rhythms, buffers, and batch sizes.
- **Stack**: Rust (Cargo)
- **Capabilities**: business initialization (name, weekly capacity, hourly revenue), service catalog with setup/holding costs, weekly demand recording, takt-time calculation, bullwhip-effect metric, safety stock and reorder point, kanban sizing, economic order quantity, throughput and status dashboards, JSON state persistence in ~/.takt/state.json with env override
- **Uses**: freelancers planning batch sizes, buffers, and sustainable work cadence
- **Integrations**: shares lean-operations domain with ussyverse/andoniaussy

### ussyverse/tangleaussy
- **Description**: A local FastAPI web app that classifies household tangles (necklaces, earbuds, yarn, lights, drawstrings) and generates calm, safe knot-release plans with SVG diagrams.
- **Stack**: Python, FastAPI, Jinja/SVG, pytest/httpx
- **Capabilities**: tangle classification (loop nest, overhand knot, twist, snag, jam, yarn collapse, drawstring retrieval, unsafe/escalate), 2-8 step release plans with reversible actions and stop conditions, tension-increase warnings, largest-safe-loop and free-end routing guidance, accessible SVG diagrams, Markdown export, JSON API plus mobile-friendly HTML UI, hazard escalation
- **Uses**: households untangling jewelry, cords, and yarn without damage
- **Integrations**: standalone (household-domain sibling of saponinussy, calcaraussy)

### ussyverse/taphonussy
- **Description**: Rust GitHub Action and CLI producing taphonomy-inspired preservation triage reports (decay-risk scoring, context integrity) for keepsake inventory files in a repo.
- **Stack**: Rust (clap, serde, csv, toml), GitHub Actions
- **Capabilities**: parses JSON/CSV/TOML/TXT/MD inventories, scores risk pathways (moisture, light, abrasion, context loss), warns against irreversible actions (laminating, gluing), recommends minimal-intervention actions, Markdown/JSON reports as PR comments/artifacts
- **Uses**: households preserving memory objects via repo-based workflows
- **Integrations**: standalone (same repo-action pattern as lanugoussy)

### ussyverse/tarotussy
- **Description**: Pure-Python CLI treating Architecture Decision Records as probability distributions and running Monte Carlo "spreads" to predict cascading architectural risk.
- **Stack**: Python stdlib only, ADR markdown with YAML frontmatter
- **Capabilities**: decision-card outcome probabilities, cascade and interaction modeling, five-card readings (Tower risk cluster, Wheel cascade patterns, Hermit orphan decisions, Star risk reducers, Death decisions to reverse), Monte Carlo simulation over interdependent ADRs
- **Uses**: architects and tech leads making ADR risk tangible and communicable before incidents
- **Integrations**: calibreussy, ichniteussy (fellow ussyverse code-quality/risk analyzers)

### ussyverse/tectonicussy
- **Description**: Go CLI that models a house as tectonic plates to track maintenance stress, predict failures (elastic rebound), find overdue maintenance (seismic gaps), and show aftershock cascades.
- **Stack**: Go
- **Capabilities**: house profile init, per-plate stress accumulation with climate adjustment, repair reset, overdue-gap listing, failure date prediction, cascade/aftershock analysis per plate, ASCII status diagram
- **Uses**: homeowners maintaining roofs, HVAC, plumbing, and other house systems
- **Integrations**: ussyverse/stabilonussy (home medicine triage), ussyverse/legionaussy (plumbing stagnation) — same household-maintenance domain

### ussyverse/telegraphaussy
- **Description**: Python CLI applying 19th-century telegraphy and Signal Corps math (attenuation budgets, Shannon-Hartley, Hamming codes, precedence queuing) to data-pipeline fidelity and capacity analysis.
- **Stack**: Python stdlib only (custom YAML parser), zero dependencies
- **Capabilities**: Multiplicative attenuation/fidelity decay budgets, relay-chain series/parallel reliability models, Shannon-Hartley throughput ceilings, M/G/1 message-precedence priority queue optimization, FEC-vs-ARQ (Hamming) retry decision framework, Dead Letter Office DLQ health scoring, combined dashboard, YAML/JSON topology loading
- **Uses**: Data/platform engineers quantifying pipeline degradation, reliability, and retry-vs-redundancy tradeoffs
- **Integrations**: aquiferussy, gamutussy (sibling data-pipeline analysis tools)

### ussyverse/tellussy
- **Description**: Two-phase terminal archaeological game where you build an ancient settlement across eras, then excavate and interpret your own buried ruins on the same site.
- **Stack**: Python 3.10+, stdlib-only, terminal UI
- **Capabilities**: builder phase with buildings/residues across 3-5 eras, excavator phase with layered digging, artifact and field-journal interpretation, seeded randomness, save/load, scoring on chronology/feature ID/narrative/care
- **Uses**: terminal gamers interested in archaeology and interpretation puzzles
- **Integrations**: standalone (game sibling of escutcheonussy)

### ussyverse/tempestussy
- **Description**: Rust CLI that reframes anxiety tracking as severe-weather meteorology with pressure, wind shear, fronts, and storm forecasts.
- **Stack**: Rust, Clap 4, Serde
- **Capabilities**: check-in data models, barometric pressure/stress index, wind shear (conflicting demands), dew-point symptom threshold, instability and storm-category calculations, forecast risk from JSON or CSV files, single-sounding logging, seasonal climate summaries, metaphor explainer, deterministic sample data
- **Uses**: individuals doing reflective, metaphor-driven journaling about stress patterns (not medical software)
- **Integrations**: standalone

### ussyverse/tenocyteussy
- **Description**: Local-first FastAPI web app for conservative, non-diagnostic tendon load-response planning from daily check-in data.
- **Stack**: Python, FastAPI, Uvicorn, pytest; embedded HTML dashboard
- **Capabilities**: daily tendon check-in model, zone classifier (green/yellow/orange/blue/red/gray), load budget categories, spike-ratio detection (7-day vs 28-day baselines), morning-stiffness trends, one-variable-at-a-time progression gates, red-flag suppression of exercise guidance, JSON API plus browser dashboard, sample demo dataset
- **Uses**: individuals monitoring tendon load during training (explicitly not medical advice)
- **Integrations**: standalone

### ussyverse/terroirussy
- **Description**: C CLI taste-development journal that treats the palate like a vineyard, logging structured tastings for wine/coffee/tea/chocolate/spirits with ASCII radar fingerprints and adaptation alerts.
- **Stack**: C (gcc/POSIX), bundled SQLite amalgamation, Greatest tests
- **Capabilities**: Structured tasting logging across six dimensions (acidity, phenolics, aromatics, body, finish, sweetness), listing and SQLite storage, ASCII radar-chart fingerprints, evolution averages over sliding windows, palate adaptation/desensitization warnings, TERROIR_DB env override
- **Uses**: Enthusiasts tracking palate development across beverage categories
- **Integrations**: standalone

### ussyverse/thermoussy
- **Description**: Go-powered composite GitHub Action and local CLI that reads workout logs and writes thermodynamics-inspired Markdown training reports.
- **Stack**: Go, GitHub Actions (action.yml), CSV/JSON input
- **Capabilities**: heat-engine efficiency heuristics, entropy-style fatigue accumulation with recovery decay, Gibbs/free-capacity headroom estimates, bonk/overheat/phase warnings from load/sleep/RPE/ambient heat, report artifact upload in CI
- **Uses**: athletes generating coaching-heuristic training reports from repo-stored workout logs
- **Integrations**: shares training-analytics domain with axisussy; otherwise standalone

### ussyverse/tidalussy
- **Description**: Models irregular income as ocean tides, decomposing cash-flow history into tidal constituents to forecast spring/neap income periods and slack-water windows.
- **Stack**: Python 3.10+, FastAPI, uvicorn, Jinja2, numpy, SQLite (stdlib)
- **Capabilities**: least-squares harmonic constituent fitting (M2/S2/K1/O1/SA), 90-day net cash-flow forecasting, spring/neap tide alert detection, slack-water window identification, tidal-range volatility scoring, SVG tide charts, REST API and HTML dashboard, income/expense entry endpoints
- **Uses**: freelancers, seasonal workers, and commission salespeople with irregular income timing major purchases
- **Integrations**: standalone

### ussyverse/tidepoolussy
- **Description**: Rust library with a thin CLI for non-clinical grief/boundary/emotional-exposure practice paced via intertidal ecology metaphors.
- **Stack**: Rust, optional CLI
- **Capabilities**: tide-state assessment (energy, grief, social capacity, appetite, recovery), exposure-zone classification (Refugium to Subtidal), holdfast ranking, desiccation/overexposure risk review, boundary-plan generation (zone, timebox, stop signal, aftercare), self-harm/crisis routing to ImmediateSupport
- **Uses**: individuals structuring gentle, bounded emotional practice outside clinical settings
- **Integrations**: standalone (safety-boundary care genre shared with ussyverse/palpebraussy)

### ussyverse/tilthaussy
- **Description**: Python library for turning home-garden observations into conservative soil compaction and tilth planning cards (paths, wet-work avoidance, recovery windows).
- **Stack**: Python (setuptools, pytest, stdlib logic)
- **Capabilities**: GardenZone/TrafficEvent/SoilObservation models, compaction risk banding (green/yellow/red) with mechanism explanations, path layout recommendations (permanent paths, stepping stones, hose routes), wet-work and recovery guidance, escalation boundaries for contamination/drainage issues, demo scenario CLI (`tiltha demo`, `--json`)
- **Uses**: Home gardeners diagnosing trampled-bed and puddling problems without lab tests
- **Integrations**: same conservative household-planning niche as kerfwiseussy (woodworking) and palynoussy (allergy journaling)

### ussyverse/timeloomussy
- **Description**: Python CLI that renders a repository's git history as woven textile patterns, with files as warp threads and commits as weft passes.
- **Stack**: Python 3.10+, click CLI, SVG/terminal/WIF renderers
- **Capabilities**: git-log parsing into co-change matrices, weave-draft generation (warp-over vs weft-over grid), SVG textile rendering, ASCII/Unicode terminal rendering, WIF (Weaving Interchange Format) export, structural analysis (floats, selvedge, pattern repeats), commit-type color mapping
- **Uses**: Visualizing development texture, coupling, and churn in any git repository
- **Integrations**: standalone (could render history of any ecosystem repo, e.g. mojomast/devussy)

### ussyverse/tonalussy
- **Description**: Rust/Axum web app for practicing functional harmony with a built-in music theory engine.
- **Stack**: Rust, Axum, Tokio, serde, embedded HTML
- **Capabilities**: circle-of-fifths key map, pitch-class parsing with enharmonics, diatonic triads, chord parsing, Roman numeral analysis, harmonic function classification (secondary/borrowed), cadence detection (authentic/plagal/deceptive/half), progression transposition, practice exercise generation and grading endpoints
- **Uses**: music students practicing harmony and ear training
- **Integrations**: standalone

### ussyverse/transactaussy
- **Description**: Local-first VS Code extension for household transactive memory — mapping who knows what, how reliable that knowledge is, and what must be handed off before someone is unavailable.
- **Stack**: TypeScript, VS Code extension API (webview, globalState), node:test
- **Capabilities**: member/domain/entry modeling (primary and backup knowers, confidence, freshness, source pointers), risk scoring for single-knower domains, stale knowledge, missing backups, overloaded memory partners, transition packs for travel/caregiving/pet sitting/roommate turnover, privacy redaction flags and non-consent warnings, handoff-board webview, Markdown report rendering, sample household loader
- **Uses**: households maintaining operational knowledge (meds, pets, appliances, subscriptions) across transitions and absences
- **Integrations**: ussyverse/effusaussy (same TS + VS Code extension slot and webview architecture)

### ussyverse/trapsealussy
- **Description**: A small offline C CLI for conservative home sewer-odor triage centered on plumbing trap seals, producing mechanism/action cards and plumber-ready reports from key=value case files.
- **Stack**: C, Make, greatest.h test framework
- **Capabilities**: dry-trap identification, siphonage/vent escalation routing, red-flag safety stops, biofilm boundary detection, refill/reminder cadence, observation report rendering, sample case generator
- **Uses**: homeowners and renters triaging localized sewer odors before calling a plumber
- **Integrations**: standalone (same conservative safety-triage family as patinaussy)

### ussyverse/treadaussy
- **Description**: Local-first Python/FastAPI web app turning shoe-floor-contaminant friction reasoning into practical slip-risk planning cards for everyday walking exposures.
- **Stack**: Python, FastAPI, uvicorn, pytest; CLI entry point
- **Capabilities**: /health, /api/sample, /api/assess traction-plan cards, /api/compare footwear ranking for a route, /api/patterns near-miss summaries; deterministic rules for contaminants, tread wear, movement demand, uncertainty; red-flag route-away to clinicians/facilities/emergency guidance; CLI JSON smoke mode
- **Uses**: ordinary users comparing footwear and routes before wet, icy, or slick walks; not a medical or compliance tool
- **Integrations**: standalone

### ussyverse/triageussy
- **Description**: Python CLI that applies forensic crime-scene methodology to build/error logs, producing structured detective reports with suspects, evidence, motive, and recommended fixes.
- **Stack**: Python 3.8+ stdlib only, SQLite pattern database
- **Capabilities**: multi-format log parsing (rustc, Go, tsc, gcc/clang, Python tracebacks, JS errors, pytest/jest, CI logs), 50+ curated error patterns, git blame/history enrichment, detective/JSON/minimal/teaching render modes, custom pattern management, stdin piping from any build tool
- **Uses**: developers cutting through noisy CI/build failures quickly
- **Integrations**: standalone (dev-tooling domain; natural pipeline partner with chromatoussy dependency-risk scans)

### ussyverse/triagiaussy
- **Description**: VS Code extension that turns household emergency preparedness into an incident-command style operational card with staged actions and readiness gaps.
- **Stack**: TypeScript, VS Code extension API, Mocha
- **Capabilities**: household scenario modeling (members, mobility/medical constraints, pets, hazard types, resources, triggers, communication fallbacks), staged action plans (first 10 minutes/hour/night/24h/72h), incident roles with backups, START-style readiness gap map (immediate/delayed/minor), conservative evacuation thresholds, shelter-in-place duration estimates from resources, supply rotation tasks, explicit safety boundaries, markdown/webview rendering, sample scenario, Memento-based local storage
- **Uses**: households building practical disruption and evacuation plans
- **Integrations**: standalone

### ussyverse/trialwiseussy
- **Description**: A VS Code extension for designing and reviewing safe, reversible N-of-1 crossover experiments on personal routines, with precommitted decision memos.
- **Stack**: TypeScript, VS Code Extension API (Memento persistence), Mocha tests, webview dashboard
- **Capabilities**: AB/BA/ABAB/seeded-randomized crossover schedule generation with washout days, safety and reversibility blocking of medical/medication interventions, period-mean and delta analysis, adherence/burden/confound scoring, keep/reject/repeat/inconclusive recommendations, webview timeline dashboard with decision memo, sample plan and check-in commands
- **Uses**: individuals running disciplined self-experiments on caffeine timing, sleep schedules, workspace habits
- **Integrations**: standalone (complements pulmoussy wellness tracking)

### ussyverse/triboussy
- **Description**: Go library for tribology-inspired relationship friction analysis, modeling interactions as contact mechanics (friction, wear, lubrication, galling).
- **Stack**: Go 1.24, standard library, optional demo command
- **Capabilities**: static/kinetic/overall friction scoring, wear ledger by contact zone (abrasive, adhesive, fatigue, corrosive), lubrication recommendations (kindness units, repair time), galling/seizure detection, combined profile analysis
- **Uses**: couples or individuals journaling relationship maintenance patterns (analytical metaphor, not therapy)
- **Integrations**: standalone

### ussyverse/turnwiseussy
- **Description**: Local-first Python TUI that logs privacy-preserving conversation beats (not transcripts) and surfaces repair opportunities, listening-labor balance, and one small micro-experiment per household.
- **Stack**: Python, Rich TUI/CLI, JSON store, pytest
- **Capabilities**: interaction-beat logging, unfinished adjacency-pair detection (question/request/answer), interruption vs friendly-backchannel classification, repair/listening-labor attribution, household dashboards, micro-experiment cards, explicit privacy/safety commands and boundaries
- **Uses**: families, roommates, and co-parents improving everyday conversation dynamics without recording audio
- **Integrations**: framoraussy (sibling household-care domain tool)

### ussyverse/tympanaussy
- **Description**: Educational Python library for conservative ear-pressure travel packets, translating Eustachian-tube basics into trip cards for flights, mountain drives, and elevators.
- **Stack**: Python
- **Capabilities**: pressure-segment risk classification, equalization cue schedules, child/infant caregiver plans, congestion/allergy cautions, route-away gating for severe symptoms, Markdown packet rendering, CLI smoke mode
- **Uses**: travelers, parents, and caregivers planning pressure-change trips
- **Integrations**: standalone

### ussyverse/urticaraussy
- **Description**: Local-first FastAPI web app for logging hives/urticaria episodes with angioedema red-flag screening, UAS7 weekly scoring, cautious trigger ranking, and clinician handoff export.
- **Stack**: Python 3.10+, FastAPI, uvicorn, Jinja2, Pydantic, pytest + TestClient
- **Capabilities**: Episode logging (regions, wheal bands, itch, sleep disruption), conservative red-flag routing for airway/swallowing/collapse signs, UAS7-style 7-day scoring with missing-day warnings, trigger hypothesis ranking with insufficient-evidence labels, label-first medication notes, plain-text clinician/pharmacist handoff packet, local JSON storage with env override, HTML + JSON routes
- **Uses**: Hives patients keeping a symptom diary to share with clinicians or pharmacists
- **Integrations**: standalone

### ussyverse/validaraussy
- **Description**: Terminal C application that adapts analytical method-validation concepts to check whether a packaged small-business service offer is ready to launch.
- **Stack**: C11, Make, greatest.h test runner
- **Capabilities**: readiness dashboard for intended use/specificity/accuracy/repeatability/range/robustness, deterministic scoring rules, sample offer demo, Markdown method-label export, compact TUI menu
- **Uses**: small-business owners and consultants validating a service offer before launch
- **Integrations**: standalone (C CLI sibling of orseraussy)

### ussyverse/vectorussy
- **Description**: VS Code extension that reframes community mobilization as epidemiology: R0 tracking, super-spreaders, and transmission-chain tracing of recruitment.
- **Stack**: TypeScript, VS Code extension API (Memento storage), Mocha
- **Capabilities**: mobilization R0 calculation from recruiter edges, per-channel attack/conversion rates, super-spreader ranking by downstream reach, recruitment-tree rendering and dead-end detection, no-show leakage analysis with intervention recommendations, JSON data import, built-in sample dataset, report generation
- **Uses**: community organizers and volunteer coordinators analyzing outreach effectiveness
- **Integrations**: standalone

### ussyverse/vergentaussy
- **Description**: C-based local-first screen visual-load analyzer packaged as a GitHub Action, producing a non-diagnostic Markdown worksheet separating accommodation, vergence, blink/dryness, glare, and posture load channels.
- **Stack**: C11, Make, greatest tests; GitHub Actions composite action
- **Capabilities**: reads profile/session CSVs, writes VERGENTA-REPORT.md, per-channel visual-load separation, safety-escalation red flags, local CLI and CI action modes with artifact upload
- **Uses**: individuals/teams reasoning about screen eye strain; repo owners running ergonomic reports in CI
- **Integrations**: pairs with stenography as the other GitHub Action in the ecosystem for repo-level scanning/reporting

### ussyverse/vesselussy
- **Description**: Local-first TypeScript CLI translating pottery studio notes into ceramic-materials diagnostics: shrinkage, quartz-inversion warnings, glaze/body fit, thermal-shock risk, and technique vitrification curves.
- **Stack**: TypeScript, Node.js, npm
- **Capabilities**: Project JSON diagnosis (kiln cards), built-in clay-body database, shrinkage estimation, thermal-shock and quartz-inversion warnings, glaze fit (crazing/shivering) probability, practice-hours vitrification sigmoid, studio insight summaries from saved logs, local state in ~/.vessel, JSON/Markdown output
- **Uses**: Potters learning why pieces cracked, warped, or crazed (educational, not a kiln controller)
- **Integrations**: standalone

### ussyverse/vibraussy
- **Description**: Local-first Go web app for household appliance vibration/noise triage using rotordynamics-style condition monitoring (published as github.com/mojomast/vibraussy).
- **Stack**: Go stdlib web app, local JSON file storage
- **Capabilities**: rule-based fault-family classification (imbalance, leveling, looseness, airflow restriction, resonance/contact, bearing/belt wear, electrical escalation), confidence and severity wording, safe contrast-test recommendations, landlord/service report generation, spectrogram-lite features from pasted amplitude samples, /api/analyze JSON endpoint
- **Uses**: renters and homeowners triaging washer/dryer/fridge noise before calling a technician
- **Integrations**: standalone

### ussyverse/vitalussy
- **Description**: VS Code extension for resident-led Jane Jacobs neighborhood vitality diagnostics, scoring block observations into a Jacobs Vitality Index and action plan.
- **Stack**: TypeScript, VS Code extension API (Memento globalState), Mocha
- **Capabilities**: eyes-on-the-street scoring, mixed-use Shannon entropy, short-block/permeability measurement, aged-building granularity scoring, border-vacuum penalty detection, third-place inventory, ranked resident action recommendations, webview dashboard with dimension bars
- **Uses**: residents and block clubs advocating for safer, more social streets
- **Integrations**: standalone

### ussyverse/vorticaussy
- **Description**: Python GitHub Action and local CLI that turns household/location JSON files into conservative tornado warning shelter-selection and drill cards.
- **Stack**: Python 3.10+ (stdlib only), GitHub Action (action.yml)
- **Capabilities**: shelter hierarchy analysis (safe room/basement/interior room), hazard flagging (windows, garage, large-span rooms), mobile home/RV/campground route-away plans, watch-vs-warning response language, drill prompts (night, pets, children, mobility, route timing), Markdown + JSON report output
- **Uses**: families, renters, schools, small workplaces pre-documenting tornado shelter plans in a repo
- **Integrations**: thematically pairs with ussyverse/stormussy (severe-weather domain)

### ussyverse/watershedussy
- **Description**: Go CLI that models water availability along hiking routes using degree-day snowmelt, linear-reservoir baseflow, Hargreaves ET, and hydrograph-based carry calculations.
- **Stack**: Go (stdlib only)
- **Capabilities**: ASCII hydrograph per water source for date ranges, baseflow/quickflow separation, snowmelt and evapotranspiration estimation, water-carry liters between reliable sources from pace/sweat/reliability, route/weather JSON inputs
- **Uses**: Hikers and trail planners estimating seasonal stream reliability and pack water weight
- **Integrations**: trip-planning companion to portolanussy (layover buffers) and controlaussy (route scoring)

### ussyverse/weberaussy
- **Description**: Local Python web app for Weber-Fechner household comfort calibration, helping households test just-noticeable differences in light, sound, scent, airflow, temperature, humidity, and screens.
- **Stack**: Python, local web server (stdlib), JSON APIs, HTML/text reports
- **Capabilities**: calibration sessions per room/variable/participant, JND range and Weber-fraction estimation, detection-vs-preference separation, household overlay with sensitive-member veto zones and shared comfort bands, adaptation re-rating flags, recommendation classes (below threshold, sensitive-only, comfortable-noticeable, conflict-risk, overshoot-risk), text report and JSON export
- **Uses**: Households making evidence-based, per-person comfort decisions before buying products or overshooting settings
- **Integrations**: standalone (household-comfort sibling of ussyverse/adsorbaussy)

### ussyverse/wetbulbaussy
- **Description**: Python library for building conservative WBGT heat-stress pacing packets for everyday outdoor tasks like mowing, gardening, and dog walking.
- **Stack**: Python 3.9+, pytest, CLI entry points
- **Capabilities**: heat-index/WBGT anchoring, sun/radiant/wind modifiers, workload and clothing scoring, acclimatization modeling, work/rest and cooling guidance, buddy checks, vulnerability and symptom route-away boundaries, plan window comparison, Markdown packet rendering, demo CLI
- **Uses**: non-developers planning hot-day outdoor chores safely
- **Integrations**: physiology-pacing domain kin to pressoraussy; household-safety domain kin to aeronaussy

### ussyverse/zooxussy
- **Description**: Stdlib-only Go CLI that treats your travel life like a coral reef — tracking cumulative travel stress, symbiont-density recovery, bleaching/burnout risk, and recommending diverse recovery activities.
- **Stack**: Go standard library only, portable JSON log
- **Capabilities**: 14-day degree-stress-days rolling load metric, logistic symbiont recovery model with stress-dependent depletion, bleaching and phase-shift (trip aversion) risk warnings, Shannon-diversity resilience scoring over recovery activities (sleep, nutrition, social, nature, movement, quiet), `init`/`add-trip`/`add-recovery`/`report`/`export` commands, JSON and Markdown report formats
- **Uses**: frequent travelers monitoring cumulative travel load and planning sustainable recovery
- **Integrations**: standalone (wellness-metric sibling of ussyverse/chloroussy)
