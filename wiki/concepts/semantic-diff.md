---
tags: [concept]
---

# Semantic Diff

A **semantic diff** surfaces the *computational unit* driving a change — the formula, transformation rule, or generative instruction — rather than enumerating every affected artifact element. Proposed as a design primitive for inspectable agentic interfaces in [[Auditing and Controlling AI Agent Actions in Spreadsheets|the Pista paper]].

## The Problem It Solves

Agents typically surface what changed at the artifact's *surface*: highlighted cells, inserted lines, modified pixels. But users reason about the *operation* that produced the change — the formula, the transformation rule — and whether that operation matches their intent. When surface unit and semantic unit diverge, verification becomes intractable: users must reconstruct the agent's logic from its outputs.

The mismatch is acute in spreadsheets: if a VLOOKUP drives 500 changes, surfacing 500 highlighted cells is noise. Surfacing one formula, its source range, and its output range is signal. [[agent-traceability-steerability|Pista]] does the latter — and participants specifically cited formula-level visibility as what made verification tractable rather than exhausting.

## Generalization Across Domains

The semantic diff is domain-agnostic: it requires identifying what the meaningful unit of change is in each artifact type:

- **Spreadsheets** → the formula or transformation rule (not the cell values it produces)
- **Code agents** → the function or architectural decision (not the line diff)
- **Document agents** → the rhetorical move or structural decision (not the character edit)

A semantic diff layer that understands domain-specific artifact structure could serve as shared infrastructure for inspectable agentic interfaces — making agent reasoning legible not just to the immediate user but to anyone reviewing the artifact afterward.

## Connection to [[steerability|Steerability]]

Semantic diffs are a prerequisite for meaningful steerability: you can only steer a step you understand. Without a semantic diff, the user sees output, not intent. With one, the user sees "the agent applied a VLOOKUP over this range for this reason" — and can now judge whether that decision was correct before it propagates.
