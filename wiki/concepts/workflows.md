---
tags: [concept, core]
---

# Workflows

**Note:** As of [[T14-2026-05-05-2|the May 5 sync]], the term "workflow" has been narrowed. What was previously called a "creative workflow" or the HOW of computation is now called a [[skills|Skill]]. Workflow now refers exclusively to the **data dependency graph** between views and raw sources.

A **workflow** is a representation of data dependencies between views and raw sources. When a raw source updates, the workflow tells the system which prompts need to rerun and in what order. Analogous to GitHub Actions: "any company that tries to develop this product can just look at whatever in-house technology they have for automating workflows… I can just imagine this workflow fitting as part of that automation story." — Sumit, [[T14-2026-05-05-2]].

The earlier framing — "a workflow is the HOW to a view's WHAT" — is now the definition of [[skills|Skills]]. The constructive examples below (grounded theory, multi-pass summarization) are now properly called skills.

## Key Examples (now: Skills)

- **Grounded theory analysis** — iterative inductive coding → clustering → naming; suits messy qualitative transcripts
- **Multi-pass summarization** — repeat summarization 3× on the same content; each pass compresses further; produces materially better output than single-pass
- **Per-slide summarization** — chunk by slide, summarize independently, then compose
- **Researcher agent** — an autonomous AI agent that searches and reads external sources; it becomes a *source type* that feeds into views (discussed in [[T9-2026-05-02-2]])

In the [[living-system|living system]] model formalized in [[T12-2026-05-04-2|May 4]], workflows are the **edges** in the full computation DAG: every transformation between data nodes — including upstream data-gathering processes — is a workflow. This extends the concept beyond "how to process existing data into views" to also cover "how to collect raw data in the first place." A search query ("get top 5 Twitter posts matching X") is itself a workflow whose output becomes raw data for the next stage.

## Steerability at Workflow Boundaries

Workflows are where [[steerability|Steerability]] is most meaningful. Each step is a potential intervention point — the user can redirect before output propagates downstream. A workflow without steerability is a black box; with steerability it is a collaborative pipeline. This was the design goal articulated for [[agent-traceability-steerability|Spreadsheet Verification]] in [[T4-2026-03-16-2006|the Mar 16 meeting]].
