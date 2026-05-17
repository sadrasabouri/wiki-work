---
tags: [view, brainstorm]
generated: "2026-05-16 (updated 2026-05-16: TypeAgent/Structured RAG added)"
---

> [!note]-
> prompt: *`/brainstorm`*

## Brainstorm — 2026-05-16

---

### Provocative Hypotheses

- ⚡ **The real innovation in this project is not the wiki or the views — it is the skill library.** Views can be implemented in Word with styles. Workflows are GitHub Actions. The wiki is a well-organized database. But skills — constructive specifications of *how* to synthesize a particular type of knowledge — have no equivalent in any existing tool. If skills are the genuinely novel contribution, then the team is building a knowledge-work methodology repository and using the wiki as a testbed. The current positioning undersells the actual invention. — If true, this challenges [[views]] as the stated unifying concept and recenters [[skills]].

- **The PR-to-org-KB contribution model will see near-zero voluntary participation without an explicit incentive mechanism.** The local KB captures asymmetric information — private knowledge is most valuable precisely because others don't have it. Sharing it via PR reduces its holder's information advantage. Without strong social norms (team expectation), career incentives (contributions are credited), or material benefit (the contributor gets better org-KB outputs in return), the opt-in model will produce a sparse org KB surrounded by rich personal KBs. — If true, this challenges [[local-first-kb]] and [[semi-private-mashing]] as practical org-scale mechanisms.

- ⚡ **The wiki will eventually converge on a single voice, and that convergence is a bug, not a feature.** If skills standardize synthesis methodology and the community skill library grows dominant, all KBs built with the same skill set will produce outputs with the same structure, register, and reasoning style. KB outputs from different people will become indistinguishable. This is the [[productivity-creativity-tradeoff|productivity-creativity tradeoff]] at civilizational scale. — If true, this challenges [[skills]], [[second-brain-code-method]], and any org-scale deployment.

- **A digital twin built from a provenance-tracked wiki will be a behavioral copycat, not a cognitive model — and users won't be able to tell the difference.** Provenance tracks what was *said* and when. Digital twins need to model how someone *reasons* on novel inputs. The wiki's provenance model captures the shadow of cognition, not cognition itself. Worse: the twin will sound right, because it uses the person's language and cites their sources. — If true, this challenges [[digital-twins]] and [[provenance-tracking]] as sufficient foundations for person-modeling.

- ⚡ **Foundry IQ's agentic retrieval will make the wiki project's knowledge-synthesis claim harder to defend in two years.** Foundry IQ already decomposes complex questions into parallel subqueries, reranks across sources, and returns grounded answers with citations — all from raw documents, without a structured knowledge layer. If model reasoning improves at the same rate as it has, the "structured wiki as intermediate layer" may become unnecessary overhead: an LLM with a long context window and good retrieval may synthesize as well as a hand-maintained wiki, with zero curation cost. The claim "views run on wiki (hot cache) not raw data" is an efficiency argument; it is vulnerable to faster models and cheaper inference. — If true, this challenges [[information-knowledge-pipeline]] and the project's core efficiency rationale.

- ⚡ **TypeAgent's [[structured-rag|Structured RAG]] proves that automated transcript indexing is a solved problem — which actually *strengthens* the wiki project's position.** If Microsoft Research can index 25 podcast episodes and recall all 63 books discussed (vs. Classic RAG's 15), then the raw recall problem is addressed. But Structured RAG is still "what was said?" — it cannot tell you "how has the team's understanding of this concept shifted?" or "who originally proposed this idea and who pushed back?" The wiki's human synthesis layer is not made obsolete by Structured RAG; Structured RAG could be its raw-data substrate. The wiki project's defensible claim narrows and sharpens: it is not a better retrieval system, it is the synthesis and provenance layer that sits *above* any retrieval system. — If true, this is a positioning gift: the IQ stack + TypeAgent solve the retrieval problem so the wiki doesn't have to compete on that axis.

- **The two differentiators Sadra identifies (transcript synthesis, personal→org reverse link) are the only unassailable claims.** Everything else the wiki does — retrieval, summarization, cross-document synthesis — the [[microsoft-iq-stack|IQ stack]] is actively building. Foundry IQ's agentic retrieval is a direct competitive move on the "synthesize across sources" axis. [[typeagent|TypeAgent's Structured RAG]] is a direct competitive move on the "conversational recall" axis. But no part of the IQ stack or TypeAgent extracts named concepts from meeting transcripts and tracks their evolution; no part enables individual-controlled, privacy-filtered contribution to shared knowledge. If the project focuses its positioning exclusively on these two claims, it becomes much harder to dismiss — and much easier to explain. — If true, the project's framing problem is that it leads with views/workflows (technically interesting, easily replicated) rather than with transcript synthesis and reverse contribution (genuinely novel, no incumbent).

---

### Unexplored Implications

- **[[living-system]]** taken to its extreme: if everything is a DAG and every view recomputes when its inputs change, then every view file in `views/` is already stale — from the moment a new transcript is ingested. Every new slash command added without the recalc engine is a view that will silently go stale. The team is accumulating technical debt against its own vision.

- **[[skills]]** taken to their extreme: the most valuable skills will NOT be written by KB users. They will be written by domain experts who have never used a KB. A grounded-theory skill is most precisely written by a qualitative researcher. A narrative-compression skill by a science journalist. The community skill library is a knowledge-work expertise marketplace where practitioners package methodology for non-practitioners.

- **[[semi-private-mashing]]** taken to its extreme: the current model assumes the user knows which sources are worth ingesting. But the most valuable insights often come from dismissed sources. At maximum deployment, the right model inverts: ingest *everything*, let the user specify exclusion rules. Default posture shifts from opt-in to opt-out.

- **[[productivity-creativity-tradeoff]]** applied to the wiki project itself: if AI-powered synthesis reduces aha moments by filling the incubation space, and the wiki automates synthesis, then the wiki is making its own team less creative. The more successfully it surfaces connections, the less friction drives the team to discover them independently.

- **Fabric IQ's typed ontology edges are a quiet indictment of the wiki's undifferentiated wikilinks.** The wiki uses `[[concept]]` links with no edge type — every relationship is the same. But "X caused Y", "X is an instance of Y", and "X contradicts Y" carry fundamentally different epistemic weight. If the wiki's knowledge graph had typed edges (like [[fabric-iq|Fabric IQ]]'s predefined relation types), queries like "what are the tensions in this project?" or "what concepts are prerequisites for this one?" would become precise rather than approximate. Untyped links are a design convenience that caps the graph's analytical depth.

- **The Work IQ MCP server ([[microsoftwork-iq MCP Server and CLI for accessing Work IQ|Work IQ MCP]]) points to an obvious extension: the wiki itself should be an MCP server.** If Work IQ exposes M365 data via MCP so any coding agent can query collaboration signals, the wiki's knowledge layer should be equivalently accessible — any agent (not just the wiki CLI) could query concepts, people, and events. This is the difference between a local KB and an org-scale knowledge API. The [[local-first-kb]] PR model already has the right shape; the missing piece is exposing the wiki's read interface as MCP so downstream agents can invoke it.

---

### One Big Bet

The project's most defensible long-term claim is not about the wiki or the views — it is about the **two reverse flows** that the Microsoft IQ Stack cannot do: extracting structured knowledge from conversations, and letting individuals contribute upward to shared knowledge on their own terms. Every other feature the project has is being actively built by Microsoft. If the project pitches itself as a contribution model for organizational knowledge rather than a KB viewer, it becomes a complement to the IQ stack rather than a competitor to it.
