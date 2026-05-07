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

Sadra surveyed ~700 comments on Karpathy's GitHub gist in [[T15-2026-05-06|May 6]] and expanded the taxonomy in [[LLM-Wiki Related Works]]. Three distinct user segments have emerged, each solving a different problem:

### For Software Developers

The core pain is the **cold-start problem**: on every new coding agent interaction, the developer must re-supply context about who they are, what projects they're working on, how projects relate, and what design decisions were made. A structural persistent memory eliminates this tax. [[LLM-Wiki Related Works]]

Notable projects:
| Project | What it does |
|---------|-------------|
| `.brain` folder (@samflipppy) | Local project-root markdown layout: `index.md`, architecture, decisions, changelog, deployment notes, schemas, pipeline notes |
| [Claude-persistent-memory](https://github.com/pjmattingly/Claude-persistent-memory) | Persistent memory backed by NotebookLM as the wiki layer |
| [hyalo](https://github.com/ractive/hyalo) | CLI for agents to search markdown KBs, inspect frontmatter, move files, repair links |
| [Freelance](https://github.com/duct-tape-and-markdown/freelance) | Provenance-first: propositions track source file hashes and stale status — connects to [[provenance-tracking]] |
| [Lore](https://github.com/cianmarbo/Lore) | Generates/updates documentation from Claude Code conversations; positioned for team infrastructure |

### For Researchers

Researchers generate insights continuously — during paper reading, conferences, coffee-break conversations — and need a system that accumulates these and surfaces connections across them over time. [[LLM-Wiki Related Works]]

Notable projects:
| Project | What it does |
|---------|-------------|
| [Exocortex write-up](https://jayswamimusic.substack.com/p/i-built-an-exocortex-i-didnt-know) (@jayswami) | Indexes sources + session transcripts, corrections, reasoning threads; convergence criterion: "the system begins reflecting the author's voice" |
| [Memex](https://github.com/memex-lab/memex) | Mobile app that auto-organizes daily recordings into a PARA markdown wiki and life-pattern cards |
| [IDEA.md](https://github.com/pithpusher/IDEA.md) | Vendor-neutral idea specification format: thesis / problem / how-it-works / limits / where-to-start |
| [paper-spec](https://github.com/spectralbranding/paper-spec) | Research programs as git repos; adds `.wiki/` for PDFs, datasets, emails, review exchanges, concepts, authors, methods — connects to [[kb-as-codebase]] |
| [llm-research-wiki](https://github.com/MetamusicX/llm-research-wiki) | Academic template (music/philosophy) with concepts, authors, debates, syntheses, ingest/query/lint, Claude schema |
| [OmegaWiki](https://github.com/skyllwt/OmegaWiki) | Full research lifecycle: ingest papers → typed knowledge graph → idea generation → experiment design → paper draft → reviewer response. Most ambitious in this category. |
| [RIS/SPATE](https://zenodo.org/records/19914452) | Research Intelligence System with Prompt IDs, provenance registry, and self-constructing taxonomy |

OmegaWiki is the closest to the [[wiki-kb-project|Wiki KB Project]]'s long-term vision for researchers: not just storage and retrieval but an active participant in the research workflow from idea to publication.

### For Teams

Team-oriented deployments focus on shared memory across multiple contributors: onboarding, product decisions, meeting history, multi-user agent workflows. [[LLM-Wiki Related Works]]

| Project | What it does |
|---------|-------------|
| [Peeps Skill](https://github.com/Know-Your-People/peeps-skill) | People and organization intelligence |
| [Waykee Cortex](https://waykee.com/) | Hierarchical knowledge + work tracking; context inheritance across systems/modules/screens and tasks/bugs/milestones |
| [agent-wiki](https://github.com/junbjnnn/llm-wiki/) | Team wiki inside a project repo; ingests PRDs, meeting notes, API specs, postmortems into summaries, ADRs, runbooks, entity pages |
| [Beever Atlas](https://github.com/Beever-AI/beever-atlas) | Team-chat-to-wiki for Slack/Discord/Teams corpora; typed graph + semantic store + citations + MCP server |

**Beever Atlas** is architecturally closest to the [[wiki-kb-project|Wiki KB Project]] at team scale: it produces a typed graph with citations from conversational corpora and exposes it via an MCP server — exactly the structured knowledge layer + tool-access pattern this project targets. The gap: no [[semi-private-mashing|semi-private mashing]], no [[views|views]] as first-class constructs.

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

The Karpathy GitHub gist — the origin post for the LLM-wiki pattern — has accumulated ~700 public comments from practitioners. Sadra mined these in [[T15-2026-05-06|May 6]], categorizing related implementations into three groups:

1. **Software engineering** — teams applying the wiki pattern to code-adjacent knowledge work (architecture decisions, incident postmortems, design docs)
2. **Researchers and ideators** — individual practitioners building personal research KBs from papers, notes, and transcripts
3. **Teams** — organizational-scale deployments where multiple people ingest into a shared graph

This is the most direct empirical survey of where the ecosystem has gone from Karpathy's original prompt. The three-category split maps loosely onto the [[wiki-kb-project|Wiki KB Project]]'s three target audiences: personal KB (researchers), team KB (teams), and the broader org brain (organizational-scale).

## Wiki vs. RAG: Compression as the Central Concern

Sadra's interpretability argument — that wiki edges are typed and traversable while RAG similarity scores are opaque — received a refinement from Sumit in [[T15-2026-05-06|May 6]]: **data compression** is the more fundamental concern in RAG, not interpretability. A RAG index is a compressed representation of a corpus; the quality question is whether the compression preserves the semantics needed for downstream tasks.

The synthesis: the wiki's advantage is that its compression model (entity extraction + typed relations) is *declarative* — inspectable, correctable, extensible. An embedding is not directly editable. The interpretability argument and the compression argument are the same point at different levels of abstraction.

## Applied Compute Context Engine: Empirical Validation of the Architecture

The [[Remember, Refine, Retrieve A Context Engine for Enterprise Agents|Applied Compute Context Engine]] (published 2026-05-01) is the most rigorous external validation of the Remember→Refine→Retrieve architecture. Key results:

- **16.9% relative improvement** on APEX-Agents (long-horizon investment banking, consulting, law tasks) vs. no-context baseline
- **Reasoning-effort amortization**: a model with Contextbase at *low* reasoning matches the same model *without* Contextbase at *medium* reasoning. Context shifts the cost-quality Pareto frontier rather than trading within it.

The paper also provides the cleanest diagnosis of why knowledge work context is hard: unlike code (centralized in VCS, ships with a complete dependency tree, forces merge conflict resolution), knowledge work is scattered, implicit, and divergent. The Context Engine's Refinery swarm — lightweight taggers plus powerful synthesis agents — is designed to close all three gaps.

See [[context-base]] for the full architecture and empirical breakdown.

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
