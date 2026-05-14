---
tags:
generated: 2026-05-13
---

> [!note]-
> prompt: *`/query for a fixed task of cerating a summary of a meeting transcript what are the creative workflows people can use`*

# Creative Workflows (Skills) for Summarizing a Meeting Transcript

## Documented Skills for Transcript Summarization

| Provenance                                                         | Skill                                                    | Method                                                                                           | Best for                                                                                         |
| ------------------------------------------------------------------ | -------------------------------------------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| [[wiki/concepts/skills.md]] · Sumit Gulwani (credit: Nikhil Swami) | **Grounded theory analysis**                             | Inductive coding → clustering → naming                                                           | Messy qualitative transcripts; when categories are not known in advance                          |
| [[wiki/concepts/skills.md]] · Sumit Gulwani                        | **Multi-pass summarization**                             | Compress 3× on the same content; each pass tighter                                               | Any transcript; confirmed "materially better than single-pass"                                   |
| [[wiki/concepts/skills.md]] · Sumit Gulwani                        | **Per-section chunking**                                 | Summarize each section independently, then compose                                               | Long transcripts with identifiable topic sections                                                |
| [[wiki/concepts/skills.md]] · Sumit Gulwani                        | **Repeated distillation and mash-up**                    | Iterate distillations; have an agent mash competing versions; repeat until convergence           | When multiple competing readings of the transcript are plausible                                 |
| [[wiki/concepts/skills.md]] · Sumit Gulwani                        | **Debating agents**                                      | Multiple agents argue different versions of the same artifact to surface the strongest synthesis | When the "right framing" of the meeting is genuinely contested                                   |
| [[wiki/events/2026-05-06.md]] · Sumit Gulwani                      | **Template extraction at the right level of generality** | Extract a reusable template from a summary you like; re-run it against the raw transcript        | When you have a previous good summary and want to regenerate it from new/updated source material |
