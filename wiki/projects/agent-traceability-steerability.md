---
tags: [project]
---

# Agent Traceability and Steerability in Spreadsheets (Pista)

Published as **"Auditing and Controlling AI Agent Actions in Spreadsheets"** ([[Auditing and Controlling AI Agent Actions in Spreadsheets]], arxiv 2604.20070). Authors: [[sadra-sabouri|Sadra Sabouri]], [[athena-saghi|Zeinabsadat (Athena) Saghi]], Run Huang, [[sujay-maladi|Sujay Maladi]], Esmeralda Eufracio, [[sumit-gulwani|Sumit Gulwani]], [[souti-chattopadhyay|Souti Chattopadhyay]].

The research tool ([[agent-lens|Agent Lens]], "Pista") addresses the [[scalable-oversight|scalable oversight]] problem: as agents become more capable, their execution becomes harder to oversee. The central argument: **meaningful human oversight of AI agents in knowledge work requires not improved post-hoc review mechanisms, but active participation in decisions as they are made.**

## Why Spreadsheets Specifically

Spreadsheets are where process and artifact are inseparable. Every agent decision lands directly in cells the user owns, is accountable for, and must stand behind. There is no separate "running application" distinct from the code — unlike code agents, the computation *is* the artifact. Agents currently achieve only 44–70% success on real-world spreadsheet benchmarks and offer users little means to understand decisions or redirect them. Discussed in [[T1-2026-02-20-2301|the Feb 20 meeting]].

## Formative Study (N=8)

Technology probe with two features (step-by-step reveal + localized editing). Surfaced five challenges across three gulfs of interaction:

**Gulf of Evaluation:**
- C1: Can't probe/clarify agent decisions — static explanations insufficient; users need to "ask follow-up questions"
- C2: Computation logic hidden behind values — users need formulas, references, dependencies surfaced upfront

**Gulf of Execution:**
- C3: Low confidence in editing — can't predict how an edit propagates; no way to compare alternatives or revert

**Gulf of Envisioning:**
- C4: Difficulty specifying upfront — high-level prompts leave key decisions to the agent
- C5: Not knowing what to question or try — users need a "second pair of eyes" to surface unknown unknowns

## Pista: Design Goals and Features

Three design goals, seven features (F1–F7):

**DG1 — Make execution traceable and digestible:**
- **F1** Decomposing Agent Execution — pauses at steps that modify data/logic or make decisions affecting downstream steps
- **F2** In-Situ Explanations — what the agent did and why, with proactive follow-up suggestions (F7)
- **F3** Surfacing Computation Logic — formulas, source ranges, output ranges displayed in UI (the [[semantic-diff|semantic diff]])

**DG2 — Enable granular intervention and exploratory refinement:**
- **F4** Localized Editing — corrections scoped to current step; agent revises only that step and propagates
- **F5** Branching Exploration — edits create a new branch; all subsequent steps regenerated from edited state; original preserved; displayed as a tree; **most adopted feature: 94% of participants, median 3 uses**

**DG3 — Scaffold task specification and guided exploration:**
- **F6** Scaffolded Task Formulation — editable requirements list inferred from prompt before execution begins
- **F7** Scaffolding Questions — proactive follow-up and edit suggestions at each step

## Summative Study (N=16)

Within-subjects comparison: Pista vs. baseline agent of equivalent capability.

Key results:
- **Same success rate** (Pista: 0.53, Baseline: 0.50) — Pista does not reduce task performance
- **More issues detected** (2.12 vs. 1.75 per session)
- **Fewer, shorter prompts** (3.18 vs. 4.00 prompts; 12.9 vs. 27.6 words) — localized editing replaces full re-prompts
- **Richer verbal explanations** of agent process (M=4.38 vs. M=2.94, p=0.015) — participation builds comprehension
- **Trust accumulated through interaction**, not from output quality — "I wasn't worried about the changes because it let me verify each step"
- **12 of 16** participants reported stronger sense of ownership over output

## Three Theoretical Contributions

1. **Calibrated trust through participation** — trust is not a post-hoc verdict; it accumulates during interaction. Users who checked more carefully trusted the output *more*, not less. Meaningful oversight requires participation in execution rather than post-hoc review.

2. **[[semantic-diff|Semantic diff]] primitive** — surface the computational unit (formula, rule) rather than the artifact surface (highlighted cells). Generalizes to code agents (function/architectural decision) and document agents (rhetorical move).

3. **Persistent envisioning support** — the [[gulf-of-envisioning|Gulf of Envisioning]] recurs at every intervention point, not just at task start. The system should provide scaffolded starting points for expressing a correction at each step, not just at task entry.

## Framework: Stop, See, Steer

The [[agent-lens|Agent Lens]] framework: **stop** (execution pauses), **see** (F2, F3 — the [[semantic-diff|semantic diff]] of each step), **steer** (F4, F5 — localized edit or branch). [[steerability|Steerability]] is the theoretical framing.

## Connection to [[wiki-kb-project|Wiki KB Project]]

[[sumit-gulwani|Sumit]] identified [[views|Views]] as the abstraction unifying both projects in [[T4-2026-03-16-2006|Mar 16]]. The DAG view, step-by-step reveal, and formula-only view are all views of agent computation in the same sense that design docs and topic summaries are views of a knowledge corpus.

## Sources

[[T1-2026-02-20-2301|Feb 20]], [[T2-2026-03-04-1912|Mar 4]], [[T3-2026-03-11-1846|Mar 11]], [[T4-2026-03-16-2006|Mar 16]], [[Agent's Traceability and Steerability Project]], [[Auditing and Controlling AI Agent Actions in Spreadsheets]]
