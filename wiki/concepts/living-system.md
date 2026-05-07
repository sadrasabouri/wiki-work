---
tags: [concept]
---

# Living System

The KB as an always-current, self-updating system that recomputes whenever new data arrives — like Excel formulas, not Excel values. Articulated by [[sumit-gulwani|Sumit]] across two late-night syncs in [[2026-05-04|May 4]] ([[T11-2026-05-04-1]], [[T12-2026-05-04-2]]).

## The Excel Formula Analogy — Three Concrete Anchors

Three real-world examples grounded the concept in [[T14-2026-05-05-2|the May 5 sync]]:
1. **Dashboards** — auto-update when new data arrives; already standard in BI tools
2. **Excel formulas / recalc engine** — static cells vs. formula cells; the formula recomputes when inputs change
3. **Excel "Equals Copilot" feature** — a prompt-powered cell; the prompt applies to new inputs and repeats automatically

These examples show the recalc model applied to *objective*, code-expressible computation. The KB extends it to *subjective* and *aesthetic* content: "the recalc feature was never applied to an entire document because it is subjective… but hey, now we have the power to process this." See also [[views|Document as View]].

"Another way to think about this knowledge graph is that it also encodes workflow automation... when you change A1 and B1, C1 automatically updates. So that kind of workflow automation we are trying to do." — Sumit, [[T12-2026-05-04-2]]

## Trigger Types

Two types of events that should trigger recomputation:

1. **Manual raw data addition** — a new transcript, email, or document is ingested. Downstream wiki pages and views that depend on this source update.
2. **Automated data-gathering process** — a upstream workflow (e.g., "get the 5 most popular Twitter posts matching X criteria") runs and produces new raw data. The system reruns from there.

Trigger type 2 is novel: raw data does not have to come from human authoring. The user's creativity goes into specifying the data-gathering criteria; the system handles execution and downstream propagation. When rerun tomorrow, the raw data may differ, and the wiki updates accordingly.

## Automated Raw Data Generation

Standard assumption: raw data = human-authored content (transcripts, emails). Sumit challenged this: "raw data can come from a process." The process is itself a creative workflow — "go to X, get top 5 posts with at least 100 likes, ordered by recency." Capturing this process in the system means the system can rerun it autonomously.

This extends the concept of [[workflows|Workflows]] upstream: workflows don't only describe how to process existing raw data into views — they can also describe how to *collect* raw data from external sources.

## Everything is a DAG

The cleanest formulation of the system architecture, from [[T12-2026-05-04-2]]: **"Nodes are data, edges is a workflow. That's it."**

Every artifact — Twitter post, wiki concept page, view output — is a node (data at some refinement level). Every transformation is an edge (workflow). The system is a DAG. This subsumes all previous framings: the [[information-knowledge-pipeline|raw→knowledge→views pipeline]] is one path through this DAG; the [[dag-of-computation|DAG of Computation]] in spreadsheet verification is a subgraph.

## Temporal Navigation via Source Filtering

A living system with provenance tracking enables a new form of temporal navigation: let users filter which input sources participate in computing a view. Default = all sources. Filtering out transcripts from the last week = seeing the KB state from before that week.

This was proposed in [[T11-2026-05-04-1|the May 4 early morning sync]]: "The temporal view can be just a special case or a side effect of another more general functionality, which is the ability to let them select which input sources should participate." Compare to [[temporal-knowledge|purge/supersede]], which modifies the KB permanently; source filtering is a non-destructive, query-time operation.

## Relation to MapReduce

Most computations in the system are MapReduce-style: a wiki page is produced by mapping over relevant raw sources and reducing to a summary. This structure supports incremental recomputation — when one source changes, only the downstream nodes that depend on it need to recompute.
