# Context: OpenRun Seed Branch And Sovereign Branches

## Session Goal

Turn OpenRun into a minimal collaborative Markdown workspace where the repository is the product, coding agents are the runtime, and collaborators can start from a shared entrypoint without being forced into a shared trunk workflow.

## What Changed

- Seeded the repository with the base OpenRun structure:
  - `AGENTS.md`
  - `README.md`
  - `index.md`
  - `log.md`
  - `raw/`
  - `wiki/`
  - `decisions/`
- Kept the Karpathy LLM Wiki text as the reference body of `AGENTS.md`.
- Added an OpenRun collaboration layer to `AGENTS.md` describing how agents should operate in this repo.
- Revised the collaboration model after deeper reasoning:
  - the default branch is not shared truth
  - durable knowledge work should not merge into the default branch
  - each collaborator keeps a sovereign branch
  - collaboration happens by inspecting another branch and selectively importing desired work into your own branch
- Renamed the default branch from `main` to `seed`.
- Updated the GitHub default branch to `seed`.
- Deleted remote `main`.
- Created the first personal branch, `danie/main`, from `seed`.

## Why The Model Changed

The first version of the repo treated `main` as a shared base branch. That model was rejected because it smuggled in trunk semantics that do not fit the actual product.

From first principles:

- A new participant needs a stable entrypoint.
- A collaborator needs a durable place to keep ongoing work.
- Adoption of another person's work should be explicit.
- Knowledge work does not require a single canonical shared content branch.

Using a shared `main` branch creates false consensus, unnecessary merge pressure, and avoidable social gravity toward one official version of the wiki. OpenRun is better understood as a common substrate for many sovereign workspaces than as one communal wiki with a trunk.

The cleaner model is:

- `seed` is a bootstrap template branch.
- Personal branches are the real durable workspaces.
- Collaboration is pull-based, not trunk-based.
- The template branch changes only when the workspace contract or starter structure changes.

## Durable Project-Level Decisions

- The repository is the durable system of record.
- The coding agent harness is external to the repository.
- The default branch is a fresh workspace template.
- Durable knowledge work lives on sovereign personal or session branches.
- Ordinary knowledge work should not merge back into the default branch.
- If a collaborator wants material from another branch, they inspect it and selectively adopt it into their own branch.

These decisions are encoded directly in `AGENTS.md` and `README.md`.

## Commits Created During The Session

- `0b8b312` `Seed OpenRun collaborative markdown workspace`
- `bd4a77b` `Define branch-sovereign OpenRun workflow`

## Resulting Repo State

- GitHub default branch: `seed`
- Template branch: `seed`
- Personal branch in use: `danie/main`
- No project-local `CLAUDE.md` or `.codex/rules/` exists
- No user-level rules were changed in this session

## Follow-On Work

- Start ingesting real source material on `danie/main`.
- Let other collaborators branch from `seed`.
- Refine `AGENTS.md` only after observing real ingest/query/lint cycles.
