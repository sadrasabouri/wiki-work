---
tags: [concept]
---

# Context Base vs. Knowledge Base

A **context base** is an architecture for storing an enterprise's accumulated context so that AI agents can complete long-horizon, cross-application tasks autonomously. The term and architecture come from the Applied Compute paper [[Remember, Refine, Retrieve A Context Engine for Enterprise Agents]], which Sumit shared in [[T14-2026-05-05-2|the May 5 sync]]. It is close to but distinct from the **knowledge base** this project builds.

## The Applied Compute Architecture (Context Base)

Three phases:
1. **Remember** — ingests raw resources from SaaS connectors (S3, Azure, Google Drive, GitHub) and, critically, agent traces from prior runs. Day-zero sources: existing documentation (SOPs, runbooks, wikis), completed work (ticket histories, exemplars), and secondary data (meeting notes, emails, product logs).
2. **Refine** — an always-on **swarm of curation agents** that processes new sources: lightweight agents tag incoming documents; slower, more powerful agents handle high-stakes synthesis. Each Refine pass extracts facts, skills, and procedures; resolves conflicting information; and prepares indexes for retrieval. The swarm is tiered by computational cost — cheap agents run continuously, expensive agents run infrequently.
3. **Retrieve** — a set of APIs that agents call at runtime to search the Contextbase.

Key characteristic: every agent run becomes a candidate for the next Refinery pass. The context base learns from the agent's own outputs (a reinforcement loop). Human feedback is a first-class input — subject matter experts can accept or reject changes to the Contextbase; dedicated Refine jobs incorporate explicit feedback. The goal is automation — reducing human involvement in long-horizon task execution.

## Why Knowledge Work Context Is Hard to Build

The paper identifies three structural gaps between code and knowledge work that make the latter hard to index [[Remember, Refine, Retrieve A Context Engine for Enterprise Agents]]:

1. **Scattered vs. centralized** — Code lives in version control; with sufficient reasoning, everything can be traced to its definition. Knowledge work is scattered without clear links. Critical information often exists only in experts' heads.
2. **Implicit vs. explicit dependencies** — Code ships with a complete dependency tree (it must, or it won't run). Knowledge work context has no equivalent forcing function — key information is frequently never written down.
3. **Convergent vs. divergent documentation** — Code forces merge conflict resolution; only the primary branch ships. Knowledge documentation diverges freely — internal docs accumulate outdated and incorrect information with no mechanism to force reconciliation.

These three gaps explain *why* the same LLM capabilities that made coding agents tractable haven't automatically produced knowledge work agents of equal quality. The Context Engine addresses all three: SaaS connectors solve scattering; the Refinery extracts implicit knowledge from traces; the Refine swarm continuously reconciles conflicts.

## Empirical Results

Tested on APEX-Agents (long-horizon investment banking, consulting, law tasks) and GDPVal (real-world economically valuable tasks across 44 occupations) [[Remember, Refine, Retrieve A Context Engine for Enterprise Agents]]:

- **APEX-Agents**: 16.9% relative improvement (GPT-5.4 medium), 15.8% (GPT-5.4-mini medium)
- **GDPVal**: more modest — 83.6% → 85.1% (GPT-5.4); hypothesized cause: less reusable structure across tasks, less overlap between training and eval

### Reasoning-Effort Amortization

The most actionable finding: **a model with a Contextbase at low reasoning effort matches the same model without a Contextbase at medium reasoning effort.** The lift from context is largest at lower reasoning budgets and diminishes at very high reasoning (where task saturation limits headroom):

| Reasoning level | Without Contextbase | With Contextbase | Lift |
|--|--|--|--|
| Low | 44.5% | 52.4% | +7.9% |
| Medium | 52.3% | 56.0% | +3.7% |
| Extra-high | 60.4% | 59.7% | -0.7% |

The implication: context is most valuable precisely where it is cheapest to deploy — low-reasoning agents. At pilot scale, higher per-rollout cost is tolerable; at production scale, low-reasoning + Contextbase is the economically viable path. **The Contextbase shifts the cost-quality Pareto frontier rather than trading off within it.**

## How This Project Differs (Knowledge Base)

This project is a knowledge base for **human knowledge work**, not an agent automation pipeline:

| | Context Base | Knowledge Base (this project) |
|--|--|--|
| **Who consumes it** | AI agents running autonomously | Humans defining views, reading outputs |
| **Primary goal** | Agent task completion | Human insight, communication, decision-making |
| **Raw sources** | Docs, completed work, agent outputs | Transcripts, emails, notes |
| **Feedback loop** | Agent outputs → next refinery pass | Human-reviewed PRs → wiki updates |
| **Novel contribution** | Memory + reinforcement for agents | Views-not-documents; organizational brain; semi-private mashup |

The Refine phase corresponds to the [[information-knowledge-pipeline|wiki layer]] here. The Retrieve phase corresponds to [[views|views]] (queries over the knowledge layer). But views in this project are richer — they are templates with prompts and [[skills]], not just search APIs.

## Work IQ as a Productized Context Base

[[workiq|Work IQ]] (Microsoft 365) is the closest shipping product to the applied compute architecture: its Data layer = Remember, its semantic index = Refine, its Skills/Tools layer = Retrieve. Work IQ demonstrates the context base at org scale — grounding Copilot in all of M365 — but does not add the knowledge layer. It retrieves from documents; it does not synthesize concept pages or support personal→org knowledge contribution. See [[workiq]] for the full analysis.

The broader [[microsoft-iq-stack|Microsoft IQ Stack]] extends this: [[foundry-iq|Foundry IQ]] adds a managed knowledge layer over unstructured content (agentic retrieval with citations); [[fabric-iq|Fabric IQ]] adds an ontology layer over structured business data. Together these three layers constitute Microsoft's production-scale instantiation of the context base — with the same gap the wiki project addresses: no synthesis, no temporal evolution tracking, no personal→org contribution model.

## Convergent Framing of Related Work

Sumit situates three pieces as convergent frames (from [[T14-2026-05-05-2]]):

1. **[[second-brain-code-method|Building a Second Brain / CODE]]** (Tiago Forte, pre-LLM) — personal PKM; capture, organize, distill, express
2. **Karpathy's LLM-wiki** — immutable raw sources + LLM-maintained markdown wiki of entities and cross-references + schema; automates the "distill" step; critique of RAG: "LLM is rediscovering knowledge from scratch on every question. There is no accumulation"
3. **Applied compute / context base** — extends Karpathy-style architecture for enterprise agent automation with reinforcement loop

This project's position: extends (2) and (3) with the views-not-documents model (documents as living views), the organizational-brain application at Satya-scale, and [[semi-private-mashing|semi-private mashup]] as a first-class capability.
