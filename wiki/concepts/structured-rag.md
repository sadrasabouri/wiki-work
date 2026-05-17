---
tags: [concept]
---

# Structured RAG

Microsoft Research's [[typeagent|TypeAgent]] team's alternative to classic vector-based retrieval for agent memory — specifically designed to scale over conversation-sized corpora (meeting transcripts, email threads, podcast archives) without losing precision or forgetting older information. Documented in [[TypeAgent - KnowPro - Memory]] and implemented in the [[TypeAgent - KnowPro|KnowPro]] package.

## Classic RAG vs. Structured RAG

**Classic RAG**: embed each conversation turn as a dense vector → embed the user query → retrieve the top-k turns by cosine similarity → stuff them into the answer prompt.

**Structured RAG** replaces vector similarity with an extraction-then-index pipeline:

**Indexing phase (per message):**
1. Extract short topic sentences and tree-structured entity/relationship information from each turn.
2. Extract key terms from entities and topics.
3. Store terms in an **inverted index** mapping terms → entities/topics → source messages.
4. Store any structured metadata (email to/from, image geo-tags) in a relational table alongside the inverted index.

**Query phase (per user request):**
1. Convert the natural-language request into a **query expression** with two components: *scope expressions* (time range, topic description, document range) that restrict the search space, and *tree-pattern expressions* that match specific entity/relationship trees via logical operators.
2. If the request involves structured metadata, add a relational join to the query.
3. Execute the query → ranked lists of entities, topics, and actions ordered by relevance score.
4. Populate the answer prompt with top entities/topics; if token budget remains, add the source messages they came from.
5. Submit to LLM for answer generation.

## Six Structural Advantages Over Classic RAG

| Advantage | Mechanism | Why it matters |
|---|---|---|
| **Size** | Inverted index vs. 4K-dimensional vector per turn | Index stays in RAM on a single VM; vector DBs require disk + distributed clusters at scale |
| **Structure** | Dense extracted entities vs. diluted embeddings | Query "what email did Kevin send Satya about AI models?" matches on all three constraints; Classic RAG returns crimson t-shirts alongside soccer balls |
| **Inference** | Post-index type expansion (artist → person) | Handles questions like "what people did we talk about?" even if entities were indexed as specific types |
| **Diverse knowledge** | Pre-existing structure (sender/receiver/subject) joins with extracted structure | "What cactus did I see on my Arizona hike last month?" works across extracted entity + image geo-tag |
| **Associative memory** | Discrete index terms enable pre-fetch while user types | Agent can begin fetching "cactus" memories before user finishes the sentence; supports completion hints |
| **Memory management** | Inverted indices and relational tables are queryable/editable | Embeddings are opaque; structured indices can be explored, pruned, and debugged with standard tools |

The size advantage is particularly sharp: with 3K input tokens, Structured RAG recalled all 63 books discussed in 25 Behind-the-Tech podcasts; Classic RAG recalled 15 books while consuming twice as many tokens. At 128K tokens, Classic RAG reached 31 (demo: [[TypeAgent - KnowPro - Memory]]).

## Critical Design Choice: Small Models Are Sufficient

Structured RAG uses simple (small, fine-tuned) models for the extraction phase — only answer generation needs a large model. This is what makes it economically viable for indexing large conversation corpora. Classic RAG's entire value depends on the quality of a single large embedding model; degrading the model degrades recall directly.

The KnowPro implementation uses secondary indices for related terms ("novel" → "book") and caches related-term discovery during query execution. Models can also suggest related terms during extraction.

## Relation to Azure AI Search

Structured RAG's inverted index is explicitly positioned as inheriting 30+ years of inverted-index engineering from Lucene and Azure AI Search. [[Security Filter Pattern - Azure AI Search]] shows how Azure AI Search already handles the security filtering of document-level access via the `search.in()` OData function — the same index-first, filter-at-query-time pattern that Structured RAG uses for precision.

## Contrast with the Wiki KB Project

Both Structured RAG and the [[wiki-kb-project|Wiki KB Project]] target the same underlying problem: making the content of conversations queryable and meaningful across time. The architectural divergence is significant:

| Dimension | Structured RAG (KnowPro) | Wiki KB Project |
|---|---|---|
| **Synthesis** | Automatic extraction (entities, topics) via LLM | Human-curated concept pages |
| **Unit of knowledge** | Entity/topic record pointing back to source messages | Concept page synthesizing across multiple sources |
| **Temporal model** | All messages retained; scope expressions filter time | Explicit [[temporal-knowledge\|temporal model]] with [[purge-operation\|purge]] |
| **Human role** | Passive (automatic indexing) | Active (ingest, clarify, trim) |
| **Query precision** | Structural — tree-pattern matching, relational joins | Semantic — reasoning over synthesized concept pages |
| **Evolution tracking** | None ("what did we discuss?", not "how has this idea evolved?") | Core design goal: provenance and temporal evolution |

Structured RAG maximizes recall over large corpora with minimal human effort. The wiki pattern maximizes insight depth by investing human synthesis. They are complementary: Structured RAG answers "what was said?"; the wiki answers "what does it mean and how did it evolve?" This is why the IQ stack gap ([[microsoft-iq-stack|Microsoft IQ Stack]]) identified in [[Microsoft Infrastructure for Organizational Brain]] is not closed by TypeAgent — TypeAgent indexes conversations structurally; it does not synthesize named concepts that evolve across them.
