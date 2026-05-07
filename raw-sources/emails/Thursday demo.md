---
timestamp: "2026-05-03T15:20:47-07:00"
source: "[[Thursday demo.eml]]"
source_path: "raw/emails/Thursday demo.eml"
source_type: "eml"
tags:
  - extracted
---
# Thursday demo

Source: [[Thursday demo.eml]]

## Email Metadata

- **Subject:** Re: [EXTERNAL] Re: Thursday demo
- **From:** Sumit Gulwani <sumitg@microsoft.com>
- **To:** Sadra Sabouri Halestani <sabourih@usc.edu>
- **Cc:** Souti Chattopadhyay <schattop@usc.edu>
- **Date:** Sun, 03 May 2026 17:35:02 +0000

## Body

3. Aha, I see what you mean by the "skills" connection. Yes, that'd be a good analogy to use, especially as these workflows may be applied to multiple views. So one may think of "workflows" as a special kind of "skills" that may also be definable and buildable via some graphic language of constructs that we may discover such as processing and repeating blocks.

Some notes that I shared with them to request more time for now:
-The VIEWS on top of this wiki/KB management is the future of Office and knowledge work. For instance, one view can be a table, or a design document, or even a presentation. [In fact, I am thinking of using this "presentation" view to present the ideas and in that sense the title of this presentation would be something along the lines of "presentation about this presentation" or "about itself"   - and for that what I have done is tens of conversations/meetings since you signed me up where this entire presentation will come to life out of those transcripts/emails/Teams-chats and without any hand-specific curation
-Ability to mash "semi-private information" (for lack of a better term), wherein say an exchange between you and me can be filtered to enrich this KB that relates to a specific topic/group. Our exchange might be private to us and might be on a variety of topics, but with appropriate filters, we both may be ok for it to be distilled to enrich a given KB. This is HUGE because if you think about how to simulate life, there are 2 key components I think: information processing and choice making by an individual AND communication between individuals. The beautiful thing about this world is that we have a small degree of separation (6) between any two individuals, and with this concept of semi-private-info mash (following all differential privacy norms) would be key to accelerate progress/evolution of any KB and thus any organization/society. The best place to experiment with this concept would be a large organization like Excel or Microsoft.
side note: the reason why I noted that down above is that all this is going into my raw sources to enrich my KB, and hopefully that leads to a better presentation of Thu. And it was all human written (want to strictly separate that from AI-generated "slop")

A very surreal observation: Today I maintain my KB in a more primitive fashion, but few days ago, I noticed that my agent (Claude Code CLI) became smart enough to start summarizing my content and organizing it in more interesting ways. As I was trying to get something done too quickly, I chided it to not try to be too smart and still do things the original (dumb) way as I was not yet ready for a transition to V2 myself.

But now that I think about it, it was using terms like "minimal specs" and "KB" and its summary was starting to be organized differently. It was very very surreal, almost as if the system had consciousness (as it started to do things that I never asked it to, but it just learned about those from my raw notes and processed newsletters!).

________________________________
From: Sadra Sabouri Halestani <sabourih@usc.edu>
Sent: Sunday, May 3, 2026 8:25 AM
To: Sumit Gulwani <sumitg@microsoft.com>
Cc: Souti Chattopadhyay <schattop@usc.edu>
Subject: Re: [EXTERNAL] Re: Thursday demo

1. yes that's what I meant
2. that's a good idea. will work on that.
3. similar to how users define custom skills to define workflows for different tasks. these workflows are predefined (probably tested to be somewhat optimal) workflows to provide a certain view
4. ok I will work on it today to have raw contents at least that gives gist of the bigger idea

completely agree on the last two part mentioned.

On Sun, May 3, 2026 at 1:31 AM Sumit Gulwani <sumitg@microsoft.com<mailto:sumitg@microsoft.com>> wrote:
1. I love this hierarchical structure. By "I don't want to bound the user by designers' constraints", do you mean that users should be able to define their own views and sub-views for themselves, right? 2. Love this connection to coding.
1. I love this hierarchical structure. By "I don't want to bound the user by designers' constraints", do you mean that users should be able to define their own views and sub-views for themselves, right?
2. Love this connection to coding. I think this is genuinely spread out across multiple transcripts. Lets pull in a view that describes comparison to coding, bootstrapped out of our transcripts.
3. Not sure I understand the connection with skills.md. I would think that this is in the same category as the point 2 above where this general idea is genuinely spread out across multiple transcripts.
4. Not sure I understand this. Are you saying we have too much content. There I can just walk through a smaller number of views depending on time. But my hope is that this is so damn impressive that they should give me more time for a demo. Thats why the earlier you can send me something, I may have an opportunity to run it by them for them to give me more time.

Some other thoughts:
Another top-level view besides a "presentation" can be a "design document" or even a "research paper" with a template defined.

Basically a view can be seen as a template whose holes are filled with prompts FROM a specified source of raw information and USING a specified workflow. The latter two are optional and default to "all information" and "let the agent infer the workflow".


Best Wishes,
Sumit

________________________________
From: Sadra Sabouri Halestani <sabourih@usc.edu<mailto:sabourih@usc.edu>>
Sent: Sunday, May 3, 2026 12:28 AM
To: Sumit Gulwani <sumitg@microsoft.com<mailto:sumitg@microsoft.com>>
Cc: Souti Chattopadhyay <schattop@usc.edu<mailto:schattop@usc.edu>>
Subject: [EXTERNAL] Re: Thursday demo

I liked the ideas here. Minor points that could augment the ideas:

  *   when we're defining these views it's good to think about their generalization as well. as you mentioned in the last email the sub-view could be a useful name convention. for example /summary/problem-defintion, /presentation/related-work. at the other hand I don't want to bound the user by designers' constraints. Then I would say any prompts we're using to achieve our (sub)goals is the initiation of a view.
  *   I love the of a knowledge wiki to a codebase. It had all components (PRs: adding personal knowledge to common knowledge, Refactor: trimming and reconstruction entities in a way that makes more efficient representation of the data). In fact this can be a nice closing remarks that help people imagine the components of our envisioned system.
  *   the last part about updating creative workflows aligns well with the SKILLS.md for agents.
  *   the ideas in the last email sounds good but I'm worried about being too fine-grained for the presentation with having too many layers.

On Sun, May 3, 2026 at 12:07 AM Sumit Gulwani <sumitg@microsoft.com<mailto:sumitg@microsoft.com>> wrote:
So the presentation would just be a bunch of views (perhaps with notion of sub-views) in which case the top-level view I guess is just a folder name? Each (sub)view can have multiple workflows associated with it. For instance, if the initial
So the presentation would just be a bunch of views (perhaps with notion of sub-views) in which case the top-level view I guess is just a folder name?

Each (sub)view can have multiple workflows associated with it. For instance, if the initial workflow is empty, and I do not like the result, then I can define another workflow that provides more detailed guidance to the system. For instance, I can define a view as "related work" but then if I do not like what the system pull out, I can provide more constructive specification such as the related work will have two parts: comparison with KBs of the past and new work (such as Teams templates). Not sure if this should be seen as workflow or perhaps a more detailed guidance for the view prompt.

We can also show the difference between the idea of re-processing based on the output generated in the first round. These can be shown as "Alternates" for that view (each "alternate" is associated with some workflow, or perhaps even with a smaller set of input transcripts (if the user wants to control that—-aha, that can be one way to show temporal aspect).

So, an "alternate" or rendering of a view is a function of the prompt for that view, a potential workflow that the user specified, and an optional selection of the raw data that the user specified.


________________________________
From: Sumit Gulwani <sumitg@microsoft.com<mailto:sumitg@microsoft.com>>
Sent: Saturday, May 2, 2026 11:52 PM
To: Sadra Sabouri Halestani <sabourih@usc.edu<mailto:sabourih@usc.edu>>
Cc: Souti Chattopadhyay <schattop@usc.edu<mailto:schattop@usc.edu>>
Subject: Re: Thursday demo

And then on the technical ideas part:
One technical idea is about defining views/workflows. There one section can be about a bunch of bullets for "creative views". Each of these is associated with a prompt (such that tomorrow if we discuss another example of a creative view in our transcript, it will be pulled into this view automatically)
________________________________
From: Sumit Gulwani
Sent: Saturday, May 2, 2026 11:47 PM
To: Sadra Sabouri Halestani <sabourih@usc.edu<mailto:sabourih@usc.edu>>
Cc: Souti Chattopadhyay <schattop@usc.edu<mailto:schattop@usc.edu>>
Subject: Thursday demo

Some notes that I had started writing before we got on the call:

@Sadra<mailto:sabourih@usc.edu>: all these emails are also good source of raw info for our wiki 🙂

I am wondering if we can do the presentation using our wiki itself!

The wiki contains many raw sources including transcripts. Many of these transcripts are about the KB process/project. So, all we have to do is to define some views that help explain the key points that I want to land. For instance,
-one such view can be about "problem definition" or "motivation/applications". This can also pull in the specific stories that I had talked about: creation and maintenance of design docs from a collection of Teams chat, and people reviews, and creating presentations.

-Another can be about "related work" which contains two points: Similarities and Differences with traditional KBs of the past, what is happening in this broad area today for instance, Teams custom templates can be seen as views (but without workflows) on top of a single transcript.

-Another can be about the 4-5 key technical ideas that we have had.

-Would be good to showcase some specific quotes/analogies at the right place such as "degree of separation" when we motivate mashing up on semi-private information which I think deserves its own bullet. Another philosophy we can mention there is that of simulation involves individual processing/choice-making and communication. Our wiki choices seem to accelerate both "processing" of information into knowledge and communication (by allowing to bring in semi-private info)

-Another analogy that would be good to talk about is with respect to coding. Just as we seek "specification mechanism" and "IDEs" of the future in the future of coding, we have the same questions for knowledge work - which is what our wiki is doing. One key difference though is that our system is additive (more information can be added to the system at any time, and the system should update - I wonder though if that can be related to adding of more test cases 🙂)
