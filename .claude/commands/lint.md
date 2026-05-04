---
description: Lint the wiki for consistency issues — broken links, orphan pages, contradictions, stale claims, and missing concept pages. Run periodically to keep the KB healthy.
argument-hint: [scope]  optional — a subdirectory or concept name to limit the check
---

Lint the wiki${ $ARGUMENTS ? " — scope: $ARGUMENTS" : " — full scan" }.

## Checks to Run

### 1. Broken wikilinks
For every `[[link]]` in every wiki page, verify a file with that name exists in `wiki/` or `raw/`. List all broken links with the page they appear in.

### 2. Orphan pages
Find wiki pages not referenced by any other wiki page or by `wiki/index.md`. List them — they may need cross-references added or may be deletable.

### 3. Missing concept pages
Find concept names mentioned inline in wiki pages (capitalized noun phrases used as if they should have pages) that don't have a corresponding file in `wiki/concepts/`. List candidates.

### 4. Contradictions
Look for claims that conflict between pages — same concept described differently, dates that don't match, people attributed differently. Flag each pair with the two conflicting statements.

### 5. Stale claims
Find claims in wiki pages that cite only early sources (before 2026-04) on topics that were actively discussed in later meetings. These may have been refined or superseded without the page being updated. Flag them.

### 6. Index completeness
Compare `wiki/index.md` against all `.md` files in `wiki/concepts/`, `wiki/people/`, `wiki/projects/`, `wiki/events/`. List any pages missing from the index.

## Output

Produce a report with one section per check. Use ✅ for clean, ⚠️ for warnings, ❌ for errors. End with a prioritized fix list: which issues to address first and why.
