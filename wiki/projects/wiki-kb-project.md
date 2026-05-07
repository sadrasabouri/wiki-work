---
tags: [project]
---

# Wiki KB Project

Research project on AI-powered knowledge management. The central claim: a KB structured around [[views|Views]] and maintained by AI can serve as infrastructure for both individual cognition and team communication — operationalizing the [[simulation-metaphor|simulation metaphor]].

## Three Novel Contributions

As articulated in [[Thursday demo]] and refined in [[T7-2026-05-01|the May 1 sync]]:

1. **[[views|Views]]** — declarative specs (prompts/templates) applied to raw sources to produce purpose-specific outputs. User-definable, hierarchical, saveable. The unifying abstraction across both this project and [[agent-traceability-steerability|Spreadsheet Verification]].
2. **[[semi-private-mashing|Semi-private mashing]]** — filtering private exchanges (1:1 meetings) to extract only parts relevant to a shared KB, while preserving privacy. Key differentiator from existing KB tools.
3. **[[information-knowledge-pipeline|Efficiency via the information→knowledge→views pipeline]]** — views run on wiki (processed knowledge), not raw data; intermediate summaries are precomputed once and reused. Reduces latency and cost of view generation. Discussed in [[T7-2026-05-01|May 1 sync]] and formalized as the full pipeline in [[T10-2026-05-03|May 3]]. Structurally identical to Tiago Forte's "Intermediate Packets" in [[second-brain-code-method|BASB]] — both identify reuse as the leverage point.

## Intellectual Lineage

The LLM-wiki pattern is rooted in the [[second-brain-code-method|Building a Second Brain]] tradition (Tiago Forte's CODE method) and was popularized as an LLM-native workflow by Andrej Karpathy's X post — see [[llm-wiki-landscape|LLM-Wiki Landscape]] for the full ecosystem. The key differentiator from Karpathy's personal KB pattern: this project targets team/organizational knowledge, not personal notes — confirmed explicitly in [[T10-2026-05-03|the May 3 sync]] ("we never call it a personal knowledge base"). [[semi-private-mashing|Semi-private mashing]] is the mechanism that makes organizational scope possible.

## External Positioning

AI critic [[gary-marcus|Gary Marcus]] argued in May 2026 that GenAI is net negative outside of coding and brainstorming. [[sumit-gulwani|Sumit]] forwarded this post noting "Our wiki kinda allows us to 'brainstorming'" ([[Presentation]]). The wiki project doesn't need to rebut Marcus — it operates within the domain he already grants legitimate. This is a stronger positioning move than arguing against the critique: the project lives inside the exception.

## Three-Layer Architecture

In [[T15-2026-05-06|the May 6 sync]], [[sumit-gulwani|Sumit]] insisted on a strict **three-layer architecture** with `raw/` `wiki/` `views/` as **peer top-level directories**, not nested. This mirrors the [[information-knowledge-pipeline|information→knowledge→views pipeline]]: raw sources are immutable inputs; the wiki is processed knowledge; views are purpose-specific renderings. Conflating layers in the file system conflates them in any reader's mental model. The repo was reorganized the same day.

## Self-Referential Nature

The project is its own best use case — see [[self-referential-kb]]. The raw sources feeding this KB are the transcripts of the meetings that designed it. The presentation on Thursday is planned to be generated from the KB itself.

## Key People

[[sadra-sabouri|Sadra Sabouri]], [[sumit-gulwani|Sumit Gulwani]], [[souti-chattopadhyay|Souti Chattopadhyay]].

## Sources

Emails: [[Thursday demo]], [[Presentation]], [[misc thoughts]], [[Transcripts]]. Meetings: [[T7-2026-05-01|May 1]], [[T8-2026-05-02-1|May 2 morning]], [[T9-2026-05-02-2|May 2 evening]], [[T10-2026-05-03|May 3]], [[T11-2026-05-04-1|May 4a]], [[T12-2026-05-04-2|May 4b]], [[T13-2026-05-05-1|May 5 morning]], [[T14-2026-05-05-2|May 5 evening]], [[T15-2026-05-06|May 6]].
