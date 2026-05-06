## Open Questions: all

### Unresolved Design Questions

- **Should views and workflows be defined together or separately?** — raised explicitly by Sumit in [[Sadra-2May2026-TRANSCRIPT2]] ("Should we separate this out? Should we, should we not?"), left open; the wiki presents them as cleanly distinct but the transcript shows ambiguity. The argument for separation: reusability (same view, multiple workflows). The argument against: a single prompt naturally combines both; forcing separation adds friction.

- **How does percolation actually work?** — [[temporal-knowledge]] names percolation as a key operation but gives no design; [[Sadra-2May2026-TRANSCRIPT]] says "Sadra explored percolation approaches (changes ripple upward through dependent pages)" without specifying any mechanism. Two strategies mentioned in transcript (percolation, targeted invalidation) but no decision recorded.

- **How are semi-private mashing filters specified and enforced?** — [[semi-private-mashing]] describes filtering as "a first-class operation" but no design exists. The [[Thursday demo]] email mentions "differential privacy norms" as relevant but this thread was never developed. The [[Sadra-1May2026-Transcript]] shows the team agreeing to "talk about it to sell the idea" while acknowledging Sadra cannot implement it in time.

- **What is the summative study design for Spreadsheet Verification?** — the formative study (8 sessions) is done; the summative study is the next step, but no design for participant selection, tasks, or evaluation metrics appears anywhere. [[agent-traceability-steerability]] says "Active Feb–March 2026" but the summative study is still planned as of May.

- **What provenance scheme should the KB use?** — [[provenance-tracking]] lists three options (frontmatter flags, git blame, inline citations) with no decision between them. The current wiki uses inline wikilinks as citations but this is not systematically enforced; there are claims on several pages without citations.

- **How should obsolete DAG paths be handled after user edits?** — raised by [[souti-chattopadhyay]] in [[GMT20260316-200648_Recording.transcript]]: once a user chooses a path, alternatives become irrelevant — should the DAG prune them? Sadra called it "out of scope for this paper" but the design question was never resolved for the system.

- **Is the KB queryable at a point in time?** — [[temporal-knowledge]] states "the KB should be queryable at a point in time" as a requirement, but no implementation path is specified. Two options are named (git history, explicit timestamps on claims) with no decision.

---

### Conceptual Tensions

- **Semi-private mashing as core contribution vs. unverifiable claim** — [[wiki-kb-project]] and [[semi-private-mashing]] both frame it as a clear novel contribution. But in [[Sadra-1May2026-Transcript]], Sadra explicitly says: "I think this is not a good motivation for us... this is something that is very hard to claim, and I think this is not the core contribution. We don't know if the digested information in the wiki can return back to the actual information or not." Souti and Sumit overrode this concern for the pitch — but the technical objection was never resolved and doesn't appear anywhere in the wiki. The wiki presents the contribution as more settled than it is.

- **Views and workflows as distinct vs. naturally combined** — [[views]] and [[workflows]] treat the declarative/constructive split as a clean boundary. But [[Sadra-2May2026-TRANSCRIPT2]] records Sumit saying "you can imagine that you can write both the constructive parts as well as the declarative part together as one prompt." The separation is an analytical preference, not an architectural necessity — and the wiki doesn't surface this.

- **Steerability as user-initiated vs. agent-initiated** — [[steerability]] frames steerability as a user action (human intervenes in agent process). [[bidirectional-collaboration]] and [[human-as-api]] imply the inverse: the agent should proactively create steer points by calling the human at the right moments. These are not contradictory, but the wiki treats them as separate concerns rather than as two sides of the same design space.

- **Views as mitigation for the productivity-creativity tradeoff** — [[productivity-creativity-tradeoff]] claims "[[views|Views]] are one mitigation" for the reduction of creative insight. No reasoning or evidence for this is given. The mechanism would need to be: because the human defines what to see (the view prompt), they retain the creative framing work. But this is speculative and was never discussed in any transcript — it may be a confabulation in the wiki page itself.

- **Efficiency via intermediate summaries as a "novel contribution"** — [[wiki-kb-project]] lists this as the third contribution alongside views and semi-private mashing. But it appears nowhere else in the wiki — no dedicated concept page, no design, no discussion of what makes this approach novel vs. existing caching and summarization systems. It was mentioned briefly in [[Sadra-1May2026-Transcript]] without being elaborated.

- **Agent as source type vs. human as source** — [[workflows]] describes a "researcher agent" as a new source type for the KB. [[Sadra-2May2026-TRANSCRIPT2]] shows Sumit noting a potential asymmetry: "if I want authenticity, if I want my voice in my summary and so on, then whenever the choice is pending, everything has to bias ourselves... with respect to the human output." This creates a trust hierarchy between human-sourced and AI-sourced content that the wiki doesn't address.

---

### Missing Pages

- `[[intermediate-summaries]]` — listed as the third novel contribution of the [[wiki-kb-project]] (applying views to pre-computed summaries for efficiency), but has no dedicated concept page and is not defined or designed anywhere in the wiki.

- `[[interaction-md]]` — the `interaction.md` concept from [[human-as-api]]: an agent-maintained preference file accumulated from past interaction trajectories. Mentioned as a key design idea; no page.

- `[[grounded-theory]]` — discussed extensively in [[Sadra-1May2026-Transcript]] and [[Sadra-2May2026-TRANSCRIPT2]] as the canonical example of a creative workflow; the name and methodology are referenced but never documented in the wiki. Central to the [[workflows]] concept.

- `[[researcher-agent]]` — mentioned in [[workflows]] as "a new source type" that feeds AI-generated related-work into the KB. Discussed in [[Sadra-2May2026-TRANSCRIPT2]] as a planned component. No page.

- `[[unknown-unknowns]]` — the idea of asking the AI "what have none of us thought about?" emerged from the [[GMT20260316-200648_Recording.transcript|Mar 16]] formative study as a user-expressed need, was discussed by Sumit as potentially "a big enough idea to invest something into it," and connects directly to the [[gulf-of-envisioning]] problem. No page.

- `[[degree-of-separation]]` — invoked in [[Thursday demo]] as the motivation for semi-private mashing ("every person is connected to every other person through just five or six connections"); used as a philosophical anchor for the project. No page.

---

### Potentially Stale Claims

- [[agent-traceability-steerability]] states "Active Feb–March 2026" — the summative study is actively planned as of May 2026; the project is not concluded. The status description is stale.

- [[wiki-kb-project]] states "The presentation on Thursday is planned to be generated from the KB itself" — today is Thursday May 3, 2026 (the day of ingestion). This is now a past event, not a future plan. The page should be updated to reflect whether this was done and what the outcome was.

- [[gulf-of-envisioning]] states preloaded Q&A was "validated as a user need in the Mar 16 formative study results" — what was validated is that users *wanted rationalization for each step* (they asked why steps were taken). Preloaded Q&A is a proposed *solution* to that need, proposed by Sadra, but not yet validated in the summative study. The framing conflates need-validation with solution-validation.

- [[semi-private-mashing]] describes filtering as "the [[wiki-kb-project|Wiki KB Project]] treats this as a first-class operation rather than a manual preprocessing step" — but as of [[Sadra-1May2026-Transcript]], Sadra explicitly questioned whether it was implementable as a technical claim and the team agreed to pitch it as a direction rather than an implemented feature. "First-class operation" overstates the current state.

- [[provenance-tracking]] proposes "inline citations — every claim linked to a raw source; if no source exists, it's unverified" — this is a design aspiration, not current practice. Several pages in the wiki contain claims without wikilink citations (e.g., [[steerability]], [[gulf-of-envisioning]]).

---

### Top 3 Priorities Before the Next Phase

1. **Resolve the semi-private mashing status** — the gap between how the wiki presents it (core novel contribution, first-class operation) and what the May 1 transcript shows (team agreed it's a pitch direction, not a technical claim) is the largest misrepresentation in the KB. Before any paper or public pitch, the team needs to decide: is this a research contribution or a design vision? [[semi-private-mashing]], [[wiki-kb-project]]

2. **Design the views/workflows separation** — this is the central architectural question of the Wiki KB Project. Sumit explicitly left it open in [[Sadra-2May2026-TRANSCRIPT2]]. Everything downstream (implementation, efficiency claims, user study design) depends on this decision. A dedicated concept page for `[[intermediate-summaries]]` would also emerge from this work. [[views]], [[workflows]]

3. **Create the missing `[[intermediate-summaries]]` concept page** — it is the *third named contribution* of the project and has no dedicated page, no design, and no discussion of what makes it novel. Without this, the project's three-contribution claim is two-thirds specified. [[wiki-kb-project]]
