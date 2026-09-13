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

The strongest next build is **Agent Fix Lab**, a local tool that turns a failed
coding-agent run and a human correction into a reproducible regression case.
Start with:

- [`ussyverse/triageussy`](https://github.com/ussyverse/triageussy) for extracting
  structured error evidence.
- [`ussyverse/petrichorussy`](https://github.com/ussyverse/petrichorussy) for
  configuration snapshots and diffs.
- [`mojomast/hermes-correction-aware-learning`](https://github.com/mojomast/hermes-correction-aware-learning)
  for correction records, retractions, and recurrence checks.

The first version should target Python projects and one agent workflow. A Hermes
import adapter is follow-on work. AgentReplay is deferred until its TypeScript
store is repaired and its architecture is tested.

See [the independent product assessment](docs/research/conclusion.md) for the
decision, runtime evidence, alternatives, acceptance criteria, and proposed
two-week validation cycle. The previous shot-to-sound recommendation remains
the strongest creative experiment.

## Strong candidates

| Rank | Product idea | Projects | Primary user |
|---|---|---|---|
| 1 | Agent Fix Lab | `triageussy` + `petrichorussy` + `mojomast/hermes-correction-aware-learning` | Coding-agent maintainers |
| 2 | Service-improvement desk | `andoniaussy` + `shewhartaussy` + `a3viaussy` | Small repair and IT service teams |
| 3 | Shot-to-sound capture planner | `kuleshovussy` + `foleyaussy`; `chromascriptussy` later | Independent creators and small film teams |
| 4 | Scope-and-capacity quote worksheet | `bidussy` + `taktussy`; `recapturaussy` only if needed | Small service businesses |

## Documents

- [`docs/research/conclusion.md`](docs/research/conclusion.md): latest independent
  product assessment, source and runtime findings, ranked recommendations, and
  next-cycle validation plan.
- [`docs/COMPOUNDED_IDEAS.md`](docs/COMPOUNDED_IDEAS.md): canonical synthesis
  of 20 independent brainstorming passes. It reduces 188 raw proposals to 146
  distinct candidates and ranks the strongest 30.
- [`docs/SOURCE_CHECKED_COMBINATIONS.md`](docs/SOURCE_CHECKED_COMBINATIONS.md):
  prior independent shortlist. All 459 catalog entries were screened and 27
  promising repositories received targeted static source inspection.
- [`docs/REPOSITORY_INDEX.md`](docs/REPOSITORY_INDEX.md): complete working index
  of 330 public `ussyverse` repositories and 129 public `mojomast`
  repositories, captured on 2026-09-13.
- [`docs/INITIAL_COMBINATIONS.md`](docs/INITIAL_COMBINATIONS.md): the first broad
  ecosystem clustering and twelve speculative combinations. Preserve it as
  brainstorming history; later source inspection rejected or narrowed several
  ideas.
- [`AGENTS.md`](AGENTS.md): instructions for agents continuing this research.
- [`docs/ideas-01-developer.md`](docs/ideas-01-developer.md) through
  [`docs/ideas-20-red-team.md`](docs/ideas-20-red-team.md): raw, lens-specific
  brainstorming passes retained for evidence and ideas outside the top 30.

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
then inspected source in 27 repositories. The latest assessment inspected 13
candidate repositories, ran four Python suites with 404 passing tests, and used
targeted runtime probes to test several important component boundaries. It did
not build an integrated product or conduct customer research.

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
