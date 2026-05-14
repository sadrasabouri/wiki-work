---
tags: [view, contribution-map]
generated: 2026-05-13
---

> [!note]-
> prompt: *`/contribution-map wiki-kb-project`*

## Contribution Map: Wiki KB Project

| Provenance | Person | Contribution | Date |
|-----------|--------|--------------|------|
| [[T4-2026-03-16-2006]] | [[sumit-gulwani]] | Identified **views** as the unifying abstraction across both projects: "the big, big idea is not step-by-step reveal — it is providing different kinds of views into the output of the agent." | 2026-03-16 |
| [[T7-2026-05-01]] | [[sumit-gulwani]] | Opened the first three-way sync with a live Microsoft Teams example of parallel teams unaware of each other's work — making the abstract KB problem concrete and real-time. | 2026-05-01 |
| [[T7-2026-05-01]] | [[souti-chattopadhyay]] | Coined **digital twins** as the KB's long-term goal: capturing not just technical content but tacit knowledge, interaction styles, and emotional patterns. | 2026-05-01 |
| [[T7-2026-05-01]] | [[souti-chattopadhyay]] | Raised **privacy as a design constraint** on semi-private mashing — the first explicit articulation of the boundary condition on what can flow into shared KBs. | 2026-05-01 |
| [[T7-2026-05-01]] | [[souti-chattopadhyay]] | Observed that models already know "grounded theory" — but **workflows specify when and how to apply it**, not just that it exists; reframing workflows as creative methodology, not just procedure. | 2026-05-01 |
| [[misc thoughts]] (email, 2026-05-02 14:06) | [[sumit-gulwani]] | Proposed the **self-referential presentation**: "A Presentation About This Presentation" — using the KB that contains transcripts about itself as the presentation medium. | 2026-05-02 |
| [[T8-2026-05-02-1]] | [[sadra-sabouri]] | Introduced the **simulation metaphor**: world progress = individual processing/choice-making + communication; KB accelerates both dimensions simultaneously. | 2026-05-02 |
| [[T8-2026-05-02-1]] | [[sadra-sabouri]] | Proposed KB graph update strategies — **percolation approaches** where changes ripple upward through dependent pages when a new source arrives. | 2026-05-02 |
| [[T9-2026-05-02-2]] | [[sumit-gulwani]] | Named **purge** as a first-class KB operation — without explicit superseding, contradictions accumulate silently over time. | 2026-05-02 |
| [[T9-2026-05-02-2]] | [[sumit-gulwani]] | Articulated **provenance tracking**: "AI slop" (unverified AI output) vs. "AI beauty" (verified or high-quality) — the KB must distinguish them. | 2026-05-02 |
| [[Thursday demo]] (email, 2026-05-02 23:47) | [[sumit-gulwani]] | First explicit articulation of **semi-private mashing** with the degree-of-separation framing: filtering private exchanges (1:1 meetings) via differential-privacy-style norms to enrich shared KBs — named as the mechanism for simulating societal progress. | 2026-05-02 |
| [[Thursday demo]] (email, 2026-05-03 01:31) | [[sumit-gulwani]] | Settled the core definition: **view = template whose holes are filled with prompts from a specified source and optional workflow**; input sources and workflow both default to "all" and "agent-inferred." | 2026-05-03 |
| [[Thursday demo]] (email, 2026-05-03 00:28) | [[sadra-sabouri]] | Drew the **KB-as-codebase analogy**: PRs = adding personal knowledge to shared KB; refactoring = trimming and reconstructing entities for more efficient representation; deprecation = purge. | 2026-05-03 |
| [[T10-2026-05-03]] | [[sumit-gulwani]] | Reached the **semantic index** insight: the wiki is not a view output but a structured intermediate that makes future views efficient — typed, concept-categorized, unlike opaque vector indexes. | 2026-05-03 |
| [[T10-2026-05-03]] | [[sumit-gulwani]] | Proposed **embedded views (Option 2)**: views as prompt-powered holes inside existing applications (Word, PowerPoint, Excel) rather than standalone CLI output — views live inside documents, not replacing them. | 2026-05-03 |
| [[T10-2026-05-03]] | [[sumit-gulwani]] | Observed that **ingest implicitly defines the wiki schema**: the choice of entity types (people, concepts, events, projects) is a design decision embedded in the ingest prompt, not ontologically fixed. | 2026-05-03 |
| [[T10-2026-05-03]] | [[sumit-gulwani]] | Flagged the **vibe-session gap**: defining a good view requires iterative refinement, but the CLI skips over that process; ideal UX would let users distill a vibe session into a reusable view definition. | 2026-05-03 |
| [[T10-2026-05-03]] | [[sumit-gulwani]] | Confirmed the key Karpathy differentiator: **"We never call it a personal knowledge base."** The wiki project's novelty is organizational scope; semi-private mashing is the mechanism. | 2026-05-03 |
| [[T10-2026-05-03]] | [[souti-chattopadhyay]] | Proposed the **graphical interface vision**: embedded agent + wiki where users select files, chat with the agent, and define/modify views without the CLI — views as the research contribution, not the infrastructure. | 2026-05-03 |
| [[T11-2026-05-04-1]] | [[sumit-gulwani]] | Extended the DAG concept to the full system: **full-system provenance DAG** where raw data, wiki entities, and view outputs are all nodes at different refinement levels — edges are computational relationships. | 2026-05-04 |
| [[T11-2026-05-04-1]] | [[sumit-gulwani]] | Proposed **temporal navigation via source filtering**: let users filter which input sources participate in computing a view — filtering out recent transcripts simulates past KB state. | 2026-05-04 |
| [[T12-2026-05-04-2]] | [[sumit-gulwani]] | Proposed **automated raw data generation**: the process that generates raw data is itself a capturable workflow (e.g., "get top 5 Twitter posts with ≥100 likes") — user creativity applies to data-gathering criteria, not just processing. | 2026-05-04 |
| [[T12-2026-05-04-2]] | [[sumit-gulwani]] | Gave the cleanest system formulation: **"Nodes are data, edges is a workflow. That's it."** — the entire system is a DAG of data at different refinement levels, connected by workflows. | 2026-05-04 |
| [[T12-2026-05-04-2]] | [[sadra-sabouri]] | Articulated why wiki has **privileged status as indexing infrastructure**: it is a special kind of node that creates the index making all future views efficient — not just a computed result. | 2026-05-04 |
| [[T12-2026-05-04-2]] | [[sadra-sabouri]] | Proposed **knowledge graph and event log** as alternative foundational infrastructure views that could complement or replace wiki as the indexing layer. | 2026-05-04 |
| [[T13-2026-05-05-1]] | [[sumit-gulwani]] | Diagnosed the **AI slop problem from the connect exercise**: all raw sources present, pipeline correct, output still mediocre — "Having raw sources and a processing pipeline is not good enough. There is something more." Missing: the skill encoding how to compute output. | 2026-05-05 |
| [[T14-2026-05-05-2]] | [[sumit-gulwani]] | Settled precise final definitions: **view = template + holes (each hole = prompt + optional skill)**; **workflow** = data dependency graph (narrowed from earlier creative sense); **skill** = creative methodology encoding HOW to compute one hole. | 2026-05-05 |
| [[T14-2026-05-05-2]] | [[sumit-gulwani]] | Introduced **document as view**: every paragraph of a document can be a prompt; a document authored this way auto-updates as the KB grows — the document is not a product, it is a live view. | 2026-05-05 |
| [[T14-2026-05-05-2]] | [[sumit-gulwani]] | Shared the **context base vs. knowledge base** distinction (from Applied Compute paper): agent-focused (Remember→Refine→Retrieve) vs. human-centered; positioning this project as extending Karpathy for organizational, human-in-the-loop knowledge work. | 2026-05-05 |
| [[T15-2026-05-06]] | [[sumit-gulwani]] | Insisted on **three-layer architecture as top-level directory structure**: `raw/`, `wiki/`, `views/` as peer folders — conflating layers in the file system conflates them conceptually for any reader navigating the repo. | 2026-05-06 |
| [[T15-2026-05-06]] | [[sumit-gulwani]] | Introduced the **FlashFill analogy for view authoring**: accumulating input-output revision examples narrows the agent's hypothesis space toward the right output, the same way FlashFill converges on a transformation from examples. | 2026-05-06 |
| [[T15-2026-05-06]] | [[sumit-gulwani]] | Distilled the **right-level-of-generality skill**: extracting a template from an example is a program-ranking problem — too general loses the voice, too specific just copies; named as his "biggest find" of the day. | 2026-05-06 |
| [[T15-2026-05-06]] | [[sumit-gulwani]] | Revealed **stories as the top personal-wiki content type** (ahead of concepts and people): atomic anecdotes tagged for cross-context reuse — same story usable in a scientific talk and a personal speech. | 2026-05-06 |
| [[T15-2026-05-06]] | [[sumit-gulwani]] | Articulated the **Satya pitch** as the actual goal of the Thursday talk: sponsorship, not science — Satya + organizational-brain at CEO scope as the vision and win condition. | 2026-05-06 |
| [[T15-2026-05-06]] | [[souti-chattopadhyay]] | Introduced **emergence of knowledge** as a research direction: ICLR-published network-analytic methods predicting when teams are close to discovering new ideas — generalizing views from descriptive to predictive. | 2026-05-06 |
| [[T15-2026-05-06]] | [[souti-chattopadhyay]] | Performed the **slop-recovery move**: pointed Sumit to a sentence already in his own wiki page (views as unifying abstraction) rather than generating greenfield text — revalidating provenance and grounded-examples-first as design primitives. | 2026-05-06 |
| [[T15-2026-05-06]] | [[sadra-sabouri]] | Mined **700 comments from Karpathy's GitHub gist** — the LLM-wiki origin point — categorizing related work into software engineering, researcher/ideator, and team use cases; establishing the ecosystem map. | 2026-05-06 |
| [[Building a Second Brain The Definitive Introductory Guide]] | [[tiago-forte]] | Established **BASB/CODE method** (Capture, Organize, Distill, Express) as the pre-LLM PKM intellectual predecessor; "Intermediate Packets" anticipated the project's efficiency-via-intermediate-summaries contribution. Not a project participant. | pre-2026 |

### Observations

- **Sumit drives the majority of terminological and architectural decisions.** Almost every named concept — views, purge, provenance, skills, three-layer architecture, FlashFill analogy — was first coined or precisely settled by Sumit. The concentration is striking given that he has fewer documented meeting hours than Sadra.

- **Sadra's contributions are consistently analogical and structural.** The simulation metaphor, KB-as-codebase, and wiki-as-indexing-infrastructure are Sadra's — each reframes the system in a way that makes it easier to argue for and extend, rather than changing what the system does. His contributions are positioning and architectural, not terminological.

- **Souti's contributions are research-grade and forward-looking.** Digital twins, emergence of knowledge, the graphical interface vision, and the slop-recovery move are all distinctly research-lab contributions — they extend the project's theoretical reach rather than its immediate implementation. Her appearances in the record are fewer but consistently non-redundant.

- **Semi-private mashing was first clearly named by Sumit in an email** (Thursday demo, May 2 at 23:47), not in a meeting. The concept predates all May transcripts and carries the "degree of separation" simulation framing — it was not crowd-sourced in a meeting but arrived pre-formed.

- **The simulation metaphor — central to the project page — came entirely from Sadra**, not Sumit. This is a surprising attribution given that Sumit's name appears on most other framing decisions.

- **Tiago Forte and Andrej Karpathy shaped the project significantly but are not in the record.** Forte's Intermediate Packets anticipated the efficiency contribution; Karpathy's X post established the LLM-wiki pattern the project extends. Their influence is real but mediated entirely through Sumit and Sadra reading and citing them.

- **The May 6 slop-recovery moment was Souti's only interventional move in a session she was otherwise a listener in** — and it had immediate, high-emotional-valence impact on Sumit. The contribution of "point to existing wiki content rather than generate new" was demonstrated live, not just argued.
