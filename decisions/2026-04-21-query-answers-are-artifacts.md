---
title: Substantive query answers are wiki artifacts, not chat
date: 2026-04-21
author: danie
status: accepted
---

# Substantive query answers are wiki artifacts, not chat

## Context

The OpenRun contract (`AGENTS.md`, lines 1–49) defines the repo layout (`raw/`, `wiki/`, `decisions/`, `index.md`, `log.md`), editing rules, and the branch model. The core conceptual loop that makes the repo a *compounding* knowledge base — `ingest` → `query` → `lint` — lives only in the "LLM Wiki" essay further down (lines 51+). The essay mentions in passing that "good answers can be filed back into the wiki as new pages" (line 89), but this is prose, not a rule.

Observed consequence: an agent that reads the contract section carefully and then answers a substantive user question will answer in chat and stop, because:

1. The contract lists directories and editing rules but no verbs. It never instructs the agent to turn a query answer into a durable artifact.
2. Line 40 — "Start from the existing Markdown structure before inventing new files" — reads, on its own, as discouragement from creating new files. Without a counter-rule promoting the query→wiki loop, a cautious agent defaults to not writing.
3. There is no trigger condition telling the agent *when* an answer is substantive enough to warrant filing.

This was surfaced in a real session on 2026-04-21 where a user had to explicitly ask "add this as an artifact" after a multi-paragraph synthesis had been produced in chat.

## Decision

1. **Promote the `ingest / query / lint` loop from essay to contract.** Add an `### Operations` subsection to `AGENTS.md`'s core section that names the three verbs and, for each, states what the agent is expected to produce on the filesystem.
2. **Make query→artifact the default, not an option.** State explicitly that substantive answers to user questions are filed as wiki pages (or appended to existing pages), with an `index.md` entry and a `log.md` `query` line. Chat-only answers are a fallback for trivial or conversational exchanges, not the default for synthesis.
3. **Provide a filing threshold.** The default trigger: any answer that synthesizes multiple facts, takes more than a short paragraph, or that the user is likely to want to refer back to, is an artifact. When in genuine doubt, ask once; after that, file by default for that session.
4. **Clarify line 40.** The "start from existing structure" rule is about *reusing pages where a topic already has one*, not about suppressing new pages. New durable topics get new pages; that is the intended growth pattern.

## Consequences

- Agents reading the contract alone (without the essay) will now see the query→file loop as a first-class rule.
- `wiki/` will grow faster because answers stop evaporating into chat history.
- `log.md` becomes a useful timeline of what has been asked, not just what has been ingested.
- Risk: low-value questions (clarifications, small lookups) could pollute the wiki if the threshold is interpreted too liberally. The filing-threshold clause above is the mitigation; lint passes are the backstop.

## Related

- `AGENTS.md` — patched in the same change.
- `wiki/cortisol-vs-adrenaline.md` — the filing of this page was the trigger for this decision.
- `log.md` — `query` entries now expected for substantive answers.
