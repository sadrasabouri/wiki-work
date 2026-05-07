---
timestamp: 2026-05-06T15:11:47-07:00
tags:
---
# **Task Division**

Tasks have been split between the two. Sadra is owning the presentation (based on the wiki view) and Sumit is working on the pre-read document, a comprehensive write-up of the idea that will be reviewed by distinguished AI practitioners and AI leaders at Microsoft ahead of the meeting.

**Upcoming Presentation**

The presentation is tomorrow, Thursday May 7, 1-2 pm, as part of an internal Microsoft event. Six people are presenting, roughly 10 minutes each, with Sumit going last. Since the presentations are thematically related, there may be opportunities to draw connections across presenters.

**Sumit's Document Generation Workflow**

Sumit shared his approach to generating the pre-read document. He reverse-engineered it by starting from the desired content outline and having an agent fill it in. Where sections were too short, he prompted the agent to merge paragraphs for a more balanced result. He drew an analogy to FlashFill: just as FlashFill narrows down a large space of possible functions by accumulating input-output examples, the same iterative example-driven approach could guide the agent toward the right presentation output. He suggested applying this to the presentation as well.

**Sadra's Updates**

Sadra updated the wiki by reading and ingesting relevant documents, and mined 700 comments from Karpathy's GitHub gist, extracting related work across three categories: (I) software engineering, (II) researchers and ideators, and (III) teams.

Sadra also built a new "clarify" command that prompts the agent to surface assumptions and inconsistencies in the wiki. The command will generate a set of questions for the user to answer, after which the wiki gets refactored accordingly.

**Action Item for Sadra:** Look into WorkIQ, an internal Microsoft tool, to identify connections between existing work and the current project direction.

**Discussion on Wiki vs. RAG**

Sadra presented the interpretability advantages of the wiki structure over a RAG-based approach. Sumit noted that data compression is a more central concern in RAG, but encouraged Sadra to develop the idea further.