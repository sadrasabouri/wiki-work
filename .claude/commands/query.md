---
description: Answer a question by synthesizing relevant wiki pages. The default view — cite sources inline, surface tensions, and file valuable answers back into the wiki.
argument-hint: <your question>
---

Answer this question using the wiki: $ARGUMENTS

## Steps

1. Read `wiki/index.md` to survey available pages.

2. Identify the 3–5 most relevant pages for this question. Read each one fully.

3. If the question references a raw source directly (e.g. "what did Sumit say about views in the Mar 16 meeting"), also read the relevant transcript.

4. Synthesize an answer:
   - Order claims by confidence — well-sourced, cross-corroborated claims first
   - Use inline `[[wikilinks]]` for every factual claim — no citation-free assertions
   - Explicitly flag anything that is uncertain, hedged, or from only a single source
   - Surface tensions or contradictions rather than papering over them

5. If the answer reveals a gap — a concept that comes up but has no wiki page, or a connection not captured anywhere — note it at the end.

6. If the answer is substantive and non-obvious (i.e. it took synthesis across multiple pages to produce), offer to file it as a new wiki page. If accepted, write it to the appropriate `wiki/` subdirectory and update `wiki/index.md`.

## Save Output

Slugify the argument (lowercase, spaces → hyphens). Save the complete output as-is to `wiki/query-<slug>.md`.

Append to `wiki/log.md`: `## [YYYY-MM-DD] view:query | $ARGUMENTS`
