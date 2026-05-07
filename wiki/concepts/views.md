---
tags: [concept, core]
---

# Views

A **view** is a template with holes, where each hole is filled by executing a prompt against an optional specification of input sources. Each prompt can optionally be associated with a [[skills|skill]] that describes a better way to compute that piece. This is the most precise definition, settled in [[T14-2026-05-05-2|the May 5 evening sync]]: "A view is a template. Its holes are filled by executing prompts against an optional specification of input sources. Each prompt can optionally be associated with a skill."

Views define WHAT to show, not HOW to produce it (that's [[skills|Skills]] for per-prompt methodology and [[workflows|Workflows]] for data dependencies). Views are the central unifying concept across both [[wiki-kb-project|Wiki KB Project]] and [[agent-traceability-steerability|Spreadsheet Verification]]; Sumit drew this connection explicitly in [[T4-2026-03-16-2006|the Mar 16 meeting]].

## Structure

A view has three layers:
1. **Template** — the structure with named holes (required)
2. **Prompts** — one per hole; declarative specs for what to fill each hole with (required)
3. **Skills** — optional per-prompt methodology; without a skill, the agent chooses its own approach (see [[skills]])
4. **Source selection** — optional specification of which raw sources feed which holes

This layering was articulated in [[Thursday demo]], refined during [[T7-2026-05-01|the May 1 three-way sync]], and made precise in [[T14-2026-05-05-2|May 5]].

## Document as View

Every paragraph of a document can be a prompt in a view. Sumit articulated this in [[T14-2026-05-05-2|the May 5 sync]] while describing his internal blog post: the motivating story section, the definitions section, the applications section — each is a prompt over the KB, optionally guided by a skill. A document authored this way becomes a living document: when new transcripts arrive, the document's prompts rerun and it updates. "I want this document also to be a view in some sense." This is the "recalc model taken to its extreme" — what dashboards and Excel formulas do for objective, code-expressible computation, views do for subjective and aesthetic content.

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

## View Definition UX: Vibe Sessions and the FlashFill Analogy

Sumit noted in [[T10-2026-05-03|the May 3 sync]] that defining the right view requires iteration: "the real experience is going to be that I'm trying to create some view, and it will take a lot of iteration before I land onto something that I like." The natural UX is a **vibe session** — an interactive back-and-forth that explores the right prompt and workflow. After the session, the user should be able to distill it into a reusable view definition. The current CLI lacks this facility.

In [[T15-2026-05-06|the May 6 sync]], Sumit made the convergence mechanism concrete via the **FlashFill analogy**: FlashFill narrows a large space of possible transformation functions by accumulating input-output examples. The same principle applies to view authoring — each revision is a new example, narrowing the hypothesis space until the agent produces the right output. You don't specify the skill upfront; you accumulate examples until the view converges. This is a practical workflow for authoring both the template structure and the per-hole prompts.

## Embedded Views

An alternative rendering model proposed in May 3: instead of generating standalone files, views are embedded inside existing applications (Word, PowerPoint, Excel) as prompt-powered holes in a document template. See [[embedded-views]].
