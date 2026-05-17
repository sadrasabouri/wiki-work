---
tags: [view, design-doc]
generated: 2026-05-16
---

> [!note]-
> prompt: *Proposal — Synthesis IQ as a native extension of the Microsoft IQ stack*

# Synthesis IQ — Proposal

**One sentence:** Synthesis IQ is a fourth IQ layer that sits above Foundry IQ and converts retrieved document chunks and meeting transcripts into a structured, time-stamped knowledge graph — enabling agents to answer not just *"what does the doc say?"* but *"how has this idea evolved, and who owns it?"*

---

## The Gap in the Current Stack

The three existing IQ layers handle retrieval well:

| Layer | What it retrieves | What it cannot do |
|---|---|---|
| **Work IQ** | M365 signals — emails, meetings, Teams, org graph | Synthesize signals into persistent named concepts |
| **Foundry IQ** | Unstructured documents — policies, transcripts, wikis | Extract evolving concepts; track who said what across sessions |
| **Fabric IQ** | Structured data — OneLake, Power BI, KPIs | Anything unstructured or conversational |

The result is a well-indexed *memory* with no *understanding*. An agent with the full IQ stack can answer "what documents mention Project X?" — it cannot answer "what is the team's current shared understanding of Project X, how did it change last week, and which open questions remain unresolved?"

Two structural gaps, both unaddressed by TypeAgent's Structured RAG and by any current IQ layer:

1. **Transcript → named concepts.** Meeting transcripts enter Foundry IQ as chunks. No system currently extracts *named, evolving ideas* — attributing them to people, connecting them across sessions, and flagging when a concept shifts meaning. This synthesis is the difference between a retrieval index and a knowledge base.

2. **Personal → organizational contribution (the reverse link).** Every IQ layer flows *downward*: org data enriches agent context. There is no mechanism for an individual to push a private insight upward into the shared knowledge layer. Alice's insight from her 1:1 transcript — which would solve Bob's problem three teams over — stays invisible. The result is what Sadra documents in [[Microsoft Infrastructure for Organizational Brain]]: "tons of rework that wouldn't exist if there were a common source of updating knowledge where individuals can contribute using their semi-private information."

---

## Proposal: Synthesis IQ

Synthesis IQ is a **knowledge synthesis and contribution layer** that closes both gaps, built entirely from native Microsoft components.

### Positioning in the IQ Stack

```
┌─────────────────────────────────────────────────────┐
│                   VIEWS LAYER                       │
│   Design docs · Timelines · Presentations · Queries │
│   (Copilot Studio agents / MCP server API)          │
├─────────────────────────────────────────────────────┤
│              ★ SYNTHESIS IQ (new)                   │
│   Concept pages · People pages · Project pages      │
│   Provenance graph · Temporal evolution model       │
│   Semi-private mashing · PR contribution model      │
├─────────────────────────────────────────────────────┤
│                  FOUNDRY IQ                         │
│   Unstructured docs · Agentic retrieval · ACLs      │
├─────────────────────────────────────────────────────┤
│                  FABRIC IQ                          │
│   Structured data · Ontologies · OneLake            │
├─────────────────────────────────────────────────────┤
│                   WORK IQ                           │
│   M365 signals · Emails · Meetings · Org graph      │
└─────────────────────────────────────────────────────┘
```

Synthesis IQ does not replace any existing layer. It reads from Foundry IQ (retrieved document chunks + transcripts) and Work IQ (who-talked-to-whom signals from Microsoft Graph), then produces structured knowledge pages that the Views layer and any Copilot Studio agent can consume.

---

## What Synthesis IQ Does

### 1. Concept Extraction and Synthesis

An Azure AI Foundry synthesis agent reads retrieved content from Foundry IQ and produces **concept pages** — structured Markdown documents that:
- Define the concept as the team currently understands it
- Trace its origin to the first source that introduced it
- Link to every subsequent source where it was refined, challenged, or renamed
- Attribute contributions to specific people (from Work IQ / Microsoft Graph org signals)

This is structurally distinct from Foundry IQ's agentic retrieval: retrieval answers a point-in-time question; synthesis builds a durable, versioned knowledge artifact.

### 2. Temporal Evolution Model

Every concept page carries a provenance chain: when the idea was introduced, how it changed, and which source triggered each change. This makes possible a class of queries no retrieval system can answer:

- "How has our definition of 'views' changed since February?"
- "Who introduced the idea of semi-private mashing, and who has pushed back?"
- "What concepts were active in April but have gone quiet since?"

Temporal integrity is maintained via a **purge operation**: when a source is retracted or superseded, Synthesis IQ propagates the invalidation through all concept pages that cited it — the same way a live spreadsheet recalculates when a cell changes.

### 3. Semi-Private Mashing (Personal → Org Contribution)

The contribution model inverts the IQ stack's one-way flow:

```
Personal KB (local device)
  ├── TypeAgent/KnowPro → structured conversation recall
  ├── Azure AI Foundry agent → synthesis on-device
  ├── Microsoft Purview labels → privacy classification
  └── Author-controlled selection → PR to org Synthesis IQ
         ↓
  SharePoint / OneLake (shared org KB)
         ↓
  Synthesis IQ (merged into shared concept graph)
```

The **PR boundary is the privacy filter**: only content the author explicitly includes crosses from the private layer to the shared one. Microsoft Purview sensitivity labels provide automated classification to help authors identify what should stay private — but the final selection is always author-controlled.

This is the missing mechanism Work IQ lacks. Work IQ can retrieve what exists in M365; it cannot surface what someone *knows privately* that would solve a colleague's problem.

---

## Native Microsoft Component Mapping

Every layer of Synthesis IQ uses a component Microsoft already ships or has in research preview:

| Synthesis IQ capability | Microsoft component | Notes |
|---|---|---|
| **Raw conversation recall** | TypeAgent / KnowPro (Structured RAG) | Inverted-index entity/topic extraction; replaces vector embeddings for conversation memory |
| **Document retrieval input** | Foundry IQ | Provides agentic retrieval over org documents as input to the synthesis agent |
| **Org relationship signals** | Microsoft Graph (via Work IQ MCP server) | Who talks to whom; team membership; attribution scaffolding |
| **LLM synthesis** | Azure AI Foundry | Concept page generation, semantic diffing, purge propagation |
| **Knowledge index** | Azure AI Search | Inverted index over concept pages; `search.in()` security filter for access control |
| **Shared org KB storage** | SharePoint / OneLake | "Main branch" of the shared concept graph |
| **Privacy classification** | Microsoft Purview | Sensitivity labels on personal content before author-selection |
| **Contribution review** | Azure DevOps / GitHub (PR model) | Structural privacy boundary; AI reviewer checks for contradictions + leakage |
| **Views / agent consumption** | Copilot Studio | Orchestrates view generation; exposes Synthesis IQ as an MCP server |
| **Personal on-device processing** | TypeAgent Shell (local) | Runs the local KB privately; no cloud egress until PR |
| **Identity / access control** | Microsoft Entra | Per-user retrieval scoping; mirrors Foundry IQ's permission model |

Synthesis IQ is not a new technology stack — it is a new **orchestration layer** connecting components Microsoft already builds.

---

## Differences from Each Current Microsoft System

### vs. Foundry IQ

| | Foundry IQ | Synthesis IQ |
|---|---|---|
| Unit of knowledge | Document chunk with citation | Concept page synthesizing across N sources |
| Retrieval | Parallel subqueries → rerank → grounded answer | Read index → reason over concept pages |
| Temporal model | None (periodic re-index) | Explicit — provenance chain + purge propagation |
| Human contribution | Upload source; system indexes | Author-controlled — PR model with privacy filter |
| Transcript handling | Ingest as document; surface as chunk | Extract named concepts; attribute to people; track evolution |

### vs. Work IQ

| | Work IQ | Synthesis IQ |
|---|---|---|
| Data source | All of M365 (automatic) | Meeting transcripts + documents (synthesis-gated) |
| Knowledge layer | None (semantic index over raw signals) | Typed graph: concepts, people, projects, events |
| Contribution direction | Top-down only (org data → agent context) | Bidirectional — personal insight → shared knowledge |
| Privacy model | ACL-based (what's already in M365) | Author-controlled extraction before any shared indexing |

### vs. TypeAgent / Structured RAG

TypeAgent addresses conversation *recall* — not synthesis. Structured RAG answers "what books did we discuss?" by matching entity trees. Synthesis IQ answers "how has our understanding of this concept evolved?" by building concept pages. TypeAgent is the ideal **raw-layer substrate** for Synthesis IQ: it provides low-cost, high-recall conversation indexing that the synthesis agent reads to produce concept pages. The two are complementary, not competitive.

| | TypeAgent / Structured RAG | Synthesis IQ |
|---|---|---|
| Goal | Maximize recall over conversation history | Build structured knowledge artifacts |
| Unit | Entity/topic record pointing back to message | Concept page with provenance chain |
| Human involvement | Passive (automatic indexing) | Active (synthesis agent + author contribution) |
| Evolution tracking | None | Core design goal |
| Privacy | No contribution model | Semi-private mashing + PR model |

---

## Why "IQ Stack Extension" Is the Right Frame

The IQ stack's thesis is that intelligence layers compound: Work IQ enriches Foundry IQ; Fabric IQ grounds Fabric with semantics. Synthesis IQ follows the same pattern — it consumes outputs from Foundry IQ and Work IQ and produces a new type of asset (concept pages) that makes all downstream agent queries more grounded.

Concretely: a Copilot Studio agent with access to Synthesis IQ can answer "what does the org currently know about supplier SLA practices, and who are the people who most recently updated that understanding?" — a query that requires concept pages (Synthesis IQ), document chunks (Foundry IQ), and org-graph attribution (Work IQ). None of the three layers alone can answer it; all three together can.

---

## Open Questions

1. **Review bottleneck.** Who or what reviews an incoming PR to the shared org KB? In software, code review is human. In knowledge, an AI reviewer could check for contradictions, privacy leakage, and provenance gaps — but this review layer is not yet designed.

2. **Contribution incentives.** The PR model works only if people contribute. What mechanism ensures that sharing private knowledge to the shared KB is worth the author's effort? Without credit tracking or visibility, the org KB will stay sparse while personal KBs grow rich.

3. **Synthesis quality gatekeeping.** Concept pages are AI-generated. How does the org know which pages are reliable? The [[provenance-tracking|provenance-tracking]] model tags AI-generated content — but a mechanism for human endorsement or correction is needed before Synthesis IQ can be used for high-stakes decisions.

4. **Scope boundary.** The wiki pattern currently targets research teams with shared meeting transcripts. What is the minimal viable deployment? A single team with a single shared calendar + meeting transcripts is a plausible first scope.

5. **TypeAgent maturity.** KnowPro is experimental sample code, not a shipping library. The Structured RAG substrate is the most technically immature component. What is the fallback if TypeAgent's production path is delayed?
