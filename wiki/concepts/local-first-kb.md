---
tags: [concept]
---

# Local-First KB

A personal knowledge base architecture where private information is processed and indexed entirely on the user's device, then selectively merged with a shared organizational KB via a PR-like contribution model. Proposed by [[sadra-sabouri|Sadra]] in [[Personal Private Knowledge Management]] as the structural answer to the privacy problem.

## The Architecture

The flow has two distinct phases:

1. **Local phase** — raw private data (emails, 1:1 transcripts, personal notes) is ingested and structured entirely on-device. No private content reaches a shared layer.
2. **Merge phase** — the user selects which distilled knowledge units to contribute upstream, submitting them as a pull request to the shared org KB. The PR model gives the user explicit control over what leaves the private layer.

This is the concrete implementation of [[semi-private-mashing|Semi-Private Mashing]]: local processing operationalizes the "filter before it enters the shared layer" requirement. And it extends [[kb-as-codebase|KB as Codebase]]: personal KB = local branch; org KB = main branch; contribution = PR.

## matvellosoknowledge: A Concrete Instantiation

The [[matvellosoknowledge]] GitHub project (by Eduardo Mello) implements this pattern in production:

- **Privacy-first, local inference** — all processing runs via Ollama (local LLMs); no data sent to cloud APIs
- **Connected sources** — Gmail, Outlook; extracts To Do lists, shopping lists, reading lists, and a knowledge graph
- **MY PREFERENCES.md** — user-configurable markdown file that acts as the domain-specific extraction ruleset; a real-world analogue to [[skills|Skills]] in this project (the user encodes HOW the agent should process and prioritize, not just what to extract)

## The RAG Critique

matvellosoknowledge uses embeddings + cosine similarity for retrieval — the RAG pattern. Sadra's note identifies the structural weakness: "this makes the dependency uninterpretable compared to a graph structure." [[Personal Private Knowledge Management]]

The critique generalizes: RAG-based local KBs can retrieve relevant chunks, but cannot answer *why* two pieces of knowledge are related, or traverse a typed relation chain. The graph-structured wiki provides interpretable provenance — a traceable path from conclusion to source — that embeddings cannot.

This directly reinforces the [[llm-wiki-landscape|Wiki vs. RAG]] distinction: graph traversal over structured nodes beats embedding search over raw chunks for grounded reasoning.

## Open Design Question

The PR-to-org-KB model raises a review problem: who (or what) reviews the incoming PR? In software, code review is human-executed. In a shared KB, an AI reviewer could check for:
- Contradictions with existing claims
- Privacy leakage (content that should have been filtered)
- Provenance completeness (is the distilled claim properly linked to its local source?)

This review layer is not yet designed.
