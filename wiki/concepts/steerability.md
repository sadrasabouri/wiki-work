---
tags: [concept]
---

# Steerability

The user's ability to redirect AI output at granular steps rather than only evaluating the final result. Coined by [[sumit-gulwani|Sumit Gulwani]] in [[GMT20260316-200648_Recording.transcript|the Mar 16 meeting]] to replace "granular feedback" — feedback implies post-hoc correction; steerability implies real-time co-authorship.

## Why the Rename Matters

"Granular feedback" positions the user as a judge: agent acts, user scores. "Steerability" positions the user as a driver: agent proposes a step, user redirects before it propagates downstream. This reframing directly shaped the "stop, see, steer" triad that became the [[agent-lens|Agent Lens]] framework name for [[agent-traceability-steerability|Spreadsheet Verification]].

## Steerability and Workflows

Steerability is most meaningful at [[workflows|Workflow]] step boundaries. Multiple steps create multiple steer points; without explicit step structure there is nothing to steer *between*. This is why [[workflows]] are first-class objects rather than implementation details.

## The Gulf of Envisioning Obstacle

A fundamental blocker: users cannot form stable mental models of non-deterministic AI capabilities — the [[gulf-of-envisioning|Gulf of Envisioning]]. If users don't know what the agent *can* do, they can't know when or how to steer. Preloaded Q&A and capability scaffolding were proposed as mitigations in [[GMT20260316-200648_Recording.transcript|the Mar 16 meeting]] and revisited in [[Souti-3Apr2026-TRANSCRIPT-Part2|the Apr 3 Part 2 meeting]].

## Empirical Validation: Calibrated Trust Through Participation

The summative study in [[Auditing and Controlling AI Agent Actions in Spreadsheets|the Pista paper]] (N=16) provides the clearest empirical grounding: users with step-level steerability sent significantly fewer and shorter prompts (3.18 vs. 4.00 prompts; 12.9 vs. 27.6 words) while detecting more issues (2.12 vs. 1.75). Crucially, **trust accumulated through the interaction itself**, not from output quality — users who checked more carefully trusted the output *more*, not less. This reframes the goal: steerability is not just a correction mechanism; it is how appropriate trust gets calibrated during task execution.
