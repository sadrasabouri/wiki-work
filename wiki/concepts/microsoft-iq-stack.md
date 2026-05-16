---
tags: [concept]
---

# Microsoft IQ Stack

Microsoft's enterprise AI architecture organized as a **three-layer intelligence stack** (Work IQ + Fabric IQ + Foundry IQ) plus build tools (Microsoft Foundry, Copilot Studio) and governance frameworks (Agent 365, Agent Factory). Documented in [[Demystifying Microsoft's AI Strategy Work IQ, Fabric IQ, Foundry IQ, and More]] and the official [[What is Foundry IQ?]] docs; synthesized against the [[wiki-kb-project]] in [[Microsoft Infrastructure for Organizational Brain]].

The IQ layers are **architectural outcomes, not products** — they describe what types of intelligence an agent can draw from, not SKUs you purchase.

## The Three Layers

| Layer | Domain | What it provides |
|---|---|---|
| **[[fabric-iq\|Fabric IQ]]** (foundation) | Structured enterprise data | Ontologies, semantic models, KPIs, data lineage — business meaning layered over raw data in OneLake/Power BI |
| **[[foundry-iq\|Foundry IQ]]** (middle) | Unstructured knowledge | Documents, policies, contracts, wikis — permission-aware retrieval with agentic decomposition and citations |
| **[[workiq\|Work IQ]]** (top) | Workflow and collaboration | Signals from M365: emails, meetings, calendars, org relationships — personalizes agents to how *this* org actually works |

The canonical example is supply chain delay management: Fabric IQ flags anomalies in on-time delivery data; Foundry IQ retrieves the relevant supplier SLA clause; Work IQ knows the operations team is already drowning in manual chase-ups. Only a system drawing all three can act usefully rather than just surface another dashboard.

## Build and Governance

**Microsoft Foundry** — pro-code engineering backbone: model selection, fine-tuning, vector DBs, prompt flows, QA, security. Where experiments become production-grade.

**Copilot Studio** — low-code/no-code orchestration above Foundry. Designs agent behavior, connects data sources, defines actions. "Foundry creates the brain; Copilot Studio orchestrates it in real workflows."

**Agent 365** — runtime governance layer. Monitoring, compliance enforcement, observability, alerting. Converts experimental projects into trusted enterprise solutions.

**Agent Factory** — scaling via blueprints/templates. If a supply chain agent works, replicate its component pattern (Fabric connection + Foundry retrieval + Copilot Studio orchestration) for finance and HR. Treats AI development like manufacturing.

## Where the [[wiki-kb-project|Wiki KB Project]] Differs

Sadra's analysis in [[Microsoft Infrastructure for Organizational Brain]] identifies two structural gaps the IQ stack does not close:

**1. Transcript enrichment → knowledge synthesis.** Foundry IQ ingests documents but treats them as retrieval sources. The wiki project extracts *concepts* from meeting transcripts — named ideas that evolve across sessions, attributed to people, linked to related concepts. Pre-agent systems couldn't extract meaningful structure from transcripts; the wiki pattern represents what becomes possible now. This is a layer above Foundry IQ's retrieval.

**2. Personal → organizational contribution (the reverse link).** The IQ stack flows downward: org data enriches agents. There is no mechanism for an individual to push a private insight upward into the shared knowledge layer. This is exactly what [[semi-private-mashing]] and the [[local-first-kb]] PR model address. Work IQ + Foundry IQ together index what already exists in org systems; they cannot surface "Alice's insight from her 1:1 transcript that would solve Bob's problem three teams over."

The wiki project's position: the IQ stack handles the data/context/knowledge retrieval well. The missing layer is **structured synthesis** (wiki) plus **bottom-up contribution** (semi-private mashing + PR model). These are complementary, not competing.

## Connection to Work IQ's Skills Analogue

Work IQ's "Business skills" — natural-language org-process instructions agents discover at runtime — are the closest thing in any shipping product to the [[skills]] concept. Both encode HOW to do something. The difference: Work IQ skills are consistent cross-agent procedure rules; wiki skills are per-prompt creative methodology for filling a view hole. Same structural pattern, different semantic scope.

## Connection to Fabric IQ's "Operational Agents"

Fabric IQ lets users publish their chat sessions with data agents as **operational agents** — reusable prompts others can run. This is functionally a primitive version of [[skills]]: it captures a methodology for extracting insight from a data lake and makes it reusable. The difference is that Fabric IQ operational agents operate over a fixed ontology of structured data, while wiki skills encode creative reasoning over free-form knowledge.
