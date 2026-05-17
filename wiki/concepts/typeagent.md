---
tags: [concept]
---

# TypeAgent

Microsoft Research's open-source exploration of a **single personal agent** architecture with natural language interfaces. Source: [[TypeAgent]] and [[TypeAgent - KnowPro]]. Status: experimental sample code, not a framework; tested on developer machines with Azure OpenAI services only.

## Three Principles

The TypeAgent team articulated three principles that govern how stochastic LLMs and deterministic software can be safely combined:

1. **Distill models into logical structures** — Rather than calling an LLM for every operation, identify patterns and replace model calls with learned logical rules. For memory, this means building ontologies from text (Structured RAG entity extraction). For actions, it means caching successful action translations via TypeAgent Cache.

2. **Use structure to control information density** — Discrete, typed schemas fit more useful content into a fixed attention window. Applications define action sets via dense typed schemas (TypeChat); memory uses tight semantic structures (topic sentences + entity trees) rather than diluted vector embeddings.

3. **Use structure to enable collaboration** — Structured outputs allow humans, programs, and models to collaborate at defined interfaces. Humans decide how to disambiguate action requests; models extract structure; programs execute.

## AMP Architecture: Actions + Memory + Plans

The central research thesis is that **Actions, Memory, and Plans** are not independent agent components — they flow together:

> "Actions like 'add to my calendar pickle ball game 2-3pm on Friday' yield memories that can become parameters of future actions like 'put in an hour of recovery time after my pickle ball game.'"

AMP is being applied to the web through a browser that lets websites register actions via a JavaScript interface — the same single personal agent can then act across applications that have declared their action contracts.

## Key Components

**TypeAgent Dispatcher** — Routes user natural-language requests to agents whose typed contract best matches intent. The central nervous system of the personal agent. Uses structured prompting + LLM to perform action dispatch.

**[[structured-rag|KnowPro / Structured RAG]]** — Implements agent memory using Structured RAG: inverted-index-based conversation indexing with entity/topic extraction, scope expressions, and tree-pattern query. Designed to retain all conversation history with super-human precision and recall.

**TypeAgent Cache** — Distills LLM-to-action translation into logical pattern rules. Once a successful translation is cached, future similar requests bypass the LLM entirely — reducing both cost and latency.

**TypeAgent Shell** — An Electron app integrating the above components: conversational interface with voice, multi-agent dispatch, Structured RAG memory, and TypeAgent Cache.

## Relation to the Microsoft IQ Stack

TypeAgent is a research prototype, not a shipping product, and sits outside the [[microsoft-iq-stack|Microsoft IQ Stack]] (Work IQ / Fabric IQ / Foundry IQ). But it represents the research direction Microsoft is exploring *beyond* the IQ stack for personal and conversational memory:

- The IQ stack handles enterprise unstructured content retrieval ([[foundry-iq|Foundry IQ]]) at the organization level.
- TypeAgent targets personal agent memory at the individual level, over conversation-sized data (transcripts, email threads).
- [[structured-rag|Structured RAG]] is explicitly positioned as closing the gap between document retrieval (Azure AI Search / Foundry IQ) and conversation understanding.

## Contrast with the Wiki KB Project

Both TypeAgent and the [[wiki-kb-project|Wiki KB Project]] aim to make conversation history queryable. The key differences:

- TypeAgent's memory is **automated and passive** — index everything via LLM extraction, let users query. The wiki requires **active human synthesis** — ingest, clarify, trim, and curate.
- TypeAgent answers **recall questions** ("what books did we discuss?"). The wiki answers **insight questions** ("how has our framing of this concept evolved?").
- TypeAgent has no equivalent to [[semi-private-mashing|semi-private mashing]] — it does not address how personal conversations contribute to shared organizational knowledge.
- TypeAgent's [[structured-rag|Structured RAG]] is a strong complement to the wiki pattern: it could serve as the raw-data retrieval layer underneath the wiki, while the wiki provides the structured-synthesis layer above it.

The two structural gaps from [[Microsoft Infrastructure for Organizational Brain]] — transcript synthesis into named concepts, and personal→org reverse contribution — remain open in TypeAgent. TypeAgent indexes what was said; it does not synthesize named ideas that evolve across people and meetings.
