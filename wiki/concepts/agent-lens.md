---
tags: [concept]
---

# Agent Lens

The framework name for the [[spreadsheet-verification|Spreadsheet Verification]] tool, named in [[GMT20260316-200648_Recording.transcript|the Mar 16 meeting]]. The three verbs: **stop** (pause execution), **see** (the [[dag-of-computation|DAG of computation]]), **steer** (correct a step before it propagates).

## Why "Lens"

The metaphor is precise: a lens doesn't change what's there — it changes how you perceive it. Agent Lens doesn't modify what the agent computes; it changes how the human sees and interacts with the agent's computation. This framing is important because it positions the tool as augmenting human perception rather than constraining agent behavior.

## Relationship to [[views|Views]]

Agent Lens is the product instantiation of the [[views]] concept for the spreadsheet domain. "Stop, see, steer" maps to: stop the agent (make execution inspectable), see a view of computation (the DAG or step-by-step), steer by editing that view (correcting a step).

[[sumit-gulwani|Sumit]] explicitly connected Agent Lens to the broader views concept in the Mar 16 meeting — the same moment he identified [[views]] as the unifying abstraction across both the spreadsheet tool and the [[wiki-kb-project|Wiki KB Project]].

## The [[steerability|Steerability]] Embodiment

Agent Lens is the concrete system that gives [[steerability]] a physical form: the DAG is the "steer point," the agent pauses at each node, and the human decides whether to continue or redirect. The earlier term "granular feedback" that Sumit replaced with "steerability" maps exactly to the steer step in this framework.
