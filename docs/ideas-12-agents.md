# New Agent-Oriented Product Ideas

**Date:** 2026-09-13

**Scope:** Eight new agent-specific product candidates, plus two rejected
directions. This pass avoids the current source-checked shortlist and the
existing numbered notes that already cover documentation drift, generic test
evidence, pipeline handoff rehearsal, private agent permissions, and general
release evidence.

## Evidence Boundary

**Exists** means the named capability was present in source inspected during
this pass. **Proposed** means a new adapter, shared data model, product surface,
or workflow. **Unverified** means runtime behavior, end-to-end compatibility, or
domain value was not established here.

The relevant source was inspected in:

- `mojomast/clanker03`
- `mojomast/becomussy`
- `mojomast/hermes-agent`
- `mojomast/nexussy`
- `ussyverse/chainletussy`
- `ussyverse/rosettussy`
- `ussyverse/codelineageussy`
- `ussyverse/reverseoracleussy`
- `ussyverse/meridianussy`
- `ussyverse/clavisussy`
- `ussyverse/operonussy`
- `ussyverse/curatorussy`

Recorded revisions available from the inspected checkouts were:

| Repository | Revision |
|---|---|
| `mojomast/clanker03` | `e9f8608828c31077980f9e86224799c60c8f73e4` |
| `mojomast/becomussy` | `7ac531e2f48ece3e5f2013eddf6d5fd8cde7af3f` |
| `ussyverse/rosettussy` | `59a85443b6d63f5d31b090333c9235e241c1e74c` |

The source inspection used workspace reads and `git rev-parse --verify HEAD` in
the recorded checkouts. Revisions for the other cited checkouts were not
recorded in this handoff. No candidate was installed, built, modified, or
runtime-tested. No test result is claimed.

## Ranking

The order favors a recurring task for an identifiable user, a natural shared
entity, useful output from saved local inputs, concrete source reuse, and small
adapter scope. It is a product judgment, not a market estimate.

| Rank | Product | Exact repositories | Deliverable |
|---:|---|---|---|
| 1 | Trajectory-to-regression clinic | `mojomast/clanker03` + `mojomast/hermes-agent` + `ussyverse/chainletussy` + `ussyverse/rosettussy` | Reproducible agent regression case and practice card |
| 2 | Self-revision adoption dossier | `mojomast/becomussy` + `ussyverse/codelineageussy` + `ussyverse/reverseoracleussy` | Human decision record for an agent-proposed revision |
| 3 | Critical-path agent brief | `mojomast/nexussy` + `ussyverse/meridianussy` + `ussyverse/rosettussy` | Smallest next-task packet with dependency and contract context |
| 4 | Agent exception key | `mojomast/hermes-agent` + `ussyverse/clavisussy` + `ussyverse/operonussy` | Deterministic exception classification and response card |
| 5 | Evidence retention planner | `mojomast/clanker03` + `mojomast/becomussy` + `ussyverse/curatorussy` + `ussyverse/chainletussy` | Reviewable retention and replay schedule |
| 6 | Tool-contract drift drill | `mojomast/nexussy` + `ussyverse/rosettussy` + `ussyverse/clavisussy` | Interactive contract check for agent tools |
| 7 | Delegation bottleneck review | `mojomast/hermes-agent` + `ussyverse/meridianussy` + `ussyverse/chainletussy` | Intervention brief for repeated delegation blockage |
| 8 | Agent repository transfer pack | `mojomast/clanker03` + `ussyverse/codelineageussy` + `ussyverse/curatorussy` + `ussyverse/rosettussy` | Evidence-linked transfer packet for a new agent or maintainer |

## 1. Trajectory-to-Regression Clinic

**Exact repositories:** `mojomast/clanker03`, `mojomast/hermes-agent`,
`ussyverse/chainletussy`, `ussyverse/rosettussy`

**User and recurring pain:** An agent-platform maintainer sees a bad tool
choice, repeated correction, or unsafe delegation in a real session. They can
read the transcript, but turning that event into a small deterministic
regression case is slow and often loses the surrounding state.

**Product promise:** "Turn one reviewed agent trajectory into a replayable case
that tests routing, procedure execution, and tool-contract clarity."

**Input -> processing -> output:** Saved session events, decision points, state
snapshots, selected tool inputs/outputs, and reviewer correction -> extract a
minimal trajectory, convert it to a Hermes evaluation case, replay the related
procedure against Chainlet's attempt model, and inspect callable documentation
with Rosetta -> a JSONL regression case plus Markdown practice card containing
the original event, minimized context, expected decision, observed decision,
and next review action.

**Existing source to reuse:**

- **Exists:** [`clanker03/agentreplay/schema.sql`](https://github.com/mojomast/clanker03/blob/HEAD/agentreplay/schema.sql) stores ordered sessions/events, blobs, snapshots, decision points, and summaries.
- **Exists:** [`clanker03/agentreplay/store.ts`](https://github.com/mojomast/clanker03/blob/HEAD/agentreplay/store.ts) implements `recordEvent`, `createSnapshot`, `recordDecision`, `getDecisions`, and paginated event access.
- **Exists:** [`hermes-agent/agent/task_router_eval.py`](https://github.com/mojomast/hermes-agent/blob/HEAD/agent/task_router_eval.py) loads golden cases and measures route accuracy, over/under-delegation, unsafe delegation, and parallel precision/recall.
- **Exists:** [`chainletussy/src/chainletussy/analyzer.py`](https://github.com/ussyverse/chainletussy/blob/HEAD/src/chainletussy/analyzer.py) calculates chain breaks, prompt dependence, fading/escalation recommendations, and guardrails.
- **Exists:** [`rosettussy/src/rosetta/inscription.py`](https://github.com/ussyverse/rosettussy/blob/HEAD/src/rosetta/inscription.py) compares callable docstrings, arguments, returns, and a minimal runtime witness.

**Missing integration work:** Define a redacted `TrajectoryCase` schema; map
event IDs to stable task/tool IDs; minimize context without changing the
decision; capture reviewer-labeled expected behavior; export a Hermes JSONL
case; and keep raw trajectory data separate from the shareable case.

**Maturity and feasibility caveats:** AgentReplay stores full blobs and may
contain secrets or private prompts. Hermes cases encode maintainer expectations,
not model-independent truth. Chainlet's prompt and error classifications are
heuristics. Rosetta's runtime witness cannot safely exercise arbitrary tools.
**Proposed** minimization and redaction are **Unverified**.

**Smallest useful demo:** Select one recorded tool-selection mistake, replace
private input with a fixture, produce one Hermes case and one Chainlet card, and
rerun the case after changing the routing rule.

**Acceptance criteria:**

- The regression case links to the source event and records what was removed during minimization.
- Private blobs are not copied into the exported case by default.
- Expected route, actual route, and reviewer correction remain separate fields.
- Replaying the saved case requires no live model call.
- A failed or incomplete replay is labeled unknown rather than passing.

**Why better than separate tools:** AgentReplay supplies the concrete incident,
Hermes turns it into a repeatable evaluation, Chainlet describes the human/tool
procedure around it, and Rosetta exposes a contract gap that may explain the
failure. The output is a new regression fixture, not another transcript viewer.

**Rejected adjacent components:** Game engines and game-agent replay tools were
not added. `clanker03` already appears in the game-oriented notes; this proposal
uses general agent task decisions and deliberately excludes game state.

## 2. Self-Revision Adoption Dossier

**Exact repositories:** `mojomast/becomussy`, `ussyverse/codelineageussy`,
`ussyverse/reverseoracleussy`

**User and recurring pain:** A team allows an agent to propose changes to its
own prompts, policies, or supporting code. Reviewers need to know whether the
proposal resembles a known repository pattern, whether the alternative behaves
better in a controlled comparison, and why the proposal was adopted or rejected.

**Product promise:** "Make an agent self-revision reversible, comparable, and
human-adopted rather than silently self-modifying."

**Input -> processing -> output:** Revision proposal plus baseline and
alternative checkout -> run baseline/counterfactual tests, compare code metrics,
trace changed functions through history, and create an approval/rejection/
deferral record -> a dossier containing the proposal, alternative, test results,
lineage evidence, reviewer rationale, and adoption state.

**Existing source to reuse:**

- **Exists:** [`becomussy/backend/app/models/governance.py`](https://github.com/mojomast/becomussy/blob/HEAD/backend/app/models/governance.py) defines an immutable `ApprovalDecision` with actor, timestamp, notes, requested evidence, and decision state.
- **Exists:** [`becomussy/backend/app/services/governance/__init__.py`](https://github.com/mojomast/becomussy/blob/HEAD/backend/app/services/governance/__init__.py) implements approve, reject, defer, evidence-count policy, and freeze controls.
- **Exists:** [`reverseoracleussy/src/reverseoracle/evaluator.py`](https://github.com/ussyverse/reverseoracleussy/blob/HEAD/src/reverseoracle/evaluator.py) evaluates baseline/counterfactual pytest results, code metrics, and textual differences.
- **Exists:** [`reverseoracleussy/src/reverseoracle/models.py`](https://github.com/ussyverse/reverseoracleussy/blob/HEAD/src/reverseoracle/models.py) stores `DecisionContext`, `EvolutionStep`, `EvaluationResult`, and `AnalysisReport`.
- **Exists:** [`codelineageussy/src/codelineage/core.py`](https://github.com/ussyverse/codelineageussy/blob/HEAD/src/codelineage/core.py) traces Python function history and emits structural evolution detections.

**Missing integration work:** Bind proposals to immutable source revisions;
create isolated candidate worktrees; map proposal claims to test evidence and
lineage records; require an explicit rollback pointer; and make approval apply
only after the saved dossier is complete.

**Maturity and feasibility caveats:** Becomussy's freeze state is in-memory in
the inspected MVP. ReverseOracle runs pytest directly and does not establish
environment parity. Codelineage analyzes Python functions and its evolutionary
labels are heuristic. **Proposed** application/rollback behavior and the
cross-repository contract are **Unverified**.

**Smallest useful demo:** Propose one prompt/config change and one code
alternative, run both against a tiny fixture, show a history match, then defer
the proposal while requesting a missing test.

**Acceptance criteria:**

- The approved record names exact baseline and candidate revisions.
- Rejection and deferral preserve the candidate and requested evidence.
- Tests, lineage findings, and reviewer rationale are separate evidence types.
- No proposal is applied as a side effect of generating the dossier.
- A rollback target is present before an approval can be marked adoptable.

**Why better than separate tools:** ReverseOracle measures the alternative,
Codelineage supplies repository history, and Becomussy controls the irreversible
decision. The product makes self-improvement a governed change process instead
of an opaque agent capability.

**Rejected adjacent components:** A larger swarm or second model router was not
added. More generation capacity does not supply the rollback and adoption
record that this workflow requires.

## 3. Critical-Path Agent Brief

**Exact repositories:** `mojomast/nexussy`, `ussyverse/meridianussy`,
`ussyverse/rosettussy`

**User and recurring pain:** An operator starts an agent build run with a long
task list. The agent spends time on a visible task that does not unlock the next
work, while a missing dependency or undocumented interface blocks the actual
critical path.

**Product promise:** "Give the agent and its human owner the smallest next task,
why it unlocks work, and which contract is still unclear."

**Input -> processing -> output:** Approved task list with dependencies,
estimated effort, repository files, and desired audience -> Meridian computes
bottlenecks, steep dependency transitions, contour clusters, and critical route;
Nexussy supplies phase/review artifact boundaries; Rosetta checks selected
callable contracts -> a bounded next-task brief with unlock score, dependencies,
source files, documentation gaps, and a stop/review condition.

**Existing source to reuse:**

- **Exists:** [`meridianussy/pkg/meridian/analysis.go`](https://github.com/ussyverse/meridianussy/blob/HEAD/pkg/meridian/analysis.go) implements `Bottlenecks`, `SteepClimbs`, `ContourClusters`, and `CriticalRoute` over dependency-linked tasks.
- **Exists:** [`nexussy/core/nexussy/artifacts/store.py`](https://github.com/mojomast/nexussy/blob/HEAD/core/nexussy/artifacts/store.py) defines anchored artifact paths and safe atomic writes with SHA-256 results.
- **Exists:** [`nexussy/core/nexussy/pipeline/stages/review.py`](https://github.com/mojomast/nexussy/blob/HEAD/core/nexussy/pipeline/stages/review.py) reviews plans and handoffs for unclear tasks, cross-boundary risks, and development readiness.
- **Exists:** [`rosettussy/src/rosetta/inscription.py`](https://github.com/ussyverse/rosettussy/blob/HEAD/src/rosetta/inscription.py) provides source-level argument/return/docstring comparison and runtime-witness divergences.

**Missing integration work:** Define a task ID contract between Meridian and
Nexussy; map task IDs to files and callables; preserve the raw dependency graph;
make effort units explicit; and prevent the brief from silently becoming an
autonomous task assignment.

**Maturity and feasibility caveats:** Meridian's effort and unlock values are
planning heuristics. Nexussy's artifact anchors are specialized to its own
pipeline files. Rosetta's runtime check is limited and may invoke code with
side effects. **Proposed** task mapping and agent consumption are
**Unverified**.

**Smallest useful demo:** Use five local tasks with one dependency bottleneck
and one undocumented function. Generate a brief for the bottleneck task and
require human confirmation before handing it to the agent.

**Acceptance criteria:**

- The brief shows the dependency path and calculation inputs behind its chosen task.
- A task with missing dependencies is blocked or marked unknown, not promoted.
- Callable/documentation findings link to exact files and symbols.
- The original task list and generated brief are both retained.
- A human can reject the proposed next task without changing source files.

**Why better than separate tools:** Meridian explains what unlocks work,
Rosetta explains an interface gap, and Nexussy provides a reviewable handoff
artifact. It improves agent focus without adding another planner or router.

**Rejected adjacent components:** A general autonomous project planner was not
added. The useful boundary is a human-reviewed next-task brief, not a new
end-to-end orchestration system.

## 4. Agent Exception Key

**Exact repositories:** `mojomast/hermes-agent`, `ussyverse/clavisussy`,
`ussyverse/operonussy`

**User and recurring pain:** Agents produce recurring exceptions such as missing
context, unsafe write requests, ambiguous user intent, or repeated tool failure.
Operators handle them inconsistently because the agent's free-form explanation
does not provide a stable classification or response path.

**Product promise:** "Classify common agent exceptions with a deterministic,
editable key and show the right response instructions for this audience."

**Input -> processing -> output:** Structured exception facts and task context ->
Clavis traverses a binary key and validates coverage/determinism; Operon selects
operator, developer, or end-user instructions by context; Hermes evaluation
cases measure whether routing avoids unsafe delegation -> a terminal exception
card with classification path, evidence fields, response SLA, assignee, and a
new evaluation case when the operator corrects the classification.

**Existing source to reuse:**

- **Exists:** [`clavisussy/clavis/engine.py`](https://github.com/ussyverse/clavisussy/blob/HEAD/clavis/engine.py) models JSON dichotomous keys, interactive traversal, terminal classifications, response SLAs, and assignees.
- **Exists:** [`clavisussy/clavis/validation.py`](https://github.com/ussyverse/clavisussy/blob/HEAD/clavis/validation.py) validates terminal coverage and deterministic paths.
- **Exists:** [`clavisussy/clavis/adaptive.py`](https://github.com/ussyverse/clavisussy/blob/HEAD/clavis/adaptive.py) compares original/correct paths and proposes a new question or refined wording after a misclassification.
- **Exists:** [`operonussy/src/operon/transcription.py`](https://github.com/ussyverse/operonussy/blob/HEAD/src/operon/transcription.py) selects conditional documentation using audience and context factors.
- **Exists:** [`hermes-agent/agent/task_router_eval.py`](https://github.com/mojomast/hermes-agent/blob/HEAD/agent/task_router_eval.py) supports golden routing cases, forbidden routes, required reasons, and unsafe-delegation counts.

**Missing integration work:** Define an exception fact vocabulary; author and
version keys; map terminal IDs to Hermes expected routes; capture operator
corrections; and never infer a security or safety terminal from unstructured
agent prose alone.

**Maturity and feasibility caveats:** Clavis validates structural key properties,
not whether its questions describe reality. Operon uses motif matching and
fixed strengths. Hermes evaluation measures supplied expectations. **Proposed**
exception extraction, key authoring workflow, and operational response are
**Unverified**.

**Smallest useful demo:** Author a six-terminal key for failed tool calls,
validate it, classify ten saved exceptions, correct one path, and emit an
updated question proposal plus a Hermes regression case.

**Acceptance criteria:**

- Every classification retains the complete question/answer path.
- Unanswered or contradictory facts produce review/unknown rather than a terminal claim.
- Key revisions preserve prior classifications and identify the revision used.
- A correction creates a reviewable adaptive event, not an automatic key edit.
- Audience-specific instructions are separate projections of the same terminal record.

**Why better than separate tools:** Clavis gives deterministic classification,
Operon gives the correct explanation surface, and Hermes checks routing behavior
against explicit cases. The artifact is an operator response card, not a free-form
agent verdict.

**Rejected adjacent components:** A generic anomaly score was not added. An
exception key needs explicit questions and paths; averaging anomaly signals
would hide the missing facts that should cause escalation.

## 5. Evidence Retention Planner

**Exact repositories:** `mojomast/clanker03`, `mojomast/becomussy`,
`ussyverse/curatorussy`, `ussyverse/chainletussy`

**User and recurring pain:** Teams want enough agent history to investigate
mistakes and improve evaluation, but retaining every prompt, tool output, and
reasoning blob indefinitely increases privacy, storage, and review burden.

**Product promise:** "Choose what an agent run must retain, what can be
compressed, and what should expire, with a reason visible to the reviewer."

**Input -> processing -> output:** Session metadata, event/blob types, risk
class, unresolved review items, and replay needs -> Clanker reports session
contents and retention policy candidates; Becomussy records the human policy
decision and freeze state; Curator reports provenance/condition; Chainlet checks
whether the retained subset still supports a prescribed replay procedure -> a
retention receipt naming kept metadata, expired content, replay limitations,
review date, and approver.

**Existing source to reuse:**

- **Exists:** [`clanker03/agentreplay/schema.sql`](https://github.com/mojomast/clanker03/blob/HEAD/agentreplay/schema.sql) includes blob types, checksums, session summaries, retention policies, archive metadata, and configurable blob deletion fields.
- **Exists:** [`clanker03/agentreplay/store.ts`](https://github.com/mojomast/clanker03/blob/HEAD/agentreplay/store.ts) reports storage statistics and identifies completed/cancelled sessions eligible for archival.
- **Exists:** [`becomussy/backend/app/services/governance/__init__.py`](https://github.com/mojomast/becomussy/blob/HEAD/backend/app/services/governance/__init__.py) supports evidence requests, immutable decisions, and freeze controls.
- **Exists:** [`curatorussy/curator/conservation.py`](https://github.com/ussyverse/curatorussy/blob/HEAD/curator/conservation.py) calculates document age, code age delta, dependency drift, link rot, and review treatment.
- **Exists:** [`chainletussy/src/chainletussy/analyzer.py`](https://github.com/ussyverse/chainletussy/blob/HEAD/src/chainletussy/analyzer.py) reports which procedure links lack attempts and where retained practice evidence shows chain breaks.

**Missing integration work:** Define retention classes for prompts, tool
inputs/outputs, snapshots, and decisions; implement a deletion/archive executor;
prove what a compressed run can no longer replay; bind retention changes to a
policy revision; and provide an export that excludes sensitive raw content.

**Maturity and feasibility caveats:** AgentReplay's schema has retention fields,
but this does not prove a complete retention worker. Becomussy freeze state is
MVP in-memory. Curator provenance is synthetic in the inspected implementation.
Chainlet practice evidence is not a privacy classifier. **Proposed** deletion,
compression, and restore behavior is **Unverified**.

**Smallest useful demo:** Create one session with a prompt, tool output,
decision, and snapshot; retain the decision and metadata, archive the tool
output, delete the prompt, and issue a receipt saying which replay steps are no
longer possible.

**Acceptance criteria:**

- The receipt lists every retained, archived, redacted, and deleted content class.
- Deletion is explicit, reversible only when an archive exists, and never implied by a score.
- A replay attempt reports missing inputs instead of fabricating them.
- Policy changes require a named reviewer and revision identifier.
- Raw sensitive content is not included in the shareable receipt.

**Why better than separate tools:** Clanker knows what evidence exists,
Chainlet tests the practical replay consequence, Curator supplies review timing,
and Becomussy records the policy decision. This makes retention a reviewable
tradeoff rather than a fixed “keep everything” or “delete everything” rule.

**Rejected adjacent components:** Hosted memory services were not added. They
would expand the data boundary before the local retention contract is proven.

## 6. Tool-Contract Drift Drill

**Exact repositories:** `mojomast/nexussy`, `ussyverse/rosettussy`,
`ussyverse/clavisussy`

**User and recurring pain:** An agent tool changes its arguments, return shape,
path behavior, or failure wording. The agent may continue calling it because the
tool name still exists, while the operator discovers the mismatch only after a
bad task or a confusing refusal.

**Product promise:** "Let a maintainer rehearse tool contract changes against
realistic calls before exposing the new contract to an agent."

**Input -> processing -> output:** Old/new callable or tool adapter, contract
examples, allowed paths, and expected failures -> Rosetta compares signatures,
docstrings, and safe runtime witnesses; Nexussy applies path/anchor validation
to the test artifact; Clavis traverses a deterministic key for breaking versus
non-breaking changes -> a drill report with contract diff, example paths,
expected terminal outcome, untested branches, and reviewer disposition.

**Existing source to reuse:**

- **Exists:** [`nexussy/core/nexussy/security.py`](https://github.com/mojomast/nexussy/blob/HEAD/core/nexussy/security.py) sanitizes relative paths, rejects traversal, and scrubs common secret formats.
- **Exists:** [`nexussy/core/nexussy/artifacts/store.py`](https://github.com/mojomast/nexussy/blob/HEAD/core/nexussy/artifacts/store.py) validates known artifact anchors and safely writes a hashed result.
- **Exists:** [`rosettussy/src/rosetta/inscription.py`](https://github.com/ussyverse/rosettussy/blob/HEAD/src/rosetta/inscription.py) extracts arguments/returns and records documentation/runtime divergences.
- **Exists:** [`clavisussy/clavis/engine.py`](https://github.com/ussyverse/clavisussy/blob/HEAD/clavis/engine.py) provides path-preserving binary classification with terminal response metadata.

**Missing integration work:** Define tool-contract fields beyond Python
signatures; build safe fixture calls; map changes to a versioned key; model
permission failures separately from implementation failures; and never run a
candidate tool against a production workspace.

**Maturity and feasibility caveats:** Rosetta's runtime probe is limited and can
execute side effects if not constrained. Nexussy path checks do not sandbox a
process. Clavis determinism does not validate the contract's semantics.
**Proposed** fixture execution and contract taxonomy are **Unverified**.

**Smallest useful demo:** Change one tool parameter and one denied-path error,
run three safe fixtures, and emit a report showing one breaking branch, one
unchanged branch, and one branch with no fixture.

**Acceptance criteria:**

- No fixture can access a path outside a temporary workspace.
- Signature, return, permission, and error changes are reported separately.
- Missing fixtures remain visible as unverified branches.
- The key path and contract revision are saved with the report.
- The drill never promotes a contract change automatically.

**Why better than separate tools:** Rosetta finds the interface mismatch,
Nexussy makes the fixture artifact safer to handle, and Clavis gives the
maintainer a repeatable breaking-change vocabulary.

**Rejected adjacent components:** A general API-drift predictor was not added.
The useful first step is a constrained contract drill, not an unsupported
prediction about production compatibility.

## 7. Delegation Bottleneck Review

**Exact repositories:** `mojomast/hermes-agent`, `ussyverse/meridianussy`,
`ussyverse/chainletussy`

**User and recurring pain:** A multi-agent workflow repeatedly stalls at the
same handoff. The operator sees more delegation, retries, or subagents, but not
which prerequisite unlocks the blocked work or whether the procedure itself is
unclear.

**Product promise:** "Replace repeated delegation with a measured intervention
brief: the blocked task, the dependency that unlocks it, and the next experiment."

**Input -> processing -> output:** Hermes routing decisions and timestamps,
task/dependency graph, task outcomes, and procedure attempts -> aggregate route
and unsafe/over-delegation counts; Meridian ranks bottlenecks and critical route;
Chainlet analyzes prompt dependence, chain breaks, and repeated errors -> an
operator brief with raw route cases, bottleneck task, affected handoff,
candidate intervention, and a follow-up measurement.

**Existing source to reuse:**

- **Exists:** [`hermes-agent/agent/task_router_eval.py`](https://github.com/mojomast/hermes-agent/blob/HEAD/agent/task_router_eval.py) computes route confusion, over/under-delegation, unsafe delegation, and tag-level accuracy.
- **Exists:** [`hermes-agent/scripts/evaluate_task_router.py`](https://github.com/mojomast/hermes-agent/blob/HEAD/scripts/evaluate_task_router.py) exposes strict thresholds for routing accuracy and parallel precision/recall.
- **Exists:** [`meridianussy/pkg/meridian/analysis.go`](https://github.com/ussyverse/meridianussy/blob/HEAD/pkg/meridian/analysis.go) ranks dependency bottlenecks and computes the highest-effort critical route.
- **Exists:** [`chainletussy/src/chainletussy/analyzer.py`](https://github.com/ussyverse/chainletussy/blob/HEAD/src/chainletussy/analyzer.py) reports link stats, chain breaks, prompt recommendations, and errorless guardrails.

**Missing integration work:** Define a shared task/run/time schema; distinguish
waiting from failed work; map Hermes route cases to Meridian task IDs; identify
the procedure attempt that corresponds to a handoff; and store an intervention
with an owner and check date.

**Maturity and feasibility caveats:** Hermes evaluation cases are hand-authored
expectations. Meridian's effort values are heuristic. Chainlet's procedure
outcomes require consistent attempt capture. **Proposed** live-event ingestion
and the bottleneck-to-intervention join are **Unverified**.

**Smallest useful demo:** Use six saved tasks with one prerequisite blocking two
others, three route decisions, and two procedure attempts. Show that adding a
retry does not change the bottleneck and nominate one missing prerequisite to
measure.

**Acceptance criteria:**

- Every bottleneck includes its dependent tasks and calculation inputs.
- Route counts retain the raw cases and do not become a single health score.
- A procedure break links to the attempts that produced it.
- The brief names a human owner and follow-up measurement.
- The product does not spawn agents or change routing as a side effect.

**Why better than separate tools:** Hermes shows the delegation symptom,
Meridian shows what unlocks work, and Chainlet shows whether the human/tool
procedure transfers between steps. The result is a specific intervention, not a
larger orchestration layer.

**Rejected adjacent components:** `mojomast/swarmussy` and another router were
not added. More workers would increase the observed symptom without identifying
the missing prerequisite.

## 8. Agent Repository Transfer Pack

**Exact repositories:** `mojomast/clanker03`, `ussyverse/codelineageussy`,
`ussyverse/curatorussy`, `ussyverse/rosettussy`

**User and recurring pain:** A team transfers an active repository from one
agent configuration or maintainer to another. The new worker receives files and
a summary, but not which decisions were made, which functions changed often,
which docs are stale, or which claims still lack evidence.

**Product promise:** "Hand an agent or maintainer a bounded repository brief
that preserves decisions and uncertainty without exporting the whole session."

**Input -> processing -> output:** Selected AgentReplay session, repository
revision, changed files, documentation set, and transfer goal -> summarize
decision points, trace changed functions and history, inspect callable/document
alignment, and calculate documentation condition -> a filtered transfer pack
containing current task, decisions, relevant files, open questions, history
coverage, documentation gaps, and exact commands to resume.

**Existing source to reuse:**

- **Exists:** [`clanker03/agentreplay/store.ts`](https://github.com/mojomast/clanker03/blob/HEAD/agentreplay/store.ts) retrieves session events, decisions, state at a sequence, and storage statistics.
- **Exists:** [`clanker03/agentreplay/schema.sql`](https://github.com/mojomast/clanker03/blob/HEAD/agentreplay/schema.sql) provides session IDs, ordered event identity, state snapshots, decision points, and retention metadata.
- **Exists:** [`codelineageussy/src/codelineage/core.py`](https://github.com/ussyverse/codelineageussy/blob/HEAD/src/codelineage/core.py) returns tracked functions, history detections, and tree members for a repository.
- **Exists:** [`curatorussy/curator/conservation.py`](https://github.com/ussyverse/curatorussy/blob/HEAD/curator/conservation.py) reports documentation age, code age, dependency drift, and link rot.
- **Exists:** [`rosettussy/src/rosetta/scoring.py`](https://github.com/ussyverse/rosettussy/blob/HEAD/src/rosetta/scoring.py) reports matched parameters, documentation score inputs, and divergences.

**Missing integration work:** Define transfer goals and field-level visibility;
select the minimum event subset; map session decisions to repository revisions;
generate safe resume commands; preserve raw pack provenance; and support a
recipient acknowledging or correcting each transferred claim.

**Maturity and feasibility caveats:** AgentReplay may contain sensitive full
blobs. Codelineage is Python-focused and can be noisy or incomplete with shallow
history. Curator's inspected provenance helper synthesizes commit-like records
from file metadata. Rosetta's score is a heuristic. **Proposed** selection,
redaction, and recipient acknowledgment are **Unverified**.

**Smallest useful demo:** Transfer one interrupted Python task involving three
files. Export two decisions, one changed-function history entry, one stale-link
finding, and one resume command while excluding the full prompt and tool blobs.

**Acceptance criteria:**

- The pack identifies the session, repository revision, and transfer goal.
- Every included claim links to an event, file, symbol, or document metric.
- Excluded blobs remain excluded from the transfer projection by default.
- History/documentation coverage gaps are shown rather than filled with guesses.
- A recipient can acknowledge, correct, or reject each claim without editing the source repository.

**Why better than separate tools:** AgentReplay preserves the work context,
Codelineage explains repository change, Curator identifies maintenance gaps, and
Rosetta tests the code/document boundary. The transfer pack is a practical
handoff artifact rather than a generic agent memory store.

**Rejected adjacent components:** A hosted vector memory or autonomous summary
agent was not added. It would increase data exposure and unsupported claims
before the field-level transfer contract is validated.

## Rejected Directions

### A. Autonomous Everything-Agent

**Temptation:** Combine `mojomast/hermes-agent`, `mojomast/nexussy`,
`mojomast/clanker03`, `ussyverse/parliamentussy`, and several routers into a
system that plans, edits, approves, deploys, and self-revises without a human
boundary.

**Why rejected:** This is an orchestration stack, not a product outcome. It
would combine execution, governance, memory, and deployment before the smaller
evidence artifacts have been validated. It also risks treating approval records
as permission to automate high-consequence actions. The accepted ideas isolate
one decision or handoff and retain a human review point.

**Status:** The proposal is rejected at screening. No claim is made here that
the named repositories form an operational integration.

### B. Universal Agent Reliability Score

**Temptation:** Average Hermes routing metrics, Chainlet chain-break scores,
Rosetta documentation scores, Codelineage detections, and Curator condition
grades into one agent reliability percentage.

**Why rejected:** These outputs measure different entities, use different
baselines, and carry different uncertainty. A good routing case does not prove a
good procedure, a documentation score does not prove behavior, and repository
history does not prove safety. Averaging them would hide the raw reason for
review. The accepted ideas keep route, procedure, contract, history, and
retention evidence separate.

**Status:** The individual source capabilities are useful, but the combined
score is unsupported and should not be implemented as a merge or deployment
gate.

## Next Validation Steps

1. Choose the Trajectory-to-Regression Clinic or Self-Revision Adoption Dossier as the first saved-input prototype.
2. Pin every selected repository revision and run each repository's documented tests in isolated environments.
3. Define stable IDs, timestamps, visibility classes, raw-output retention, and missing/unknown states before adding a live agent.
4. Exercise incomplete, contradictory, secret-bearing, and failed-run inputs; confirm that the output requests review rather than inventing evidence.
5. Test the resulting artifact with an actual agent maintainer or operator and record whether it changes a recurring decision.
