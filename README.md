# OpenRun

OpenRun is a branch-first Markdown workspace for collaborative knowledge building with coding agents.

The repository is the product. Your coding agent is the runtime. There is no required server, scheduler, or harness inside this repo.

The default branch is only the entrypoint for a fresh workspace. Real work lives on personal branches.

## How To Work

1. Start from the default template branch.
2. Create your own branch.
3. Add or revise Markdown files.
4. Compare your branch with other branches using git.
5. Pull specific work from other branches into your own branch only when you want it.

## Branch Rules

- The default branch is a bootstrap template, not a shared wiki.
- Do not merge ordinary knowledge work into the default branch.
- Use clear branch names such as `name/main`, `name/topic`, or `name/date-topic`.
- Keep exploratory, disputed, and durable knowledge work on branches.
- If you want material from another branch, import it into your own branch deliberately after reviewing the diff.

## Workspace

- [AGENTS.md](./AGENTS.md) is the operating contract for coding agents.
- [index.md](./index.md) is the catalog of durable pages.
- [log.md](./log.md) is the append-only event log.
- [raw/README.md](./raw/README.md) describes source material.
- [wiki/README.md](./wiki/README.md) describes synthesized shared knowledge.
- [decisions/README.md](./decisions/README.md) describes durable project decisions.

## Runtime Model

Anyone can use any coding agent locally against this repo. Local automation such as cron jobs, search tooling, or editor plugins is optional and stays outside the repo unless collaborators explicitly decide otherwise.

## Collaboration Model

There is no canonical shared content branch. The repo provides a common starting point and shared conventions. Each branch is a sovereign workspace. Collaboration happens when one person chooses to inspect and adopt work from another branch.
