# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

Personal knowledge base on the LLM Wiki pattern. **Domain:** AI-powered knowledge management (Sadra Sabouri, Sumit Gulwani, Souti Chattopadhyay).

- `raw-sources/` — immutable sources. Markdown extractions committed; binaries (`.eml`, `.vtt`, `.docx`) gitignored.
- `wiki/` — LLM-maintained pages. `concepts/` `people/` `projects/` `events/` hold canonical knowledge.
- `views/` — generated view artifacts (presentations, timelines, queries, etc.). All view commands write here.
- `.claude/commands/` — slash command implementations (full step-by-step instructions live there).

## Wiki Conventions

- Read `wiki/index.md` first on any query; update it on every ingest.
- Append to `wiki/log.md` on every operation: `## [YYYY-MM-DD] operation | title`.
- Every `[[wikilink]]` must resolve to an existing file in `wiki/` or `raw-sources/`. Raw sources link by filename: `[[Thursday demo]]` → `raw-sources/emails/Thursday demo.md`.
- Pages must be insightful — synthesize and connect, don't summarize.

## Slash Commands

### Operations

| Command | Usage | What it does |
|---------|-------|--------------|
| `/ingest` | `/ingest raw-sources/emails/new.md` | Read source → write wiki pages → update index, log, and regenerate relevant views |
| `/purge` | `/purge GMT20260316...transcript` | Supersede claims from a meeting → update wiki pages → regenerate affected views |
| `/lint` | `/lint [scope]` | Audit: broken links, orphans, contradictions, stale claims, index gaps |
| `/trim` | `/trim [scope]` | Remove deprecated concepts, superseded definitions, and outdated framings; distinct from purge (source-targeted) and lint (non-destructive) |
| `/clarify` | `/clarify [concept or "all"]` | Generate critical questions about definitions and concept relationships → user answers → wiki updated |

### Views — output saved to `views/`

| Command | Argument | Output |
|---------|----------|--------|
| `/query` | question | Markdown answer with `[[citations]]` — **default** |
| `/timeline` | concept or project | Chronological table of how the idea evolved across meetings |
| `/design-doc` | concept or project | Problem / Motivation / Approach / Open Questions |
| `/contribution-map` | concept or project | Attribution table: who introduced what, when, from which source |
| `/open-questions` | concept, project, or `all` | Grouped: design questions, tensions, missing pages, stale claims |
| `/person-brief` | `Person: topic` | Narrative on a person's position and how it evolved |
| `/presentation` | `<path-to-template>` | Fill a template file with wiki content; e.g. `/presentation .claude/templates/sumit-lightning.md` |
| `/digest` | `YYYY-MM-DD` | ≤10 insight-bullets on what is new since that date |
