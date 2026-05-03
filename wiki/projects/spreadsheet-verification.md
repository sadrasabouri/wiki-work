---
tags: [project]
---

# Spreadsheet Verification

Research tool (also called "R2" and "[[agent-lens|Agent Lens]]") for helping humans verify AI agent computation in spreadsheets. The core problem: as agents become more capable, human verification becomes harder — this is the [[scalable-oversight|scalable oversight]] problem.

## Why Spreadsheets Specifically

Spreadsheets are *data-centric*: users think in terms of data transformations (input data → output data), not process (code logic). This creates a different verification challenge than programming: users check outputs cell-by-cell rather than comparing code against a mental model. Discussed in [[GMT20260220-230118_Recording.transcript|the Feb 20 meeting]].

## Framework: Stop, See, Steer

The [[agent-lens|Agent Lens]] framework: **stop** execution at a computation step, **see** the [[dag-of-computation|DAG of computation]] showing dependencies, **steer** by correcting a step before it propagates. [[steerability|Steerability]] is the theoretical framing; the DAG is the visual mechanism.

## Formative Study

Eight participatory design sessions conducted before the Mar 16 meeting. Key findings: users liked step-by-step reveal; they wanted to understand the rationalization behind each step (validated the preloaded Q&A idea); they wanted to explore alternatives. See [[GMT20260316-200648_Recording.transcript|Mar 16]] for Sadra's presentation of results to Sumit.

## Connection to [[wiki-kb-project|Wiki KB Project]]

[[sumit-gulwani|Sumit]] identified [[views|Views]] as the abstraction that unifies both projects in [[GMT20260316-200648_Recording.transcript|Mar 16]]. The DAG view, step-by-step reveal, and formula-only view are all views of agent computation in the same sense that design docs and topic summaries are views of a knowledge corpus.

## Key People

[[sadra-sabouri|Sadra Sabouri]], [[souti-chattopadhyay|Souti Chattopadhyay]], [[sujay-maladi|Sujay Maladi]], [[athena-saghi|Athena Saghi]]. Active Feb–March 2026.

## Sources

[[GMT20260220-230118_Recording.transcript|Feb 20]], [[GMT20260304-191231_Recording.transcript|Mar 4]], [[GMT20260311-184637_Recording.transcript|Mar 11]], [[GMT20260316-200648_Recording.transcript|Mar 16]]
