# Privacy-first recombinations: local control, sharing, and auditability

**Date:** 2026-09-13
**Focus:** offline/local-first personal data control, inspectable sharing, and
security evidence.  These are new proposals, not additions to the ten-item
shortlist in `SOURCE_CHECKED_COMBINATIONS.md`.

## Method and evidence boundary

I read the required brainstorming documents and inspected the checked-out
source/manifests in `/home/ubuntu/ussy/repos` on the date above.  The inspected
revisions were:

| Repository | Revision | Source areas inspected |
|---|---:|---|
| `ussyverse/mintussy` | `ade5430` | `mint/models.py`, `provenance.py`, `counterfeit.py`, `lockfile.py`, `pyproject.toml` |
| `ussyverse/cambiumussy` | `5fe4d0d` | `cambium/models.py`, `compatibility.py`, `storage.py`, `pyproject.toml` |
| `ussyverse/sentinelussy` | `1b86f9c` | `sentinel/profile.py`, `checker.py`, `db.py` |
| `ussyverse/kinshipussy` | `308bbb3` | `kinship/types.go`, `analysis.go`, `go.mod` |
| `ussyverse/quorumussy` | `397531d` | `internal/quorum/model.go`, `main.go`, tests |
| `ussyverse/parliamentussy` | `1de34fe` | `src/parliament/models.py`, `storage.py`, `pyproject.toml` |
| `ussyverse/palynoussy` | `c12a506` | `src/lib.zig`, `README.md` |
| `ussyverse/resonaussy` | `711c89a` | `pkg/resona/resona.go` |
| `ussyverse/patchwiseussy` | `f6e04a9` | `src/lib.zig`, `README.md` |
| `ussyverse/taphonussy` | `432c97d` | `src/lib.rs`, `src/main.rs` |
| `ussyverse/raciaussy` | `f7d1bfe` | `src/models.ts`, `src/engine.ts`, `package.json` |
| `ussyverse/recapturaussy` | `2640919` | `src/lib.zig`, `src/main.zig`, README, integration tests |
| `mojomast/arrhivescrape` | `afffec1` | `archive_recovery/cli.py`, `pipeline/normalization.py`, `pipeline/validation.py`, `state.py`, `pyproject.toml` |
| `mojomast/clanker02` | `624233d` | `src/auth/crypto.ts`, `auth/middleware.ts`, `services/query-engine.ts`, `package.json` |
| `mojomast/citewiser` | `284dc76` | `pkg/access/access.go`, `pkg/provenance/trail.go`, `provenance/redact.go`, `pkg/packer/packer.go`, `go.mod` |
| `mojomast/openclawssy` | `46e0018` | `internal/policy/{capability,pathguard,redact}.go`, `internal/audit/logger.go`, `internal/secrets/store.go`, `internal/agent/ledger.go`, `internal/contract/contract.go`, `go.mod` |
| `mojomast/PGaudussy` | `3ff9aa3` | `dbaudit.py`, `utils/{audit,backup,connection,fixes}.py`, `README.md` |
| `mojomast/hermes-correction-aware-learning` | `84c8c8c` | `README.md`, `src/correction_aware_learning/{store,reports}.py` |

No candidate repository was modified.  I did not build, install, or runtime-test
these checkouts in this pass.  Existing tests and README examples below are
evidence of intended contracts, not evidence that a deployment works.

Verification commands run while preparing this file: `git status --short`,
`git diff --stat`, and `git diff --check` from `/home/ubuntu/ussy/brainstorm`.

The labels mean:

- **Exists:** present in inspected source.
- **Proposed:** adapter, product workflow, or security behavior to implement.
- **Unverified:** claimed by documentation or not exercised here.

## At a glance

| Idea | Repositories | Local/privacy angle |
|---|---|---|
| 1. Dependency provenance gate | `ussyverse/mintussy` + `ussyverse/cambiumussy` + `ussyverse/sentinelussy` | Keep package evidence and policy decisions in a local review bundle. |
| 2. Care-circle consent ledger | `ussyverse/kinshipussy` + `ussyverse/quorumussy` + `ussyverse/parliamentussy` | Share only a consented decision projection, not the whole care graph. |
| 3. Private exposure and cadence notebook | `ussyverse/palynoussy` + `ussyverse/resonaussy` + `ussyverse/patchwiseussy` | Offline personal journal with explicit retention and export controls. |
| 4. Keepsake custody packet | `ussyverse/taphonussy` + `ussyverse/kinshipussy` + `ussyverse/raciaussy` | Transfer object responsibility without publishing family details. |
| 5. Private legacy-site release | `mojomast/arrhivescrape` + `ussyverse/taphonussy` + `ussyverse/patchwiseussy` | Recover locally, inspect leakage, and publish only an approved projection. |
| 6. Cited private knowledge bulletin | `mojomast/clanker02` + `mojomast/citewiser` + `ussyverse/sentinelussy` + `ussyverse/parliamentussy` | ACL-filtered, cited extracts with a local publication gate. |
| 7. Personal agent permission vault | `mojomast/openclawssy` + `ussyverse/parliamentussy` + `ussyverse/quorumussy` | Encrypt secrets locally and require explicit approval for sharing/actions. |
| 8. Correction evidence review desk | `mojomast/hermes-correction-aware-learning` + `ussyverse/parliamentussy` + `ussyverse/sentinelussy` | Count-only, opaque evidence prevents raw conversations becoming training data. |
| 9. Least-privilege migration receipt | `mojomast/PGaudussy` + `ussyverse/mintussy` + `ussyverse/parliamentussy` | Review database permission changes with package and approval provenance. |
| 10. Pseudonymous lead-capacity exchange | `ussyverse/recapturaussy` + `ussyverse/quorumussy` + `ussyverse/raciaussy` | Collaborate on aggregate demand without exchanging raw contact lists. |

## 1. Dependency provenance gate

**Target user and pain.** A maintainer of a small offline-capable application
needs to decide whether a dependency upgrade is acceptable, but cannot upload a
lockfile, private package names, or build metadata to a hosted scanner.

**Product promise.** “Review a dependency change locally with provenance,
compatibility, and unusual-change evidence in one decision packet.”

**Exact repositories.** `ussyverse/mintussy`, `ussyverse/cambiumussy`,
`ussyverse/sentinelussy`.

**Existing evidence.** **Exists:** Mint's `parse_package_lock_json` in
[`lockfile.py`](https://github.com/ussyverse/mintussy/blob/ade5430/mint/lockfile.py)
reads npm lockfile v1 and v2+ entries, including resolved URLs and integrity
fields. `create_provenance_chain` and `determine_provenance_level` in
[`provenance.py`](https://github.com/ussyverse/mintussy/blob/ade5430/mint/provenance.py)
represent source/build/publish links and report gaps. Its counterfeit checks in
[`counterfeit.py`](https://github.com/ussyverse/mintussy/blob/ade5430/mint/counterfeit.py)
cover typosquats, registry mismatches, publisher changes, supplied hash
mismatches, foreign files, and low provenance levels. **Exists:** Cambium's
AST/interface compatibility functions in
[`compatibility.py`](https://github.com/ussyverse/cambiumussy/blob/5fe4d0d/cambium/compatibility.py)
compare exported names, preconditions, and simplified version ranges, while
`Storage` in [`storage.py`](https://github.com/ussyverse/cambiumussy/blob/5fe4d0d/cambium/storage.py)
keeps local SQLite snapshots. **Exists:** Sentinel can build a codebase profile
from current source or sampled git history and compare later Python patterns in
[`profile.py`](https://github.com/ussyverse/sentinelussy/blob/1b86f9c/sentinel/profile.py)
and [`checker.py`](https://github.com/ussyverse/sentinelussy/blob/1b86f9c/sentinel/checker.py).

**Proposed handoff/data flow.** A local wrapper reads a lockfile and selected
non-secret package metadata -> Mint emits provenance/counterfeit findings ->
Cambium compares the proposed dependency interface with the consumer and stores
the before/after snapshot -> Sentinel checks only the changed local source tree
against an owner-approved profile -> a review bundle contains raw local
evidence, hashes, warnings, and a human decision. No raw lockfile leaves the
machine unless the user explicitly exports it.

**Missing integration work.** Build the canonical upgrade/decision schema, bridge
the three languages, normalize package/module IDs, redact paths and package
names by policy, and add a local bundle viewer. No existing component joins
these reports.

**MVP and acceptance.** One npm project, one normal upgrade, one registry
mismatch, and one intentionally changed Python adapter. The bundle must show
the exact package/version, provenance gaps, compatibility inputs, Sentinel
locations, and an explicit `unknown` state when evidence is absent. A reviewer
must be able to delete the raw lockfile and retain a separately marked summary.

**Value of combination.** Mint answers “where did this package come from?”,
Cambium answers “does this consumer/provider boundary line up?”, and Sentinel
answers “is this change unusual for this repository?” Separate reports do not
join those three questions at one upgrade decision.

**Risks, maturity, and security.** These are small alpha/prototype components;
no integration exists. Cambium's compatibility and drift values are heuristics:
its version parser converts versions to a major/minor/patch float and its
default missing-version behavior assumes compatibility. Mint's “signatures” and
`verified` flags are caller-supplied fields; it does not fetch or cryptographically
verify registry signatures. Sentinel persists absolute `root_path` and source
file names in SQLite/profile JSON. **Proposed:** encrypt the bundle, redact paths,
and require a human review. Do not turn any score into an automatic allow rule.

**Rejected adjacent components.** A generic hosted vulnerability scanner was
not added: it would defeat the local-data requirement and does not supply this
compatibility/history handoff.

## 2. Care-circle consent ledger

**Target user and pain.** A distributed family or chosen-family care circle
needs to coordinate recurring help while respecting who consented to what. A
shared spreadsheet exposes health/care details to people who only need a narrow
task or decision.

**Product promise.** “Turn a care gap into a consented, expiring task card
without sharing the whole relationship graph.”

**Exact repositories.** `ussyverse/kinshipussy`, `ussyverse/quorumussy`,
`ussyverse/parliamentussy`.

**Existing evidence.** **Exists:** Kinship's `CareEdge` includes `Consent`,
`Explicitness`, reliability, criticality, and cognitive load in
[`types.go`](https://github.com/ussyverse/kinshipussy/blob/308bbb3/kinship/types.go).
`BackupPathGaps`, `SimulateUnavailable`, ambiguity alerts, and conversation
prompts are implemented in
[`analysis.go`](https://github.com/ussyverse/kinshipussy/blob/308bbb3/kinship/analysis.go).
**Exists:** Quorum reads/writes a local JSON `DecisionFile`, records weighted
preferences, vetoes, tolerances, and notes, and produces quorum/polarization/
veto reports in [`model.go`](https://github.com/ussyverse/quorumussy/blob/397531d/internal/quorum/model.go)
and its CLI [`main.go`](https://github.com/ussyverse/quorumussy/blob/397531d/main.go).
**Exists:** Parliament models motion states, votes, agents, and sessions, and
its `JournalEntry` hashes the previous hash, timestamp, and data. `verify_chain`
checks that chain in [`storage.py`](https://github.com/ussyverse/parliamentussy/blob/1de34fe/src/parliament/storage.py).

**Proposed handoff/data flow.** The private care graph remains on one device ->
Kinship identifies a backup or ambiguous-consent gap -> the product creates a
minimal Quorum question containing only the task, constraints, and pseudonymous
member IDs -> after consent, a Parliament motion records the agreed assignment,
expiry, and review date -> each recipient receives only their task card.

**Missing integration work.** Define a consent and expiry schema, map Kinship
edges to task-scoped Quorum motions, generate recipient projections, and add
authenticated encrypted export/import. The current files do not provide this
handoff.

**MVP and acceptance.** Model one elder-check-in task with two backups, one
declined participant, and one temporary absence. The exported packet must omit
unrelated care edges and private notes; a recipient can verify their assignment
and expiry; tampering with the journal causes verification failure; changing
consent requires a new decision rather than silently rewriting history.

**Value of combination.** Kinship detects structural care gaps, Quorum provides
a non-accusatory consent/choice interaction, and Parliament supplies an
inspectable decision history. This is a consent boundary, not another household
load dashboard.

**Risks, maturity, and security.** Kinship's load/reciprocity numbers are
heuristics, and `Report` uses the current clock. Quorum's `Save` writes JSON with
mode `0644`, includes member names, notes, and ballots, and has no encryption or
authentication. Parliament's hash chain is integrity evidence, not a signature,
access control, or confidentiality mechanism; journal data is plaintext. The
Quorum “confidence” is a mathematical signal, not consent validity. **Proposed:**
use opaque IDs, encrypted local storage, per-recipient projections, authenticated
signatures for remote sharing, and an append-only audit event for every export.

**Rejected adjacent components.** A general family calendar was not added: it
would broaden disclosure and does not resolve consent, backup coverage, or
decision provenance.

## 3. Private exposure and cadence notebook

**Target user and pain.** An allergy sufferer or person tracking environmental
triggers wants to see delayed exposure patterns and routine interactions without
uploading intimate notes to a health app, while retaining the original journal
and controlling what is shared with a clinician.

**Product promise.** “Find timing patterns in a private journal and export only
the evidence a human clinician needs to inspect.”

**Exact repositories.** `ussyverse/palynoussy`, `ussyverse/resonaussy`,
`ussyverse/patchwiseussy`.

**Existing evidence.** **Exists:** Palyno's `AnalyzeInput` and `analyzeJson` in
[`src/lib.zig`](https://github.com/ussyverse/palynoussy/blob/c12a506/src/lib.zig)
match exposure/symptom timestamps in fixed lag windows, calculate reservoir
levels, and emit uncertainty-labeled trigger candidates and low-risk experiment
cards. The README states no accounts, network APIs, or diagnosis claims.
**Exists:** Resona's `BuildDailySignals`, `AggregateWindow`, `AnalyzePair`, and
`DetectDamping` in [`resona.go`](https://github.com/ussyverse/resonaussy/blob/711c89a/pkg/resona/resona.go)
compare timed habit events, energy logs, overlap, correlation, and cadence.
**Exists:** Patchwise parses local text/CSV lists and in
[`src/lib.zig`](https://github.com/ussyverse/patchwiseussy/blob/f6e04a9/src/lib.zig)
reports weak titles, duplicate trails, source gaps, and refinding drills.

**Proposed handoff/data flow.** A local journal stores raw events and a separate
export policy -> Palyno analyzes exposure-to-symptom lag without diagnosis ->
Resona compares routines such as cleaning, sleep, and outdoor activity ->
Patchwise audits the local journal index for enough context to refind an event ->
the user selects a date range and fields for a clinician-facing summary while
the raw journal stays encrypted and local.

**Missing integration work.** Define one timezone-aware event schema, implement
encrypted persistence and retention/deletion, map Resona events to Palyno
exposure windows, and create an explicit field-level export projection.

**MVP and acceptance.** Import one week of hand-authored JSON, identify one
delayed symptom association, compare two routines, and export a summary with
IDs/times/severity but no free-form notes unless explicitly selected. The app
must have a “raw stays local” default, a visible medical disclaimer, and a
destructive export confirmation. A delete operation must remove the index entry
and report what encrypted local files remain.

**Value of combination.** Palyno handles exposure lag and reservoirs, Resona
handles interaction/cadence, and Patchwise handles the often-neglected ability
to find the original evidence later. It creates a private evidence notebook,
not a predictive health authority.

**Risks, maturity, and security.** Palyno's trigger mapping is string matching
and its scores are within-user associations, not causality; it has no persistence
or encryption in inspected source. Resona normalizes days to UTC, which can
surprise users entering local times, and its burnout labels are heuristics.
Patchwise's cleanup recommendations are not secure deletion and its parser has
simple comma handling. **Proposed:** use an encrypted store, local timezone
metadata, field-level export allowlists, and a clinician review step. Never
recommend medication changes or infer a diagnosis.

**Rejected adjacent components.** A diagnosis or medication-recommendation
engine was not added: the inspected algorithms support exploratory associations,
not clinical validity or treatment advice.

## 4. Keepsake custody packet

**Target user and pain.** Relatives, executors, or a small museum-like household
need to move photographs, letters, and objects between caretakers. They need to
preserve context and name responsibility without sending the whole family graph
or storage address to every recipient.

**Product promise.** “Hand off a keepsake with its preservation instructions and
accountability, while minimizing family disclosure.”

**Exact repositories.** `ussyverse/taphonussy`, `ussyverse/kinshipussy`,
`ussyverse/raciaussy`.

**Existing evidence.** **Exists:** Taphon parses local JSON/CSV/TOML/text
inventories into `KeepsakeItem`, calculates material/context risk, retains
assemblages, and emits “do not” actions and reports in
[`src/lib.rs`](https://github.com/ussyverse/taphonussy/blob/432c97d/src/lib.rs).
**Exists:** Kinship can model care edges, consent, criticality, and backup
paths. **Exists:** Racia's `TaskRow` has `requiredAccess`, affected people,
temporary assignment expiry, and RACI roles in
[`models.ts`](https://github.com/ussyverse/raciaussy/blob/f7d1bfe/src/models.ts);
`analyzePlan` flags missing/multiple owners and owner access gaps in
[`engine.ts`](https://github.com/ussyverse/raciaussy/blob/f7d1bfe/src/engine.ts).

**Proposed handoff/data flow.** Inventory and photographs are assessed locally by
Taphon -> each item gets a stable custody ID and a preservation status -> Racia
assigns one accountable custodian, a doer, and a temporary expiry -> Kinship
checks whether the receiving care network has a consensual backup -> a filtered
handoff packet contains only the item projection, care label, recipient, and
return/review date.

**Missing integration work.** Create stable item and custody IDs, attach risk
reports to Racia tasks, map backups to Kinship edges, strip paths/free text from
recipient packets, and implement encrypted attachment transfer.

**MVP and acceptance.** Transfer one box containing a damp photograph, a letter
with an uncertain owner, and a metal/paper object. The sender must be able to
export a packet without raw family notes or absolute local paths; the recipient
must see quarantine/context instructions and a named backup; changing the box
assignment must produce a new version and preserve the old audit record.

**Value of combination.** Taphon protects the physical/context evidence, Racia
defines operational custody, and Kinship tests whether the human backup network
is real. None alone describes a safe, privacy-minimized transfer.

**Risks, maturity, and security.** Taphon serializes `raw_text`, `source_file`,
and `input_path`; its reports are not safe to share by default. Its material
rules are conservative keyword heuristics, not conservation expertise. Kinship
and Racia store names and notes as ordinary JSON structures. **Proposed:** use
opaque IDs, separate encrypted originals from a handoff projection, strip paths
and names not needed by the recipient, and add a tested attachment-copy/fixity
step. No encryption or authenticated sharing exists in these three checkouts.

**Rejected adjacent components.** A public family tree was not added: it would
expose more relationship data than custody requires and is unrelated to the
preservation acceptance test.

## 5. Private legacy-site release

**Target user and pain.** A person recovering a dead personal site, forum, or
blog wants a local mirror that preserves history but does not accidentally
republish forms, tracking links, private paths, or an unreviewed archive capture.

**Product promise.** “Recover a usable local mirror, inspect its leakage, and
publish only an approved projection.”

**Exact repositories.** `mojomast/arrhivescrape`, `ussyverse/taphonussy`,
`ussyverse/patchwiseussy`.

**Existing evidence.** **Exists:** Arrhivescrape's CLI offers publication
policies (`private-local`, `private-tailnet`, public modes), third-party audit
modes, loopback defaults, and review flags in
[`cli.py`](https://github.com/mojomast/arrhivescrape/blob/afffec1/archive_recovery/cli.py).
Its normalization code removes Wayback artifacts, neutralizes forms, rewrites
first-party URLs, preserves hashes, and writes atomic files in
[`normalization.py`](https://github.com/mojomast/arrhivescrape/blob/afffec1/archive_recovery/pipeline/normalization.py).
Validation checks missing files, internal references, external references, and
MIME warnings in [`validation.py`](https://github.com/mojomast/arrhivescrape/blob/afffec1/archive_recovery/pipeline/validation.py).
Its SQLite state records runs, captures, hashes, raw paths, and events, but is
not encrypted. **Exists:** Taphon can triage a generated inventory of pages,
attachments, and contextual notes. **Exists:** Patchwise can audit the local
manifest for weak/opaque names, missing source notes, and duplicate trails.

**Proposed handoff/data flow.** Download and normalize captures into a private
staging tree -> generate a manifest projection with page IDs, source dates, and
hashes -> Patchwise identifies pages whose labels do not preserve provenance ->
Taphon flags context-poor attachments or risky preservation actions -> a human
reviews external links, forms, and sensitive records -> only the approved
projection is promoted to a local or tailnet mirror.

**Missing integration work.** Add a release manifest schema, connect page and
attachment IDs across the three tools, implement PII/secret scanning and an
approval gate, and separate encrypted raw captures from the served tree.

**MVP and acceptance.** Recover ten pages containing one HTML form, one external
tracker, one private-looking attachment, and two duplicate captures. The local
release must neutralize the form, list external links, preserve raw/final hashes,
and refuse promotion until the attachment and privacy review are acknowledged.

**Value of combination.** Arrhivescrape supplies real recovery/normalization;
Patchwise makes provenance and refinding quality visible; Taphon adds a
context-first preservation review for the digital keepsake inventory. The
deliverable is a reviewed mirror, not a generic archive dashboard.

**Risks, maturity, and security.** Arrhivescrape's privacy settings and review
flags are real configuration surfaces, not proof that every sensitive datum is
detected. Raw capture paths and URLs are retained in manifests/SQLite, and
“private-tailnet” is not encryption at rest. Regex/HTML rewriting is not a full
browser security boundary. Taphon can expose local paths and raw text in JSON;
Patchwise does not scrub URLs. **Proposed:** encrypt raw runs, scan PII/secrets
before release, bind approvals to hashes, disable public serving by default, and
test forms, scripts, external URLs, and attachment leakage with adversarial
fixtures.

**Rejected adjacent components.** A public CDN or hosted archive was not added:
it increases the blast radius before local review and does not improve
normalization or leakage evidence.

## 6. Cited private knowledge bulletin

**Target user and pain.** A small team wants to circulate a short answer from
private GitHub/Slack/Notion material, but needs citations and recipient-specific
redaction. “The model saw it” must not become “everyone can read it.”

**Product promise.** “Answer from private material with citations whose content
and visibility are checked for each recipient.”

**Exact repositories.** `mojomast/clanker02`, `mojomast/citewiser`,
`ussyverse/sentinelussy`, `ussyverse/parliamentussy`.

**Existing evidence.** **Exists:** Clanker02 has bcrypt token/password helpers
in [`crypto.ts`](https://github.com/mojomast/clanker02/blob/624233d/src/auth/crypto.ts),
JWT/API-key/workspace membership middleware in
[`middleware.ts`](https://github.com/mojomast/clanker02/blob/624233d/src/auth/middleware.ts),
and a local-Ollama-default query path with citations in
[`query-engine.ts`](https://github.com/mojomast/clanker02/blob/624233d/src/services/query-engine.ts).
**Exists:** Citewiser's `DefaultController` checks tenant, clearance, and trusted
approver requirements in [`access.go`](https://github.com/mojomast/citewiser/blob/284dc76/pkg/access/access.go);
`RedactSourceTrail` and `RedactSourceRef` remove unauthorized trail/reference
fields in [`redact.go`](https://github.com/mojomast/citewiser/blob/284dc76/pkg/provenance/redact.go),
and the packer emits source trails, suppression reasons, and structural plan
hashes. **Exists:** Sentinel provides a local code anomaly report. **Exists:**
Parliament provides a hash-linked publication decision record.

**Proposed handoff/data flow.** Clanker connectors ingest into a local workspace
-> an adapter maps documents to Citewiser nodes with tenant, sensitivity, source,
and approval metadata -> Citewiser packs and redacts recipient-specific context
before any model call -> a local renderer creates a cited bulletin -> Sentinel
reviews the connector/export code for unexpected file patterns -> Parliament
records approver, plan hash, recipient class, and expiry. Raw chunks remain local.

**Missing integration work.** Enforce Citewiser policy before indexing and
generation, implement connector-to-node metadata mapping, add recipient
projection tests, and bind Parliament approvals to content/index hashes.

**MVP and acceptance.** Two tenants, one restricted document, one public document,
and one answer with a cited source. A public recipient must receive neither
restricted text nor its URL/path; a restricted recipient gets the permitted
citation; changing a node or plan hash invalidates the approval; a deletion in
the source workspace removes it from the next local index after an explicit
re-index.

**Value of combination.** Clanker gives a usable indexing/query surface,
Citewiser supplies the actual authorization/provenance boundary, Sentinel adds
a narrow preflight over the local adapter, and Parliament makes publication
approval inspectable. This is safer than adding another LLM router.

**Risks, maturity, and security.** Clanker02's query engine uses an
`InMemoryVectorStore`; it does not itself enforce Citewiser ACLs, and the
`CrossEncoderReranker` local/non-local branches currently use the same heuristic.
Its auth middleware is a web-app surface, not end-to-end document encryption.
Citewiser's packer passes `allow_unapproved_agentic_nodes=true` in its internal
ranking context at [`packer.go`](https://github.com/mojomast/citewiser/blob/284dc76/pkg/packer/packer.go),
so the proposed wrapper must not treat the packer alone as a final policy gate.
Its docs state callers must redact trails, and unknown sensitivity is fail-closed
but not necessarily warned. Sentinel's anomaly score is not a leak detector.
Parliament is plaintext and unsigned. **Proposed:** enforce ACLs before indexing
and before generation, use recipient allowlists, encrypt indexes and exports,
bind approval to content hashes, and test prompt-injection/exfiltration cases.

**Rejected adjacent components.** A second LLM router was not added: routing
does not solve source authorization or citation leakage and would expand the
unverified orchestration surface.

## 7. Personal agent permission vault

**Target user and pain.** A solo operator wants a local assistant to read notes,
run narrow automations, and remember decisions, but wants secrets, workspace
boundaries, and sharing permissions to be explicit and reviewable.

**Product promise.** “Let a local agent do useful work without granting it
unbounded access to secrets, files, or personal memory.”

**Exact repositories.** `mojomast/openclawssy`, `ussyverse/parliamentussy`,
`ussyverse/quorumussy`.

**Existing evidence.** **Exists:** Openclawssy checks per-agent tool grants in
[`capability.go`](https://github.com/mojomast/openclawssy/blob/46e0018/internal/policy/capability.go),
resolves traversal/symlink-safe workspace paths and protects control-plane files
in [`pathguard.go`](https://github.com/mojomast/openclawssy/blob/46e0018/internal/policy/pathguard.go),
and writes structured append-only JSONL audit events with restricted file modes
in [`logger.go`](https://github.com/mojomast/openclawssy/blob/46e0018/internal/audit/logger.go).
**Exists:** Its secret store uses AES-GCM with a 32-byte master key, atomic
`0600` writes, and `0700` parent directories in
[`secrets/store.go`](https://github.com/mojomast/openclawssy/blob/46e0018/internal/secrets/store.go).
Its `DecisionLedger` records normalized run/agent decision records. **Exists:**
Parliament's hash-linked journal can record approvals. **Exists:** Quorum's
weighted/veto-aware local decision file can collect a household/team consent
decision.

**Proposed handoff/data flow.** The vault stores encrypted secret names/values
through Openclawssy -> an agent requests a capability or a specific export -> a
minimal Quorum decision collects an owner/team approval -> Parliament records
the motion and expiry -> Openclawssy executes only the granted tool/path and
logs a redacted run event -> an export worker produces a selected-field packet,
never the whole memory or secret store.

**Missing integration work.** Add a vault-level approval/export schema, connect
Quorum decisions to Openclawssy capability grants, make Parliament records
tamper-evident and authenticated, and add encrypted retention/rotation flows
for all non-secret stores.

**MVP and acceptance.** One local agent can read `notes/` but not `.openclawssy/`,
can request one time-limited export, and can use one stored API key without the
key appearing in an audit event. Denied traversal, denied capability, approval,
execution, and expiry must all be visible. Rotating the master key and deleting
an export must have explicit operator confirmation.

**Value of combination.** Openclawssy supplies the real enforcement and secret
encryption; Quorum provides a human-readable consent interaction; Parliament
provides a separate integrity-verifiable approval history. The combination
turns “local agent” into a bounded personal-data workflow rather than a chat UI.

**Risks, maturity, and security.** Openclawssy's AES-GCM implementation is
present, but key custody, backup, rotation, and compromise recovery remain
product work. Its generic `RedactString` uses narrow regexes and can miss JSON
quoting, structured PII, or secrets without key-like syntax; the long-token rule
can also over-redact. Audit logs are append-only files, not tamper-evident
signatures. Quorum saves plaintext `0644` JSON. Parliament does not encrypt or
authenticate entries. **Proposed:** keep Openclawssy policy as the enforcement
point, add key rotation/recovery tests, encrypt/permission the other stores, and
use signed export receipts. Do not expose the dashboard beyond a controlled
loopback/tailnet boundary without an authenticated deployment review.

**Rejected adjacent components.** A hosted agent memory service was not added:
it conflicts with the local boundary and would create a new data-exfiltration
dependency rather than improve enforcement.

## 8. Correction evidence review desk

**Target user and pain.** An operator evaluating a personal agent needs to learn
from corrections without retaining raw conversations, prompts, commands, or
tool results in a shared training/evaluation corpus.

**Product promise.** “Measure correction patterns without turning private traces
into reusable raw training data.”

**Exact repositories.** `mojomast/hermes-correction-aware-learning`,
`ussyverse/parliamentussy`, `ussyverse/sentinelussy`.

**Existing evidence.** **Exists:** The correction-aware package constrains IDs,
enums, confidence, and SHA-256 digests in
[`store.py`](https://github.com/mojomast/hermes-correction-aware-learning/blob/84c8c8c/src/correction_aware_learning/store.py),
supports immutable outcome events, supersession, retraction relations, and
cycle checks. **Exists:** Its public projection is explicitly count-only and
fail-closed on privacy/safety invariants in
[`reports.py`](https://github.com/mojomast/hermes-correction-aware-learning/blob/84c8c8c/src/correction_aware_learning/reports.py).
The README says `capture-pytest` discards output/arguments after structural
classification and that the package is shadow-only. **Exists:** Sentinel can
profile/check the local embedding code, with feedback persisted in SQLite.
**Exists:** Parliament can record a motion and hash-linked operator review.

**Proposed handoff/data flow.** A trusted host supplies opaque trace IDs and
allowlisted correction facts -> correction-aware-learning stores only structured
evidence/digests -> Sentinel checks the embedding/reporting adapter for unusual
file access or data retention patterns -> a reviewer sees count-only recurrence
and raw evidence locally -> Parliament records whether a dataset export is
approved, rejected, or revoked. No raw transcript enters the shared report.

**Missing integration work.** Define an authenticated capture adapter, make the
count-only projection the default boundary, connect Sentinel findings to the
capture review, and bind Parliament approvals/retractions to dataset versions.

**MVP and acceptance.** Create three synthetic traces across two sessions, one
strict correction pair, one retraction, and one privacy-canary string. The public
report must contain no raw text, IDs, digests, prompts, commands, or tool
payloads; a malformed safety invariant must fail closed; Parliament must record
the export decision without copying the underlying evidence.

**Value of combination.** Correction-aware-learning supplies a narrow, tested
evidence vocabulary; Sentinel gives the local host a reviewable code change
surface; Parliament adds human governance and revocation history. The result is
an evidence escrow, not an autonomous learner.

**Risks, maturity, and security.** The package's lower-level append API treats
source labels as caller assertions unless the host authenticates the actor and
capture channel. It is shadow-only and does not attest that a `pytest` executable
is genuine. Sentinel stores root paths/source locations and is not a privacy
scanner. Parliament's journal is plaintext and only hash-linked. **Proposed:**
authenticate the capture host, encrypt the private store, minimize retention,
use count-only default exports, and require a human motion before any downstream
training/evaluation consumer receives data. Never activate lessons from the
count alone.

**Rejected adjacent components.** A full autonomous online learner was not
added: it would exceed the package's shadow-only evidence contract and make
privacy deletion/retraction materially harder.

## 9. Least-privilege migration receipt

**Target user and pain.** A small team operating a PostgreSQL-backed personal or
community service needs to change roles/permissions safely and prove later what
was reviewed, which package version supplied the migration, and what rollback
exists, without sending database catalogs to a SaaS compliance system.

**Product promise.** “Approve a least-privilege database change locally and
retain a receipt proving what was examined and what changed.”

**Exact repositories.** `mojomast/PGaudussy`, `ussyverse/mintussy`,
`ussyverse/parliamentussy`.

**Existing evidence.** **Exists:** PGaudussy connects through `pg_service.conf`
or explicit parameters, audits roles/schemas/tables/functions/databases, emits
permission issues, and has dry-run/backup/fix workflows in
[`dbaudit.py`](https://github.com/mojomast/PGaudussy/blob/3ff9aa3/dbaudit.py) and
[`utils/audit.py`](https://github.com/mojomast/PGaudussy/blob/3ff9aa3/utils/audit.py).
`PermissionFixer` generates SQL and rollback SQL in
[`utils/fixes.py`](https://github.com/mojomast/PGaudussy/blob/3ff9aa3/utils/fixes.py);
`BackupManager` invokes local `pg_dump` and records backup metadata in
[`utils/backup.py`](https://github.com/mojomast/PGaudussy/blob/3ff9aa3/utils/backup.py).
**Exists:** Mint can parse a package lockfile and report provenance gaps/hash or
publisher changes. **Exists:** Parliament can record the migration motion,
votes, and integrity-verifiable journal chain.

**Proposed handoff/data flow.** Run PGaudussy against a local/staged database
catalog -> retain a redacted issue set and generated fix/rollback hashes -> Mint
records the exact migration dependency provenance -> Parliament opens a
least-privilege motion with affected role/object classes, not row contents ->
after human approval, apply the SQL in a separately controlled step -> rerun the
audit and append before/after receipt plus backup hash.

**Missing integration work.** Add catalog redaction, safe SQL identifier quoting,
transactional execution, encrypted backup/receipt handling, migration-to-package
mapping, and a post-change failure gate.

**MVP and acceptance.** Use a disposable PostgreSQL fixture with a PUBLIC table
grant and a read-only role. The tool must produce a dry-run script, rollback
script, backup identifier, package provenance record, approval record, and
post-change audit. The receipt must not contain row data, passwords, or raw
connection strings. A failed post-change audit must prevent a “success” status.

**Value of combination.** PGaudussy understands database permissions and
rollback artifacts, Mint supplies software supply-chain context, and Parliament
binds the decision to a human/auditable process. This is a change receipt, not a
generic security score.

**Risks, maturity, and security.** PGaudussy is an early/first serious project,
not source-audited as production-safe. `dbaudit.py` creates directories and
logging at import time; explicit CLI passwords are accepted; logs and backup
metadata contain operational identifiers; backups are not encrypted in inspected
code. Fix SQL is built with f-strings from database/grantee names and needs
identifier quoting and injection tests. A rollback script is not a transaction
or guaranteed semantic inverse. Mint provenance verification is data-model
classification, not actual signature verification. Parliament is plaintext and
unsigned. **Proposed:** use a disposable read-only audit role, secret-file or
OS credential integration, encrypted/permissioned receipts, SQL identifier
quoting, explicit transaction/rollback tests, and a human gate before applying
anything. Do not run the MVP against production first.

**Rejected adjacent components.** A cloud compliance dashboard was not added:
it would require exporting the sensitive catalog and would not fix PGaudussy's
local SQL and credential safety gaps.

## 10. Pseudonymous lead-capacity exchange

**Target user and pain.** Several small makers or community sellers want to
estimate shared demand and decide whether to add a class/waitlist slot, but do
not want to exchange names, email addresses, or phone numbers with one another.

**Product promise.** “Make a cautious shared capacity decision from local lead
lists without exchanging the lists themselves.”

**Exact repositories.** `ussyverse/recapturaussy`, `ussyverse/quorumussy`,
`ussyverse/raciaussy`.

**Existing evidence.** **Exists:** Recaptura normalizes email/phone/handle/name
identities, supports explicit aliases, computes source overlap and Chapman/
Lincoln-Petersen estimates, refuses zero-overlap estimates, warns about dependent
sources, and has `redactIdentityHash` in
[`src/lib.zig`](https://github.com/ussyverse/recapturaussy/blob/2640919/src/lib.zig).
Its build file demonstrates unit/integration test targets, but they were not run
here. **Exists:** Quorum stores local ballots, vetoes, tolerances, and a group
suggestion. **Exists:** Racia checks task ownership, required access, and owner
load in its local TypeScript core.

**Proposed handoff/data flow.** Each participant normalizes and deduplicates raw
leads locally -> the parties exchange only source IDs, counts, overlap summaries,
and a jointly chosen keyed pseudonym scheme -> Recaptura produces a bounded
lower-bound estimate with warnings -> Quorum records whether to open a waitlist
or add a slot -> Racia assigns accountable owners for the agreed follow-up and
required access -> raw contact lists never enter the shared decision file.

**Missing integration work.** Define aggregate-only and keyed-hash exchange
formats, add per-project key rotation and consent/deletion semantics, connect
Recaptura warnings to Quorum decision context, and generate Racia task packets
without contact data.

**MVP and acceptance.** Two local CSV files share three contacts and contain
several unique contacts. Demonstrate a zero-overlap warning and a dependent
source warning, then make a Quorum decision from aggregate numbers. A shared
packet must not contain an email, phone, handle, name, or reversible raw identity
key; each party must be able to reproduce its own aggregate from its local raw
file.

**Value of combination.** Recaptura turns private lists into cautious aggregate
evidence, Quorum turns that evidence into a group decision, and Racia turns the
decision into bounded responsibility. This is useful without centralizing a CRM.

**Risks, maturity, and security.** Recaptura's identity hash uses a fixed
Wyhash seed, not a secret key, so `anon-*` values are pseudonyms rather than
strong anonymization; common emails/phones are vulnerable to dictionary attacks.
Its normalization removes punctuation and can merge or separate people
incorrectly, while capture-recapture assumptions are fragile. Racia and Quorum
are local files with names/notes and no encryption/authentication. **Proposed:**
use a per-project secret keyed hash or avoid sharing pseudonyms entirely, add
explicit consent and deletion/rotation semantics, exchange only aggregates,
encrypt local files, and do not infer individual demand or rank people.

**Rejected adjacent components.** A shared CRM or person-level lead score was
not added: both would centralize identities and turn uncertain population
estimates into individual judgments.

## Rejected ideas

These are intentionally recorded so future agents do not revive attractive but
unsafe combinations without new evidence.

### Rejected A: “One encrypted super-journal”

**Temptation:** combine every local store above, especially Openclawssy secrets,
Parliament decisions, Quorum ballots, Kinship care graphs, and Palyno health
notes, behind one universal encrypted database.

**Why rejected.** Encryption at rest does not solve purpose limitation, recipient
scope, or the danger of correlating unrelated sensitive domains. The inspected
projects use incompatible schemas and retention semantics; most do not have
authenticated multi-user sharing, key rotation, or field-level export policy.
The product would require a large new platform before proving a user outcome and
would create a high-value single compromise target. Prefer narrow stores and
explicit projections, as in ideas 2, 3, 4, and 7.

### Rejected B: “Anonymous family care market”

**Temptation:** use `ussyverse/kinshipussy`, `ussyverse/recapturaussy`, and
`ussyverse/quorumussy` to publish a score ranking relatives or volunteers by
care capacity, reliability, and willingness, using hashed identities so the
ranking appears private.

**Why rejected.** Kinship's capacity, reliability, friction, reciprocity, and
consent values are self-reported/heuristic care-network inputs, not a fair
eligibility or trust credential. Recaptura's fixed-seed identity hash is not
anonymous against dictionary attacks. Quorum's weighted signals and veto
diagnostics are designed to support a conversation, not rank people. A public
ranking would expose sensitive relationship inferences and turn uncertain
signals into a social authority. Use consented task-specific packets, never a
person score.

## Suggested next validation

Start with the smallest non-networked demos for ideas 1, 2, 7, and 10. Pin the
listed revisions, run each repository's documented focused tests, and then test
user-authored data. Security acceptance should include path/URL leakage scans,
secret-canary inputs, tampered journal/hash checks, encrypted-file permission
checks, recipient projection tests, deletion/retention tests, and explicit
unknown states when evidence is missing. No idea should be advertised as
securely shareable until those checks pass.
