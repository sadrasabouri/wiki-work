---
tags: [concept]
---

# Second Brain / CODE Method

The "Building a Second Brain" (BASB) methodology, developed by Tiago Forte at Forte Labs, is the pre-LLM intellectual foundation for the LLM-wiki pattern. Its four-step CODE method — **Capture, Organize, Distill, Express** — defines the same workflow that LLM agents like Claude now partially automate. The connection is made explicit in [[LLM-Wiki Related Works]].

## The CODE Framework

Each step maps to a component in modern LLM-wiki systems:

| CODE Step | Manual Practice | LLM-Wiki Equivalent |
|-----------|----------------|---------------------|
| **Capture** | Save resonant content to a note app | Raw source ingestion; `raw-sources/` directory |
| **Organize** | PARA method (Projects/Areas/Resources/Archive) | Entity extraction → wiki graph structure |
| **Distill** | Progressive Summarization — multi-layer summaries | Intermediate summaries; view distillation |
| **Express** | Publish writing, slide decks, blog posts | [[views\|Views]] — rendering raw knowledge for a purpose |

The LLM-wiki pattern does not replace this workflow; it automates the parts that bottleneck humans (organizing raw input, maintaining consistent cross-references, generating distillation layers).

## Progressive Summarization and Intermediate Packets

Two BASB techniques are structurally important for understanding the [[wiki-kb-project|Wiki KB Project]]:

- **Progressive Summarization** — notes are summarized in multiple passes at increasing levels of abstraction, creating a "zoomable" structure. This is the same principle behind multi-level views: the same raw source can be rendered at high or low granularity depending on the query.
- **Intermediate Packets** — work is broken into reusable chunks rather than produced end-to-end. The Wiki KB Project's third contribution ("efficiency via intermediate summaries") is structurally identical: apply views to intermediate summaries rather than raw sources to reduce latency and cost.

The Intermediate Packets parallel is not coincidental — both identify that the bottleneck in knowledge work is reuse, not production.

## Lossiness is a Feature, Not a Bug

The lossiness critique of LLM wikis (raised by Anatoly Krasnovsky, cited in [[LLM-Wiki Related Works]]) is already acknowledged within BASB: distillation is *intentionally* lossy. The BASB philosophy says distilling to the essence is preferable to maintaining a complete but unnavigable archive. The wiki approach inherits this tradeoff explicitly.

The critique is therefore not that wiki-from-notes is flawed relative to some lossless standard — it's that the compression ratio and compression quality of LLM-based distillation have not been benchmarked against human curation or RAG retrieval.

## PARA vs. Wiki Graph

BASB's PARA organizing method (Projects, Areas, Resources, Archive) organizes by *actionability*. A wiki organizes by *conceptual relation*. These are orthogonal: PARA answers "what am I doing with this?" while a wiki answers "what is this connected to?" The Karpathy pattern collapsed these into the wiki frame; BASB suggests they serve different cognitive needs.

## Sources

- [[Building a Second Brain The Definitive Introductory Guide]] — [[tiago-forte|Tiago Forte]], Forte Labs (2023)
- [[LLM-Wiki Related Works]] — Sadra's note situating BASB as the historical antecedent of LLM-wiki tools
