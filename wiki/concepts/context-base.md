---
tags: [concept]
---

# Context Base vs. Knowledge Base

A **context base** is an architecture for storing an enterprise's accumulated context so that AI agents can complete long-horizon, cross-application tasks autonomously. The term comes from an "applied compute" paper Sumit shared in [[Sadra-5May2026-TRANSCRIPT2|the May 5 sync]]. It is close to but distinct from the **knowledge base** this project builds.

## The Applied Compute Architecture (Context Base)

Three phases:
1. **Remember** — ingest raw sources (existing documentation, completed work, secondary data: meeting notes, emails, databases; agent outputs from prior runs)
2. **Refine** — curation agent extracts, links, resolves conflicts, prepares indexes for retrieval
3. **Retrieve** — a set of APIs that agents call at runtime to search the context base

Key characteristic: every agent run becomes a candidate for the next refinery pass. The context base learns from the agent's own outputs (a reinforcement loop). The goal is automation — reducing human involvement in long-horizon task execution.

## How This Project Differs (Knowledge Base)

This project is a knowledge base for **human knowledge work**, not an agent automation pipeline:

| | Context Base | Knowledge Base (this project) |
|--|--|--|
| **Who consumes it** | AI agents running autonomously | Humans defining views, reading outputs |
| **Primary goal** | Agent task completion | Human insight, communication, decision-making |
| **Raw sources** | Docs, completed work, agent outputs | Transcripts, emails, notes |
| **Feedback loop** | Agent outputs → next refinery pass | Human-reviewed PRs → wiki updates |
| **Novel contribution** | Memory + reinforcement for agents | Views-not-documents; organizational brain; semi-private mashup |

The Refine phase in the applied compute paper corresponds to the [[information-knowledge-pipeline|wiki layer]] here. The Retrieve phase corresponds to [[views|views]] (queries over the knowledge layer). But views in this project are richer — they are templates with prompts and [[skills]], not just search APIs.

## Convergent Framing of Related Work

Sumit situates three pieces as convergent frames (from [[Sadra-5May2026-TRANSCRIPT2]]):

1. **[[second-brain-code-method|Building a Second Brain / CODE]]** (Tiago Forte, pre-LLM) — personal PKM; capture, organize, distill, express
2. **Karpathy's LLM-wiki** — immutable raw sources + LLM-maintained markdown wiki of entities and cross-references + schema; automates the "distill" step; critique of RAG: "LLM is rediscovering knowledge from scratch on every question. There is no accumulation"
3. **Applied compute / context base** — extends Karpathy-style architecture for enterprise agent automation with reinforcement loop

This project's position: extends (2) and (3) with the views-not-documents model (documents as living views), the organizational-brain application at Satya-scale, and [[semi-private-mashing|semi-private mashup]] as a first-class capability.
