# Log

Append new entries to the end of this file. Use the format:

`## [YYYY-MM-DD] action | title - author`

## [2026-04-21] bootstrap | OpenRun seed repository - Codex

- Added the initial OpenRun collaboration contract to `AGENTS.md`.
- Seeded the repository with `README.md`, `index.md`, `log.md`, and the base content directories.

## [2026-04-21] decision | Shifted OpenRun to sovereign branch collaboration - Codex

- Reframed the default branch as a fresh workspace template rather than a shared truth branch.
- Updated the repo contract so durable knowledge work stays on personal branches.
- Documented pull-based collaboration: inspect another branch, then selectively import what you want into your own branch.

## [2026-04-21] query | Cortisol vs adrenaline — evolutionary split of the stress response - danie

- Filed `wiki/cortisol-vs-adrenaline.md` synthesizing why vertebrates run a fast SAM/amine axis and a slow HPA/steroid axis rather than a single stress hormone.
- Indexed the page in `index.md` under Wiki.
- No new raw source ingested; candidate sources noted in the page's `source_refs` for future ingest.

## [2026-04-21] decision | Query answers are wiki artifacts, not chat - danie

- Added `decisions/2026-04-21-query-answers-are-artifacts.md` recording the rule.
- Patched `AGENTS.md`: added an `### Operations` subsection to the core contract naming `ingest / query / lint` with explicit filesystem outputs and a filing threshold for queries.
- Clarified the "start from existing Markdown structure" rule so it is not read as discouragement from creating new files.
- Trigger: the cortisol Q/A above had to be filed only after the user explicitly asked, exposing that the query→artifact loop was essay-only in the prior contract.

## [2026-04-21] ingest | Bridgham, Carroll & Thornton 2006 (Science) — ancestral corticoid receptor - danie

- Filed `raw/bridgham-2006-mr-gr-evolution.md` with the full citation, verbatim abstract (via PubMed 16601189), and a scoped list of what the paper does and does not support.
- Patched `wiki/cortisol-vs-adrenaline.md`: promoted Bridgham 2006 to a real `source_ref`; rewrote the Evolutionary sketch to attribute the two-amino-acid specificity result to the MR/aldosterone lineage (not GR/cortisol) and to flag that the ~450 Mya dating is not established by this paper; softened the same claim in the comparison table pending a dedicated source.
- Indexed the raw file in `index.md` under Raw.
- First exercise of the `ingest` verb. It materially changed the wiki page — surfaced a misattribution that synthesis-from-general-knowledge had let stand — which validates ingest as a distinct check from lint.
