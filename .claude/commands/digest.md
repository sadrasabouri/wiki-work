---
description: Executive summary of what is new in the wiki since a given date. Write one insight-bullet per significant development — not page counts, but what was learned. Useful at the start of a meeting or after a gap in engagement.
argument-hint: <YYYY-MM-DD>  optional — defaults to 7 days ago
---

Produce a Digest since: $ARGUMENTS

If no date is provided, use 7 days before today.

## Steps

1. Read `wiki/log.md`. Find all entries after `$ARGUMENTS`.

2. For each entry (ingest, purge, query, lint), read the pages that were created or modified.

3. For each new or significantly updated page, extract the one most important insight — not "a page was created about X" but "we now understand that X implies Y, which wasn't clear before."

4. Identify the sharpest open question that emerged since `$ARGUMENTS` — something that is now visible precisely *because* of the new material.

## Output Format

```markdown
## Digest — since $ARGUMENTS

### What's New
- **[[concept/event]]** — <the insight in one sentence; what this changes or clarifies>
- ...

### Most Important Open Question
<The single question that most needs answering now, given what was added.>

### What to Read First
If you have 10 minutes: [[page-1]], [[page-2]].
```

Keep the entire digest under 10 bullets. Density over completeness — if two entries say the same thing, merge them.

## Save Output

Save to `views/digest-<YYYY-MM-DD>.md` (using the argument date, or today's date if none given) with this frontmatter, followed immediately by a prompt indicator line before any content:

```yaml
---
tags: [view, digest]
prompt: /digest $ARGUMENTS
generated: YYYY-MM-DD
---

> *`/digest $ARGUMENTS`*
```

Append to `wiki/log.md`: `## [YYYY-MM-DD] view:digest | since $ARGUMENTS`
