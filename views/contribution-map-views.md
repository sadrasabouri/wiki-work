## Contribution Map: views

| Person | Contribution | Date | Source |
|--------|--------------|------|--------|
| [[sumit-gulwani\|Sumit Gulwani]] | Coined "views" as the central abstraction — "the big, big idea is not a step-by-step reveal, it is providing different kinds of views into the output of the agent" — and named step-by-step reveal and DAG as two concrete view types. | 2026-03-16 | [[GMT20260316-200648_Recording.transcript]] |
| [[sadra-sabouri\|Sadra Sabouri]] | Immediately drew the database view analogy upon hearing the term — "this is, like, the analogy of, like, database view, right?" — grounding an abstract idea in a concrete prior art. | 2026-03-16 | [[GMT20260316-200648_Recording.transcript]] |
| [[sumit-gulwani\|Sumit Gulwani]] | Identified views as user-definable and domain-dependent — "the views will depend upon the output task, or the domain of tasks. Also, it may depend upon the kind of user, or the curiosity the user has at that point of time." | 2026-03-16 | [[GMT20260316-200648_Recording.transcript]] |
| [[sumit-gulwani\|Sumit Gulwani]] | Extended views beyond one-shot tasks to interactive, in-progress processes — "the goal of these views is to steer the process. The process may not even be finished." | 2026-03-16 | [[GMT20260316-200648_Recording.transcript]] |
| [[sumit-gulwani\|Sumit Gulwani]] | Proposed the presentation view and self-referential application — "I am thinking of using this 'presentation' view to present the ideas... the title of this presentation would be something along the lines of 'presentation about this presentation'" | 2026-05-02 | [[Thursday demo]] |
| [[sumit-gulwani\|Sumit Gulwani]] | Formalized the three-part structure of a view: prompt template (required) + workflow (optional) + raw data selection (optional) — "a view can be seen as a template whose holes are filled with prompts FROM a specified source of raw information and USING a specified workflow." | 2026-05-03 | [[Thursday demo]] |
| [[sadra-sabouri\|Sadra Sabouri]] | Proposed hierarchical views and sub-views (e.g., `/summary/problem-definition`, `/presentation/related-work`), resisting over-constraint — "I don't want to bound the user by designers' constraints." | 2026-05-03 | [[Thursday demo]] |
| [[sumit-gulwani\|Sumit Gulwani]] | Articulated the views taxonomy — design document, contribution review, topic summary — with rich examples (contribution view for performance review; design doc for parallel teams problem). | 2026-05-01 | [[Sadra-1May2026-Transcript]] |
| [[souti-chattopadhyay\|Souti Chattopadhyay]] | Extended views beyond summarization to analytical insights — "where do Sumit and Sadra's ideas sort of diverge... where do they converge and what are maybe some of the conflicts and how did the conflict evolve over time." | 2026-05-01 | [[Sadra-1May2026-Transcript]] |
| [[sumit-gulwani\|Sumit Gulwani]] | Identified Microsoft Teams speaker-summary and custom-template features as real-world analogues to views — grounding the concept in an existing product as related work. | 2026-05-01 | [[Sadra-1May2026-Transcript]] |
| [[sumit-gulwani\|Sumit Gulwani]] | Drew the declarative/constructive distinction formally — "view can be declarative, what the user wants, and workflow is more a constructive specification." | 2026-05-02 | [[Sadra-2May2026-TRANSCRIPT2]] |
| [[sadra-sabouri\|Sadra Sabouri]] | Named "purge" as the inverse of ingest — the operation required to remove or supersede nodes and edges when a source is retracted or outdated — making temporal integrity a first-class KB concern. | 2026-05-02 | [[Sadra-2May2026-TRANSCRIPT2]] |

### Observations

- **The database analogy was Sadra's, not Sumit's.** Sumit coined the term "views"; Sadra immediately connected it to database views ("like, the analogy of, like, database view, right?"). Sumit confirmed it enthusiastically. This connection is typically attributed to Sumit in downstream summaries, but the record is unambiguous.

- **Souti's contribution to views is systematically underweighted.** She is rarely foregrounded in discussions of views, but she made the pivotal move of pushing the concept beyond summarization — the insight that views could surface contradictions, divergences, and convergences across speakers, not just compress content. This opened the "creative views" direction that Sumit later developed into the associative/novelty prompts idea.

- **Sadra's sub-view proposal and Sumit's hierarchical structure endorsement were co-developed in real time over email**, not sequentially. Sadra proposed the generalization; Sumit said "I love this hierarchical structure" and extended it with the sub-view-as-slide-title idea. Attribution is genuinely shared.

- **The declarative/constructive distinction** (views vs. workflows) was formalized by Sumit in the May 2 evening meeting, but the underlying intuition existed earlier — Sadra's May 3 email described "predefined (probably tested to be somewhat optimal) workflows to provide a certain view," showing the split was already implicit before being named.

- **Purge as a first-class operation was named by Sadra**, not Sumit, emerging from a concrete concern about reverting ingested sources. Sumit extended it to cover privacy-motivated removal (not just temporal obsolescence).

- **Sujay Maladi is absent from all views-specific discussions.** He was present at the Feb 20 kickoff and contributed the must-haves/nice-to-haves rubric, which shaped early view-type distinctions (functional vs. aesthetic), but is not in the record for any views discussion after Mar 16.

- **The Teams engineering team** is an unnamed influence: their speaker-summary and template features, cited by Sumit on May 1 as the clearest real-world analogue to views, shaped the framing of what user-definable views look like in practice — but no individual is credited.
