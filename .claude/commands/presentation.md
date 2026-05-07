---
description: Generate a presentation by filling a template file with content synthesized from the wiki.
argument-hint: <path-to-template>  e.g. "templates/sumit-lightning.md"
---

Generate presentation from template: $ARGUMENTS

## Steps

1. **Load the template.** Read `$ARGUMENTS`. Extract frontmatter parameters (audience, concepts, duration, etc.). Substitute every `{{var}}` placeholder in the template body — including inside `> fill:` prompts and section headings — with the matching frontmatter value before doing anything else. The section headings and substituted `> fill:` prompts define the slide structure.

2. **Read the wiki.** Read `wiki/index.md`. Then read all pages listed under the frontmatter `concepts` key, plus any pages those link to that are relevant. If no `concepts` key is set, read all concept and project pages.

3. **Fill each section.** For every `## Section` in the template, execute its `> fill:` prompt against the wiki content. Each section becomes one slide:
   - Write 3–5 bullets drawn from specific wiki pages — concrete and grounded, not generic
   - Cite the originating raw source inline: `*[[raw-sources/path/to/file]] · Person*` — use the transcript or document the claim came from, not just the wiki page that synthesized it
   - Add a `> speaker note:` line with what to say aloud (1–2 sentences max)
   - Preserve any static content in the template that is not inside a `> fill:` block

4. **Save output.** Derive the output slug from the template filename (basename without extension). Write to `views/presentation-<slug>.md`. The output file's frontmatter must include all fields from the template frontmatter plus:
   ```
   prompt: /presentation $ARGUMENTS
   generated: YYYY-MM-DD
   ```
   Immediately after the frontmatter (before the first heading), add a collapsed prompt callout:
   ```
   > [!note]-
   > prompt: *`/presentation $ARGUMENTS`*
   ```
   Append to `wiki/log.md`:
   ```
   ## [YYYY-MM-DD] view:presentation | $ARGUMENTS
   ```

5. **Report back:** the slide titles and a one-sentence presenter brief.
