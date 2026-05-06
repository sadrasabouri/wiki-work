---
tags: [concept, core]
---

# Information → Knowledge → Views Pipeline

The three-layer architecture of the [[wiki-kb-project|Wiki KB Project]], crystallized in [[Sadra-3May2026-TRANSCRIPT|the May 3 three-way sync]]:

```
Raw Data (Information)  →  Wiki (Knowledge)  →  Views (Rendered Output)
```

The pipeline is not just organizational — it is a **performance and coherence architecture**. Views run on the wiki, not on raw data. This is the foundational efficiency claim of the system.

## Layer 1: Raw Data (Information)

Unprocessed sources: meeting transcripts, emails, documents, notes, social media posts. These are information in the information-theory sense: they contain signal, but it is buried in noise and unorganized for retrieval. Stored in `raw/`.

Raw data can also come from upstream automated processes — a search query, a data-gathering workflow — not just manual ingestion. See [[living-system]].

## Layer 2: Wiki (Knowledge)

The wiki is **knowledge**: processed, organized, cross-linked, typed by entity (people, concepts, events, projects). It is the **semantic index** of the raw corpus — the layer that makes efficient view computation possible.

Sumit's framing from [[Sadra-3May2026-TRANSCRIPT|May 3]]: "Wiki is providing the right kinds of artifacts to do good indexing about different kinds of entities, such as people, topics, entities and so on." Not a vector index (mechanical, flat) but a semantic index (structured, typed, relational).

The wiki is also the **hot cache**: common intermediates that many views will query are precomputed once and reused. For a new entity type (e.g., "speaker style"), the wiki initially lacks entries; after one full-corpus ingest pass, the entity is cached and future views access it cheaply.

### Schema is Defined by Ingest

The wiki's entity schema (what counts as a concept vs. a person vs. a project) is not fixed ontologically — it is defined by the ingest command's instructions. Sumit observed: "your ingest is in some sense describing the structure of this wiki." New entity types can be added to ingest; future ingests extract them retroactively.

## Layer 3: Views (Rendered Output)

Views are purpose-specific renderings over the wiki. They are computationally efficient *because* the wiki has already processed the raw data. A contribution map view reads wiki people and event pages, not raw transcripts. A timeline view reads wiki events, not raw transcripts. The raw data is accessed only if a view requires something the wiki doesn't have.

This creates an efficiency tradeoff: if the wiki hasn't cached a needed entity type, a view must go back to raw data. The solution is to ensure the ingest prompt is comprehensive enough to extract what views will need.

## Connection to Existing Concepts

- [[views|Views]] — the Layer 3 rendering mechanism
- [[workflows|Workflows]] — describe HOW to compute within each layer transition
- [[dag-of-computation|DAG of Computation]] — the general graph structure of which layers feed into which
- [[living-system|Living System]] — how the pipeline stays current as new raw data arrives
- [[provenance-tracking|Provenance Tracking]] — tracking which wiki claims come from which raw sources

## Contrast with RAG

A RAG system compresses all information into a flat embedding index and retrieves chunks at query time. The Information → Knowledge → Views pipeline is more structured: it pre-organizes information into a typed semantic index (wiki), which enables richer, more coherent view generation than retrieval over raw chunks. This is why wiki-based systems cut token usage 75–99% vs. unstructured context ([[llm-wiki-landscape]]).
