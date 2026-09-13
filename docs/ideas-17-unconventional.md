# Ideas 17: Unconventional Recombination Candidates

**Date:** 2026-09-13
**Scope:** New proposals relative to the existing brainstorm files and the ten-item shortlist in [`SOURCE_CHECKED_COMBINATIONS.md`](SOURCE_CHECKED_COMBINATIONS.md).

## Evidence Boundary

`Exists` means the named source was inspected at the revision below. `Proposed` means an adapter or product workflow still has to be built. `Unverified` means the cross-repository contract and runtime behavior have not been tested. I screened the existing `docs/ideas-*.md` files and avoided their documented combinations and product concepts where practical.

### Inspected Revisions

| Repository | Revision | Key source inspected |
|---|---|---|
| `ussyverse/auscultussy` | `875b0c2` | `src/ausculta/models.py`, `src/ausculta/engine.py`, `pyproject.toml` |
| `ussyverse/ethonussy` | `4b2a5da` | `src/ethon.nim`, `src/main.nim`, `action.yml` |
| `ussyverse/fascinaussy` | `ffd7973` | `src/fascina.nim`, `src/main.nim`, `fascina.nimble` |
| `ussyverse/satiaussy` | `6a9ae4b` | `src/lib.rs`, `Cargo.toml` |
| `ussyverse/myceliumussy` | `efffc8e` | `src/mycelium/network.py`, `pyproject.toml` |
| `ussyverse/neophagaussy` | `57f137d` | `src/index.ts`, `package.json` |
| `ussyverse/nicheussy` | `88609bc` | `src/lib.zig`, `src/main.zig`, `build.zig` |
| `ussyverse/oarsaussy` | `0bc01a6` | `src/lib.zig`, `src/main.zig`, `build.zig` |
| `ussyverse/saponinussy` | `5d2d360` | `src/saponin/models.py`, `src/saponin/engine.py` |

Commands run for provenance:

```text
git -C <repository> rev-parse --short HEAD
git status --short
git diff --check
```

No candidate repository was built, installed, or runtime-tested. Existing tests and action manifests establish intended contracts only. Before implementation, run each selected native test command and feed it user-authored fixtures.

## Ranked Ideas

The ranking favors a recurring task, a natural shared entity, a concrete output, and useful behavior before hosting or synchronization. It is a product judgment, not a market ranking.

## 1. Meeting Aftercare Loop

**Repositories:** `ussyverse/auscultussy` + `ussyverse/oarsaussy` + `ussyverse/fascinaussy`

**User and recurring pain.** A team lead sees the same meeting fail in slightly different ways: unclear decisions, re-litigation, concentrated burden, and exhausted participants. A retrospective can become another coercive conversation, while recovery breaks are logged separately from meeting quality.

**Product promise.** “Diagnose the meeting pattern, prepare a non-controlling repair conversation, and check whether the group recovered.”

**Flow:** facilitator-entered meeting beats and follow-up outcomes -> Ausculta diagnosis and intervention cards -> Oarsa consent-gated conversation card -> Fascina microbreak/recovery log -> dated comparison report.

**Existing source to reuse:**

- **Exists:** `auscultussy/src/ausculta/models.py` defines `MeetingObservation`, `Beat`, `Murmur`, and `OutcomeFollowup`; `engine.py` implements `diagnose_meeting`, `trend_analysis`, and intervention cards. [Source](https://github.com/ussyverse/auscultussy/blob/875b0c2/src/ausculta/engine.py)
- **Exists:** `oarsaussy/src/lib.zig` defines consent, safety, righting-reflex, change/sustain markers, and reflection analysis in `Conversation` and `analyze`. [Source](https://github.com/ussyverse/oarsaussy/blob/0bc01a6/src/lib.zig)
- **Exists:** `fascinaussy/src/fascina.nim` defines `LogEntry`, restoration balance, anchor scoring, and recovery-rhythm recommendations. [Source](https://github.com/ussyverse/fascinaussy/blob/ffd7973/src/fascina.nim)

**Missing integration:** Join `meetingId`, `beatId`, `conversationId`, and `breakLogId`; preserve raw facilitator notes; require explicit permission before producing the Oarsa card; compare later observations without claiming that a break caused improvement.

**Maturity and feasibility:** **Exists:** three local deterministic analyzers. **Proposed:** meeting-series store, consent flow, and joined report. **Unverified:** language/runtime packaging and whether self-entered observations are reliable enough for team decisions. The cardiac terms are metaphors, not medical assessments.

**Smallest useful demo:** Four meetings with one repeated closure murmur, one opt-in repair conversation, and six before/after microbreak entries.

**Acceptance criteria:** No conversation card is generated without permission; a missed action remains distinct from a low recovery score; the report shows raw observations beside trend labels; participants can mark a suggested intervention unsuitable.

**Why better than separate tools:** Ausculta finds the recurring meeting pattern, Oarsa protects the conversation boundary, and Fascina captures a concrete recovery experiment. The shared entity is a meeting cycle, not an all-purpose team-health score.

**Rejected adjacent component:** `ussyverse/axisussy` is excluded because adding physiological recovery scores would make a facilitation tool look medically authoritative.

## 2. Decision-to-Execution Handoff Trace

**Repositories:** `ussyverse/auscultussy` + `ussyverse/ethonussy`

**User and recurring pain.** Engineering teams make decisions in meetings and then discover in CI that the intended setup, command order, or configuration never reached the workflow. They need to know whether the failure is a missing handoff, a repeated workflow habit, or simply insufficient evidence.

**Product promise.** “Show which meeting decision was supposed to change execution, and where the workflow diverged.”

**Flow:** a decision beat with owner, expected artifact, and review date -> CI log plus structured workflow events -> Ausculta closure/perfusion findings + Ethon repeated command sequences, displacement activities, sign stimuli, and imprint profile -> handoff trace with evidence gaps.

**Existing source to reuse:**

- **Exists:** `auscultussy/src/ausculta/models.py` has `Beat.perfusion_targets`, `perfusion_received`, `decision_made`, `assignment_made`, and `explicit_deferral`; `engine.py` computes `perfusion_score` and closure diagnoses. [Source](https://github.com/ussyverse/auscultussy/blob/875b0c2/src/ausculta/models.py)
- **Exists:** `ethonussy/src/ethon.nim` implements `detectFAPs`, `recognizeSignStimulus`, `detectDisplacement`, and `generateImprint`; `src/main.nim` exposes `fap`, `stimulus`, `displacement`, and `imprint`. [Source](https://github.com/ussyverse/ethonussy/blob/4b2a5da/src/ethon.nim)

**Missing integration:** Add an explicit handoff record, map meeting artifact names to normalized workflow fields, retain the original log and actual exit status, and distinguish “not observed” from “not done.” Do not infer that an Ethon pattern caused the CI result.

**Maturity and feasibility:** **Exists:** meeting output/perfusion fields and CI log/event analyzers. **Proposed:** trace schema and a local report generator. **Unverified:** event timestamp alignment, log parser coverage, and useful correlation with real meeting artifacts.

**Smallest useful demo:** One meeting assigns a setup-file change, followed by two CI logs: one where the setup repeats the old command sequence and one where it follows the new sequence.

**Acceptance criteria:** The report links each expected output to observed or missing evidence; Ethon findings retain their raw commands and counts; an absent meeting record does not become a false failed handoff; a user can override the suggested join.

**Why better than separate tools:** Ausculta explains whether the decision closed and reached its intended audience; Ethon explains what execution actually repeated. Together they expose the boundary between agreement and behavior.

**Rejected adjacent component:** `ussyverse/triageussy` is deferred. Error extraction would be useful in a later failure packet but is not necessary to prove the decision-to-execution handoff.

## 3. Role-Habitat Negotiation Kit

**Repositories:** `ussyverse/nicheussy` + `ussyverse/oarsaussy` + `ussyverse/ethonussy`

**User and recurring pain.** A knowledge worker knows their role is selecting for visible emergencies while preventive work disappears. They need evidence for a small environmental change and a conversation that asks for collaboration rather than prescribing a behavior change.

**Product promise.** “Turn recurring work friction into one reversible role experiment and a respectful manager conversation.”

**Flow:** task/stakeholder profile plus selected workflow logs -> Niche pressure, affordance-gap, and intervention analysis + Ethon setup/FAP patterns -> Oarsa permission opener and autonomy-preserving conversation card -> one-week experiment and review note.

**Existing source to reuse:**

- **Exists:** `nicheussy/src/lib.zig` defines `Task`, `Stakeholder`, `Intervention`, `RoleProfile`, `selectionPressure`, `nicheBreadth`, and `bestIntervention`. [Source](https://github.com/ussyverse/nicheussy/blob/88609bc/src/lib.zig)
- **Exists:** `ethonussy/src/ethon.nim` defines workflow events, sign-stimulus recognition, displacement detection, and successful setup `ImprintProfile`. [Source](https://github.com/ussyverse/ethonussy/blob/4b2a5da/src/ethon.nim)
- **Exists:** `oarsaussy/src/lib.zig` routes missing consent or high-stakes topics away and emits open questions, reflection type, and autonomy language. [Source](https://github.com/ussyverse/oarsaussy/blob/0bc01a6/src/lib.zig)

**Missing integration:** Map observed commands to role tasks without treating frequency as preference; bind one intervention to a feedback date; let the worker redact logs before showing them to a manager; keep the Oarsa safety gate authoritative for the conversation surface.

**Maturity and feasibility:** **Exists:** role-environment model, workflow pattern extraction, and conversation-prep core. **Proposed:** evidence picker and experiment ledger. **Unverified:** whether command traces represent meaningful role pressure and whether managers accept the generated brief. Niche scores are heuristics, not personnel ratings.

**Smallest useful demo:** A support engineer with urgent escalations, invisible documentation, two setup logs, and one proposed protected documentation block.

**Acceptance criteria:** The output names the raw task evidence behind pressure; the manager packet contains no unselected command payloads; the experiment has a reversible action and review date; a conversation with no permission produces a route-away card.

**Why better than separate tools:** Niche identifies the environmental lever, Ethon supplies behavioral traces, and Oarsa turns the result into a consented conversation rather than an employee diagnosis.

**Rejected adjacent component:** `ussyverse/fascinaussy` is omitted here to keep the manager packet about role design rather than personal fatigue surveillance.

## 4. Workflow Imprint Onboarding Guide

**Repositories:** `ussyverse/ethonussy` + `ussyverse/fascinaussy`

**User and recurring pain.** New contributors copy a successful setup sequence badly, repeat low-value shell checks, and lose attention before reaching a first useful change. Maintainers need a local guide derived from real successful runs and a non-prescriptive recovery rhythm.

**Product promise.** “Give a new contributor the shortest evidence-backed path to a first change, with recovery points that do not become productivity policing.”

**Flow:** successful and unsuccessful setup logs + optional local microbreak logs -> Ethon FAP/displacement/imprint analysis -> Fascina anchor and return-task analysis -> onboarding guide with known steps, suspicious loops, unknowns, and optional break suggestions.

**Existing source to reuse:**

- **Exists:** `ethonussy/src/ethon.nim` extracts commands, detects repeated n-grams, low-value command repetition, and generates a highest-frequency `ImprintProfile`. [Source](https://github.com/ussyverse/ethonussy/blob/4b2a5da/src/ethon.nim)
- **Exists:** `fascinaussy/src/fascina.nim` loads JSON/CSV logs, scores anchors, counts restoration, and recommends a recovery cadence. [Source](https://github.com/ussyverse/fascinaussy/blob/ffd7973/src/fascina.nim)
- **Exists:** `ethonussy/action.yml` provides a GitHub Action input/output boundary, though the product would initially use saved artifacts locally. [Source](https://github.com/ussyverse/ethonussy/blob/4b2a5da/action.yml)

**Missing integration:** Add run IDs, redact secrets from command lines, separate successful setup from merely frequent setup, and allow the newcomer to reject or edit every suggested step. Fascina output must remain optional and private.

**Maturity and feasibility:** **Exists:** command sequence and microbreak-log analyzers. **Proposed:** guide compiler and secret redaction. **Unverified:** Nim packaging in arbitrary CI images, command normalization, and the validity of inferring onboarding guidance from a small sample.

**Smallest useful demo:** Five saved setup runs, one repeated `git status` loop, one successful path, and three local break records. Generate a Markdown guide and an evidence appendix.

**Acceptance criteria:** Secrets and tokens are removed before export; a repeated command is labeled as a pattern rather than an error; the guide shows sample size; a newcomer can mark a step wrong and preserve that correction.

**Why better than separate tools:** Ethon explains what successful and stuck setup attempts actually did; Fascina helps the guide include humane recovery options without treating attention as a performance metric.

**Rejected adjacent component:** `ussyverse/levainussy` is not added because a build-health score would distract from the first-contributor path and invite unsupported judgments about productivity.

## 5. Food Bridge and Variety Ladder

**Repositories:** `ussyverse/satiaussy` + `ussyverse/myceliumussy` + `ussyverse/neophagaussy`

**User and recurring pain.** A caregiver wants to offer more food variety without turning a child's or adult's meal into a negotiation. They need an accepted-neighbor bridge, a sensory description, and a record of calm exposure. Generic meal planners optimize variety while ignoring pressure, distress, and safety boundaries.

**Product promise.** “Find one familiar bridge toward a new food, offer it without pressure, and preserve what actually happened.”

**Flow:** safe-food list, target-food properties, pantry ingredients, and optional meal context -> Mycelium substitution/neighbor graph + Satia sensory contrast map -> Neophaga safety screen and exposure rung -> pressure-free offer card and event history.

**Existing source to reuse:**

- **Exists:** `myceliumussy/src/mycelium/network.py` implements `substitution_chain`, `symbiotic_clusters`, `spore_dispersal`, and `resilience_score` over ingredient graphs. [Source](https://github.com/ussyverse/myceliumussy/blob/efffc8e/src/mycelium/network.py)
- **Exists:** `satiaussy/src/lib.rs` defines sensory profiles, `sensory_distance`, monotony/variety-loop measures, bounded contrast, and safety suppression in `analyze`. [Source](https://github.com/ussyverse/satiaussy/blob/6a9ae4b/src/lib.rs)
- **Exists:** `neophagaussy/src/index.ts` defines `EaterProfile`, `TargetFood`, `ExposureEvent`, `screenSafety`, `recommendNextRung`, `suggestNeighborBridges`, and pressure-free caregiver scripts. [Source](https://github.com/ussyverse/neophagaussy/blob/57f137d/src/index.ts)

**Missing integration:** Keep graph compatibility separate from sensory familiarity and separate both from safety. Pass only a selected candidate to Neophaga; record refusal, distress, predictability, and pressure flags exactly. Do not use Satia or Mycelium scores to override a route-away flag.

**Maturity and feasibility:** **Exists:** all three domain cores. **Proposed:** shared food IDs, caregiver UI, and event storage. **Unverified:** graph coverage, sensory descriptions, and any effect on eating behavior. This is not feeding therapy, allergy advice, nutrition advice, or a diet planner.

**Smallest useful demo:** One safe food, three accepted neighbors, one target, two calm look/smell events, and one refusal that is respected.

**Acceptance criteria:** A medical/allergy route-away suppresses household recommendations; a refusal remains a valid recorded outcome but not a success claim; the bridge changes only one declared property; the output contains no calories or weight goals.

**Why better than separate tools:** Mycelium finds a culinary path, Satia makes sensory contrast explicit, and Neophaga protects the interpersonal and safety boundary. The combination supports a small next offer instead of a forced menu.

**Rejected adjacent component:** `ussyverse/criticaussy` is not included because Neophaga already owns the explicit route-away boundary for this workflow; adding a second risk vocabulary would make conflicts harder to interpret.

## 6. Non-Coercive Kitchen Cleanup Repair

**Repositories:** `ussyverse/saponinussy` + `ussyverse/oarsaussy`

**User and recurring pain.** Roommates or family members repeatedly argue about a dirty pan, strong cleaners, or an uncompleted cleanup task. One person wants to explain the material/soil mechanism; the other wants autonomy and a conversation that does not become shaming or forced compliance.

**Product promise.** “Separate the cleaning problem from the people problem, then ask before offering help.”

**Flow:** item material, soil, water, prior attempt, and permission status -> Saponin mechanism report and one-variable trial -> Oarsa consent/safety gate and supportive conversation card -> mutually chosen trial and outcome note.

**Existing source to reuse:**

- **Exists:** `saponinussy/src/saponin/models.py` defines material, soil, water, attempt, safety, and `MechanismReport` models.
- **Exists:** `saponinussy/src/saponin/engine.py` implements chemical/material warnings, mechanism scores, safe next steps, one-variable trials, and escalation messages. [Source](https://github.com/ussyverse/saponinussy/blob/5d2d360/src/saponin/engine.py)
- **Exists:** `oarsaussy/src/lib.zig` analyzes permission, safety, advice/reflection balance, and autonomy language. [Source](https://github.com/ussyverse/oarsaussy/blob/0bc01a6/src/lib.zig)

**Missing integration:** Make “ask before advice” a hard product boundary; render Saponin's chemical warnings independently from the relationship card; allow either person to end the conversation; record the chosen trial without exposing private notes.

**Maturity and feasibility:** **Exists:** detailed cleaning mechanism/safety rules and a local conversation analyzer. **Proposed:** household task record and permission-first UI. **Unverified:** material taxonomy coverage and usability across different household relationships. Saponin does not establish sanitation, and Oarsa is not therapy.

**Smallest useful demo:** A greasy cast-iron pan, a prior vinegar attempt, one consented conversation, and a plain warm-detergent trial.

**Acceptance criteria:** A chemical mixing warning cannot be buried by the conversation output; no advice card appears when permission is absent; the selected trial changes one variable; the product never labels a person lazy, resistant, or unsafe.

**Why better than separate tools:** Saponin makes the object problem actionable, while Oarsa prevents technical correctness from becoming interpersonal pressure. Their handoff is a specific household repair conversation.

**Rejected adjacent component:** `ussyverse/raciaussy` is left out because assigning a responsible owner would reproduce a task-management frame; this product is about consent and mechanism, not workload scoring.

## 7. Potluck Variety-to-Cleanup Board

**Repositories:** `ussyverse/satiaussy` + `ussyverse/myceliumussy` + `ussyverse/saponinussy`

**User and recurring pain.** A community meal has too many similar dishes, missing bridge ingredients, and a cleanup pile full of incompatible materials and soils. The organizer needs a menu and cleanup plan that can be printed before the event, not a live optimization service.

**Product promise.** “Design a varied spread that leaves a manageable cleanup trail.”

**Flow:** volunteered dishes/ingredients and serving context -> Mycelium identifies ingredient overlaps and missing bridges; Satia maps sensory monotony and variety-loop risk -> Saponin generates material-aware cleanup stations and chemical hard stops -> event spread sheet, station cards, and unresolved-input list.

**Existing source to reuse:**

- **Exists:** `satiaussy/src/lib.rs` supports `EventSpread`, item sensory profiles, monotony, bounded contrast, and recommendations. [Source](https://github.com/ussyverse/satiaussy/blob/6a9ae4b/src/lib.rs)
- **Exists:** `myceliumussy/src/mycelium/network.py` supplies pantry/dish suggestions, ingredient clusters, and substitution/decomposition suggestions. [Source](https://github.com/ussyverse/myceliumussy/blob/efffc8e/src/mycelium/network.py)
- **Exists:** `saponinussy/src/saponin/engine.py` classifies soil mechanisms and emits material warnings, chemical warnings, protocols, and one-variable trials. [Source](https://github.com/ussyverse/saponinussy/blob/5d2d360/src/saponin/engine.py)

**Missing integration:** Keep food suggestions and cleaning instructions as separate projections of the event; map actual serving vessels to material records; do not infer allergen safety or sanitation from variety/cleaning scores; require organizers to verify each item.

**Maturity and feasibility:** **Exists:** event-spread sensory analysis, ingredient graph, and cleaning triage. **Proposed:** event schema and printable board. **Unverified:** dish naming, portion units, material inputs, and whether volunteers follow station cards. The output is coordination support, not catering compliance.

**Smallest useful demo:** Ten volunteered dishes, three serving materials, one high-variety warning, and two cleanup stations with a deliberate bleach/acid conflict.

**Acceptance criteria:** The conflict is a visible stop condition; a missing vessel material blocks a strong chemical recommendation; each dish retains its source volunteer and raw ingredient list; the organizer can remove a dish without recalculating historical notes.

**Why better than separate tools:** Satia improves the spread, Mycelium reduces awkward ingredient gaps, and Saponin handles the physical aftermath. The shared entity is the event's complete lifecycle from table to sink.

**Rejected adjacent component:** `ussyverse/criticaussy` is excluded from this MVP. A potluck allergen workflow needs explicit ingredient/allergen verification and should not be implied by the menu-variety analysis.

## 8. Restorative Role Experiment Journal

**Repositories:** `ussyverse/nicheussy` + `ussyverse/fascinaussy`

**User and recurring pain.** A solo founder or knowledge worker makes repeated role changes but cannot tell whether the new environment makes valuable work easier or merely adds another self-tracking obligation. They need a short reversible experiment with a human-readable before/after record.

**Product promise.** “Change the work habitat, then check whether the change helped without turning the journal into surveillance.”

**Flow:** role tasks, stakeholders, interruptions, visibility, and proposed intervention -> Niche pressure and reversible-intervention analysis -> private Fascina log of selected recovery anchors and return-task clarity -> weekly experiment journal with raw entries, changes, and next decision.

**Existing source to reuse:**

- **Exists:** `nicheussy/src/lib.zig` calculates selection pressure, niche breadth, interruption load, resilience, and ranked interventions with reversibility, safety, persistence, and feedback windows. [Source](https://github.com/ussyverse/nicheussy/blob/88609bc/src/lib.zig)
- **Exists:** `fascinaussy/src/fascina.nim` records fatigue/clarity before and after a break, anchor quality, screen-free status, control effort, outcome, and return task. [Source](https://github.com/ussyverse/fascinaussy/blob/ffd7973/src/fascina.nim)

**Missing integration:** Bind one role intervention to a date window, keep task-habitat data separate from private fatigue entries, and let the user write the interpretation. A changed score is not proof of causal improvement.

**Maturity and feasibility:** **Exists:** deterministic role and microbreak analysis. **Proposed:** experiment journal and field-level privacy controls. **Unverified:** self-report consistency and whether the two scoring systems can be normalized without false precision. No employer dashboard belongs in the MVP.

**Smallest useful demo:** One invisible maintenance task, one protected time block, five workday entries, and three microbreak records tied to return-task clarity.

**Acceptance criteria:** The report displays sample counts and raw values; private break notes are absent from a manager export; the user can reject the intervention; the next experiment is not generated automatically from a score alone.

**Why better than separate tools:** Niche describes the environmental change and Fascina records a bounded personal recovery observation. Together they support a small role experiment without claiming to diagnose burnout.

**Rejected adjacent component:** `ussyverse/axisussy` is not added because its endocrine/allostatic metaphors would overstate what an ordinary work journal can establish.

## Rejected Ideas

### A. The Household Behavior Oracle

**Temptation:** Combine `ussyverse/oarsaussy`, `ussyverse/neophagaussy`, `ussyverse/fascinaussy`, and a health or wellness scorer into a system that predicts why a family member refuses tasks or food.

**Why reject:** Consent, food-exposure, and fatigue logs are not a validated model of another person's motives or health. The serious proposals keep the user's observations explicit, route away on red flags, and never convert a refusal or low score into a diagnosis.

### B. The Universal Human Performance Dashboard

**Temptation:** Combine `ussyverse/auscultussy`, `ussyverse/nicheussy`, `ussyverse/ethonussy`, `ussyverse/fascinaussy`, and multiple work/health metaphors into one employee ranking.

**Why reject:** Meeting observations, command repetition, role-environment heuristics, and microbreak self-reports have different units, purposes, and privacy expectations. A combined score would invite surveillance and personnel decisions unsupported by the source evidence. Keep each output attached to a bounded, voluntary experiment.

## Next Validation

1. Run native tests for `auscultussy`, `oarsaussy`, and `fascinaussy`, then prototype the Meeting Aftercare Loop with hand-authored data.
2. Run `cargo test` in `satiaussy`, `npm test` in `neophagaussy`, and the Python tests for `saponinussy` before treating the Food Bridge or Potluck ideas as feasible.
3. Validate the privacy boundary with redaction fixtures before sharing any role or recovery report.
