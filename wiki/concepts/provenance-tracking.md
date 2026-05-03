---
tags: [concept]
---

# Provenance Tracking

Distinguishing human-verified content from AI-generated content in the KB. Without it, unverified AI output ("AI slop") pollutes the KB and degrades trust in all its claims. Discussed in [[Sadra-2May2026-TRANSCRIPT2|the May 2 evening meeting]].

## The Problem

As the KB grows and AI contributes more content, the human can no longer read and verify everything. Claims begin to exist in the KB without a clear source: did a human write this? Did AI generate it and a human approve it? Did AI generate it and no one reviewed it?

## AI Slop vs. AI Beauty

The framing from the May 2 meeting: "AI slop" is unverified AI output that looks plausible but may be wrong or hallucinated. "AI beauty" is AI output that has been verified, refined, or is of demonstrably high quality. The KB should track which is which — ideally with a per-claim or per-page provenance tag.

## Implementation Approaches

- **Frontmatter flags** — `verified: true/false`, `source: human/ai`
- **Git blame** — who wrote each line and when
- **Inline citations** — every claim linked to a raw source; if no source exists, it's unverified

This connects to [[temporal-knowledge|temporal knowledge]]: provenance includes not just *who* but *when*, enabling the KB to show which claims are from early explorations vs. validated later conclusions.

## Trust and [[digital-twins|Digital Twins]]

Provenance tracking is a prerequisite for digital twins — a model of a person that contains unverified AI confabulation is worse than no model at all.
