---
tags: [concept]
---

# Foundry IQ

Microsoft's **managed knowledge layer** for enterprise data. Turns scattered unstructured content — documents, policies, manuals, FAQs, contracts, wikis — into permission-aware, multi-source knowledge bases that AI agents can query with cited, grounded answers. Part of the [[microsoft-iq-stack|Microsoft IQ Stack]]; sits between [[fabric-iq|Fabric IQ]] (structured data) and [[workiq|Work IQ]] (collaboration context). Official documentation: [[What is Foundry IQ?]].

## What It Does

Foundry IQ solves the enterprise knowledge retrieval problem: LLMs have knowledge cutoffs and cannot access proprietary org data on their own. Foundry IQ provides a configurable **knowledge base** — a collection of knowledge sources (SharePoint, OneLake, Azure Blob Storage, public web) plus retrieval parameters — that multiple agents can share.

### Agentic Retrieval

The distinctive technical capability: when an agent queries a Foundry IQ knowledge base, it does not issue a single vector search. Instead, **agentic retrieval** runs a multi-step pipeline:

1. **Query decomposition** — an LLM decomposes the complex question into targeted subqueries
2. **Parallel execution** — subqueries run across all knowledge sources simultaneously (keyword, vector, or hybrid)
3. **Semantic reranking** — results are unified and reranked across sources
4. **Grounded response** — a unified answer is returned with citations tracing each claim to a source document

This is architecturally close to what the [[wiki-kb-project]] does when it synthesizes across wiki pages to answer a query — but Foundry IQ operates over raw document chunks, not over a structured knowledge layer.

### Permission Enforcement

A first-class capability: Foundry IQ synchronizes access control lists (ACLs) from supported sources and honors Microsoft Purview sensitivity labels. Queries run under the caller's Microsoft Entra identity, so agents return only content the user is authorized to see. This is permission enforcement at retrieval time — not post-filtering.

This is a partial solution to the [[semi-private-mashing|Semi-Private Mashing]] problem: Foundry IQ respects existing permissions, but it cannot selectively filter private content that lives outside existing ACLs (e.g., personal notes or 1:1 transcripts that the author wants to partially share). The semi-private mashing problem is about *author-controlled* partial sharing, not just ACL-controlled access.

## Contrast with the Wiki Project's Knowledge Layer

Both Foundry IQ and the wiki project build a knowledge layer over raw content. The structural difference:

| Dimension | Foundry IQ | Wiki KB Project |
|---|---|---|
| Unit of knowledge | Document chunk with citation | Concept page synthesizing across sources |
| Retrieval | Agentic decomposition → parallel search → rerank | Read index → reason over concept pages |
| Temporal model | Periodic indexer re-runs | Explicit [[temporal-knowledge\|temporal model]] with [[purge-operation\|purge]] |
| Structure | Flat retrieval with metadata | Typed graph: concepts, people, projects, events |
| Human role | Upload sources; system indexes | Active knowledge synthesis (ingest, clarify, trim) |
| Evolution tracking | None (no "how did this concept change") | Provenance + temporal evolution are core design goals |

Foundry IQ's agentic retrieval is powerful for point-in-time questions over stable document corpuses. The wiki project is designed for questions about **how ideas evolved**, **who contributed what**, and **what is the current synthesized understanding** — a fundamentally different query type that flat document retrieval cannot answer.

The transcript enrichment gap (identified in [[Microsoft Infrastructure for Organizational Brain]]): Foundry IQ can ingest meeting transcripts as documents, but can only surface them as retrieved chunks. It cannot extract *named concepts*, attribute them to *people*, or track how a concept evolved *across meetings*. That synthesis is the wiki pattern's core contribution.
