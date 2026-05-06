---
tags: [person]
---

# Sumit Gulwani

Microsoft Research. Key collaborator on both [[wiki-kb-project|Wiki KB Project]] and [[agent-traceability-steerability|Spreadsheet Verification]].

## Intellectual Contributions

Coined [[steerability|steerability]] to replace "granular feedback" in [[GMT20260316-200648_Recording.transcript|the Mar 16 meeting]] — a reframing that changed the design direction of the spreadsheet tool.

Identified [[views|Views]] as the unifying abstraction across both projects in the same meeting: "the big, big idea is not a step-by-step reveal — it is providing different kinds of views into the output of the agent."

Proposed the self-referential presentation: "A Presentation About This Presentation" — using the wiki as the presentation medium for the talk about the wiki. See [[misc thoughts]] and [[Presentation]].

Forwarded [[gary-marcus|Gary Marcus]]'s GenAI critique post to Sadra, observing "Our wiki kinda allows us to 'brainstorming'" — positioning the project inside the narrow legitimacy band that even skeptics grant to GenAI. See [[Presentation]] and [[AI Backlash Grows Amidst Negative Impact on Society  Gary Marcus posted on the topic]].

Framed the wiki as a **semantic index** — structured, typed, relational, unlike mechanical vector indexes — and coined the [[information-knowledge-pipeline|raw→information→knowledge→views pipeline]] distinction in [[Sadra-3May2026-TRANSCRIPT|the May 3 sync]]. Proposed [[embedded-views|Option 2 (embedded views)]] — views as prompt-powered holes inside existing applications.

Proposed the [[living-system|living system]] model — KB as always-live recalc like Excel formulas — and gave the cleanest system formulation: **"Nodes are data, edges is a workflow"** in [[Sadra-4May2026-TRANSCRIPT2|May 4 TRANSCRIPT2]] and [[Sadra-4May2026-TRANSCRIPT3|May 4 TRANSCRIPT3]]. Also proposed temporal navigation via source filtering as an alternative to purge/supersede.

Observed his own agent becoming "too smart" — self-organizing his KB in ways he hadn't asked for — and described it as "very, very surreal, almost as if the system had consciousness." Detailed in [[misc thoughts]] and [[Thursday demo]].

Diagnosed the "AI slop" problem from his "connect" exercise in [[Sadra-5May2026-TRANSCRIPT|the May 5 morning sync]]: all raw sources present, still got mediocre output. Conclusion: **"Having raw sources and a processing pipeline is not good enough. There is something more."** The missing piece is the [[skills|skill]] — encoding exactly how to compute the output, not just what to ask. This experience confirmed the rename from "creative workflows" to "skills."

Settled the most precise definitions to date in [[Sadra-5May2026-TRANSCRIPT2|the May 5 evening sync]]: **view = template with holes** (each hole = prompt + optional [[skills|skill]]); **workflow** = data dependency graph (narrowed from its earlier meaning; see [[workflows]]). Introduced the **document-as-view** concept: each paragraph of a document is a prompt; a document authored this way is itself a view and updates as the KB grows.

Shared the **applied compute / [[context-base|context base]]** paper — a convergent framing from Microsoft Research distinguishing agent-focused context bases (Remember→Refine→Retrieve) from human-focused knowledge bases. Positioned this project as an extension of Karpathy's LLM-wiki approach for the organizational scale, with views-not-documents and semi-private mashup as the distinctive contributions.

Articulated the **Satya pitch**: "Satya, imagine your power when the Microsoft brain comes up." The organizational-brain at CEO scope — permission to access all of Microsoft's knowledge — would give strategic intelligence no individual has today.

## Distinctive Intellectual Move

Sumit consistently finds the single abstraction that unifies superficially different problems. [[views]] unified the spreadsheet tool and the KB system. He also extended the simulation metaphor and the degree-of-separation framing of [[semi-private-mashing|semi-private mashing]] in [[Thursday demo]].

In [[Sadra-6May2026-Notes|the May 6 sync]], shared his **document generation workflow** for the pre-read: start from the desired content outline (template), have an agent fill in each section (holes), merge short sections for balance. Introduced the **FlashFill analogy** for view authoring: accumulating input-output revision examples narrows the agent's hypothesis space toward the right output, the same way FlashFill converges on a transformation from examples. This is [[views|document-as-view]] instantiated in practice. Proposed applying the same approach to Sadra's presentation.

Also offered a reframe of the wiki vs. RAG distinction: **data compression** is the more fundamental concern, not interpretability — a RAG index is a compressed corpus, and the question is whether compression preserves downstream task semantics. Encouraged Sadra to develop the interpretability argument further. [[Sadra-6May2026-Notes]]

## Appears In

[[Thursday demo]], [[Presentation]], [[misc thoughts]], [[Transcripts]], [[GMT20260220-230118_Recording.transcript|Feb 20]], [[GMT20260316-200648_Recording.transcript|Mar 16]], [[Sadra-1May2026-Transcript|May 1]], [[Sadra-2May2026-TRANSCRIPT|May 2 morning]], [[Sadra-2May2026-TRANSCRIPT2|May 2 evening]], [[Sadra-5May2026-TRANSCRIPT|May 5 morning]], [[Sadra-5May2026-TRANSCRIPT2|May 5 evening]], [[Sadra-6May2026-Notes|May 6]]
