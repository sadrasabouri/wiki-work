This is a nice personal workflow, but the hype is way ahead of the evidence.

There is no benchmark, no task definition, no scale curve, and no comparison against serious baselines. We do not know whether this is better than hybrid RAG, BM25 plus reranking, vector search, GraphRAG, hierarchical summaries, long-context prompting, NotebookLM, Perplexity Spaces, or ChatGPT Projects. Calling it a new architecture without that evidence is premature.

The core problem is that an LLM Wiki is lossy compression. You take raw documents and rewrite them into derived wiki pages. That may be useful for a small curated corpus, but it can also drop caveats, dates, minority views, exact wording, edge cases, and source context. Once people start querying the wiki instead of the original material, summary errors become part of the knowledge base.

Updates are also not solved. Adding one new source can affect many entity pages, concept pages, timelines, summaries, and indexes. At scale, this becomes graph maintenance: detecting what changed, resolving conflicts, avoiding duplicates, preserving provenance, preventing stale claims, and not silently breaking old pages. “Ask the LLM to maintain it” is not an engineering solution unless there are validators, source hashes, span-level citations, regression tests, and human review.

It also does not remove retrieval. Once the wiki grows beyond a modest size, you still need search, ranking, indexing, reranking, chunking, and access control. At that point the markdown wiki is just another indexed corpus, not a replacement for RAG.

The production issues are mostly ignored: permissions, multi-user edits, audit logs, rollback, deletion, sensitive data, source versioning, concurrency, compliance, cost, latency, and update frequency. These are not small details; they are exactly where knowledge-base systems fail.

So the reasonable claim is narrow: this can be a useful workflow for small-to-medium, slow-moving, human-curated research folders. It is much less convincing for large, fast-changing, high-stakes, multi-user, or enterprise knowledge bases.

The idea is fine. The framing is the problem. Without benchmarks, baselines, provenance guarantees, update-evaluation tests, and clear boundary conditions, “LLM Wiki” is mostly a good name for a familiar pattern, not proof that RAG is obsolete.