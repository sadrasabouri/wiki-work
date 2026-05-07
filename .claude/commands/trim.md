---
description: Trim the wiki by removing deprecated concepts, superseded definitions, and outdated framings — keeping only the latest iteration of each idea. Distinct from purge (source-targeted) and lint (non-destructive updates).
argument-hint: [concept or page]  optional — scope to one concept; omit for full graph
---

Trim the wiki${ $ARGUMENTS ? " — scope: $ARGUMENTS" : " — full graph" }.

## Steps

1. **Identify deprecation candidates.** Read `wiki/index.md` and scan all wiki pages for:
   - Concepts or definitions explicitly replaced by a newer framing (e.g. "steerability" replaced "granular feedback")
   - Pages where an earlier definition is preserved as a historical note but the note is no longer useful — the old framing adds noise, not context
   - Concept pages that were merged into a broader page (e.g. a stub absorbed into a parent concept)
   - Terminology that appears in early sources but was renamed or dropped in later meetings without the wiki page being updated

2. **Clarification questions.** Before deleting anything, collect all uncertain cases and ask together:
   - A concept that *might* be deprecated but has no explicit later statement replacing it
   - A page that seems redundant with another but the overlap isn't total
   - An older framing that could be historical context worth keeping vs. dead weight

   Format: `Before trimming, I need your input: 1. [page/concept] — [question] ...`
   Apply answers before proceeding.

3. **Delete or merge.** For each confirmed deprecated item:
   - If the concept was **renamed**: update all `[[oldname]]` links to point to the new page, then delete the old page
   - If the concept was **absorbed** into a broader one: move any unique content into the parent page, then delete the stub
   - If a **definition was superseded**: remove the old definition from the page; keep only the current one. Do not add an "earlier framing" note unless the evolution is itself informative
   - If a **section within a page** is outdated: delete the section, not the whole page

4. **Repair dangling references.** After deletions, grep for any remaining `[[deleted-page]]` links across the wiki and remove or redirect them.

5. **Update index.** Remove entries for deleted pages from `wiki/index.md`.

6. **Review and update stale views in `views/`:**
   - List all files in `views/`. For each, check whether it references any page deleted or merged in steps 3–4.
   - For every affected view, re-run its `prompt` frontmatter value against the updated wiki and overwrite the file with refreshed content and a new `generated` date.

7. **Report and log.** Append to `wiki/log.md`:
   ```
   ## [YYYY-MM-DD] trim | [scope or "full graph"]
   - Pages deleted: <list>
   - Sections removed: <list>
   - Links redirected: <list>
   - Views updated: <list>
   - Clarifications applied: <list>
   ```
   Report back: what was removed and why, any redirects made, and open questions if any remain.
