---
tags: [concept]
---

# DAG of Computation

Visualizing AI agent computation as a directed acyclic graph where nodes are individual operations and edges are data dependencies between them. The key visual contribution of [[spreadsheet-verification|Spreadsheet Verification]] / [[agent-lens|Agent Lens]].

Proposed by [[sumit-gulwani|Sumit]] in [[GMT20260316-200648_Recording.transcript|the Mar 16 meeting]] as a second view alongside step-by-step reveal: "show the entire thing as a DAG, where each card talks about each step the agent did."

## Why DAG Over Linear Log

Competing approaches showed agent computation as a linear log of steps. The DAG shows the actual *causal structure*: which steps depended on which earlier outputs, where parallel computations happened, and where a single upstream error propagates to multiple downstream results. This lets users trace *why* a cell was computed incorrectly, not just *that* it was.

## The "See" in Stop/See/Steer

The DAG is the "see" component of the [[agent-lens|Agent Lens]] framework. Without seeing the computation structure, users can't identify which step to correct. The DAG makes the computation inspectable; [[steerability|steerability]] makes it modifiable.

## Connection to [[views|Views]]

The DAG view is one specific rendering of agent computation — one [[views|View]] in the views framework. A user who cares only about formula correctness would use a different view (just the formulas). A user debugging a data transformation error would use the DAG. This is precisely the use case Sumit described in the Mar 16 meeting when connecting the spreadsheet tool to the broader views concept.

## Extension: Full-System Provenance DAG

In [[Sadra-4May2026-TRANSCRIPT2|the May 4 early morning sync]], Sumit extended this concept beyond the spreadsheet context to the entire wiki KB: a graphical view of computational dependencies across ALL levels — raw sources → wiki entities → view outputs. This "provenance DAG" shows users what was computed from what across the full [[information-knowledge-pipeline|information → knowledge → views pipeline]]. 

The clean formulation from [[Sadra-4May2026-TRANSCRIPT3|the May 4 morning sync]]: **"Nodes are data, edges is a workflow."** Every artifact is a node; every transformation is an edge. The full system is one DAG — the spreadsheet tool's computation DAG is a subgraph. See [[living-system]] for the recalc implications of this architecture.
