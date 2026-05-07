---
tags: [concept, core]
---

# Skills

A **skill** is a constructive specification of HOW to compute one prompt in a [[views|view]]. Where the view's template says *what* to produce and a prompt fills a hole, the skill tells the agent the methodology to use when filling that hole — rather than letting it choose freely. Terminology confirmed in [[T14-2026-05-05-2|the May 5 evening sync]]: "We switched from workflows to using skills."

Skills were formerly called "creative workflows" in earlier sessions (e.g. [[T7-2026-05-01|May 1]], [[T9-2026-05-02-2|May 2 evening]]). The rename separates creative methodology (skills) from data dependencies (now the exclusive meaning of [[workflows]]).

## Where Skills Live

In the view/prompt/skill layering:

> View = template with holes → each hole = a prompt → each prompt = optionally guided by a skill

A skill says: "do grounded theory analysis" or "multi-pass summarization, 3 passes, compress further each time." Without a skill, the agent chooses its own methodology. With a skill, domain expertise is encoded directly. The skill is the place where the human's tacit knowledge about *how to think* is made explicit.

## Why Skills Matter

Sumit's "connect" (performance review) exercise in [[T13-2026-05-05-1|the May 5 morning sync]] demonstrated this gap: all raw sources were present, all prompts were supplied, but output was "AI slop" because no skill told the agent *how* to prioritize and synthesize. "Having raw sources and a processing pipeline is not going to be good enough."

Skills encode the creative insight — the recognition that grounded theory applies to transcript summarization, or that a 3-pass compression produces materially better output than a single pass. These insights are the durable contribution; raw prompts are merely the delivery mechanism.

## Examples

- **Grounded theory analysis** — inductive coding → clustering → naming; for messy qualitative transcripts. Sumit credits Nikhil Swami for the technique.
- **Multi-pass summarization** — compress 3× on the same content; each pass tighter than the last
- **Per-section chunking** — chunk by section, summarize independently, compose
- **Audience-aware storytelling** — pick examples relevant to the named audience; vary stories by audience without changing the view structure
- **Repeated distillation and mash-up** — Sumit's own technique: iterate distillations, then have an agent mash competing versions, repeat until convergence
- **Debating agents** — multiple agents argue versions of the same artifact to surface the strongest synthesis
- **Side-by-side / topic-by-topic refinement** — for slide decks, refine by group rather than by individual slide
- **Template extraction at the right level of generality** — see below

## Template Extraction at the Right Level of Generality

A skill Sumit named in [[T15-2026-05-06|May 6]] as his "biggest find" of the day. When you have a document you like and want to regenerate something of the same quality from updated raw data, the move is to extract a template/specification from the example — and the template must be at the *right level* of abstraction.

The connection Sumit drew: this is the **program-ranking problem from FlashFill**. FlashFill has many programs consistent with a given input-output example; the system returns not the first one but the program most likely to generalize correctly. Template extraction over a document has the same shape:

- **Too general** ("produce a 2000-word essay on X") → loses voice and structure
- **Too specific** ("produce this exact document") → no creativity, just a copy
- **Right level** → preserves voice and shape while allowing the agent room to incorporate new evidence

Concrete operating moves Sumit used:

1. **Group similar paragraphs first**, then write one specification per group rather than per paragraph
2. **Decide what to abstract per-element**: "talk about person X" → generalize to "talk about any person" sometimes, but not when X is Satya (the closing shout-out should stay concrete)
3. **Re-run the generalized template against the raw transcripts**, not against the original document — that's where the new value comes from

This skill makes the FlashFill analogy from [[views]] operational. It is the missing methodology that prevents [[views|document-as-view]] from collapsing into either over-abstracted slop or pointless exact-copy regeneration.

## Gallery of Skills

A community library of skills is a natural extension: practitioners share skills for knowledge distillation the way developers share libraries. Sumit's call-to-action in his draft post: "stand up a community pattern library, because many of us are distilling information in our own creative ways." The grounded theory prompt from this project is one example of a skill worth sharing.

**Real-world analogue at org scale:** [[workiq|Work IQ]]'s **Business skills** — "natural-language instructions that encode your organization's processes, policies, and domain knowledge in a format agents can interpret and execute" — are skills at the org-process level. Agents discover and apply them at runtime to ensure consistent behavior across the org. Same pattern as wiki skills, different scope: Work IQ skills encode org procedures; wiki skills encode per-prompt creative methodology. [[Work IQ overview]]

**Real-world analogue in the wild:** [[matvellosoknowledge]] implements a skills-equivalent called **MY PREFERENCES.md** — a plain markdown file where users encode domain-specific extraction rules and hard constraints (e.g., "always extract action items from work emails," "never include prices in shopping summaries"). The agent uses it as part of the system prompt. This confirms the skills pattern is independently discoverable: when you build a serious personal KB, you end up needing a user-configurable methodology layer. [[Personal Knowledge Management]]

## Relation to Workflows

Skills and [[workflows]] are distinct. Skills = methodology per prompt (HOW to compute a given hole). Workflows = data dependency graph across prompts and sources (WHEN to recompute). A view template has holes, each hole has a prompt, each prompt may specify a skill. The workflow determines which prompts rerun when a source changes.
