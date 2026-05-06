---
tags: [concept]
---

# LLM-Wiki Landscape

The broader ecosystem of projects that use LLMs to convert raw notes into connected, queryable wikis. Surveyed by [[sadra-sabouri|Sadra]] in [[LLM-Wiki Related Works]].

## Historical Roots: The Second Brain Vision

Before LLMs, Tiago Forte's [[second-brain-code-method|Building a Second Brain]] (BASB) methodology laid out the same workflow that LLM wiki tools now automate: **Capture → Organize → Distill → Express** (the CODE method). The core insight — that human brains are for having ideas, not storing them, and that an external digital repository should handle the storage — predates the Karpathy pattern by years.

LLM wikis are best understood as LLM-native implementations of the CODE vision: they automate the organizing and distilling steps that were previously manual and therefore bottlenecked adoption. The Karpathy X post was the triggering demo that made this automation feel tractable, not the origin of the underlying idea.

## Origin: Karpathy's Pattern

The pattern originates from Andrej Karpathy's X post, which shared a prompt for converting fleeting notes into entity-based wikis: extract entities, connect them by relations, form a navigable graph. This one-prompt demonstration seeded an ecosystem of downstream applications.

## Applications in the Wild

The pattern has been picked up across domains:

- **Finance** — using Claude + Obsidian to build a personal investment KB from raw research
- **Manager summaries** — "Garry's Opinionated OpenClawHermes Agent Brain" applies the wiki pattern to management notes
- **Personal vibe sessions** — Lore, a living KB powered by Claude Code sessions, applies it to informal personal tracking

The commonality: unstructured input → LLM-extracted entities + relations → browsable, queryable graph.

## A Documented RAG-Based Alternative: matvellosoknowledge

[[matvellosoknowledge]] (Eduardo Mello, open source) is the most fully documented local-first personal KB in the ecosystem. It connects Gmail and Outlook, runs inference locally via Ollama, and builds To Do, shopping, and reading lists alongside a knowledge graph — all without cloud API calls. Its **MY PREFERENCES.md** file lets users declare domain-specific extraction rules in plain markdown, functioning as a [[skills|skills]] analogue.

Retrieval is embeddings + cosine similarity (standard RAG). Sadra's critique in [[Personal Private Knowledge Management]]: "this makes the dependency uninterpretable compared to a graph structure." The project validates the market and privacy-first design direction while illustrating the architectural ceiling of RAG — the system can surface relevant chunks but cannot traverse typed relations or provide interpretable provenance chains. See [[local-first-kb|Local-First KB]] for the full comparison.

## Wiki vs. RAG

A structurally important distinction, documented in [[LLM-Wiki Related Works]]: wiki-based memory outperforms RAG for grounded agent tasks.

- One productized RAG-to-wiki system (llm-wiki-studio) demonstrates the shift from search-based retrieval to structured graph traversal
- An agentic memory database (mindb) reports **75–99% token reduction** vs. unstructured context, by storing knowledge in a portable SQLite file rather than embedding and retrieving raw chunks

The mechanism: a wiki's structured graph lets an agent traverse only the relevant subgraph, rather than embedding-searching over everything. This aligns with the [[wiki-kb-project|Wiki KB Project]]'s third contribution (efficiency via intermediate summaries) — the structure itself reduces compute, not just clever retrieval.

## Known Critics and Limitations

All three critiques come from Anatoly Krasnovsky's public commentary on the llm-wiki approach, cited in [[LLM-Wiki Related Works]]:

1. **Lossiness** — conversion from raw source to wiki format is not lossless. Information is compressed, paraphrased, or dropped. This is not the ultimate archival solution.
2. **No RAG benchmark** — wiki-based systems have not been rigorously benchmarked against RAG. The efficiency and quality claims are anecdotal, not experimentally established.
3. **Scaling** — as the graph grows, maintaining it becomes non-trivial. Edge consistency, orphan detection, and contradiction resolution all get harder at scale.

## Karpathy Gist Comment Mining

The Karpathy GitHub gist — the origin post for the LLM-wiki pattern — has accumulated ~700 public comments from practitioners. Sadra mined these in [[Sadra-6May2026-Notes|May 6]], categorizing related implementations into three groups:

1. **Software engineering** — teams applying the wiki pattern to code-adjacent knowledge work (architecture decisions, incident postmortems, design docs)
2. **Researchers and ideators** — individual practitioners building personal research KBs from papers, notes, and transcripts
3. **Teams** — organizational-scale deployments where multiple people ingest into a shared graph

This is the most direct empirical survey of where the ecosystem has gone from Karpathy's original prompt. The three-category split maps loosely onto the [[wiki-kb-project|Wiki KB Project]]'s three target audiences: personal KB (researchers), team KB (teams), and the broader org brain (organizational-scale).

## Wiki vs. RAG: Compression as the Central Concern

Sadra's interpretability argument — that wiki edges are typed and traversable while RAG similarity scores are opaque — received a refinement from Sumit in [[Sadra-6May2026-Notes|May 6]]: **data compression** is the more fundamental concern in RAG, not interpretability. A RAG index is a compressed representation of a corpus; the quality question is whether the compression preserves the semantics needed for downstream tasks.

The synthesis: the wiki's advantage is that its compression model (entity extraction + typed relations) is *declarative* — inspectable, correctable, extensible. An embedding is not directly editable. The interpretability argument and the compression argument are the same point at different levels of abstraction.

## Work IQ: The Microsoft Org-Scale Incumbent

[[workiq|Work IQ]] is the Microsoft product most adjacent to this project. It provides a three-layer architecture (Data, Context, Skills/Tools) grounding Microsoft 365 Copilot in enterprise data — essentially the [[context-base|applied compute context base]] productized at org scale. Its semantic index (lexical + semantic retrieval over all M365 data) is the state of the art for RAG-based organizational knowledge access.

The gap, per Sadra in [[Microsoft Tool For Idea Automation]]: Work IQ "stays in the surface level and does not connect with the organization's experience." It retrieves from documents but does not build a structured knowledge layer — no concept pages, no typed relations, no synthesis across sources. And it has no semi-private contribution model: individuals cannot selectively push personal knowledge to a shared layer while filtering private content.

Work IQ defines the floor the Wiki KB Project builds above: the context base exists; the knowledge layer and semi-private mashing are what's missing.

## How the Wiki KB Project Differentiates

The Karpathy pattern produces a generic entity graph. The [[wiki-kb-project|Wiki KB Project]] goes further on three axes:

- **[[views|Views]]** — the graph is not just browsable but queryable through user-defined declarative specs; different views render the same raw data differently for different purposes
- **[[semi-private-mashing|Semi-private mashing]]** — the project explicitly handles the case where source material is partly private; the Karpathy pattern assumes all input is freely shareable
- **[[temporal-knowledge|Temporal integrity]]** — newer sources supersede older ones; the [[purge-operation|purge]] operation maintains this; static entity graphs don't have a temporal model

The lossiness critique applies to any wiki approach. The scaling critique is an open problem for this project too — see [[open-questions-all]] for the unresolved percolation design question.
