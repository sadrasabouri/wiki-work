---
tags: [view, timeline]
prompt: /timeline views
generated: 2026-05-06
---

## Timeline: Views

| Date | Development | Source |
|------|-------------|--------|
| pre-2026-03-16 | Spreadsheet Verification operates with "step-by-step reveal" and "granular feedback on edit" — no "views" concept yet; each rendering is treated as a named feature, not an instance of a shared abstraction. | [[2026-03-11]] |
| 2026-03-16 | **Views named and unified.** Sumit reframes the entire project: "the big, big idea is not a step-by-step reveal — it is providing different kinds of views into the output of the agent." DAG view named alongside step-by-step reveal. Views identified as the abstraction unifying both Spreadsheet Verification and the Wiki KB Project. | [[2026-03-16]] |
| 2026-05-01 | Views taxonomy for the wiki KB articulated: design doc, contribution review, topic summary as example types; hierarchical views (sub-views as slide titles) noted; workflows distinguished as the constructive counterpart to views' declarative spec. | [[2026-05-01]] |
| 2026-05-02 | Views vs. workflows distinction sharpened: views are declarative (what to show), workflows are constructive (how to produce it). Teams custom summary identified as a real-world proto-view — one fixed template applied to a single transcript. | [[2026-05-02]] |
| 2026-05-03 | Sumit gives first formal definition in email: "a template whose holes are filled with prompts FROM a specified source of raw information and USING a specified workflow." User-extensibility confirmed ("users should be able to define their own views and sub-views"). Presentation-as-a-view instantiated: "VIEWS on top of this wiki/KB management is the future of Office and knowledge work." | [[Thursday demo]] |
| 2026-05-03 | Live wiki demo: wiki reframed as a **semantic index**, not a view output — views operate on wiki, not raw data (efficiency argument). Embedded views proposed as Option 2: views as prompt-powered holes inside Word/PPT/Excel rather than standalone generated files. Vibe session as view definition UX identified as a missing facility. | [[2026-05-03]] |
| 2026-05-04 | **Wiki becomes a view.** Sumit: "Wikis are also a special kind of view." In the full-system DAG, raw data, wiki entities, and view outputs are all nodes; edges are workflows. Everything-is-a-DAG formulation: "Nodes are data, edges is a workflow. That's it." Source filtering proposed as a mechanism for temporal navigation within views. | [[2026-05-04]] |
| 2026-05-05 | **Most precise definition settled.** "A view is a template. Its holes are filled by executing prompts against an optional specification of input sources. Each prompt can optionally be associated with a skill." Views/Workflows/Skills triangle fully defined — views = what, workflows = data dependencies, skills = per-hole HOW. **Document as view** articulated: every paragraph of any document can be a prompt. | [[2026-05-05]] |
| 2026-05-06 | **FlashFill analogy** for view authoring: instead of specifying the skill upfront, accumulate input-output example revisions until the view converges — the same principle FlashFill uses to narrow a space of transformation functions. Document-as-view instantiated in practice: Sumit authored his pre-read by filling section-holes via agent iteration. | [[2026-05-06]] |

### Key Inflection Points

- **2026-03-16** — The word "views" is coined and immediately promoted to the unifying abstraction across two projects. Before this meeting, step-by-step reveal was the main Spreadsheet Verification concept; after it, step-by-step reveal becomes one instance of views. This is the founding moment.
- **2026-05-03** — Two critical shifts in one day: views gets its first formal written definition (email), and the wiki is reframed as *infrastructure for views* rather than *a product of views*. Embedded views is proposed as an alternative rendering model — the concept reaches architectural maturity.
- **2026-05-04** — The boundary of "views" expands to include the wiki itself. This recursive move — wiki-as-view — unifies the entire system architecture into a single DAG model. Views is no longer a category of outputs; it is the universal node type.
- **2026-05-05** — The definition is nailed. The terminological churn (views / workflows / skills) resolves into precise, non-overlapping concepts. "Document as view" extends views beyond research artifacts into everyday knowledge work documents.

---

The "views" concept began as a reframing intervention — Sumit arriving at the Mar 16 meeting and naming what the Spreadsheet Verification project had been building all along without a word for it. It crossed projects immediately, giving the wiki KB project its central abstraction before the project had a name. Over the following weeks of intense collaboration, the concept expanded in four directions: its definition sharpened (template + prompt holes + optional skill + optional source selection); its rendering model diversified (standalone CLI vs. embedded in Office apps); its scope widened (wiki-as-view, document-as-view); and its authoring model matured (vibe sessions, FlashFill convergence). Where it stands now: views is the foundational concept — not one feature among many, but the frame inside which everything else (skills, workflows, the wiki, the DAG) finds its place.
