# Ussyverse Brainstorm

Research notebook for discovering practical, source-checked ways to combine
projects from the [Ussyverse organization](https://github.com/ussyverse) and
[mojomast](https://github.com/mojomast) into useful new products.

The Ussyverse contains hundreds of focused experiments. Many have a useful
typed model, deterministic transformation, or report hidden behind a prototype
interface. This repository asks a simple question:

> Which projects become substantially more useful when they share one real
> workflow, data model, and product surface?

This is a research and planning repository. It does not currently contain the
source code of the projects it discusses.

## Current recommendation

The strongest first build is a **shot-to-sound production planner** using:

- [`ussyverse/kuleshovussy`](https://github.com/ussyverse/kuleshovussy) for
  shot-sequence metadata and missing-shot checks.
- [`ussyverse/foleyaussy`](https://github.com/ussyverse/foleyaussy) for Foley
  planning, cue sheets, and recording checklists.
- [`ussyverse/chromascriptussy`](https://github.com/ussyverse/chromascriptussy)
  for color-script checks and visual exports.

The product would let a creator arrange a short sequence once and keep the
shot list, sound cues, and color plan synchronized as the edit changes. The
recommended first vertical slice combines Kuleshov and Foleya; Chromascript is
added after stable scene identities, editable timing, and persistence work.

See [the source-checked analysis](docs/SOURCE_CHECKED_COMBINATIONS.md) for the
proposed data model, implementation gaps, acceptance criteria, and staged MVP.

## Strong candidates

| Rank | Product idea | Projects | Primary user |
|---|---|---|---|
| 1 | Shot-to-sound production planner | `kuleshovussy` + `foleyaussy` + `chromascriptussy` | Independent creators and small film teams |
| 2 | Service problems to measured improvement | `andoniaussy` + `shewhartaussy` + `a3viaussy` | Small service and fulfillment teams |
| 3 | CI failure evidence packet | `triageussy` + `petrichorussy` | Software maintainers |
| 4 | Family archive with inspectable readings | `cartoucheussy` + `archivioussy` | Family historians and archivists |
| 5 | Confusion-focused learning lab | `cladwiseussy` + `criterioussy` | Learners and tutors |
| 6 | Household handoff rehearsal | `raciaussy` + `transactaussy` | Roommates and families |
| 7 | Volunteer gap desk | `commonsaussy` + `hoistussy` | Neighborhood and volunteer groups |
| 8 | Playable harmony-and-rhythm sketchbook | `tonalussy` + `phyllotaxisussy` + `mojomast/shoedelussy` | Music learners and live coders |
| 9 | Dependency-cycle refactoring priority | `hitchussy` + `churnmapussy` | Python maintainers |
| 10 | Return-through-refund tracker | `retouraussy` + `prospectaussy` | People managing online returns |

## Documents

- [`docs/SOURCE_CHECKED_COMBINATIONS.md`](docs/SOURCE_CHECKED_COMBINATIONS.md):
  current ranked recommendations. All 459 catalog entries were screened and 27
  promising repositories received targeted static source inspection.
- [`docs/REPOSITORY_INDEX.md`](docs/REPOSITORY_INDEX.md): complete working index
  of 330 public `ussyverse` repositories and 129 public `mojomast`
  repositories, captured on 2026-09-13.
- [`docs/INITIAL_COMBINATIONS.md`](docs/INITIAL_COMBINATIONS.md): the first broad
  ecosystem clustering and twelve speculative combinations. Preserve it as
  brainstorming history; later source inspection rejected or narrowed several
  ideas.
- [`AGENTS.md`](AGENTS.md): instructions for agents continuing this research.

## What makes a good combination?

A strong proposal should have:

1. A specific user with a recurring, recognizable problem.
2. A concrete input, transformation, and useful output.
3. Complementary projects rather than duplicate engines or stacked dashboards.
4. A clear shared data boundary between components.
5. An MVP that can prove value without building a platform first.
6. Source evidence for every reused capability.
7. Honest notes about missing adapters, demo data, unimplemented claims, and
   validation limits.

Combining projects is not the goal by itself. The combination must make a real
task easier than either project would independently.

## Research status

The catalog was produced from shallow clones and README/manifest inspection by
parallel agents. A second independent pass screened every catalog entry and
then inspected source in 27 repositories. No shortlisted component was built,
installed, or runtime-tested during that pass.

Repository descriptions are leads, not proof. Before implementing an idea,
pin revisions, run each component's tests, exercise it with user-authored data,
and verify that its actual interfaces support the proposed handoff.

## Contributing

Open an issue or pull request with a proposal that includes:

- Exact repository names and source links.
- Target user and recurring problem.
- Input to processing to output flow.
- Existing code that can be reused.
- Adapters and product work that do not yet exist.
- A small demo and acceptance criteria.
- Risks, maturity caveats, and rejected alternatives.

Agents should read and follow [`AGENTS.md`](AGENTS.md) before adding or changing
recommendations.
