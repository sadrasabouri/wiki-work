---
tags: [concept]
---

# Gulf of Envisioning

Users cannot form stable mental models of non-deterministic AI capabilities. The "gulf" is between what users imagine the AI can do and what it actually can do — and this gap is unstable because AI capabilities change unpredictably. Coined by Subramaniam et al. (Stanford, CHI).

The concept appears in [[GMT20260316-200648_Recording.transcript|the Mar 16 meeting]] and is revisited in [[Souti-3Apr2026-TRANSCRIPT-Part2|the Apr 3 Part 2 meeting]].

## Why It Blocks [[steerability|Steerability]]

[[steerability|Steerability]] requires users to know *where* and *how* to intervene in an agent's process. The Gulf of Envisioning is a precondition problem: if users can't form a mental model of what the agent is doing, they can't identify productive intervention points. A steerable system without capability transparency is still effectively a black box.

## Proposed Mitigations

- **Preloaded Q&A** — surfaces the agent's capabilities in the form of pre-answered questions the user might ask; validated as a user need in the Mar 16 formative study results
- **Capability scaffolding** — explicit onboarding to help users build accurate mental models before interacting
- **Forward deployment engineering** — deploying AI capability ahead of user mental model, then actively training the mental model to catch up; discussed in [[Souti-3Apr2026-TRANSCRIPT-Part2|Apr 3 Part 2]]

## Paper Extension: The Gap Recurs Throughout Execution

[[Auditing and Controlling AI Agent Actions in Spreadsheets|The Pista paper]] extends the original Subramonyam et al. framing: the envisioning gap does not dissolve once a task begins — **it recurs at every step where the user must intervene**. The residual burden falls on *formulating the correction*, not locating where to make it. Static scaffolding at task start is insufficient.

Design implication: agentic systems should treat envisioning support as a **persistent layer throughout execution** — at each step, provide concrete starting points for expressing a correction (exemplar edits, contrastive alternatives, intent disambiguation), not just an explanation of what happened. This is what [[agent-lens|Pista's F7]] (Scaffolding Questions) implements.

## Connection to [[human-as-api|Human as API]]

The Gulf of Envisioning also affects the [[human-as-api|human-as-API]] pattern: if the human doesn't understand what the agent can do, they can't give useful responses to the agent's requests. Both directions of the human-agent interaction are degraded.
