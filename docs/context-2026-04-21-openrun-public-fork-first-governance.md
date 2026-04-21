# Context: OpenRun Public Fork-First Governance

## Session Goal

Decide how OpenRun should work for public participation while preserving sovereignty, avoiding accidental overwrite, and keeping the upstream repository minimal.

## What Was Resolved

- Rejected the idea that public participants should create branches directly in the upstream repo.
- Confirmed that GitHub does not natively support the desired rule: "anyone can create a branch, but only write to the branch they created."
- Distinguished between two collaboration contexts:
  - a small trusted group, where shared-repo branches can be tolerable
  - public participation, where shared-repo branches do not provide a real isolation boundary
- Chose a fork-first public model for OpenRun.

## First-Principles Reasoning

Public participation and branch sovereignty are separate requirements.

- Public participation means a stranger must be able to start work without asking for write access.
- Sovereignty means a stranger's work must be isolated so another stranger cannot overwrite it.
- In GitHub's model, a branch inside one shared upstream repo is only a name in a shared namespace unless host-level permissions protect it.
- A fork is a real isolation boundary because each participant controls their own remote.

Therefore, for a public OpenRun, forks are not a workaround. They are the correct native primitive.

## Durable Decision

OpenRun should use this public model:

- The upstream repository is the template and protocol surface.
- `seed` is the protected bootstrap branch in the upstream repository.
- Public participants work in forks by default.
- Durable knowledge work lives in each participant's sovereign workspace, usually their fork.
- Adoption is pull-based: if you want someone else's work, fetch it, inspect it, and selectively adopt it into your own workspace.
- Upstream accepts template and protocol changes, not ordinary wiki content.

## Why Not Shared Upstream Branches

Using shared upstream branches for public work fails the real requirement:

- GitHub does not natively enforce dynamic creator-owned branches.
- Granting broad write access solves "can create branch" by also granting "can overwrite other branches."
- That makes same-repo public branching convenient but structurally unsound for OpenRun's goals.

The convenience of comparing branches in one repo is real, but it is a usability tradeoff, not a reason to reject the correct isolation model.

## Consequences For The Repo

- `README.md` should explain a fork-first participation flow.
- `AGENTS.md` should state that sovereign workspaces usually live in forks and that upstream is template-only.
- Upstream should remain sparse and stable.
- Template improvements may still flow back upstream from forks.
- Ordinary content, personal decisions, logs, and wiki pages should remain in participant workspaces unless someone deliberately imports them elsewhere.

## Notes

- A GitHub organization could still be useful later for governance, branding, and team management.
- An organization does not solve dynamic "branch creator owns branch" semantics by itself.
- Trusted collaborators may still choose to use shared-repo branches as a convenience mode, but that should be treated as an exception, not the public architecture.
