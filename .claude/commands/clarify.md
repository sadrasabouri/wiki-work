---
description: Generate critical questions about wiki concept definitions, relationship assumptions, and conceptual boundaries. Present questions inline for user answers, then update affected pages.
argument-hint: [concept-name or "all"]  optional — limit to a concept and its neighbors; default is all concepts
---

Audit wiki definitions and assumptions${ $ARGUMENTS && $ARGUMENTS !== "all" ? " — scope: " + $ARGUMENTS : " — full graph" }.

## Steps

### Phase 1: Generate Questions

1. **Inventory scope.** Read `wiki/index.md`. If `$ARGUMENTS` names a concept, read that page plus every concept it links to. If "all" or empty, read all pages in `wiki/concepts/`.

2. **Check definitional precision.** For each concept:
   - Is the definition sharp enough to exclude adjacent concepts? (e.g., can you tell from the definition alone whether a given real-world example is a View vs. a Workflow?)
   - Are terms used in the definition themselves defined — or do they silently inherit meaning from context?
   - Does the page give at least one counterexample — something that is *not* this concept but might be confused for it?

3. **Check relationship consistency.** Across pages:
   - If page A claims "A depends on / enables / is a subtype of B," does B's page acknowledge A?
   - If two concepts are described as distinct, is the distinction operationalizable — can you point to a case where one applies but the other does not?
   - Are there concepts that appear to be the same thing named differently (possible duplicate), or one concept that has silently split into two?

4. **Surface implicit assumptions.** For each concept:
   - What does this definition assume about the system, user, or environment that is never stated?
   - Under what conditions would the definition break down or not apply?
   - Are there concepts used in examples but never formally connected to this one?

5. **Prioritize and limit.** Select the **6–10 most consequential questions** — the ones where the user's answer would most change how the wiki represents a concept or relationship. Skip questions whose answer is obvious from existing pages. Skip purely stylistic issues.

6. **Group and present questions inline** (do NOT save a file):

```
## Clarify — [scope]

**Definitional Gaps**
1. [[page]] — [what is unclear or missing from the definition]
   → (a) [option] (b) [option] (c) [option]

**Relationship Mismatches**
2. [[page-a]] ↔ [[page-b]] — [claim in A not reflected in B, or vice versa]
   → (a) [option] (b) [option]

**Implicit Assumptions**
3. [[page]] — [assumption that is load-bearing but unstated]
   → (a) state it explicitly as: "..." (b) challenge it — the actual constraint is ... (c) leave implicit, it's obvious from context

**Possible Duplicates or Splits**
4. [[page-a]] vs [[page-b]] — [why they might be the same concept, or why one concept might be two]
   → (a) merge into [which] (b) they're distinct — the distinction is ... (c) one subsumes the other
```

### Phase 2: Apply Answers

After the user responds with answers:

7. **Update wiki pages.** For each answered question, make the minimal targeted edit:
   - Definitional gap → add the missing boundary or counterexample to the concept page
   - Relationship mismatch → add the missing cross-reference or correct the claim in one or both pages
   - Implicit assumption → add an explicit note in the relevant section (not a comment — integrate it into the prose)
   - Duplicate/split → merge pages or sharpen the distinction with an explicit contrast paragraph

8. **Do not invent.** If the user's answer is "I don't know" or "leave it open," mark it as an open question in the page (use hedged language: "It is unclear whether...") rather than guessing.

9. **Append to `wiki/log.md`:**
   ```
   ## [YYYY-MM-DD] clarify | [scope] — N questions resolved
   - Pages updated: <list>
   - Open issues left: <list>
   ```

10. **Report back:** which pages changed, what the key updates were, and any questions left unresolved.
