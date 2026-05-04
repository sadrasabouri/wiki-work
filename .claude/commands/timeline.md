---
description: Show how a concept, decision, or project evolved chronologically across meetings — meeting by meeting, with inflection points highlighted.
argument-hint: <concept-name or project-name>
---

Produce a Timeline view for: $ARGUMENTS

## Steps

1. Read `wiki/index.md` to locate the target concept or project page. Read it.

2. Find all `wiki/events/` pages that link to or discuss `$ARGUMENTS`. Read each one.

3. If significant details are missing from the event pages, also read the corresponding raw transcripts they reference.

4. Build a chronological record. For each event, extract one line answering: *what was new, renamed, decided, or shifted about `$ARGUMENTS` after this meeting?*
   - If nothing changed, skip the event.
   - Highlight inflection points — moments where terminology changed, framing shifted, or a new contributor entered.

## Output Format

```
## Timeline: $ARGUMENTS

| Date | Development | Source |
|------|-------------|--------|
| YYYY-MM-DD | <what changed in one sentence> | [[event-page]] |
...

### Key Inflection Points
- **YYYY-MM-DD** — <why this meeting was the turning point>
```

End with a one-paragraph synthesis: where did this concept start, how did it evolve, where does it stand now?

## Save Output

Slugify the argument (lowercase, spaces → hyphens). Save the complete output as-is to `views/timeline-<slug>.md`.

Append to `wiki/log.md`: `## [YYYY-MM-DD] view:timeline | $ARGUMENTS`
