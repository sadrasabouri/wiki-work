---
description: Purge or supersede claims in the wiki that are sourced from a specific meeting when that information is outdated, retracted, or invalidated by newer sources.
argument-hint: <meeting-filename-or-date>  e.g. GMT20260316-200648_Recording.transcript or 2026-03-16
---

Purge claims sourced from the meeting: $ARGUMENTS

## Steps

1. Identify the target raw source filename. If given a date (e.g. `2026-03-16`), find the corresponding transcript in `raw/meeting-transcripts/`.

2. Search all wiki pages for citations to that source:
   - Run: `grep -rl "$ARGUMENTS" wiki/`
   - Also check for the date pattern if a filename was given.

3. For each wiki page containing a citation to this meeting, read the page in full and identify every claim that cites it.

4. For each cited claim, make one of three determinations:
   - **(a) Superseded** — a newer source says something contradictory or more refined. Remove the claim and inline-cite the superseding source instead.
   - **(b) Contradicted but not resolved** — flag with `> ⚠️ Unverified: this claim from [[<meeting>]] may be outdated — no later source confirms or refutes it.`
   - **(c) Still valid** — retain unchanged.

5. Edit affected pages. Never silently delete — either replace with the updated claim + new source, or add the ⚠️ flag.

6. Review and update stale views in `views/`:
   - List all files in `views/`. For each, check whether it cites the purged meeting or draws from any page modified in step 5.
   - For every affected view, re-run its `prompt` frontmatter value against the updated wiki and overwrite the file with refreshed content and a new `generated` date.

7. Append to `wiki/log.md`:
   ```
   ## [YYYY-MM-DD] purge | <meeting name>
   - Pages modified: <list>
   - Claims removed: <count> | Claims flagged: <count> | Claims retained: <count>
   - Views regenerated: <list>
   ```

8. Report back: which pages were changed, what was removed or flagged, views regenerated, and whether any removals created orphaned references that need follow-up.
