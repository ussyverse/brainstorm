# Archives, Genealogy, Evidence, and Personal Knowledge

**Research date:** 2026-09-13
**Scope:** new combinations relative to the ten proposals in `README.md` and
`docs/SOURCE_CHECKED_COMBINATIONS.md`. The existing family-archive proposal is
`ussyverse/cartoucheussy` + `ussyverse/archivioussy`; none of the proposals below
uses that exact pair.

## Reading This Note

**Exists** means the capability was present in source inspected at the revision
listed below. **Proposed** means an adapter, product workflow, or data model that
does not currently exist in the inspected repositories. **Unverified** means a
README, fixture, heuristic, or intended contract was not runtime-tested here.
The proposals retain raw files, source identifiers, revisions, and uncertainty;
they do not treat a score as historical truth or a heuristic as authentication.

I inspected manifests, entry points, core models, and selected implementation
files in the repositories listed below. I ran `git rev-parse HEAD` in each
checkout to record the revision. I did not build, install, or runtime-test these
projects in this pass, and no candidate repository was modified.

| Repository | Inspected revision |
|---|---|
| `mojomast/arrhivescrape` | `afffec1fddbe624b2e1779f689610fb9d7e98c99` |
| `mojomast/BackupUSSY` | `82aa03bf52dbc561d1b24a5bd69df5b1b411b7d0` |
| `mojomast/citewiser` | `284dc76a68ee75517d14bab262c88bc866669b02` |
| `mojomast/hermes-correction-aware-learning` | `84c8c8c7e27c820cbc1aa0a5fcf99f891f503f48` |
| `ussyverse/archivioussy` | `918d6905d9227758fee973b0b303d9c528be22cd` |
| `ussyverse/chunkussy` | `eecbcede0906da72d4b89427d837dd7deaf4d4b7` |
| `ussyverse/codelineageussy` | `e9e4d7722ba6f442c5d72bb8e11e43939ef44587` |
| `ussyverse/curatorussy` | `ce516147688a634a6dd6c6498dcbbeeda1b3b47b` |
| `ussyverse/kinshipussy` | `308bbb34cff23a771419772a21a63cf032f1ca46` |
| `ussyverse/morphemaussy` | `09f8f56f09363347f4ce4b7b81936141d2777f6d` |
| `ussyverse/recapturaussy` | `26409192246c532b78cc51f9c75860b40259ec74` |
| `ussyverse/stenographussy` | `876be3ff4a3c01948bd9e715186d25ed9e6a6506` |
| `ussyverse/taphonussy` | `432c97d8d0e4948ad105c9d58adf6eaaeff07212` |
| `ussyverse/timeloomussy` | `5ff813317842ccfd83cd48b70dcbac14745649bc` |

All revision identifiers above came from the local checkouts at the time of
inspection and should be rechecked if those checkouts are refreshed.

## New Product Ideas

### 1. Heritage Web Recovery Desk

**Target user and pain.** A local historical society, fan archive, or former
site owner has a dead domain and fragmented Wayback captures. Browser replay is
hard to cite, missing assets are invisible, and a rushed public mirror can expose
private names, forms, or tracking material.

**Exact repositories.** `mojomast/arrhivescrape` + `ussyverse/curatorussy` +
`ussyverse/stenographussy`.

**Product promise.** Recover a reviewable static collection, catalog what each
file is, and flag suspicious or privacy-sensitive text before publication.

**Existing evidence.**

- **Exists:** `arrhivescrape/archive_recovery/pipeline/inventory.py` records CDX
  pages, resume state, capture rows, and dependency-recovery records. Its
  `normalization.py` rewrites first-party links, neutralizes forms, writes raw
  and final hashes, and emits a site manifest. Its `validation.py` checks missing
  files, internal references, external references, and MIME/content warnings.
  See [inventory](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/pipeline/inventory.py),
  [normalization](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/pipeline/normalization.py),
  and [validation](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/pipeline/validation.py).
- **Exists:** Curator has `Document`, MARC-like metadata, controlled tags,
  classification, SQLite persistence, accession numbers, exhibitions, and
  conservation reports. See [models](https://github.com/ussyverse/curatorussy/blob/HEAD/curator/models.py),
  [catalog](https://github.com/ussyverse/curatorussy/blob/HEAD/curator/catalog.py),
  and [storage](https://github.com/ussyverse/curatorussy/blob/HEAD/curator/storage.py).
- **Exists:** Stenography scans HTML, text, JSON, and related files for zero-width
  characters, homoglyphs, bidi controls, whitespace patterns, and comment
  steganography, with line/column findings and SARIF output. See
  [engine.py](https://github.com/ussyverse/stenographussy/blob/HEAD/stenography/engine.py)
  and [models.py](https://github.com/ussyverse/stenographussy/blob/HEAD/stenography/models.py).

**Proposed handoff and data flow.** CDX captures and raw blobs -> normalized
site manifest keyed by `run_id`, original URL, capture timestamp, raw hash, and
final hash -> a catalog row for each approved file -> Stenography findings
attached to the same manifest row -> human privacy review -> a private or
public release dossier. A finding is a review prompt, not proof of malicious
intent.

**MVP.** Recover one small, public-domain or owner-authorized site fixture;
display three capture choices, one missing dependency, one normalized page, the
catalog record, and a scan report. Require a human checkbox before copying any
file into a release directory.

**Why the combination earns its complexity.** Recovery, description, and
publication safety are separate jobs. The shared capture/file identity keeps a
catalog note and a scan finding tied to the exact bytes and transformation that
will be released, rather than to an unrepeatable browser view.

**Risks, maturity, and privacy.** Arrhivescrape performs URL rewriting and
content transformation, not historical authenticity. Stenography is a source
scanner and will produce false positives in legacy text; its security severity
must not be copied into an archival judgment. Curator's provenance implementation
uses synthetic file metadata commits in `curator/provenance.py`, so it cannot
establish a real chain of custody without a new importer. Recovered sites may
contain personal data, credentials, or third-party copyrighted material. Keep
all runs private by default and preserve the original archive URLs and raw blobs.

### 2. Tape-to-Finding-Aid Vault

**Target user and pain.** A family historian or small museum has scans, photos,
letters, and born-digital folders on aging disks and wants a searchable record of
where the copies are, which items need gentle handling, and which claims still
need a witness.

**Exact repositories.** `mojomast/BackupUSSY` + `ussyverse/archivioussy` +
`ussyverse/taphonussy`.

**Product promise.** Make redundant storage and intellectual control one
deliberate intake workflow without pretending a checksum proves the story is
true.

**Existing evidence.**

- **Exists:** BackupUSSY's `src/archive_manager.py` has cached tar creation,
  SHA-256 archive checksums, tape/archive records, and file indexing. Its
  `src/database_manager.py` has SQLite tables for tapes, archives, and files,
  search methods, status fields, and inventory export/import. See
  [archive_manager.py](https://github.com/mojomast/BackupUSSY/blob/HEAD/src/archive_manager.py)
  and [database_manager.py](https://github.com/mojomast/BackupUSSY/blob/HEAD/src/database_manager.py).
- **Exists:** Archivio models artifacts, people, source notes, claims,
  evidence links, counterclaims, sensitivity, and verification tasks. The store
  computes attachment SHA-256 fixity and produces finding-aid Markdown. See
  [models.py](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/models.py)
  and [storage.py](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/storage.py).
- **Exists:** Taphon parses JSON, CSV, TOML, text, and Markdown inventories into
  keepsake items, preserves assemblage/context notes, and emits risk pathways,
  context integrity, minimal-intervention actions, and warnings against cleaning,
  laminating, gluing, or discarding labels. See [lib.rs](https://github.com/ussyverse/taphonussy/blob/HEAD/src/lib.rs).

**Proposed handoff and data flow.** Intake folder -> a manifest with a stable
`item_id`, source path, archive job ID, tape label, archive checksum, and
attachment hash -> Archivio artifact/source-note records -> Taphon inventory and
preservation report -> human-added claim/evidence links -> finding aid plus a
recovery lookup that points to tape/archive/file location. Never infer a claim
from an object name alone.

**MVP.** Use a local folder and an exported BackupUSSY inventory before requiring
physical tape hardware. Accession five files and two boxes, record one disputed
date, run Taphon on the box inventory, and show a finding aid that says both
which copy is stored where and which evidence is missing. Tape write/recovery is
a later acceptance test, not an assumed MVP capability.

**Why the combination earns its complexity.** BackupUSSY answers "where is the
byte copy?", Archivio answers "what does the family say about it?", and Taphon
answers "what context or material condition should not be lost while moving it?"
Separate tools leave those identifiers disconnected.

**Risks, maturity, and privacy.** BackupUSSY explicitly labels itself active,
experimental, Windows-oriented, and not production-ready. Its file index sets
`file_checksum` to `None` in the inspected archive path, so the product must not
claim file-level fixity from the database. Archivio JSON export includes all
artifact dictionaries and local paths even when claim filtering is applied; a
new safe export projection is mandatory. Taphon is a keyword/rule triage aid,
not conservation expertise. Tape labels, family names, and paths are sensitive;
encrypt or keep the index offline and separate shareable finding aids from the
full vault.

### 3. Family Care Handoff from Evidence

**Target user and pain.** Relatives coordinating elder care, a move, or an
estate have boxes of documents and keepsakes but also need a current, consented
answer to "who knows this, who does the work, and what breaks if they are away?"
Historical relationship claims and present-day obligations are often conflated.

**Exact repositories.** `ussyverse/archivioussy` + `ussyverse/kinshipussy` +
`ussyverse/taphonussy`.

**Product promise.** Produce a handoff packet that distinguishes documented
family history, physical-object context, and explicitly agreed current care.

**Existing evidence.**

- **Exists:** Archivio has typed `PersonRef`, sensitivity/living flags, claims,
  source notes, evidence links, counterclaims, and verification tasks. See
  [models.py](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/models.py).
- **Exists:** Kinshipussy accepts people and care edges with tie type, care type,
  hours, cognitive load, criticality, reliability, consent, explicitness, and
  friction. `Report()` emits care loads, ambiguity alerts, backup gaps,
  household clusters, and neutral conversation prompts. See
  [types.go](https://github.com/ussyverse/kinshipussy/blob/HEAD/kinship/types.go)
  and [analysis.go](https://github.com/ussyverse/kinshipussy/blob/HEAD/kinship/analysis.go).
- **Exists:** Taphon preserves assemblage, location, materials, condition notes,
  and context notes and warns when labels, envelopes, companions, or context
  should be documented before rearrangement. See [lib.rs](https://github.com/ussyverse/taphonussy/blob/HEAD/src/lib.rs).

**Proposed handoff and data flow.** Human-reviewed Archivio people and claim
records -> a separate current-care editor that creates Kinshipussy people and
care edges only after consent -> simulated absence and backup-gap report -> a
Taphon report for the physical box or document group -> a filtered handoff card
with links to approved artifacts and explicit unresolved questions. A historical
claim must never silently create a living person's care obligation.

**MVP.** Five people, three care edges, one caregiver unavailable, and one box
containing a labeled photo, an unlabeled envelope, and a disputed story. The
acceptance demo must show a neutral backup prompt and a source link, while
keeping the claim and care edge as separate records.

**Why the combination earns its complexity.** Archivio handles evidentiary
status, Kinshipussy handles current labor and backup structure, and Taphon
handles the physical/context preservation problem. A family can act on a care
gap without rewriting uncertain genealogy.

**Risks, maturity, and privacy.** Kinshipussy scores are planning heuristics,
not objective measures of love, duty, reliability, or family identity. Its report
uses current time for decay and exposes health-adjacent care categories; the
product needs consent, access controls, and a non-accusatory display. Archivio's
living-person redaction is simple string matching, and Taphon cannot assess
actual conservation conditions from prose. Do not share raw relationship notes
or medical paperwork by default.

### 4. Correction-Aware Research Notebook

**Target user and pain.** An independent researcher or investigative writer
revises an interpretation as new sources arrive. Ordinary notes overwrite the
old reading, while ordinary RAG answers hide which source version was admitted
or suppressed.

**Exact repositories.** `mojomast/hermes-correction-aware-learning` +
`mojomast/citewiser` + `ussyverse/archivioussy` + `ussyverse/curatorussy`.

**Product promise.** Keep a cited current reading, its superseded readings, and
the reason for correction in one local notebook, without auto-updating a claim
or teaching the user that a recurrence count is truth.

**Existing evidence.**

- **Exists:** Correction-aware-learning has an append-only SQLite schema for
  trace contexts, outcome events, relations, supersession, retraction, digests,
  cycle checks, effective-evidence queries, and count-only recurrence reports.
  It explicitly keeps `activation_allowed` false. See
  [schema.py](https://github.com/mojomast/hermes-correction-aware-learning/blob/HEAD/src/correction_aware_learning/schema.py)
  and [store.py](https://github.com/mojomast/hermes-correction-aware-learning/blob/HEAD/src/correction_aware_learning/store.py).
- **Exists:** CitewiseRAG applies access gates before deterministic ranking and
  context packing, preserves source refs/trails, versions, locators, hygiene
  signals, and plan hashes. It consumes candidates; it does not retrieve,
  chunk, or call an LLM. See [README](https://github.com/mojomast/citewiser/blob/HEAD/README.md)
  and the `pkg/provenance`, `pkg/access`, and `pkg/packer` packages.
- **Exists:** Archivio stores claim/evidence/counterclaim relationships and
  source notes. Curator supplies document metadata, classification, accession,
  and a local SQLite audit surface. See [Archivio storage](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/storage.py)
  and [Curator CLI](https://github.com/ussyverse/curatorussy/blob/HEAD/curator/cli.py).

**Proposed handoff and data flow.** Local source files and notes -> Archivio
artifact/claim records plus curator catalog rows -> a manual or existing
retriever produces Citewise candidate nodes with claim ID, source revision,
locator, sensitivity, and evidence path -> Citewise emits an access-checked
context plan -> a researcher accepts or rejects an interpretation -> the
correction ledger records an opaque event, supersession, digest, and later human
verification. Raw prose remains in the notebook, not in the correction package.

**MVP.** Five Markdown sources, three claims, one superseded interpretation,
one restricted source, and one later correction. Manually construct the
candidate JSON expected by Citewise; show the accepted packet, suppressed-node
reasons, and append-only correction history. No LLM answer generation is needed.

**Why the combination earns its complexity.** Archivio gives a human-readable
claim graph, Curator makes the document collection navigable, Citewise makes a
bounded cited packet, and the correction ledger prevents revision history from
being erased. This is a research notebook, not an autonomous knowledge system.

**Risks, maturity, and privacy.** Citewise's access policy is not a complete
viewer authorization model, and it requires an upstream retrieval adapter. The
correction package stores opaque identifiers and caller assertions, not actor
authentication or raw content. Curator's provenance chain is synthetic unless
replaced, and Archivio's JSON export is not safely filtered at artifact level.
The adapter must preserve source revision and locator data and must show
  "unverified" rather than converting confidence into fact.

### 5. Archive Reading Desk

**Target user and pain.** A student, volunteer transcriber, or researcher reads
dense historical prose or a technical finding aid. Rereading produces vague
familiarity, while unfamiliar terms and false etymologies cause confident
misreadings.

**Exact repositories.** `ussyverse/chunkussy` + `ussyverse/morphemaussy` +
`ussyverse/curatorussy`.

**Product promise.** Turn a cataloged source into short, source-linked
reconstruction prompts and an explicit glossary, while preserving the original
transcript and every uncertainty marker.

**Existing evidence.**

- **Exists:** Chunk's C API parses sentences, classifies definition/causal/list/
  comparison structure, groups three-to-five items, produces a tree, generates
  reconstruction prompts, interleaves review, and calibrates confidence against
  correctness. See [chunk.h](https://github.com/ussyverse/chunkussy/blob/HEAD/chunk.h)
  and [chunk.c](https://github.com/ussyverse/chunkussy/blob/HEAD/chunk.c).
- **Exists:** Morphema supports an editable local morpheme table, greedy
  segmentation, aliases/allomorphs, false-split warnings, custom vocabulary,
  transfer attempts, word families, and printable study sheets. See
  [lib.rs](https://github.com/ussyverse/morphemaussy/blob/HEAD/src/lib.rs).
- **Exists:** Curator can catalog Markdown documents, normalize controlled tags,
  classify a collection, check cross-reference integrity, and persist audit
  records. See [catalog.py](https://github.com/ussyverse/curatorussy/blob/HEAD/curator/catalog.py).

**Proposed handoff and data flow.** A source file plus edition/page metadata ->
Curator accession and catalog record -> Chunk creates a chunk record with
source revision and character/page offsets added by the adapter -> a reader
selects unfamiliar terms and supplies or approves Morphema entries -> prompts,
answers, confidence, and corrections are stored beside the source locator.
Chunk's generated grouping is a study aid, not a statement about the author's
argument structure.

**MVP.** One two-page public-domain transcript, six manually approved glossary
entries, four chunks, and one high-confidence wrong reconstruction. The demo
must let a reader open the exact source passage from a prompt and export a plain
text review sheet.

**Why the combination earns its complexity.** Curator answers "which edition
and where?", Chunk answers "what can I reconstruct?", and Morphema answers "what
does this unfamiliar word appear to contain, with what warnings?" The resulting
study artifact has provenance rather than detached flashcards.

**Risks, maturity, and privacy.** Chunk has fixed sentence/text limits and
keyword-overlap heuristics; it does not understand argument or OCR quality.
Morphema's confidence is a segmentation/productivity heuristic, not validated
etymology, and its greedy matching can be wrong. Curator's default provenance
logic is aimed at software documentation. Preserve OCR, diplomatic transcript,
normalized text, and user interpretation as distinct layers.

### 6. Versioned Oral-History Notebook

**Target user and pain.** A small oral-history project collects interviews in a
Git-backed Markdown folder. Editors need to improve readability without losing
the witness's words, the chain of custody, or the exact revision that supported
a published claim.

**Exact repositories.** `ussyverse/archivioussy` + `ussyverse/curatorussy` +
`ussyverse/timeloomussy`.

**Product promise.** Make transcript revisions inspectable as editorial events,
not silent replacements, and attach each claim to a source-note version.

**Existing evidence.**

- **Exists:** Archivio has `SourceNote` fields for witness, citation, transcript,
  interview date, and chain-of-custody text, plus claims, evidence links, and
  fixity reports. See [models.py](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/models.py).
- **Exists:** Curator has document cataloging, accession records, Markdown link
  checks, and provenance/audit storage. Its implementation details are in
  [cli.py](https://github.com/ussyverse/curatorussy/blob/HEAD/curator/cli.py)
  and [provenance.py](https://github.com/ussyverse/curatorussy/blob/HEAD/curator/provenance.py).
- **Exists:** Timeloom parses Git commits into file/change-type records and
  builds a binary file-by-commit co-change matrix, then reports repeated patterns
  and coupling clusters. See [git_parser.py](https://github.com/ussyverse/timeloomussy/blob/HEAD/src/timeloom/git_parser.py)
  and [analysis.py](https://github.com/ussyverse/timeloomussy/blob/HEAD/src/timeloom/analysis.py).

**Proposed handoff and data flow.** Transcript, audio checksum, consent form,
and finding aid -> Archivio source note and artifact -> Curator catalog keyed by
transcript path and revision -> Timeloom history report -> a new line/claim
locator table that records which revision a human used. Co-change clusters may
show that transcript and metadata changed together; they must not be described
as proof of editorial misconduct or source dependence.

**MVP.** Three committed transcript revisions, one audio/file hash, one disputed
name, and one published claim. Show a timeline with the raw and normalized text,
the exact revision link, a Timeloom file-history summary, and a human-entered
resolution.

**Why the combination earns its complexity.** Archivio preserves testimony and
claim status, Curator provides collection-level finding aids, and Timeloom
provides a compact view of editorial change patterns. The combination supports
review without pretending that Git history is the whole provenance record.

**Risks, maturity, and privacy.** Timeloom is file-level history and its commit
type classification is keyword based; it cannot identify a real author or prove
that a change altered meaning. Curator's inspected provenance implementation
creates synthetic commits from file metadata rather than reading Git history.
Archivio stores external paths and its living-person redaction is limited. Keep
audio, consent, names, and transcript exports in separate access tiers.

### 7. Genealogy Record Reconciliation Workbench

**Target user and pain.** A family historian or local genealogy society compares
partial indexes, family spreadsheets, cemetery records, and oral recollections.
They need to know which sources overlap and which identity matches require review,
not a silent merge based on a shared name.

**Exact repositories.** `ussyverse/kinshipussy` + `ussyverse/archivioussy` +
`ussyverse/recapturaussy`.

**Product promise.** Quantify source overlap as a lead for investigation, keep
manual identity merges explicit, and only then let a human create a current or
historical relationship record.

**Existing evidence.**

- **Exists:** Recaptura normalizes email, phone, handle, name, and postal fields;
  accepts explicit aliases; builds overlap matrices; refuses zero-overlap
  estimates; emits warnings for sparse/ambiguous/dependent sources; and can
  redact identity keys. See [lib.zig](https://github.com/ussyverse/recapturaussy/blob/HEAD/src/lib.zig).
- **Exists:** Archivio represents artifacts, people, claims, source notes,
  evidence links, contradictions, and verification tasks. See [storage.py](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/storage.py).
- **Exists:** Kinshipussy can model explicit people and tie/care edges and
  produce household/relationship analysis only after those records exist. See
  [types.go](https://github.com/ussyverse/kinshipussy/blob/HEAD/kinship/types.go).

**Proposed handoff and data flow.** Imported record rows with source IDs -> a
review queue for exact, alias, and name-only matches -> Recaptura overlap report
with source relationship assumptions and warnings -> human accepts or rejects an
identity alias -> Archivio evidence link to the original record -> optional
Kinshipussy edge with its own date, basis, and consent/status fields. The
statistical estimate is used to decide what to investigate, never to assert how
many people existed.

**MVP.** Three small, public or synthetic datasets with repeated names and one
false match. Show a zero-overlap refusal, a manual alias review, an overlap
warning, and a family claim whose evidence links still point to the source rows.
Do not ingest living-person data for the first demonstration.

**Why the combination earns its complexity.** Recaptura exposes the shape of
the reconciliation problem, Archivio preserves the evidentiary trail, and
Kinshipussy provides a separate graph for a deliberately accepted relationship.
This is safer than treating a deduplication score as a family tree.

**Risks, maturity, and privacy.** Recaptura's capture-recapture assumptions
were designed for lead lists, not genealogy; independence, capture probability,
and name normalization are likely invalid. Its name-only key is explicitly
ambiguous. Kinshipussy's graph scores are not genealogical proof. Archivio's
default data model includes living/private flags but does not solve access
control. Use opaque local IDs, minimize living-person fields, preserve raw source
rows, and label all match results as candidates pending review.

### 8. Recovery Release Ledger

**Target user and pain.** An archivist repeats recovery of the same dead site as
new captures or dependencies appear. They need to explain what was added,
rewritten, or left unresolved in each release and why a current mirror differs
from an earlier one.

**Exact repositories.** `mojomast/arrhivescrape` + `ussyverse/curatorussy` +
`ussyverse/timeloomussy`.

**Product promise.** Turn successive recovery runs into comparable, reviewable
release dossiers rather than a pile of staging directories.

**Existing evidence.**

- **Exists:** Arrhivescrape persists run IDs, frozen run configuration, raw
  content-addressed downloads, capture manifests, normalization records with
  raw/final hashes, unresolved links, collision status, and validation reports.
  See [state.py](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/state.py)
  and [normalization.py](https://github.com/mojomast/arrhivescrape/blob/HEAD/archive_recovery/pipeline/normalization.py).
- **Exists:** Curator has accession numbers, document metadata, condition/link
  reports, and an audit JSON projection. See [conservation.py](https://github.com/ussyverse/curatorussy/blob/HEAD/curator/conservation.py).
- **Exists:** Timeloom parses commit timestamps, authors, messages, rename rows,
  file changes, and co-change matrices, with JSON-friendly analysis models. See
  [git_parser.py](https://github.com/ussyverse/timeloomussy/blob/HEAD/src/timeloom/git_parser.py).

**Proposed handoff and data flow.** Approved Arrhivescrape run directory -> a
Git-backed release repository with generated files and a sidecar preserving
capture/run IDs -> Curator catalog and release accession -> Timeloom analysis of
release commits -> a comparison report that uses direct manifest/hash joins for
content truth and Timeloom only for change-context visualization. Unresolved
links and skipped captures remain first-class records.

**MVP.** Run the pipeline against a checked-in local fixture twice, with a new
capture/dependency represented in the second fixture. Commit each approved
release, then show direct file/hash additions and a Timeloom change matrix. The
demo must distinguish "new bytes" from "files changed together."

**Why the combination earns its complexity.** Arrhivescrape supplies exact
capture evidence, Curator supplies a human-facing release shelf, and Timeloom
helps an operator inspect the shape of repeated release changes. The direct
manifest comparison, not a metaphorical score, is the product's authority.

**Risks, maturity, and privacy.** Timeloom cannot compare arbitrary files by
content and has no semantic diff; generated manifests can dominate its matrix.
Curator's documentation deterioration model uses assumptions about code age,
links, and dependencies that do not directly measure historical-site quality.
Arrhivescrape's normalized output is a transformation, not an authentic copy.
Never delete prior raw runs, and review query strings, forms, names, and
third-party assets before any release is public.

### 9. Private Cited Knowledge Shelf

**Target user and pain.** A family researcher, small archive, or research group
needs to share a narrow packet with a collaborator while retaining private
notes, living-person information, source paths, and unresolved counterclaims.
"Export the folder" is too broad, while a chat summary loses citations.

**Exact repositories.** `mojomast/citewiser` + `ussyverse/archivioussy` +
`ussyverse/curatorussy`.

**Product promise.** Build audience-specific, citation-bearing reading packets
from a private collection and show what was deliberately omitted.

**Existing evidence.**

- **Exists:** Citewise has hard access checks before ranking/packing, source
  refs/trails, locators, suppression reasons, hygiene signals, deterministic
  context plans, and JSON/stdio/HTTP surfaces. See [README](https://github.com/mojomast/citewiser/blob/HEAD/README.md)
  and the `pkg/access`, `pkg/provenance`, and `pkg/packer` implementations.
- **Exists:** Archivio has `ExportProfile`, claim sensitivity/confidence,
  living/private person fields, counterclaims, finding-aid Markdown, and fixity
  reporting. See [export.py](https://github.com/ussyverse/archivioussy/blob/HEAD/src/archivio/export.py).
- **Exists:** Curator has audience-targeted exhibitions, classification facets,
  catalog completeness, and shelf browsing. See [cli.py](https://github.com/ussyverse/curatorussy/blob/HEAD/curator/cli.py)
  and [exhibition.py](https://github.com/ussyverse/curatorussy/blob/HEAD/curator/exhibition.py).

**Proposed handoff and data flow.** Archivio claim/artifact collection -> Curator
assigns audience facet and selects a shelf -> an adapter creates Citewise nodes
with sensitivity, source revision, artifact ID, locator, and evidence path ->
Citewise filters and packs a query-specific packet -> export includes citations,
suppression counts, unresolved questions, and a manifest of included files. The
adapter must independently filter attachments, not rely on claim visibility.

**MVP.** Five local notes, two artifacts, one living person, one private claim,
one counterclaim, and two audiences. Produce a family-only packet and a
collaborator packet, then inspect the packet manifest and suppressed reasons.
No remote retrieval or LLM is required; candidate nodes can be authored by hand.

**Why the combination earns its complexity.** Curator makes a collection
browseable, Archivio preserves the human evidence graph, and Citewise makes the
handoff deterministic and auditable. It solves a sharing task rather than
adding another search dashboard.

**Risks, maturity, and privacy.** Archivio's `export_json` currently includes
all artifacts even when claims are filtered, and its living-name redaction is
string based. Citewise's approval field is not by itself a viewer allow-list and
its upstream candidate contract is new integration work. Curator's provenance
and deterioration scores are not archival authenticity measures. Treat every
share export as a new privacy review, keep local paths out of packets, and
retain a machine-readable source manifest for later audit.

## Rejected Adjacent Ideas

### A. Automatic Genealogy Graph from All Archive Claims

**Temptation.** Feed every Archivio claim and source note directly into
Kinshipussy, use Recaptura's aliases to merge names, and publish a family tree
with care-load scores.

**Reason rejected.** These components do not establish identity, parentage, or
consent. Recaptura's estimates and name normalization are for overlapping lead
sources; Kinshipussy's edges are explicitly entered care relationships, not a
genealogy engine. The workflow would turn uncertain stories and living-person
data into authoritative relationships. Idea 7 retains a bounded human review
queue instead.

### B. One-Click Public Mirror of Any Recovered Site

**Temptation.** Run Arrhivescrape, pass the result through Stenography, and
publish automatically when no invisible-character finding is reported.

**Reason rejected.** A clean steganography scan says nothing about copyright,
personal data, historical authenticity, third-party assets, or unsafe forms.
Arrhivescrape's own validation and publication controls require an explicit
privacy decision, and its normalized site is a transformed representation. Idea
1 keeps a human release gate and treats security findings as review evidence,
not as a publication authority.

## Next Validation Steps

1. Pin fresh commits and test the smallest local fixture for Ideas 1, 2, and 9;
   these have the clearest file/manifest boundaries.
2. Design one portable sidecar schema for `source_id`, `revision`, `locator`,
   `raw_hash`, `derived_hash`, sensitivity, and review status. Do not force
   Archivio, Citewise, Curator, and Taphon IDs to be equal.
3. Test export redaction with living names, local paths, private attachments,
   counterclaims, and changed files before using any real family collection.
4. Validate user pain with one archivist, one family historian, and one oral
   history editor before building a shared web service.
