---
description: Render the KB as a presentation slide outline. This is the self-referential view — the wiki generates the talk about itself. Specify a topic and audience; each slide title is a sub-view prompt drawn from the wiki.
argument-hint: <topic> for <audience>  e.g. "wiki-kb-project for new collaborators" or "views for stakeholder demo"
---

Generate a Presentation for: $ARGUMENTS

Parse the argument as `<topic> for <audience>`. If no audience is specified, assume a technically fluent new collaborator.

## Steps

1. Read `wiki/index.md`. Identify all pages relevant to `<topic>`.

2. Read the most relevant concept, project, and event pages. If a specific raw source should be cited verbally, note it.

3. Define the narrative arc: what 5–8 points must land for `<audience>` to leave understanding `<topic>`? These become the slide titles — each one is a sub-view prompt (e.g. "Why existing KB tools fall short" rather than "Background").

4. For each slide:
   - Write 3–5 bullets drawn directly from wiki pages — concrete, specific, not generic
   - Add a `> speaker note:` line: what to say verbally, which raw source to reference by name

5. The final slide must be an **Open Questions** slide — run a focused `open-questions` scan on the topic and use the top-3 results.

## Output Format

```markdown
# Presentation: $ARGUMENTS

## [Slide 1 Title]
- bullet
- bullet
- bullet
> speaker note: [what to say; cite [[source]] if relevant]

## [Slide 2 Title]
...

## Open Questions
- <top question 1>
- <top question 2>
- <top question 3>
```

After the outline, add a one-paragraph **presenter brief**: what to emphasize, what to skip if short on time, and what question the audience is most likely to ask.

## Save Output

Slugify the argument (lowercase, spaces → hyphens). Save the complete output as-is to `views/presentation-<slug>.md`.

Append to `wiki/log.md`: `## [YYYY-MM-DD] view:presentation | $ARGUMENTS`
