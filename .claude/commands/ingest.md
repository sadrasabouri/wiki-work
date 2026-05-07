---
description: Ingest one or more raw source files into the wiki. For each source, reads or diffs it, extracts key takeaways, writes wiki pages, updates wiki/index.md and relevant existing pages, and appends to wiki/log.md.
argument-hint: <path-to-raw-source.md> [<path2.md> ...]
---

Ingest the raw sources at: $ARGUMENTS

## Steps

`$ARGUMENTS` may be a single file path or a space-separated list of paths. Process each file independently through steps 1–3, then perform steps 4–8 once across all files together (so cross-file connections are captured and index/log are written in one pass).

### Per-file: read and extract (repeat for each file)

1. Determine whether the source is new or modified:
   - Run `git status --short "<file>"` to check the file's status.
   - If the file is **untracked** (`??`) or **staged as new** (`A`): read the full file. All content is new.
   - If the file is **modified** (`M`): run `git diff "<file>"` to identify exactly what changed. Focus the ingest on the added lines (`+`) only — do not re-process content already in the wiki from a prior ingest. Read the full file only if additional context is needed to interpret the diff.

2. Identify the source type (email, meeting transcript, document) and key metadata (date, participants, subject).

3. Extract key takeaways from the new content only — prioritize: new concepts introduced, decisions made, terminology coined or renamed, open questions raised, connections to existing wiki concepts. Note any concepts that overlap with or relate to other files in this batch.

### Across all files: write and update

4. Determine which `wiki/` subdirectory is appropriate for each new page:
   - New concepts → `wiki/concepts/<slug>.md`
   - Meeting summary → `wiki/events/YYYY-MM-DD.md`
   - New person → `wiki/people/<name-slug>.md`
   - New project → `wiki/projects/<slug>.md`
   Write the new page(s). Pages must be insightful — synthesize and connect ideas, don't surface-level summarize. Every factual claim must link back to its source file using `[[filename]]` wikilink syntax. Where two sources in the batch relate to the same concept, synthesize them into a single page rather than writing one page per source.

5. Read `wiki/index.md`. Add a one-line entry for each new page under the appropriate category heading.

6. Scan all existing wiki pages for concepts or people mentioned in the new sources that are not yet cross-referenced. Update those pages with inline `[[wikilinks]]` where relevant.

7. Review and update stale views in `views/`:
   - List all files in `views/`. For each, check whether any wiki page it draws from was created or updated in steps 4–6.
   - For every stale view, re-run its `prompt` frontmatter value against the updated wiki and overwrite the file with refreshed content and a new `generated` date.

8. Append a single entry to `wiki/log.md` covering the whole batch:
   ```
   ## [YYYY-MM-DD] ingest | <source1 title>, <source2 title>, ...
   - Pages created: <list>
   - Pages updated: <list>
   - Views regenerated: <list>
   ```

9. Report back: pages created, pages updated, views regenerated, and 2–3 of the most surprising or insightful takeaways across the batch.
