---
tags: [view, presentation]
target: views, workflows, skills, semi-private-mashing
audience: distinguished AI practitioners (Satya's office)
generated: 2026-05-05
---

# Presentation: Grounded Examples — Views, Org Brain, Semi-Private Mashup

## Views, Not Documents

Examples sorted high to low — each shows the workflow: raw source → view template + skill → living output.

1. **Sumit's "connect" (performance review) as a view** — Sumit spent 3 days trying to auto-generate his annual review. He supplied connects of all direct reports, 1:1 transcripts, email Q&A threads, past examples, blog posts, paper lists, and hand-written guidance paragraphs — and still got slop. Root cause: no skill told the agent *how* to prioritize and synthesize. The fix: author the connect as a view — each section (story, definitions, examples) is a prompt over the KB, each prompt guided by a skill. The document then updates as new evidence arrives. *Sumit Gulwani — [[Sadra-5May2026-TRANSCRIPT2]]*

2. **This presentation, generated from the wiki** — Sadra ran `/presentation` over the KB and showed Sumit the result live. The slide outline cited the simulation metaphor, semi-private mashing, and contribution-map view — all pulled from meetings, not from scratch. Sumit's diagnosis: the KB's knowledge layer gave the agent structured material to reason over, not raw text to rediscover from zero. *Sadra Sabouri + Sumit Gulwani — [[Sadra-5May2026-TRANSCRIPT2]]*

3. **Pista: same computation, three different views** — In the spreadsheet tool, a single agent computation is rendered as a step-by-step reveal for debugging, a DAG visualization for overview, and a contribution summary for review. Sumit identified this as the moment views unified both projects: "the big, big idea is not a step-by-step reveal — it is providing different kinds of views into the output of the agent." *Sumit Gulwani — [[GMT20260316-200648_Recording.transcript]]*

4. **Sadra's cousin's chemistry PhD emails** — Sadra stress-tested the ingest pipeline on his cousin's chemistry email threads — a corpus with no predefined schema, outside the research context entirely. The wiki extracted people, concepts, and open questions automatically. "Views, not documents" generalized beyond the toy examples used in development. *Sadra Sabouri — [[Sadra-3May2026-TRANSCRIPT]]*

5. **Teams meeting auto-summary as a proto-view** — Teams already auto-generates a post-meeting summary: one fixed template, one fixed algorithm, no user control. The KB extends this to user-definable templates, per-topic summaries composable across meetings, guided by skills. The Teams summary shows the market exists; the KB shows where it goes. *Sumit Gulwani — [[Transcripts]]*

> speaker note: Lead with #1 — the connect story makes the cost of not having skills visceral. Jump to #2 to show the system actually working. #3 bridges to the technical audience via something concrete they know (spreadsheets, agents). #4 and #5 are optional fillers.

## The Organizational Brain

Examples sorted high to low — each shows a knowledge gap only org-scale synthesis can close.

1. **"Which AI trend was discussed most in Microsoft today?"** — Sumit framed this as the canonical CEO-level question. No individual can answer it. No search tool returns it. An org-brain grounded in that day's transcripts across all of Microsoft can. The permission scope required is exactly what Satya already has — "Satya, imagine your power when the Microsoft brain comes up." *Sumit Gulwani — [[Sadra-5May2026-TRANSCRIPT2]]*

2. **PageRank's cross-domain borrowing as the model** — PageRank borrowed the citation-network insight from academic publishing and applied it to the web. Neither the web team nor the citation theorists had the idea — it required cross-domain synthesis. An org brain does this continuously: fragments from one team's transcripts combined with another team's design docs surface ideas neither team had alone. Sumit named this "associative thinking." *Sumit Gulwani — [[Sadra-5May2026-TRANSCRIPT2]]*

3. **Connecting two people working on the same hidden problem** — "Identify two people in different organizations working on the same hidden problem and put them in touch." No org chart, no directory, no search returns this — it requires understanding the *content* of what people are working on. *Sumit Gulwani — [[Sadra-5May2026-TRANSCRIPT2]]*

4. **Wiki as semantic index: the May 3 live demo** — When Sumit saw the wiki live for the first time, he reframed it immediately: not a view output, but a semantic index — "structured, typed, relational, unlike mechanical vector indexes." Views run over the knowledge layer, not raw text. This is the architectural unlock for org-scale queries. *Sumit Gulwani — [[Sadra-3May2026-TRANSCRIPT]]*

5. **Digital twins for onboarding** — Souti articulated the ultimate form of the org brain: models of how each team member thinks, built from accumulated transcripts. New hires onboard against the twin, not against 100 documents. Async collaboration reaches sync quality. *Souti Chattopadhyay — [[Sadra-1May2026-Transcript]]*

> speaker note: Lead with #1 — the Satya question is concrete and immediately provocative. #2 (PageRank) earns the concept intellectually for a technical audience. #3 is the most emotionally resonant for anyone who has wasted weeks finding the right collaborator. #4 is the architectural defense if challenged. #5 is the long-term vision — use it to close.

## Semi-Private Mashup

Examples sorted high to low — each shows a real privacy tension the system must handle automatically.

1. **Agent pulls three sentences of unpublished work** — Sumit's agent, given access to a draft he was helping a colleague with, pulled three sentences of her unpublished work into his own output. He caught it manually and asked her to remove it. This is the failure mode: no privacy boundary existed, and human vigilance was the only guard. The KB must make this impossible by default — filtering before content enters the shared layer, not after. *Sumit Gulwani — [[Sadra-5May2026-TRANSCRIPT2]]*

2. **Routine prompt-level IP omission — the current workaround** — "I routinely merge general observations from my private Microsoft transcripts into shared notes with explicit prompt-level instructions to omit IP and author-restricted material." This is Sumit's manual workaround today — fragile, not auditable, and a cognitive tax paid each time. Semi-private mashing automates it: declared once in the view, enforced before content enters the shared layer, logged for audit. *Sumit Gulwani — [[Sadra-5May2026-TRANSCRIPT2]]*

3. **Souti's 1:1 concern: the design constraint that shaped the system** — In the May 1 three-way sync, Souti raised the concern explicitly: 1:1 transcripts contain sensitive content that should never appear in a shared KB. This forced the team to design semi-private mashing as a first-class operation rather than a workaround. Privacy shapes the architecture, not the other way around. *Souti Chattopadhyay — [[Sadra-1May2026-Transcript]]*

4. **First articulation: Thursday demo email** — The concept was named for the first time in the Thursday demo email: filtering private exchanges to extract only the parts relevant to a shared topic. "Semi-private mashing" was coined here, along with the observation that this is the differentiator from all existing personal KB tools, which assume all input is shareable. *Sumit Gulwani — [[Thursday demo]]*

> speaker note: Lead with #1 — the accidental IP pull is the clearest illustration of what goes wrong without this. #2 shows the manual workaround people are already doing; the system just automates it. #3 is the design history — useful if the audience pushes back on whether this is a real problem. #4 is for intellectual lineage. Be honest: the enforcement mechanism is open research.

---

**Presenter brief:** This deck is all signal — every bullet is a transcript reference, every claim is attributable. For time-constrained settings, one example per slide is enough: use #1 from each (connect-as-view, Satya question, unpublished-work incident). The through-line across all three slides: the KB makes something currently requiring manual, fragile, per-session effort into a declared, auditable, automatic operation.
