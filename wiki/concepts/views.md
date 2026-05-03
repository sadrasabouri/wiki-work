---
tags: [concept, core]
---

# Views

A **view** is a declarative specification — a prompt or template — applied to raw sources to produce a specific output. It defines WHAT to show, not HOW to produce it (that's [[workflows|Workflows]]). Views are the central unifying concept across both [[wiki-kb-project|Wiki KB Project]] and [[spreadsheet-verification|Spreadsheet Verification]]; Sumit drew this connection explicitly in [[GMT20260316-200648_Recording.transcript|the Mar 16 meeting]].

## Structure

A view has up to three parts:
1. **Prompt/template** — the declarative spec (required)
2. **Workflow** — how to populate it (optional; see [[workflows]])
3. **Raw data selection** — which sources to draw from (optional)

This decomposition was articulated in [[Thursday demo]] and refined during [[Sadra-1May2026-Transcript|the May 1 three-way sync]].

## Examples

- *Step-by-step reveal* of agent computation (spreadsheet tool)
- *DAG visualization* of a computation's dependency graph
- *Topic summary* over a Teams channel thread
- *Contribution review* isolating what changed and why
- *Design doc* view of a codebase
- The wiki itself — `wiki/index.md` is a view over all wiki pages

## Why Views Bridge Both Projects

In [[spreadsheet-verification|Spreadsheet Verification]], views render agent computation differently for different audiences. In the [[wiki-kb-project|Wiki KB Project]], views render knowledge differently for different purposes (presentation, onboarding, deep dive). The self-referential case from [[Presentation]]: using the wiki as a live presentation ("presentation about this presentation") is itself a view.

## Analogy to Database Views

A database view is a saved query over mutable data; a wiki view is a saved prompt over an evolving corpus. Both hide underlying complexity behind a purpose-specific lens. Views are user-definable and hierarchical — a "design doc" view can compose with a "topic summary" view.
