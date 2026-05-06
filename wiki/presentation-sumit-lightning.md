---
tags: [view, presentation]
target: views, skills, workflows, semi-private-mashing, llm-wiki-landscape, workiq, kb-as-codebase, living-system
audience: distinguished AI practitioners and AI leaders at Microsoft
duration: 10min
generated: 2026-05-06
---

# Microsoft Lightning Talk — for distinguished AI practitioners and AI leaders at Microsoft

## Motivating Story

[[sumit-gulwani|Sumit Gulwani]] spent three full days trying to auto-generate his annual performance review — the "connect" exercise everyone in this room knows. He fed an agent every relevant artifact: connects of all direct reports, 1:1 transcripts, email Q&A threads, past reviews, blog posts, paper lists, and hand-written guidance paragraphs. The output was slop. The missing piece wasn't context, compute, or model quality — it was infrastructure to encode *how* to synthesize, not just *what* to retrieve — what we now call a [[skills|skill]]. *Sumit Gulwani — [[Sadra-5May2026-TRANSCRIPT]]*

By contrast, **this very deck** was generated from a [[views|view]] over the [[wiki-kb-project|project's own wiki]] — same family of tooling, but with the missing piece in place. *[[presentation-grounded-examples]]*

> speaker note: Lead with this — the connect is non-IP information that makes the failure mode visible without leaking anything. Everyone here has done one; everyone has wished it auto-completed. Then point at the slide and say "this deck is what success looks like."

## Core Concepts

- **[[views|View]]** — a template with holes.
- **Hole** — a prompt evaluated over the [[wiki-kb-project|knowledge base]]; defines *what* to put there.
- **[[skills|Skill]]** — the methodology that fills the hole; defines *how* to compute it. Without a skill, the agent picks its own approach.
- **[[workflows|Workflow]]** — the data dependency graph between sources, prompts, and views; tells the system *when* to rerun what.

These slides demonstrate the structure: each `## Section` you're reading is a **hole** in a **view** template, filled by a **prompt** in [[templates/sumit-lightning|the source template]], optionally guided by a **skill** — and the **workflow** is what causes this deck to update when a new transcript lands in the wiki.

> speaker note: Hold up four fingers. View, hole, skill, workflow — what / what / how / when. Then point at the slide: *you are reading the output of all four right now*.

## The Metaphor

The KB is **Excel for subjective content**. Excel's recalc engine made it possible to express objective dependencies once and have them update forever; the KB extends that primitive to subjective and aesthetic computation. *[[living-system]]*

Mapping:
- **[[views|View]]** = a formula cell — a saved computation, not a stored value
- **Hole / prompt** = a cell reference inside the formula
- **[[skills|Skill]]** = the function called (SUM, VLOOKUP, or a domain-specific procedure) — the methodology
- **[[workflows|Workflow]]** = the recalc graph — which cells update when inputs change

Concretely: **this deck is itself a recalc cell**. Every transcript ingested between now and the next regeneration shifts what these slides say — the same way changing `A1` shifts `C1`. *[[views|Document as View]]*

> speaker note: Sumit named this directly: "the recalc feature was never applied to an entire document because it is subjective… now we have the power to process this." The Excel "Equals Copilot" feature is the proof of concept already shipping — and this deck is another. *[[living-system]]*

## Views × Needs (Live Map)

| Pain point | View type + example |
|--|--|
| "Teams already summarizes meetings, but I want my own template per topic across meetings — e.g., contradictions between two people." | **Query view** — extends the Teams auto-summary into a user-definable proto-view. *[[presentation-grounded-examples]]* |
| "Same agent computation, three audiences: a debugger, a reviewer, an executive — one rendering doesn't fit all." | **Contribution-map view** — [[agent-traceability-steerability|Pista]] renders one spreadsheet computation as step-by-step reveal, contribution summary, and overview. *[[presentation-grounded-examples]]* |
| "Tons of rework — two teams independently solving the same problem with no signal." | **Org-brain view** — surfaces solved problems before a second team begins; requires individuals to contribute selectively via [[semi-private-mashing|semi-private mashing]]. *[[presentation-grounded-examples]]* |
| "I need to give a 10-min talk on a topic that's evolving daily — and re-write it every time the wiki updates." | **Presentation view** — *this deck*, generated from [[templates/sumit-lightning|sumit-lightning.md]] over the wiki; regenerable on demand. |

> speaker note: One sentence each. The fourth row is the room you're in — say it explicitly: "the talk you're hearing is row four." The contradiction query and the rework example are the strongest for the rest of the room.

## This Generalizes Across Domains

**Software developers** *([[llm-wiki-landscape]])*
- Problem: cold-start tax — re-supplying who/what/how on every coding agent interaction
- View: a `.brain` folder with index, architecture, decisions, changelog
- Replaces: per-session prompt scaffolding

**Researchers** *([[llm-wiki-landscape]])*
- Problem: insights generated continuously across papers, conferences, and conversations evaporate before they connect
- View: OmegaWiki — typed knowledge graph driving idea generation, experiment design, paper drafts
- Replaces: scattered Obsidian notes and dead Zotero libraries

**Teams** *([[llm-wiki-landscape]])*
- Problem: institutional memory buried in Slack/Teams history, lost in onboarding
- View: Beever Atlas — chat-to-typed-graph with citations and MCP server
- Replaces: search-the-channel and ask-someone-who-was-here

> speaker note: Three slides compressed to one. The Karpathy gist's 700 comments cluster into exactly these three audiences — convergent demand, not coincidence.

## Where This Fits in the Landscape

- **[[second-brain-code-method|Second Brain (Forte)]]** — named the workflow (Capture / Organize / Distill / Express); the manual distill step bottlenecked adoption.
- **Karpathy wiki pattern** — automated entity extraction in one prompt; left [[semi-private-mashing|semi-private filtering]] and user-definable [[views|views]] unsolved. *[[llm-wiki-landscape]]*
- **[[context-base|Contextbases (Applied Compute)]] / [[workiq|Work IQ]]** — Remember→Refine→Retrieve at org scale; productized for agents; left the *human-facing* knowledge layer and personal-to-org contribution unsolved.
- **This project** — adds the human knowledge layer ([[views|views]] as first-class), [[semi-private-mashing|semi-private mashing]] with a PR model for personal→org flow ([[local-first-kb|Local-First KB]] / [[kb-as-codebase|KB as Codebase]]), and temporal integrity through [[purge-operation|purge/supersede]]. *[[wiki-kb-project]]* — and **this slide is the demo**: assembled by a [[views|view]] running over the project's own wiki.

> speaker note: Each step solved the previous one's bottleneck. Work IQ is where you sit today; the knowledge layer is what's missing above it — and what built this deck.

## What to Build Next

1. **Percolation strategy for live recalc** — when a raw source updates, which views must rerun, in what order, at what cost? Today's wiki recomputes blindly. *Why it matters:* the [[living-system]] promise depends on this being efficient at scale. *First step:* instrument the existing DAG, measure recompute cost on a 1000-source corpus, design selective propagation. *[[living-system]]*

2. **Semi-private mashing enforcement** — how do you *guarantee* (not merely hope) that private content stays out of the shared layer when an agent is the filter? *Why it matters:* the [[Sadra-5May2026-TRANSCRIPT2|unpublished-work incident]] is the failure mode every enterprise deployment will hit. *First step:* design a declarative privacy policy language + audit log; pilot on 1:1 transcripts with synthetic violations. *[[semi-private-mashing]]*

3. **AI-reviewed PRs for the org KB** — when a personal KB contributes upstream, what reviews the PR for contradictions, leakage, and provenance? *Why it matters:* without this, the [[kb-as-codebase|KB-as-codebase]] PR model collapses to "human review at scale." *First step:* prototype a reviewer agent on three contribution types (concept addition, claim revision, source supersede); measure precision/recall on injected violations. *[[local-first-kb]]*

Each answer to these questions improves *this very deck* on the next regeneration: percolation makes it cheaper, enforcement lets it cite private 1:1s safely, AI-reviewed PRs let collaborators contribute knowledge that propagates here automatically.

> speaker note: Pick one and partner with us. Each is a 6-month project that changes the architecture, not just the implementation. And every answer reshapes the deck you're watching.

---

**Presenter brief:** Open with Sumit's connect — non-IP, universally relatable, makes the cost of missing infrastructure visceral. The metaphor slide is the load-bearing one for this audience: Excel-for-subjective-content makes the entire architecture intuitive in 30 seconds. If short on time, cut "This Generalizes" — it's intellectual reinforcement, not new information. The most likely pushback: "isn't this just RAG with extra steps?" — answer with the [[context-base|compression-as-declarative-vs-opaque]] reframe and the 16.9% APEX-Agents result.
