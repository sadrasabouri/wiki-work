---
tags: [view, presentation]
target: views, workflows
audience: distinguished AI practitioners (Satya's office)
generated: 2026-05-05
note: audience updated per Sumit's feedback in Sadra-5May2026-TRANSCRIPT2; restructured to 3 slides
---

# Presentation: "Views and Workflows for Knowledge Bases" for Distinguished AI Practitioners

## Views, Not Documents

- Every document — PowerPoint, Word, design doc, status report — is actually a **view**: a template whose holes are prompts over a knowledge base ([[views]])
- The insight isn't new: **dashboards** auto-update when data changes; **Excel formulas** recompute when inputs change; **Excel Equals Copilot** applies a prompt when the cell re-triggers ([[living-system]])
- These only worked before for *objective*, code-expressible computation. AI enables the same recalc model for *subjective* and *aesthetic* content — summaries, narratives, creative analysis
- A knowledge base is: a timestamped stream of raw sources, with structured views automatically maintained on top — **views that rewrite themselves as the stream grows**

> speaker note: The recalc framing is the anchor for this slide — your audience will have used Excel formulas and will feel the click immediately. The key move is "dashboards and formulas worked for code; now AI makes the whole document recalcable." Reference [[Sadra-5May2026-TRANSCRIPT2]] where Sumit articulated this as "the heart of it." Don't use "views not documents" as a slogan until you've landed the analogy — the analogy earns the slogan. Mention that the document summarizing this research was itself generated as a view, updated as new transcripts arrived. That's the self-referential proof point.

## The Organizational Brain

- An individual's knowledge base is bounded by what they personally read, hear, and remember. An organizational brain is not ([[semi-private-mashing]], [[digital-twins]])
- AI grounded in a 10,000-person org's transcripts, emails, and design docs can: surface an idea neither team had alone; identify two people in different orgs working on the same hidden problem; retrieve tacit knowledge ("who to talk to about X, and how they handle disagreement")
- The PageRank analogy: PageRank borrowed the citation-network idea from academic publishing and applied it to the web — a cross-domain insight that transformed how we navigate information. Cross-organizational synthesis at scale is the same kind of combinatorial creativity
- **"Satya, imagine your power when the Microsoft brain comes up"** — the CEO's permission scope, already the broadest in the org, combined with a wiki spanning all of Microsoft gives strategic intelligence no individual can have today

> speaker note: This is the slide that makes the audience feel the scale. Don't start with Satya — earn it. Start with the contrast: what can one person know vs. what 10,000 people collectively know but never share. The PageRank analogy (from [[Sadra-5May2026-TRANSCRIPT2]]) is the associative-thinking example to use for a technically literate audience. Close with the Satya line — it's cheesy, but it lands for a Microsoft internal audience. Reference [[digital-twins]] for the longer-term vision (onboarding from months to days, async collaboration at sync quality).

## Semi-Private Mashup

- The organizational brain only forms if individuals choose to contribute — that choice depends on **credit** and **privacy** ([[semi-private-mashing]])
- Most KB tools force a binary: include the whole 1:1 transcript in the shared KB, or include nothing. This system filters: extracts only the parts of a private exchange relevant to a shared topic; leaves everything else private; privacy is enforced *before* content enters the shared layer
- The dual problem: the same mechanism that guards IP must also enable *appropriate* sharing — "I routinely merge general observations from private Microsoft transcripts into shared notes with explicit prompt-level instructions to omit IP"
- Both enforcement (block private content) and facilitation (share what's appropriate) should be **first-class capabilities**, not manual cognitive overhead each time

> speaker note: This is the differentiator slide for organizational buyers. Lead with the credit point — "people will contribute if they get credit in the system" — before the privacy mechanism, because it sets up *why* you want semi-private mashup to exist in the first place. Be direct that this is a research direction, not a shipped feature. The mechanism (differential privacy norms, permission-aware filtering) is not yet specified — say so and frame it as "where we're putting research effort." The best challenge to anticipate: "How do you enforce this technically?" Answer: we're starting with prompt-level instructions; the formal mechanism is open research. Reference [[Sadra-5May2026-TRANSCRIPT2]] for the Sumit anecdote about pulling unpublished work accidentally.

## Open Questions

- **Privacy mechanism** — semi-private mashup is central to the organizational-brain pitch, but the enforcement design (differential privacy, permission propagation, audit trail) is not specified. Any deployment in a sensitive enterprise context requires this to be concrete before the system can be trusted ([[semi-private-mashing]]).
- **Wiki maintenance at scale** — the PR model (agents submit, humans review) makes sense theoretically, but the incentive structures and tooling for reviewing AI-generated knowledge updates across a 10,000-person org are undesigned. Who curates? What's the review interface? ([[2026-05-05]])
- **Skill quality and gallery** — the value of the system depends heavily on the skills (creative computation methods) supplied for each view. Currently hand-crafted. A community library of skills is proposed but doesn't exist; it's unclear how skill quality would be assessed or improved over time ([[skills]]).

---

**Presenter brief:** Lead with the Excel analogy (slide 1) — this audience will grok it immediately and it gives you the "recalc for subjective content" insight without jargon. Slide 2 (organizational brain) is the one that lands emotionally for a Microsoft-internal audience; the Satya line is intentionally provocative — use it or cut it based on room read. Slide 3 (semi-private mashup) is the hardest slide — it makes a promise (privacy enforcement + appropriate sharing) the system can't yet keep, so be precise about what's designed vs. what's research. Most likely audience question: **"How is this different from what GitHub Copilot/RAG does today?"** Answer: Karpathy's critique — RAG rediscovers knowledge from scratch on every question, there is no accumulation. This system accumulates into a structured knowledge layer; views query the layer, not raw text. Second most likely: **"Who maintains the wiki?"** Answer: PR model — agents submit changes, humans review, same as open-source code evolution.
