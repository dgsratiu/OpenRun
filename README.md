# OpenRun

OpenRun is a branch-first Markdown workspace for collaborative knowledge building with coding agents.

The repository is the product. Your coding agent is the runtime. There is no required server, scheduler, or harness inside this repo.

## How To Work

1. Start from `main`.
2. Create your own branch.
3. Add or revise Markdown files.
4. Compare your branch with other branches using git.
5. Merge to `main` only when the change should become shared base state.

## Branch Rules

- `main` is the shared base branch.
- Do not push directly to `main`.
- Use clear branch names such as `name/main`, `name/topic`, or `name/date-topic`.
- Keep exploratory or disputed work on branches until someone explicitly wants it merged.

## Workspace

- [AGENTS.md](./AGENTS.md) is the operating contract for coding agents.
- [index.md](./index.md) is the catalog of durable pages.
- [log.md](./log.md) is the append-only event log.
- [raw/README.md](./raw/README.md) describes source material.
- [wiki/README.md](./wiki/README.md) describes synthesized shared knowledge.
- [decisions/README.md](./decisions/README.md) describes durable project decisions.

## Runtime Model

Anyone can use any coding agent locally against this repo. Local automation such as cron jobs, search tooling, or editor plugins is optional and stays outside the repo unless collaborators explicitly decide otherwise.
