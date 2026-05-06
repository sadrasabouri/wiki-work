---
tags: [concept]
---

# Agent Lens

The framework name for the [[agent-traceability-steerability|Spreadsheet Verification]] tool (published as Pista — from Italian/Spanish *pista*: path, trail, clue), named in [[GMT20260316-200648_Recording.transcript|the Mar 16 meeting]]. The three verbs: **stop** (pause execution), **see** (the [[dag-of-computation|DAG of computation]] and [[semantic-diff|semantic diff]]), **steer** (correct a step before it propagates).

## Seven Features (F1–F7)

Three design goals map to seven concrete features in the published system ([[Auditing and Controlling AI Agent Actions in Spreadsheets]]):

- **F1** Decomposing Agent Execution — pause at steps that modify data/logic or affect downstream decisions
- **F2** In-Situ Explanations — what the agent did and why, with proactive suggestions embedded
- **F3** Surfacing Computation Logic — formulas, dependencies, data ranges displayed upfront (the [[semantic-diff|semantic diff]])
- **F4** Localized Editing — corrections scoped to the current step only; no full re-prompt needed
- **F5** Branching Exploration — edits fork into a new branch; original preserved; displayed as a tree. *Most adopted: 94% of participants, median 3 uses.*
- **F6** Scaffolded Task Formulation — editable requirements list inferred from the prompt before execution begins
- **F7** Scaffolding Questions — proactive follow-up and edit suggestions at each step to close the [[gulf-of-envisioning|envisioning gap]]

## Why "Lens"

The metaphor is precise: a lens doesn't change what's there — it changes how you perceive it. Agent Lens doesn't modify what the agent computes; it changes how the human sees and interacts with the agent's computation. This framing is important because it positions the tool as augmenting human perception rather than constraining agent behavior.

## Relationship to [[views|Views]]

Agent Lens is the product instantiation of the [[views]] concept for the spreadsheet domain. "Stop, see, steer" maps to: stop the agent (make execution inspectable), see a view of computation (the DAG or step-by-step), steer by editing that view (correcting a step).

[[sumit-gulwani|Sumit]] explicitly connected Agent Lens to the broader views concept in the Mar 16 meeting — the same moment he identified [[views]] as the unifying abstraction across both the spreadsheet tool and the [[wiki-kb-project|Wiki KB Project]].

## The [[steerability|Steerability]] Embodiment

Agent Lens is the concrete system that gives [[steerability]] a physical form: the DAG is the "steer point," the agent pauses at each node, and the human decides whether to continue or redirect. The earlier term "granular feedback" that Sumit replaced with "steerability" maps exactly to the steer step in this framework.
