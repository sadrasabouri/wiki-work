# LLM Wiki

A knowledge base that reads your notes, meetings, and emails — and lets you query, summarize, and explore them through Claude Code.

Drop in raw sources (transcripts, emails, documents). Ask questions. Get synthesized answers with citations. The KB builds up over time and gets smarter as more sources are added.

---

## Two ways to use it

**Personal knowledge indexing** — connect your own meeting recordings, notes, and emails. Ask "what did I decide about X?" or "how did my thinking on Y evolve?" Get answers grounded in your actual words, not AI hallucination.

**Team knowledge sharing** — maintain a shared KB across a research group or team. Each person ingests their own sources; the KB surfaces connections across them. Generate onboarding docs, design documents, and contribution maps automatically.

---

## How it works

```
raw/          ← your source files go here (transcripts, emails, notes)
wiki/         ← Claude maintains this: concept pages, people, projects, events, and views
```

You never edit `wiki/` directly. Claude does, via slash commands.

---

## Getting started

**1. Add Claude Code**

This project runs on [Claude Code](https://claude.ai/code). Install the CLI and open this directory.

**2. Drop in a source file**

Put a meeting transcript, email export, or document in `raw/`. Markdown works best; `.eml`, `.vtt`, and `.docx` are supported but gitignored.

**3. Ingest it**

```
/ingest raw/your-file.md
```

Claude reads the source, extracts key ideas, writes wiki pages, and updates the index.

**4. Ask questions**

```
/query what did we decide about the API design?
/query who has been most active on the authentication work?
```

Answers come with `[[citations]]` back to source files.

---

## Slash commands

### Add and maintain knowledge

| Command | Example | What it does |
|---------|---------|--------------|
| `/ingest` | `/ingest raw/meeting-2026-05.md` | Read source, write wiki pages, update index |
| `/purge` | `/purge raw/old-transcript.md` | Remove superseded claims when a source is retracted |
| `/lint` | `/lint` | Find broken links, orphan pages, stale claims |

### Query and explore

| Command | Example | What it does |
|---------|---------|--------------|
| `/query` | `/query how did the design evolve?` | Synthesized answer with citations |
| `/timeline` | `/timeline authentication` | How a concept changed across meetings |
| `/contribution-map` | `/contribution-map API design` | Who introduced which ideas, when |
| `/open-questions` | `/open-questions all` | Unresolved decisions, tensions, missing pages |
| `/person-brief` | `/person-brief Alice: security` | What one person thinks about a topic |
| `/design-doc` | `/design-doc caching layer` | Problem / approach / open questions doc |
| `/digest` | `/digest 2026-04-01` | What's new since a date — useful before meetings |
| `/presentation` | `/presentation onboarding for new engineers` | Slide outline generated from the KB |

---

## What the KB produces

Every view command saves a Markdown file to `wiki/` — visible as a regular page in Obsidian or any Markdown viewer. Examples:

- `wiki/timeline-authentication.md` — how a design evolved
- `wiki/open-questions-all.md` — what needs a decision
- `wiki/contribution-map-api.md` — who owns which ideas

---

## Privacy

Raw sources stay in `raw/` and are never modified. If you need to share a KB without sharing private sources, use `/purge` to remove specific sources and regenerate affected pages.

For team use, the semi-private mashing pattern lets you filter a private 1:1 transcript so only the relevant, non-sensitive parts flow into the shared KB — without the full source ever touching the shared layer.
