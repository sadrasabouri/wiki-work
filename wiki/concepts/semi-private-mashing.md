---
tags: [concept]
---

# Semi-Private Information Mashing

Filtering private exchanges — 1:1 meetings, personal transcripts — to extract only the parts relevant to a shared KB, while preserving the privacy of everything else. Identified in [[Thursday demo]] as a key differentiator from existing KB tools.

## The Problem

A 1:1 between Sadra and Sumit contains a mix of: project decisions (shareable), personal context (not shareable), and half-formed ideas (judgment call). Current tools have no mechanism for this filtering — you either include the whole document or exclude it. Semi-private mashing provides a third option: include the relevant subset.

[[workiq|Work IQ]] makes the gap concrete: it indexes all of M365 at the document level but has no model for an individual selectively contributing distilled personal knowledge to a shared layer. The same gap exists across the full [[microsoft-iq-stack|Microsoft IQ Stack]]: Foundry IQ respects existing ACLs but cannot handle *author-controlled* partial sharing of private content; Work IQ captures collaboration signals but only from what's already in M365. The result, as Sadra observes in [[Microsoft Tool For Idea Automation]]: "tons of rework is happening that wouldn't be there if there was a common source of updating knowledge where individuals can contribute using their semi-private information." Work IQ can retrieve what exists; it cannot surface what someone knows privately that would solve a colleague's problem.

## Relevance as a View

Deciding what is "relevant to share" is itself a [[views|View]] — a declarative spec applied to a private source. This makes the filtering user-definable and auditable: you can see exactly what the KB extracted from a private source and why. The [[wiki-kb-project|Wiki KB Project]] treats this as a first-class operation rather than a manual preprocessing step.

## Privacy Implications

The filtering must happen *before* the content enters the shared KB. The raw private source never enters the shared layer; only the extracted, filtered output does. This was discussed in [[T7-2026-05-01|the May 1 three-way sync]] as a concern Souti raised about privacy.

## The PR Model as Concrete Mechanism

[[local-first-kb|Local-First KB]] makes this operational: the user runs a private KB locally (all processing on-device), then contributes selected distilled knowledge units to the shared org KB via a pull request. The PR boundary *is* the filter — only what the user explicitly includes in the PR crosses from the private layer to the shared one. [[Personal Knowledge Management]]

This inverts the current failure mode documented in [[T14-2026-05-05-2|the May 5 evening sync]]: Sumit's agent accidentally pulled three sentences of a colleague's unpublished work because no privacy boundary existed. The PR model makes the boundary structural, not dependent on the user catching the violation manually.
