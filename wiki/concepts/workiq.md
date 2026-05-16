---
tags: [concept]
---

# Work IQ

Microsoft's **collaboration-context intelligence layer** — the top layer of the [[microsoft-iq-stack|Microsoft IQ Stack]], above [[fabric-iq|Fabric IQ]] (structured data) and [[foundry-iq|Foundry IQ]] (unstructured knowledge). Grounds Microsoft 365 Copilot in how *this organization* works: who collaborates with whom, what workflows exist, what patterns emerge from meetings and emails. The closest existing Microsoft product to what the [[wiki-kb-project|Wiki KB Project]] is building — and the sharpest illustration of what it is missing. Documented in [[Work IQ overview]] and [[microsoftwork-iq MCP Server and CLI for accessing Work IQ]]; Sadra's analysis in [[Microsoft Tool For Idea Automation]] and [[Microsoft Infrastructure for Organizational Brain]].

## What Work IQ Does

Three integrated layers:

1. **Data** — secure access to all M365 tenant data (SharePoint, OneDrive, Outlook, Teams via Microsoft Graph), Dynamics 365/Power Apps via Dataverse, and external systems via Copilot connectors or federated MCP connectors (real-time, no pre-indexing)
2. **Context** — continuously evolving signals: Copilot memory (explicit user instructions + implicit activity patterns), a lexical + semantic index over all org data, and Dataverse intelligence for structured business data
3. **Skills and Tools** — Business skills (natural-language org process instructions that agents discover and apply at runtime), Copilot actions (MCP/REST plugins), Work IQ MCP tools for real-time M365 actions

Together, these give Copilot grounded access to org knowledge — fast, permission-respecting, semantically searchable.

## The Gap: Surface-Level Indexing Without a Knowledge Layer

Work IQ indexes raw sources (emails, files, meetings) but does not synthesize them into a structured knowledge layer. The semantic index is lexical + semantic retrieval over documents — it can surface relevant chunks, but cannot:

- Build persistent concept pages that synthesize across sources
- Track how ideas evolve across time and people
- Connect "Alice's insight from her 1:1 transcript" to "Bob's problem three teams over"

Sadra's diagnosis in [[Microsoft Tool For Idea Automation]]: Work IQ "stays in the surface level and does not connect with the organization's experience." Ideas in a person's private KB that could solve another's problem stay invisible. The result is **massive rework**: "tons of rework is happening that wouldn't be there if there was a common source of updating knowledge where individuals can contribute using their semi-private information."

This is exactly the problem [[semi-private-mashing|Semi-Private Mashing]] and the [[local-first-kb|Local-First KB]] PR model are designed to solve. Work IQ has no contribution model — you can't selectively push personal knowledge to a shared layer while filtering private content.

## How It Maps to the Applied Compute Architecture

Work IQ is a productized instantiation of the [[context-base|context base]] architecture from the applied compute paper:

| Applied Compute | Work IQ equivalent |
|--|--|
| Remember | Data layer (Microsoft Graph + connectors) |
| Refine | Semantic index + Copilot memory signals |
| Retrieve | Skills/Tools layer (agents query at runtime) |

The KB project's position: Work IQ handles the context base layer well. The wiki adds the missing **knowledge layer** — structured, typed, human-reviewed concept pages — on top, and adds **semi-private mashing** as the mechanism for personal→org knowledge flow.

## Work IQ as MCP Server

Work IQ is now accessible programmatically as an MCP server and CLI (`@microsoft/workiq` npm package, documented in [[microsoftwork-iq MCP Server and CLI for accessing Work IQ]]). This makes it natively composable with any MCP-compatible coding agent or IDE. Supported queries: emails, meetings, documents, Teams messages, people.

Three plugins in the public repo:
- **workiq** — core M365 natural-language queries
- **microsoft-365-agents-toolkit** — scaffolding, manifest authoring, eval workflows for M365 declarative agents
- **workiq-productivity** — read-only insights: email triage, meeting costs, org charts, channel audits

Key friction: requires tenant admin consent. Work IQ MCP tools require administrative rights on the M365 tenant — a significant enterprise deployment hurdle not visible in the architectural description.

## Business Skills as a Skills Analogue

Work IQ's "Business skills" — "natural-language instructions that encode your organization's processes, policies, and domain knowledge in a format agents can interpret and execute" — are the closest thing in any shipping product to the [[skills|Skills]] concept in this project. Both encode HOW to do something, not just what to retrieve. The difference: Work IQ skills are org-process rules (consistent cross-agent procedure execution); wiki skills are per-prompt creative methodology (how to fill a specific view hole). Same pattern, different scope.
