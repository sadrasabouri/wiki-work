---
description: Produce a targeted briefing on what a specific person thinks about a topic — their position, reasoning, and how it evolved across meetings.
argument-hint: <person-name>: <topic>  e.g. "Souti: steerability" or "Sumit: views"
---

Produce a Person Brief for: $ARGUMENTS

Parse the argument as `<person>: <topic>`. If no topic separator is present, produce a general brief on the person's contributions.

## Steps

1. Read `wiki/people/<person-slug>.md`.

2. Find all `wiki/events/` pages where this person appears and the topic is discussed. Read them.

3. Where an event page cites a key statement, also read the relevant section of the raw transcript for direct quotes.

4. Extract:
   - Their initial position or framing of the topic
   - The arguments or reasoning they gave
   - Any moments where their framing shifted across meetings — note what changed and what prompted it
   - Any direct quotes that capture their view precisely

5. Write as **narrative, not bullets**. "Souti's framing shifted from X to Y after the Mar 16 meeting" captures more than a bulleted list of positions. Use `[[wikilinks]]` to anchor claims to their sources.

## Output Format

2–4 paragraphs of narrative markdown. End with:

```markdown
### Direct Quotes
- "[quote]" — [[raw-source]]

### Open: What we don't know
<Any aspect of their view that is missing from the record or genuinely unclear>
```

## Save Output

Create a short slug: **at most 3 words** from the argument, lowercase, joined with hyphens (e.g. `sumit-views`, `souti-creativity`). Replace `:` with `-`, drop stop words and articles. Save to `views/person-brief-<slug>.md` with this frontmatter, followed immediately by a prompt indicator line before any content:

```yaml
---
tags: [view, person-brief]
prompt: /person-brief $ARGUMENTS
generated: YYYY-MM-DD
---

> *`/person-brief $ARGUMENTS`*
```

Append to `wiki/log.md`: `## [YYYY-MM-DD] view:person-brief | $ARGUMENTS`
