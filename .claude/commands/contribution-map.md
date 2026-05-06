---
description: Show who contributed which ideas, when, and from which source. Useful for attribution, understanding intellectual lineage, and identifying whose perspective is missing.
argument-hint: <concept-name or project-name>
---

Produce a Contribution Map for: $ARGUMENTS

## Steps

1. Read the wiki page for `$ARGUMENTS`. Note every distinct idea, framing, or naming decision.

2. Read all `wiki/events/` pages and `wiki/people/` pages that reference `$ARGUMENTS`.

3. For each distinct intellectual contribution — a new idea, a reframing, a term coined, a connection drawn — trace it to the earliest source where it appears. Use raw transcript links where possible.

4. Build the attribution table. If multiple people arrived at the same idea independently, list each. Flag contributions with no clear originator.

## Output Format

```markdown
## Contribution Map: $ARGUMENTS

| Person | Contribution | Date | Source |
|--------|--------------|------|--------|
| [[person]] | <what they introduced — one sentence> | YYYY-MM-DD | [[raw-source]] |
...

### Observations
- <Any surprising attributions, e.g. an idea assumed to be X's was actually first introduced by Y>
- <Any contributions with unclear origin>
- <Whose voice is notably absent — contributors not in the record who might have relevant views>
```

## Save Output

Create a short slug: **at most 3 words** from the argument, lowercase, joined with hyphens (e.g. `views`, `wiki-kb`, `sumit`). Drop stop words and articles. Save to `wiki/contribution-map-<slug>.md`.

Append to `wiki/log.md`: `## [YYYY-MM-DD] view:contribution-map | $ARGUMENTS`
