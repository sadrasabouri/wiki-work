---
tags: [concept]
---

# Human as API

Modeling human supervision as a tool call in an agentic workflow. The human is not a passive observer but a callable resource: the agent requests input at defined decision points, the human responds, and the agent continues. Framed by [[souti-chattopadhyay|Souti]] using Paul Grice's maxims in [[T6-2026-04-03-2|the Apr 3 Part 2 meeting]].

## Grice's Maxims as Interface Spec

The four maxims of cooperative communication translate directly to agent-human API design:
- **Quantity** — request only what the agent actually needs, not more
- **Quality** — make requests the human can answer with confidence
- **Relation** — scope requests to the current task
- **Manner** — make requests unambiguous and actionable

Violating any maxim degrades the interaction: too many requests, irrelevant requests, or ambiguous requests cause the human to disengage.

## Interaction Preferences File

The `interaction.md` concept from the same meeting: an agent accumulates a file of learned user preferences from past interaction trajectories. This file is loaded as context in future sessions, allowing better-calibrated requests over time. The file is itself a [[views|View]] over the interaction history.

## Relationship to [[steerability|Steerability]]

Human-as-API is steerability from the agent's side: the agent creates steer points proactively by calling the human at the right moments, rather than waiting for the human to interrupt. This turns steerability from a user behavior into a jointly-designed protocol.

## In [[agent-traceability-steerability|Spreadsheet Verification]]

The spreadsheet tool used human-as-API at [[dag-of-computation|DAG]] checkpoints: the agent pauses, presents the current computation step, and asks the human to confirm or correct before continuing. This was validated in the formative study described in [[T4-2026-03-16-2006|the Mar 16 meeting]].
