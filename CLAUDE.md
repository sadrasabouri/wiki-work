# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A personal knowledge base built on the LLM Wiki pattern. Raw sources (emails, meeting transcripts) live in `raw/` — immutable, never modified. The wiki is a separate layer of LLM-maintained markdown files that synthesizes those sources into structured, interlinked knowledge. You write and maintain the wiki; the human curates sources and asks questions.

**Domain:** Research on AI-powered knowledge management (Sadra Sabouri, Sumit Gulwani, Souti Chattopadhyay).

## Layers

- `raw/` — immutable source files. Markdown extractions of each source (`.md`) are committed; binary originals (`.eml`, `.vtt`, `.docx`) are gitignored and local-only.
- `wiki/` — your layer. All wiki pages live here. You create and maintain everything in this directory.

## Wiki Directory Structure

- `wiki/concepts/` — conceptual building blocks (views, workflows, steerability, etc.)
- `wiki/people/` — person profiles
- `wiki/projects/` — project overviews
- `wiki/events/` — meeting summaries; one page per meeting, named `YYYY-MM-DD.md`, linking back to the raw transcript

## Raw Source Frontmatter

```yaml
---
timestamp: "ISO-8601"
source_type: "eml | docx | vtt"
tags: [extracted]
---
```

## Wiki Conventions

- `wiki/index.md` — catalog of all wiki pages: one line per page with a link and summary, organized by category. Read this first when answering queries. Update it on every ingest.
- `wiki/log.md` — append-only record of ingests, queries, and lint passes. Each entry: `## [YYYY-MM-DD] operation | title`.
- All cross-references are inline wiki links `[[Page Name]]` within body text, not footnotes or lists. Every link must resolve to an existing `.md` file in `wiki/` or `raw/`.
- Pages should be insightful — synthesize and connect ideas, don't just surface-level summarize.
- Raw sources are linkable by filename: `[[Thursday demo]]` resolves to `raw/emails/Thursday demo.md`; `[[GMT20260316-200648_Recording.transcript|Mar 16 meeting]]` resolves to the corresponding transcript.

## Operations

**Ingest** — when a new source is added to `raw/`: read it, discuss key takeaways, write a summary page in `wiki/`, update `wiki/index.md`, update any relevant existing wiki pages, append to `wiki/log.md`.

**Query** — read `wiki/index.md` to find relevant pages, synthesize an answer with `[[page]]` citations. File valuable answers back into the wiki as new pages.

**Lint** — periodically check for: contradictions between pages, stale claims superseded by newer sources, orphan pages, missing cross-references, concepts mentioned but lacking their own page.
