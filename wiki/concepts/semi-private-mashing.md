---
tags: [concept]
---

# Semi-Private Information Mashing

Filtering private exchanges — 1:1 meetings, personal transcripts — to extract only the parts relevant to a shared KB, while preserving the privacy of everything else. Identified in [[Thursday demo]] as a key differentiator from existing KB tools.

## The Problem

A 1:1 between Sadra and Sumit contains a mix of: project decisions (shareable), personal context (not shareable), and half-formed ideas (judgment call). Current tools have no mechanism for this filtering — you either include the whole document or exclude it. Semi-private mashing provides a third option: include the relevant subset.

## Relevance as a View

Deciding what is "relevant to share" is itself a [[views|View]] — a declarative spec applied to a private source. This makes the filtering user-definable and auditable: you can see exactly what the KB extracted from a private source and why. The [[wiki-kb-project|Wiki KB Project]] treats this as a first-class operation rather than a manual preprocessing step.

## Privacy Implications

The filtering must happen *before* the content enters the shared KB. The raw private source never enters the shared layer; only the extracted, filtered output does. This was discussed in [[Sadra-1May2026-Transcript|the May 1 three-way sync]] as a concern Souti raised about privacy.
