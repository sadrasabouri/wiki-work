---
description: Surface unresolved tensions, open design questions, contradictions, and ideas mentioned but never acted on. Most useful before a meeting or when starting a new research phase.
argument-hint: <concept-name, project-name, or "all">
---

Surface Open Questions for: $ARGUMENTS

## Steps

1. If `$ARGUMENTS` is "all", read all pages in `wiki/concepts/` and `wiki/projects/`. Otherwise, read the target page(s) and all pages they link to.

2. Scan for signals of unresolved issues:
   - **Hedged language** — "might," "unclear," "TBD," "we think," "possibly"
   - **Explicit disagreements** — claims in one source contradicted by another
   - **Silent gaps** — concepts mentioned in early sources but absent from later ones (resolved silently? forgotten? deprecated?)
   - **Cited-but-missing pages** — `[[wikilinks]]` to pages that don't exist yet
   - **Design choices mentioned but not made** — options raised without a decision recorded

3. Group findings into four buckets:
   - **Unresolved design questions** — choices that need to be made
   - **Conceptual tensions** — ideas that are in friction with each other
   - **Missing pages** — concepts that need their own page
   - **Potentially stale claims** — information that may have been superseded without the page being updated

## Output Format

```markdown
## Open Questions: $ARGUMENTS

### Unresolved Design Questions
- <Question> — raised in [[source]], no resolution found

### Conceptual Tensions
- <Tension between X and Y> — [[page-a]] says one thing, [[page-b]] implies another

### Missing Pages
- `[[concept-name]]` — mentioned in [[page]], no page exists

### Potentially Stale Claims
- [[page]] claims X, sourced from [[early-meeting]] — no later source confirms
```

End with a prioritized top-3: which open questions most need resolution before the next phase of work.

## Save Output

Slugify the argument (lowercase, spaces → hyphens). Save the complete output as-is to `wiki/open-questions-<slug>.md`.

Append to `wiki/log.md`: `## [YYYY-MM-DD] view:open-questions | $ARGUMENTS`
