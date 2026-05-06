---
tags: [concept, core]
---

# Workflows

A **workflow** is a constructive specification of HOW to populate a [[views|View]]. Where a view says "give me a topic summary," a workflow says "do grounded theory analysis: code inductively, then cluster themes, then name them." The view/workflow distinction was sharpened in [[Sadra-2May2026-TRANSCRIPT2|the May 2 evening meeting]]: views are declarative (what), workflows are constructive (how).

## Key Examples

- **Grounded theory analysis** — iterative inductive coding → clustering → naming; suits messy qualitative transcripts
- **Multi-pass summarization** — repeat summarization 3× on the same content; each pass compresses further; produces materially better output than single-pass
- **Per-slide summarization** — chunk by slide, summarize independently, then compose
- **Researcher agent** — an autonomous AI agent that searches and reads external sources; it becomes a *source type* that feeds into views (discussed in [[Sadra-2May2026-TRANSCRIPT2]])

Workflows can be empty (just run the view's prompt) or elaborate. Crucially, workflows are *creative artifacts* — the insight that grounded theory applies to transcript summarization is itself a contribution, per [[Sadra-1May2026-Transcript|the May 1 sync]].

In the [[living-system|living system]] model formalized in [[Sadra-4May2026-TRANSCRIPT3|May 4]], workflows are the **edges** in the full computation DAG: every transformation between data nodes — including upstream data-gathering processes — is a workflow. This extends the concept beyond "how to process existing data into views" to also cover "how to collect raw data in the first place." A search query ("get top 5 Twitter posts matching X") is itself a workflow whose output becomes raw data for the next stage.

## Steerability at Workflow Boundaries

Workflows are where [[steerability|Steerability]] is most meaningful. Each step is a potential intervention point — the user can redirect before output propagates downstream. A workflow without steerability is a black box; with steerability it is a collaborative pipeline. This was the design goal articulated for [[spreadsheet-verification|Spreadsheet Verification]] in [[GMT20260316-200648_Recording.transcript|the Mar 16 meeting]].
