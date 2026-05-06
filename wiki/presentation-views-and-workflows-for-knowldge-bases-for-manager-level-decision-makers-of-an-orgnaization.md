---
tags: [view, presentation]
target: views, workflows
audience: manager-level decision makers
generated: 2026-05-05
---

# Presentation: "Views and Workflows for Knowledge Bases" for Manager-Level Decision Makers

## Why your knowledge workers spend more time reconstructing context than creating it

- Every meeting, email, and 1:1 contains decisions and reasoning that exist only inside one person's head five minutes later
- New joiners take months to reach productive context; existing staff re-litigate decisions they've already made
- Notion / Confluence / SharePoint store documents — they don't synthesize across them
- The bottleneck on knowledge work isn't writing; it's **reuse**

> speaker note: Open with a relatable scenario — "How many times this month did someone in your org ask a question whose answer was already in a transcript or email no one re-read?" Cite the [[simulation-metaphor]] framing without naming it: world progress = individual processing + communication; both are slow today. The point is to make managers feel the cost before introducing the solution.

## What a "view" is, in one sentence: a saved question over your team's collective knowledge

- A **view** is a prompt + a target ("Show me every concern raised about Project X") that runs over the whole knowledge base and produces an always-current answer
- Views are user-definable — managers, not engineers, can author the questions that matter to them
- Views are **hierarchical** and **composable** — a "design doc" view can compose with a "topic summary" view
- Concrete examples already in our system: [[contribution-map-views|who introduced which idea, when]], [[timeline-views|how a concept evolved across meetings]], "what does each person think about X?"

> speaker note: This is the slide where you make views feel inevitable. Use a manager-relevant example, not a technical one — "What's our team's position on remote work?" or "What concerns has Legal raised about the new vendor?" Reference [[views]] and the [[Sadra-1May2026-Transcript|May 1 sync]] where Sumit identified views as the unifying abstraction. Keep it under 60 seconds — this is the easy slide.

## Why one prompt doesn't fit all: workflows are where your domain expertise lives

- A **view** says WHAT to compute. A **workflow** says HOW to compute it
- The same view ("summarize this user research") produces materially different output depending on the workflow: grounded theory analysis vs. multi-pass summarization vs. per-section chunking
- Workflows are **creative artifacts** — choosing the right method for the right input is where your team's tacit expertise gets encoded
- Without explicit workflows, the AI picks one for you. Your senior people's methodology stays in their heads instead of in the system

> speaker note: This is the slide that earns the "views *and* workflows" framing in the title. Managers often think "we'll just use ChatGPT on our docs" — workflows are why that doesn't work for serious knowledge work. Cite [[workflows]] and the grounded theory example from [[Sadra-1May2026-Transcript]]. The implication: investing in good workflows is the same kind of investment as writing a runbook — durable institutional value.

## How this differs from Notion, RAG, and "ChatGPT on your docs"

- **Notion / Confluence**: static pages, no synthesis. You still have to read everything to answer a question
- **RAG (e.g. ChatGPT-on-your-docs)**: retrieves text chunks at query time; can't reason across them; opaque about which sources actually drove an answer; rediscovers knowledge from scratch on every query
- **This system**: pre-organizes raw sources into a structured **knowledge layer**; views run on the knowledge layer, not raw text — **75–99% lower token cost at scale** ([[llm-wiki-landscape]])
- Every claim in every output is **traceable to a source** — auditable, unlike RAG

> speaker note: Most managers' mental model of AI-on-docs is RAG. This is the slide that breaks that frame. The 75–99% number is real and from a published mind-DB benchmark cited in [[LLM-Wiki Related Works]] — but flag that it's a third-party number, not ours. The auditability point is the one that resonates with risk-averse decision makers.

## The org-scale unlock: keep 1:1s private, share what matters

- Most KB tools force a binary: include the whole 1:1 transcript in the shared KB or include nothing
- This system filters automatically — extracts only the parts of a private exchange that are relevant to a shared topic, leaves everything else private
- Privacy is enforced **before** content enters the shared layer — the raw private source never touches the team KB
- This is the differentiator vs. existing personal-KB tools (e.g. the Karpathy pattern, [[second-brain-code-method|Building a Second Brain]]); those tools assume all input is shareable. Org work doesn't

> speaker note: This is the slide that makes the system specifically organizational. The concept name is [[semi-private-mashing|semi-private mashing]] but don't say that — say "intelligent privacy filtering." Be honest with your audience: this is currently a research direction, not a shipped feature. See Open Questions slide for the gap. Reference [[Thursday demo]] where this was first articulated and [[Sadra-1May2026-Transcript|the May 1 sync]] where Souti raised privacy concerns.

## What changes for your team day-to-day: embedded, live, additive

- **Embedded views**: prompt-powered fields inside Word, PowerPoint, Excel — not a new tool to learn ([[embedded-views]])
- **Living documents**: when a new transcript arrives, every document that depends on it auto-updates ([[living-system]] — like Excel formulas, not values)
- **Additive, not migrative**: nothing has to be moved out of your existing tools; sources plug in as they're created
- The long-term direction: **digital twins** — a model of how each team member thinks. Onboarding from months to days, asynchronous collaboration at the quality of synchronous ([[digital-twins]])

> speaker note: This is the adoption slide. Manager-level audiences will be thinking "do I have to migrate everything?" — answer is no. The Excel formula analogy from [[Sadra-4May2026-TRANSCRIPT3|the May 4 sync]] lands well: cells with values vs. cells with formulas. Digital twins is the aspirational vision — present it as direction-of-travel, not a quarterly deliverable.

## Open Questions

- **Privacy guarantees** — semi-private mashing is presented as a core capability, but the design and enforcement mechanism are not yet specified ([[semi-private-mashing]], [[Sadra-1May2026-Transcript]]). Before deployment in any sensitive context, this needs concrete design and audit.
- **Performance vs. RAG** — the efficiency and quality claims are anecdotal. The system has not been rigorously benchmarked against RAG on representative org tasks ([[llm-wiki-landscape]]). Pilots should include head-to-head comparison.
- **Maintenance at scale** — the knowledge graph gets harder to maintain as it grows. Strategies for percolation, deprecation, and contradiction resolution are partially designed but not battle-tested at thousands of meetings ([[temporal-knowledge]], [[purge-operation]]). A dedicated curator role may be needed at scale.

---

**Presenter brief:** Lead with the cost-of-knowledge-work hook (slide 1) — that's what gets manager attention; the rest of the deck is justifying the spend. Slides 2 and 3 are the substantive core; do not skip them even if short on time. Slide 4 (vs. RAG) is the most important slide for technically-curious managers; if you sense the room is skeptical, expand here. Slide 5 (semi-private mashing) is the differentiator for org buyers but is currently an oversold claim — present it as a design direction, not a feature, and own that openly when challenged. Slide 6 (embedded views, digital twins) is the "what does my team experience" slide — keep it concrete. The most likely audience question: **"Do my people have to learn a new tool?"** — answer is no, embedded views means it lives inside Word/PPT/Excel; the second most likely question: **"Is our IP safe?"** — answer honestly: the privacy-filtering mechanism is a research direction, and any deployment should start in a low-sensitivity context.
