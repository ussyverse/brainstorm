# Instructions for brainstorming agents

## Mission

Help find credible, useful products that recombine focused Ussyverse projects.
Optimize for a real user outcome, not the number of repositories involved.

This repository is a durable research handoff. Preserve provenance, challenge
earlier assumptions, and make it easy for the next human or agent to understand
what is known, inferred, proposed, and still untested.

## Read first

1. Read `README.md` for the purpose and current recommendation.
2. Read `docs/COMPOUNDED_IDEAS.md` before proposing an idea already covered by
   the 20-agent synthesis.
3. Read `docs/SOURCE_CHECKED_COMBINATIONS.md` for the earlier deep analysis and
   staged audiovisual MVP.
4. Search `docs/REPOSITORY_INDEX.md` for candidate capabilities and related
   projects.
5. Use `docs/INITIAL_COMBINATIONS.md` only as historical brainstorming. It is
   not source validation and contains ideas later narrowed or rejected.

## Evidence rules

- Treat catalog and README claims as hypotheses until source or runtime
  behavior confirms them.
- Inspect the candidate repositories' manifests, entry points, core models,
  key algorithms, exports, tests, and current default branches.
- Link to exact source files or symbols supporting important capability claims.
- Distinguish these labels clearly:
  - **Exists:** implemented in inspected source.
  - **Proposed:** integration or product behavior that must be built.
  - **Unverified:** described but not source-inspected or runtime-tested.
- Do not present fixtures, sample data, mock dashboards, `.built` markers, or
  specifications as operational integrations.
- Record the date, repositories inspected, revision identifiers when possible,
  and commands actually run.
- Do not claim tests pass unless you ran them and recorded the result.

## Selection criteria

Prefer combinations that:

- Use two to four complementary projects, with at least two from `ussyverse`
  when practical.
- Address a specific recurring task for an identifiable user.
- Share a natural entity such as a sequence, incident, run, claim, attempt,
  task, or transaction.
- Produce a useful artifact, decision, or completed workflow.
- Can demonstrate value locally before requiring authentication, hosting,
  synchronization, or a large agent platform.
- Preserve raw evidence and uncertainty instead of collapsing everything into
  an unexplained score.

Avoid combinations that:

- Stack several orchestration layers, dashboards, routers, or metaphorical
  scores without a new end-user deliverable.
- Combine projects only because their themes sound similar.
- Assume differently named IDs, timestamps, units, or confidence scales are
  interoperable.
- Turn experimental health, safety, financial, or predictive heuristics into
  authoritative advice.
- Require implementing the largest component from scratch before testing the
  proposed user value.

## Proposal format

For each serious candidate, document:

1. **Working title**
2. **Exact repositories**
3. **User and recurring pain**
4. **Product promise**
5. **Input -> processing -> output flow**
6. **Existing source to reuse**, with links
7. **Missing integration work**
8. **Maturity and feasibility caveats**
9. **Smallest useful demo**
10. **Acceptance criteria**
11. **Why the combination is better than separate tools**
12. **Rejected adjacent components and why**

If ranking ideas, explain the criteria. Favor usefulness, complementarity,
concrete reuse, demonstrability, and limited missing work.

## Workflow for the next pass

1. Pull the latest version of this repository.
2. Review open issues and recent document changes to avoid duplicating work.
3. Choose an underexplored catalog area or challenge an existing shortlist
   item with fresh evidence.
4. Inspect source in each candidate repository. Clone only what is necessary.
5. Build or test the component contracts where feasible.
6. Write findings in a new dated file under `docs/research/` when the work is a
   substantial new pass. Update the main source-checked report only when the
   new evidence changes its conclusions.
7. Update `README.md` if the top recommendation or project status changes.
8. Summarize evidence, uncertainty, and next actions in the pull request.

## Repository boundaries

- Do not vendor or modify candidate projects in this repository.
- Never commit secrets, GitHub tokens, private source, or sensitive research
  data.
- Use exact owner/repository names because similarly named forks and generations
  may have materially different code.
- Keep proposals distinct from implementation. A selected product should move
  into its own repository once active development begins.

## Current high-value questions

- Does the Kuleshov/Foleya component contract survive real user-authored input
  and round-trip persistence?
- Which shortlist can deliver a useful vertical slice with the least adapter
  work after its existing test suites are run?
- Are there strong combinations hidden in underexplored creative, civic, or
  business clusters that share real data rather than only a metaphor?
- Which catalog claims need correction after source or runtime verification?
- Can a small group of actual target users validate recurring pain before a
  larger integration is built?
