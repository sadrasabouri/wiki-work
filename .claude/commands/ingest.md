---
description: Ingest a new raw source file into the wiki. Reads the source, extracts key takeaways, writes a summary page in wiki/, updates wiki/index.md, updates relevant existing wiki pages, and appends to wiki/log.md.
argument-hint: <path-to-raw-source.md>
---

Ingest the raw source at: $ARGUMENTS

## Steps

1. Read `$ARGUMENTS` in full.

2. Identify the source type (email, meeting transcript, document) and key metadata (date, participants, subject).

3. Extract key takeaways — prioritize: new concepts introduced, decisions made, terminology coined or renamed, open questions raised, connections to existing wiki concepts.

4. Determine which `wiki/` subdirectory is appropriate:
   - New concepts → `wiki/concepts/<slug>.md`
   - Meeting summary → `wiki/events/YYYY-MM-DD.md`
   - New person → `wiki/people/<name-slug>.md`
   - New project → `wiki/projects/<slug>.md`
   Write the new page(s). Pages must be insightful — synthesize and connect ideas, don't surface-level summarize. Every factual claim must link back to `$ARGUMENTS` using `[[filename]]` wikilink syntax.

5. Read `wiki/index.md`. Add a one-line entry for each new page under the appropriate category heading.

6. Scan all existing wiki pages for concepts or people mentioned in the new source that are not yet cross-referenced. Update those pages with inline `[[wikilinks]]` where relevant.

7. Regenerate stale views in `views/`:
   - List all files in `views/` whose `target` frontmatter matches any concept, person, or project touched in steps 4–6.
   - Re-run the view logic for each match and overwrite the file with updated content and a refreshed `generated` date.

8. Append to `wiki/log.md`:
   ```
   ## [YYYY-MM-DD] ingest | <source title>
   - Pages created: <list>
   - Pages updated: <list>
   - Views regenerated: <list>
   ```

9. Report back: pages created, pages updated, views regenerated, and 2–3 of the most surprising or insightful takeaways from the source.
