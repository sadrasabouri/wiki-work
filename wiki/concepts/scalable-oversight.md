---
tags: [concept]
---

# Scalable Oversight

How humans maintain meaningful oversight of AI agents as AI capability grows beyond human ability to verify each step. The academic framing of the [[agent-traceability-steerability|Spreadsheet Verification]] problem, discussed in [[GMT20260220-230118_Recording.transcript|the Feb 20 meeting]].

## The Core Tension

As agents become more capable, they produce outputs that are harder for humans to evaluate directly. A data labeler reviewing an AI-generated spreadsheet analysis cannot easily check every formula and data transformation. The question is whether useful oversight remains possible without superhuman verification capacity.

## Two Approaches Explored

- **Agent-as-verifier** — use a second (possibly weaker or differently-prompted) model to check the primary model's work; exploits the fact that verification is often easier than generation
- **Human-in-the-loop rubrics** — provide humans with must-haves vs. nice-to-haves criteria that enable fast, structured judgment rather than open-ended evaluation; reduces cognitive load at the cost of some coverage

## Data Labeler as Use Case

The primary application context was data labelers reviewing AI-annotated spreadsheets — a domain where the task is well-defined, the outputs are structured, and systematic errors (off-by-one, currency confusion) are predictable. This made it tractable to design rubrics and define must-haves.

## Connection to [[agent-lens|Agent Lens]]

The [[agent-lens|Agent Lens]] / [[dag-of-computation|DAG]] approach is a third strategy: make the computation *transparent* so humans can focus oversight at the steps most likely to fail, rather than reviewing the final output blindly. [[steerability|Steerability]] is the intervention mechanism that makes transparency actionable.

## Empirical Result: Participation Over Review

[[Auditing and Controlling AI Agent Actions in Spreadsheets|The Pista paper]] provides the clearest statement of the principle: **meaningful human oversight of AI agents in knowledge work requires not improved post-hoc review mechanisms, but active participation in decisions as they are made.** Reviewing a finished output places the entire burden of oversight on a single moment of inspection — by then, errors that were legible at the step where they occurred have become invisible in the aggregate. The scalable oversight problem, in this framing, is fundamentally a *timing* problem: oversight must happen during execution, not after.
