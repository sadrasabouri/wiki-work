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

- **Grounded theory analysis** — inductive coding → clustering → naming; for messy qualitative transcripts
- **Multi-pass summarization** — compress 3× on the same content; each pass tighter than the last
- **Per-section chunking** — chunk by section, summarize independently, compose
- **Audience-aware storytelling** — pick examples relevant to the named audience; vary stories by audience without changing the view structure

## Gallery of Skills

A community library of skills is a natural extension: practitioners share skills for knowledge distillation the way developers share libraries. Sumit's call-to-action in his draft post: "stand up a community pattern library, because many of us are distilling information in our own creative ways." The grounded theory prompt from this project is one example of a skill worth sharing.

**Real-world analogue at org scale:** [[workiq|Work IQ]]'s **Business skills** — "natural-language instructions that encode your organization's processes, policies, and domain knowledge in a format agents can interpret and execute" — are skills at the org-process level. Agents discover and apply them at runtime to ensure consistent behavior across the org. Same pattern as wiki skills, different scope: Work IQ skills encode org procedures; wiki skills encode per-prompt creative methodology. [[Work IQ overview]]

**Real-world analogue in the wild:** [[matvellosoknowledge]] implements a skills-equivalent called **MY PREFERENCES.md** — a plain markdown file where users encode domain-specific extraction rules and hard constraints (e.g., "always extract action items from work emails," "never include prices in shopping summaries"). The agent uses it as part of the system prompt. This confirms the skills pattern is independently discoverable: when you build a serious personal KB, you end up needing a user-configurable methodology layer. [[Personal Private Knowledge Management]]

## Relation to Workflows

Skills and [[workflows]] are distinct. Skills = methodology per prompt (HOW to compute a given hole). Workflows = data dependency graph across prompts and sources (WHEN to recompute). A view template has holes, each hole has a prompt, each prompt may specify a skill. The workflow determines which prompts rerun when a source changes.
