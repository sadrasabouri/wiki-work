---
description: Lint the wiki for consistency issues, update stale pages to reflect the latest iteration of ideas, and ask clarification questions when concepts are ambiguous or underdefined. Run periodically to keep the KB healthy.
argument-hint: [scope]  optional — a subdirectory or concept name to limit the check
---

Lint the wiki${ $ARGUMENTS ? " — scope: $ARGUMENTS" : " — full scan" }.

## Steps

1. **Structural fixes** (auto-fix, don't ask):
   - Broken `[[links]]` — verify each resolves to a file in `wiki/` or `raw/`; fix obvious mismatches
   - Orphan pages — add cross-references where the connection is clear
   - Index gaps — add missing entries to `wiki/index.md`

2. **Semantic updates** (update pages in place, preserve source citations):
   - Stale claims — find claims from early sources on topics refined in later meetings; update to reflect the latest iteration; keep earlier framing as a dated note rather than deleting it
   - Contradictions — resolve using the most recent source; if genuinely contested, reframe as an explicit tension
   - Concept drift — find pages whose description no longer matches how the concept is used in recent event pages; update to the current framing and note when it shifted

3. **Clarification questions** — collect all ambiguous cases first, then ask them together before writing:
   - A concept used with subtly different meanings across sources (one concept or two?)
   - A proposed idea with no clear record of adoption or rejection
   - Attribution conflicts where source priority is unclear
   - Concept stubs with too little context to write accurately

   Format: `I need your input before updating these: 1. [page] — [question] ...`
   After receiving answers, apply them.

4. **Review and update stale views in `views/`:**
   - List all files in `views/`. For each, check whether any wiki page it draws from was updated in steps 1–2.
   - For every affected view, re-run its `prompt` frontmatter value against the updated wiki and overwrite the file with refreshed content and a new `generated` date.

5. **Report and log:**
   - One section per check: ✅ clean / ⚠️ updated / ❌ open
   - Append to `wiki/log.md`:
     ```
     ## [YYYY-MM-DD] lint | [scope or "full scan"]
     - Pages fixed: <list>
     - Pages updated: <list>
     - Views updated: <list>
     - Open issues: <list>
     ```
