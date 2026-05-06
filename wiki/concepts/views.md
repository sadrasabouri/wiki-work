---
tags: [concept, core]
---

# Views

A **view** is a template with holes, where each hole is filled by executing a prompt against an optional specification of input sources. Each prompt can optionally be associated with a [[skills|skill]] that describes a better way to compute that piece. This is the most precise definition, settled in [[Sadra-5May2026-TRANSCRIPT2|the May 5 evening sync]]: "A view is a template. Its holes are filled by executing prompts against an optional specification of input sources. Each prompt can optionally be associated with a skill."

Views define WHAT to show, not HOW to produce it (that's [[skills|Skills]] for per-prompt methodology and [[workflows|Workflows]] for data dependencies). Views are the central unifying concept across both [[wiki-kb-project|Wiki KB Project]] and [[agent-traceability-steerability|Spreadsheet Verification]]; Sumit drew this connection explicitly in [[GMT20260316-200648_Recording.transcript|the Mar 16 meeting]].

## Structure

A view has three layers:
1. **Template** — the structure with named holes (required)
2. **Prompts** — one per hole; declarative specs for what to fill each hole with (required)
3. **Skills** — optional per-prompt methodology; without a skill, the agent chooses its own approach (see [[skills]])
4. **Source selection** — optional specification of which raw sources feed which holes

This layering was articulated in [[Thursday demo]], refined during [[Sadra-1May2026-Transcript|the May 1 three-way sync]], and made precise in [[Sadra-5May2026-TRANSCRIPT2|May 5]].

## Document as View

Every paragraph of a document can be a prompt in a view. Sumit articulated this in [[Sadra-5May2026-TRANSCRIPT2|the May 5 sync]] while describing his internal blog post: the motivating story section, the definitions section, the applications section — each is a prompt over the KB, optionally guided by a skill. A document authored this way becomes a living document: when new transcripts arrive, the document's prompts rerun and it updates. "I want this document also to be a view in some sense." This is the "recalc model taken to its extreme" — what dashboards and Excel formulas do for objective, code-expressible computation, views do for subjective and aesthetic content.

## Examples

- *Step-by-step reveal* of agent computation (spreadsheet tool)
- *DAG visualization* of a computation's dependency graph
- *Topic summary* over a Teams channel thread
- *Contribution review* isolating what changed and why
- *Design doc* view of a codebase
- The wiki itself — `wiki/index.md` is a view over all wiki pages

## Why Views Bridge Both Projects

In [[agent-traceability-steerability|Spreadsheet Verification]], views render agent computation differently for different audiences. In the [[wiki-kb-project|Wiki KB Project]], views render knowledge differently for different purposes (presentation, onboarding, deep dive). The self-referential case from [[Presentation]]: using the wiki as a live presentation ("presentation about this presentation") is itself a view.

## Analogy to Database Views

A database view is a saved query over mutable data; a wiki view is a saved prompt over an evolving corpus. Both hide underlying complexity behind a purpose-specific lens. Views are user-definable and hierarchical — a "design doc" view can compose with a "topic summary" view.

## View Definition UX: Vibe Sessions

Sumit noted in [[Sadra-3May2026-TRANSCRIPT|the May 3 sync]] that defining the right view requires iteration: "the real experience is going to be that I'm trying to create some view, and it will take a lot of iteration before I land onto something that I like." The natural UX is a **vibe session** — an interactive back-and-forth that explores the right prompt and workflow. After the session, the user should be able to distill it into a reusable view definition. The current CLI lacks this facility.

## Embedded Views

An alternative rendering model proposed in May 3: instead of generating standalone files, views are embedded inside existing applications (Word, PowerPoint, Excel) as prompt-powered holes in a document template. See [[embedded-views]].
