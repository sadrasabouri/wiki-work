---
description: Generate a shareable design document for a concept or project — problem, motivation, approach, and open questions — synthesized from the wiki. Suitable for onboarding or stakeholder meetings.
argument-hint: <concept-name or project-name>
---

Generate a Design Document for: $ARGUMENTS

## Steps

1. Read the wiki page for `$ARGUMENTS` (check `wiki/concepts/` and `wiki/projects/`).

2. Find all event pages and emails that substantively discuss it. Read them. If a key detail traces back to a specific transcript, read that too.

3. Fill the template below. Rules:
   - Every section must cite at least one raw source or wiki page inline
   - *Motivation* must include at least one concrete story or example from the raw sources
   - *Open Questions* must reflect real unresolved tensions from the sources — not invented ones
   - Write for an intelligent reader who is new to this project

4. After the first pass, re-read your output. Second pass: remove redundancy, sharpen the narrative, ensure every claim has a citation.

## Save Output

Create a short slug: **at most 3 words** from the argument, lowercase, joined with hyphens (e.g. `views`, `wiki-kb`, `agent-lens`). Drop stop words and articles. Save to `views/design-doc-<slug>.md` with this frontmatter, followed immediately by a collapsed prompt callout before any content:

```yaml
---
tags: [view, design-doc]
generated: YYYY-MM-DD
---

> [!note]-
> prompt: *`/design-doc $ARGUMENTS`*
```

Append to `wiki/log.md`: `## [YYYY-MM-DD] view:design-doc | $ARGUMENTS`

## Output Template

```markdown
# Design Document: $ARGUMENTS

## Problem
<What gap or pain point does this address? Be specific — who experiences it, when, how often.>

## Motivation
<Why does this matter? Include at least one concrete story or real example from the raw sources.>

## Approach
<The proposed mechanism or design. How does it work? What are the key decisions made so far?>

## Prior Art & Related Concepts
<What existing systems or concepts does this relate to? What does it borrow from, what does it depart from?>

## Open Questions
<Unresolved design choices, tensions, or risks — sourced from the actual discussions, not invented.>
```
