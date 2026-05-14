---
description: Read the whole wiki and generate wild new ideas — unexpected connections between concepts, unexplored implications of existing ideas, and provocative hypotheses the team hasn't stated yet.
argument-hint: (no argument — always runs across the whole wiki)
---

Brainstorm across the entire wiki.

## Steps

1. Read `wiki/index.md` to get the full map of concepts, people, projects, and events.

2. Read every page in `wiki/concepts/`, `wiki/projects/`, and `wiki/people/`. Skim `wiki/events/` for ideas that were raised but never developed into concept pages.

3. Hold all of it in mind and generate ideas in three modes:

   **Mode 1 — Unexpected Connections**
   Find pairs (or triples) of concepts that are documented separately but have never been explicitly linked. The link should be non-obvious: not "these are related" but "if X is true, then Y implies Z in a way nobody has written down." Aim for at least 5 connections.

   **Mode 2 — Unexplored Implications**
   Pick the most structurally consequential ideas in the wiki. Push each to its logical extreme: "if we take this seriously, what does it mean that nobody has said yet?" These should feel slightly uncomfortable — the kind of claim that, if true, would require rethinking something the team currently takes for granted. Aim for at least 4 implications.

   **Mode 3 — Provocative Hypotheses**
   Generate falsifiable claims — things that might be true but would surprise the team if confirmed. Frame each as a testable proposition, not a vague conjecture. Each hypothesis should name who or what would be most challenged if it turned out to be correct. Aim for at least 4 hypotheses.

4. Do NOT hedge excessively. The value is in the wildness. Flag only the ideas you believe are genuinely speculative (not grounded in existing wiki content) with a ⚡ marker. Ideas that are grounded but underdeveloped get no marker.

## Output Format

```markdown
## Brainstorm — YYYY-MM-DD

### Unexpected Connections

- **[[concept-a]] × [[concept-b]]**: <one sentence describing the non-obvious link and why it matters>
  > <Optional: one sentence on what this connection implies or unlocks>

...

### Unexplored Implications

- **[[concept]]** taken to its extreme: <claim — stated boldly, not hedged>
  > <What this would require the team to change or confront>

...

### Provocative Hypotheses

- ⚡ <Hypothesis stated as a proposition> — if true, this challenges [[person or concept]] most directly.

...

### One Big Bet
A single sentence: the most consequential idea from above, if the team were to act on only one.
```

## Save Output

Save to `views/brainstorm-YYYY-MM-DD.md` with this frontmatter, followed immediately by a collapsed prompt callout before any content:

```yaml
---
tags: [view, brainstorm]
generated: YYYY-MM-DD
---

> [!note]-
> prompt: *`/brainstorm`*
```

Append to `wiki/log.md`: `## [YYYY-MM-DD] view:brainstorm | whole wiki`
