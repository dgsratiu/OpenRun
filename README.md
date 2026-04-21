# OpenRun

OpenRun is a public Markdown protocol for sovereign knowledge work with coding agents.

The repository is the product. Your coding agent is the runtime. There is no required server, scheduler, or harness inside this repo.

This upstream repository is the template and protocol surface. Real work lives in sovereign workspaces, usually forks.

## What This Repo Is

- `seed` is the bootstrap branch for a fresh OpenRun workspace.
- This upstream repo defines the protocol: layout, conventions, and agent instructions.
- Public participants should fork this repo and work in their own fork.
- Upstream is not the shared content wiki for everyone on the internet.

## Public Participation

1. Fork this repository on GitHub.
2. Clone your fork locally.
3. Create a long-lived working branch from `seed` in your fork.
4. Do your ingest, query, lint, and synthesis work in that fork.
5. If you want someone else's work, fetch it from their fork and selectively adopt it into yours.

Example:

```bash
git clone https://github.com/<you>/OpenRun.git
cd OpenRun
git remote add upstream https://github.com/dgsratiu/OpenRun.git
git fetch upstream
git checkout -b <you>/main upstream/seed
git push -u origin <you>/main
```

## Adopting Work From Another Fork

Forks remain connected through GitHub's fork network, but comparison is explicit rather than automatic.

```bash
git remote add alice https://github.com/alice/OpenRun.git
git fetch alice
git diff <you>/main alice/alice/main
```

If you want material from another participant, inspect it first, then selectively merge, cherry-pick, or copy only what you want into your own workspace.

## What Belongs Upstream

- `AGENTS.md` protocol changes
- `README.md` workflow and participation changes
- starter layout and template files
- example conventions that improve the protocol for everyone
- documentation about how OpenRun works

## What Does Not Belong Upstream

- ordinary wiki pages
- personal or branch-local logs
- personal decision records
- branch-local source ingests
- synthesized knowledge artifacts that belong to a participant workspace

## Workspace Layout

- [AGENTS.md](./AGENTS.md) is the operating contract for coding agents.
- [index.md](./index.md) is the catalog of durable pages.
- [log.md](./log.md) is the append-only event log.
- [raw/README.md](./raw/README.md) describes source material.
- [wiki/README.md](./wiki/README.md) describes synthesized shared knowledge.
- [decisions/README.md](./decisions/README.md) describes durable project decisions.

## Runtime Model

Anyone can use any coding agent locally against this repo. Local automation such as cron jobs, search tooling, or editor plugins is optional and stays outside the repo unless collaborators explicitly decide otherwise.

## Collaboration Model

There is no canonical shared content branch. The upstream repo provides a common starting point and shared conventions. Each participant keeps a sovereign workspace, usually in a fork. Collaboration happens when one person chooses to inspect and adopt work from another workspace.
