---
tags: [concept]
---

# Fabric IQ

Microsoft's **structured-data intelligence layer** built on Microsoft Fabric and OneLake. Transforms raw enterprise data into an **ontology** — a knowledge graph of entities and typed relationships — so AI agents can reason over business semantics rather than raw tables. Part of the [[microsoft-iq-stack|Microsoft IQ Stack]]; complements [[foundry-iq|Foundry IQ]] (unstructured knowledge) and [[workiq|Work IQ]] (collaboration signals).

Sadra's analysis in [[Microsoft Infrastructure for Organizational Brain]]; practitioner patterns from [[FabricIQ How are you using AI capabilities to bring value to the business?]].

## What It Is

Fabric IQ models business data with an **ontology** — an explicit graph of:
- **Entities**: business objects that already exist (products, suppliers, employees, contracts)
- **Relations**: typed edges between entities (e.g., "supplier → delivers → product"; edge types are predefined, not free-form)
- **Semantic models and KPIs**: business metrics layered over the raw data, giving numbers business meaning

The connected components of this ontology are called **Lakes**. Multiple Lakes can coexist and be queried independently or jointly.

AI agents query the ontology via APIs and MCP connectors — they interact with a semantically enriched graph, not raw SQL. Agents can answer complex analytical questions by traversing entity relations rather than executing ad hoc joins.

## Operational Agents (Published Chats)

Fabric IQ lets users publish a successful chat session with a data agent as an **operational agent** — a reusable prompt/workflow that others can invoke without reconstructing the query. This is structurally similar to the [[skills|Skills]] concept: it encodes HOW to extract a particular insight from the ontology and makes that methodology reusable.

The difference from wiki skills: Fabric IQ operational agents operate over a fixed, typed ontology of structured business data. Wiki skills encode creative reasoning methodology over free-form knowledge. Same reusability pattern, different substrate.

## Practitioner Patterns

From the r/MicrosoftFabric community ([[FabricIQ How are you using AI capabilities to bring value to the business?]]):

**Narrow scope is critical.** "Things get hairy when you try to reach across many different topics." Practitioners build focused data agents per domain, then orchestrate them with Copilot Studio. A single generalist agent degrades in accuracy; specialized agents orchestrated via multi-agent routing performs better.

**Semantic RAG over generic RAG.** Domain-specific retrieval (an agent "trained" on a specific data structure) outperforms generic ChatGPT-style retrieval for structured data questions. The recommended pattern: separate quantitative and qualitative agents, combine in a multi-agent router.

**BI reports and agents are complementary.** Agents augment dashboards with natural-language follow-up; they don't replace custom reports. "I still build custom dashboards that no current agent can spin up. Agents can help with follow-up questions, deeper exploration." BI remains the visual anchor; agents handle conversational drill-down.

**Cost is a real friction.** Data agents are "very resource-hungry" for development and testing. Practitioners recommend a separate dev/test capacity allocation. Enterprise adoption friction exists beyond the technical architecture.

## Contrast with the Wiki Project

Fabric IQ's ontology and the wiki's concept graph are structurally analogous but semantically different:

| Dimension | Fabric IQ | Wiki KB Project |
|---|---|---|
| Data substrate | Structured business data (tables, KPIs, metrics) | Meeting transcripts, emails, design docs, notes |
| Graph nodes | Business entities (products, suppliers, employees) | Concepts, people, projects, events |
| Edge types | Predefined, typed business relations | Wikilinks (free-form, author-defined) |
| Update mechanism | Scheduled indexer runs, incremental data refresh | Human-triggered ingest via [[ingest]] skill |
| Who contributes | Data engineers publishing semantic models | Individuals contributing semi-private knowledge via [[semi-private-mashing]] |

The ontology-as-graph idea is worth stealing back: Fabric IQ's explicit typing of relationships ("delivers", "reports-to") is more precise than the wiki's undifferentiated wikilinks. Adding typed edges to the knowledge graph is a potential future direction for the [[wiki-kb-project]].
