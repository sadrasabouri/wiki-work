---
timestamp: "2026-05-03T15:20:47-07:00"
source: "[[Sadra-1May2026-Transcript.docx]]"
source_path: "raw/meeting-transcripts/Sadra-1May2026-Transcript.docx"
source_type: "docx"
tags:
  - extracted
---
# Sadra-1May2026-Transcript

Source: [[Sadra-1May2026-Transcript.docx]]

SoutiSadraSumit sync-20260501_143938-Meeting Transcript

May 1, 2026, 9:39PM

57m 6s

Sumit Gulwani started transcription

Sumit Gulwani   0:06
Okay, so I started the recording again. So let me read out the exchange that I had.
With.
some people on our Teams channel regarding some, you know, random project that was being discussed.
At.
So someone says, person A says.
I was wondering if there was a way to collate design documents or some other form of documents on the different approaches being used by each team to aid with this problem X.
It is currently a bit tricky finding documentation on how each team is tackling this large problem X. So the context is that that X is a large problem and and then I've been calling this out for a long time and slowly you know different sets of people have been working on it.
completely unaware of what the other person is doing, right? So now all those people are coming together for the first time to discuss problem X. And then someone person, and at the end of that meeting, one person says, I was wondering if there's a way to collate design documents or some form of documents, documentation on the different approaches being used by each team to aid with this problem X.
It is currently a bit tricky finding documentation on how each team is tackling this problem X.
And then I say.
Oh, we are considering an agentic workflow to solve precisely this problem. This agent that you would then query would be grounded in all of our team's conversations, which is where I believe the real IP of our Excel organization lives.
Until then, you know, let's count on this person's effort to build such a collateral and this other person who's trying to organize a workshop which we will record and share.
Then another person D. says.
Agent experiences that let us explore and summarize active work streams are valuable.
But they do not replace the need for a process to track the most up-to-date design documents and proposals in a consistent centralized repository.
Teams messages are an ever-evolving landscape of changing perspectives.
that are easy to miss a detail that may invalidate our understanding of an earlier assumption.
Design docs and up-to-date problem statements allow us to capture these many and varied conversations into a concrete snapshot of what is the current thing.
To which I respond.
Very well said. And that's exactly how this agent shall work.
to treat the team's channels as a time-stamped evolution of ideas.
and to generate and maintain different views on top of it.
such as design documents and up to date problem statements that you referenced in a central repository.
Someone should even be able to come and tell this agent to evolve a design doc based on the transcript of their private meeting, parts of which were relevant to the design doc.
Right, so, so just an example, so nothing much detail here, but just an example of Sadra what we spoke about yesterday as well. The interesting constructive insight here is that there is some notion of the most up-to-date design document and a centralized, you know, problem statement document.
And if I want to reflect on the wiki that you created, so there you do have a active in a work list that you are talking about.
And maybe out all this transcription with this different kind of information, but we can imagine that someone defined a work stream or a view of maintaining the latest, you know, design document on the three choices or two techniques that different teams are working on.
And then, as more more transcripts come in, those techniques get refined, or maybe a 4th technique gets added, but that's one view that someone has designed, right? And that view is, I want a design document on problem X. That's a view that someone has designed, right? And maybe one can go and imagine that someone describes, you know, what this is, what what what X is, you know, what a design document of X means, what form it should take, maybe someone describes that.
And then the goal of our knowledge base management evolution would be that as more data comes in, all these rules should keep getting updated accordingly.
So that's maybe one constructive insight I take, right? So I need to repeat it that in all this narrative that I read, this exchange that I read of this conversation that I was reading out.

Sadra   4:27
Okay.

Sumit Gulwani   4:37
The way I relate it to our past discussion is that this is an example of a view that can be defined by someone on our knowledge base. So how does one go and define that view? And how is it updated in an efficient way?

Sadra   4:47
S.

Sumit Gulwani   4:53
how it is even trimmed, right, as you were talking about, would be an interesting problem.

Sadra   4:57
I.

Sumit Gulwani   5:00
EXCEL.

Souti Chattopadhyay   5:05
Yeah.

Sadra   5:07
So I started working on...
That, like, video or like that presentation, I, I have shared the, like, a, the, the, the document drive with you. I haven't published it yet, but one thing that I realized was that...

Sumit Gulwani   5:26
The.

Sadra   5:29
Maybe, so for this one, I'm using the best codex model, not, not, not, but this is not another coding task. This is like a more like reasoning task.
What I did was that I, as we talked yesterday, I merged my personal Wiki to the shared Wiki of the lab that was in that website. And then I asked us to find the connections between this newly generated graph, which is by combining this, or like by adding edges between my graph and the released graph.
and then I ask it to make a presentation. The presentation.
Gives ideas, but, but, but, but, but is not good for, like, presenting. It's very this disjoint ideas that it seems like it forced itself to connect some ideas, something like that.

Sumit Gulwani   6:30
Yes, so let's start with the overall story very complicated here, right? Because I will just have two minutes, right? But let's get to the heart of it, right? So for example, I feel that, maybe let me actually, I am digressing, but I'll connect you all together, right? So we also need to do a good related work survey, literature survey on what is going on, right? The field is moving very fast. So for example, even in Microsoft Teams.

Sadra   6:35
I.

Sumit Gulwani   6:50
Earlier I would get an AI summary of the conversation. Okay, but now recently I'm getting two other interesting things from it. So one is I see that I can get a speaker organized summary. So what it will do is that for each speaker it will have like you know 5 to 10 bullet points of what that speaker talked about in the entire meeting.

Sadra   6:54
Yes.
Yes.

Sumit Gulwani   7:11
which is more detailed and very different from the AI summaries. In AI summary, what it does is it comes up with the overall five points about the meeting and then each point it tags, you know, a particular speaker that, you know, or these two, three or two speakers talked about this or three speakers talked about this and so on. This is how it maintains the provenance of those insights.

Sadra   7:20
I.
Yes.

Sumit Gulwani   7:31
But as I said, the other view that it is now starting to give is a speaker summary view. More detailed, and for each speaker, it will have 5 to 10 bullet points. Then yet another view that I have not tried out yet.
is that template. You can define your own template.
And now that I think about it, this is not very different from what I just mentioned, right? So let's say I have a bunch of teams transcripts, bunch of documents, all my raw data is there, agent, whatever I have, right? So from all of that, I want to design a view which describes, so the example of the view was I wanted a design document for problem X.
Maybe all three approaches or all the approaches that different people are working on problem X, and that becomes maybe the header of my view. And then I need to describe a little bit about it, and we describe a template and so on, right? So what I'm saying is that this notion of views, I feel, is a very powerful one.
But other people are also realizing it and things are happening around very quickly in this field. So let's make sure we understand what the latest is in terms of these, at least these established products and what kind of views are being offered. But our general theory is that we can let anyone define any view or any template.
over a bunch of data and we will do this in a more efficient manner, right? That's, I think, the novel component I see.
The second thing is, and maybe I will repeat it for Rene since she was not there yesterday.
that I believe that projecting.
The parts that are OK to be shared with a group, Vicky, from a more private conversation.
is going to be a very key part of evolving a group wiki.

Souti Chattopadhyay   9:18
Mm.

Sumit Gulwani   9:19
And the reason being that if you think about privacy and security and all those kinds of things today, right, people will immediately say, oh, this is not allowed. You know, this call private, this conversation was private conversation between Rini and some other friend of hers. And how can we use that information? We cannot really add that transcript to the group wiki between Sumit, Sadra, Rini, and other students.

Souti Chattopadhyay   9:39
Mm.

Sumit Gulwani   9:40
And that's a very, very limiting perspective, right? And I feel that the most interesting things are going to actually happen and come from this kind of enrichment. Because there is this thing that, you know, every person in the world is connected to every other person through just, you know, five or six connections. And we want to gather the wisdom of the entire world. And it can be gathered if we allow for these kinds of things to actually happen.
But if we keep it very closed, and that's what really distinguishes us, right? So if you think about any like in this pool that we will come together, we all come together. We have people who bring different backgrounds and everyone contributes. So why is this group diverse? This group is diverse because everyone gets to have their own experiences in life, right? You interact with your own.
group of people, I interact with my own group of people and that's what really defines you and me, right? The way we are and that's why we are diverse. That's the perspective we bring in. And we have to be absolutely make this a first class citizen.
And I think that's going to be a very normal component. Now, the key interesting technical part is how do you set up these filters? And how do you define what information can you merge, what information you cannot merge, and so on?
And I was giving another example to Sadra yesterday that maybe I wrote up something in the paper form and I sent it to you folks at the very start of, you know, when you were writing the paper. How did I generate the paper, right? So I generated that paper from my, of course, this transcript that I was recording, and then I said, this is a template I want. But I matched that information up with some other private transcriptions that I had, which had Microsoft IP, but I told the agent that, look, you know, you're not allowed to take that.
Microsoft IP details and so on and put into this, you know, that would be problematic. But in all these conversations, even though they are Microsoft IP, there are many things that are related to this particular topic that I am working with Rini and Sadra on, but they are not private or they need not be private and match that information up.
Right, of course, I did this without any formal checks and so on, but that would be the thing, right? How do you make sure that this is actually preserved and no one is able to hack into those things and so on, and then the filters are there, but that I believe would be one of the very key.
Key aspects of this demo, right? So, two things Sadra, I will say, right? You know, they resonate very strongly with what we want to show in this demo is the ability to define different views, and this example that I gave you was one such example.
Today, you probably, this magic is lost in your, as you say, that there is a summary and these different projects are going on and so on, right? But you just generalize it to the sense that, well, this is a view, right? This is an example of a view that someone has defined. And then the second part is that how we are able to allow people to bring in more information from their private channels.
To contribute to this.
So that might be another another interesting more detail that you can probably add add to this.

Souti Chattopadhyay   12:32
Mm.

Sadra   12:37
Can you elaborate on, so I understood like one view could be the design view, for example. Can you give me some other examples for me to understand the domain of, like some other examples of view?

Sumit Gulwani   12:54
View, I'll give you another view, right? Another view, right? Think about, you know, the person who leads EXCEL, 700 people, they manage. Think about Satya, 200,000 people, you know, report to him, right? Now, don't use this example, he's a politically incorrect example site, but let's say someone wants to decide, you know, who to fire.

Sadra   13:04
Yes.

Sumit Gulwani   13:13
And, you know, these layoffs are happening. They want to understand the contributions of these people, right? Maybe they even want to do it at the, you know, they want to understand it at the related to the level at which they are in the company, right, related to the seniority.
Are these people discussions are happening right now? You know, this is a season that I have to write, you know, reviews for people and so on. How do I know who has worked what? Today, most of the artifacts that we are creating.
are don't have a longer shelf life.
And how do I know who came up with what idea?
It becomes very hard to judge someone in today's time period. Well, this was always a difficult problem, but today it's even more difficult problem. In fact, I even had seen like even one year ago, people talking about it on LinkedIn, that in this new world, ideas become the most important currency. Cost of execution goes down to zero.
And the way we keep prominence and track of ideas does not exist today.
In fact, I've seen many people saying I'm going to hide my idea because I'm not confident that if I share, you know, I'll get credit for it. I feel very upset when I see those kinds of things, you know, from people on my team, but this is happening. So in this environment, you can imagine even more important, why is it important to be able to create a view that tells me.
How has this people this person contributed? Now, I might have my all the transcripts, team transcripts, and so on, but but this view of the contribution is not really about their detailed technical contributions, but it is at a more higher level, which is what this person contributed, what are the overall impact of their contributions, how did they contribute?
Did they build on the work of others? Did they do something or did they help others? So this is the dimension. This is a view that my manager will have when he tries to evaluate one. So how is my manager evaluating me? Not based upon what Sumit did.
but based upon what is the impact of what Sumit did, and based upon how did Sumit operate.
Did he build on the work of others? Did he lift others and made them successful? So this is a view that my manager will have. So if my manager has access to all of my team's conversations, which he has, right, but he has no time to look into all of that, right? But this is what he would care about. This is very different than a design talk, but this is just a view, a different view. I hope you see what I'm saying here, right?

Sadra   15:20
Yes.
No.
Yes, so my idea for this is that once we have some data structure, for example, for now this knowledge graph that we're thinking of, the rest would be, and also a nice way to query this knowledge graph, this is also doable with this.
infrastructure that I'm using, then the rest would be any natural language query could be potentially a view that the agent which has access to this data structure and tools to query this data structure efficiently can give to the person.

Sumit Gulwani   16:04
Yes, yes, but this view will not just be natural language description. It can be a rich template also, because I might say that, look, I want Sumit contributions in one page. Everyone gets one page. I don't want more than one page. Everyone gets, because everyone at the same time, I don't want to read someone's contribution which is 2 pages and someone contributions one page. So that's my template. And in one page, I'm saying half of the page has to be about what and half of the page has to be about how.

Souti Chattopadhyay   16:04
Okay.

Sadra   16:04
Yes.
Oh.

Sumit Gulwani   16:25
And then, and then how part I need, you know, two parts. How did Sumit build on the work of others and how did Sumit contribute to other people's success? 25, 25%, right? So, that's a template I am probably trying to set, right? I can even give some examples of that, for example, like, like Danny was asking me, how does SOW take? What form should SOW take? Right? And he was asking me this question, right? So, I can give some examples of that, for example, and so on.

Sadra   16:32
Yeah.
Yes.
I.

Souti Chattopadhyay   16:46
I think, I think, Sadra, template and query are basically hinting to the same, yeah, same thing, just different formats, right? So, template would be a type of query, but Sumit, I do want to highlight something else. It's just beyond right now, we are thinking of in terms of summary, right? That you know, summarize what impact.

Sadra   16:53
Saghi.
Soares.

Souti Chattopadhyay   17:08
X had on da da da, but we can also extend beyond just summarizing. Summarizing is already what tools are doing and we can do it in a more intelligent and efficient manner, sure. But we can also try to see other insights. For instance, like where do Sumit and Sadra's ideas sort of diverge, right?

Sadra   17:26
Show.

Souti Chattopadhyay   17:27
where do they converge and what are maybe some of the conflicts and how did the conflict evolve over time, et cetera, et cetera. So these kinds of insights.

Sadra   17:30
Saghi.

Sumit Gulwani   17:34
So, just hold on. I'm just sending a note to someone who wants to meet regarding this meeting on Monday. So, in meeting now, can chat after 3:30. So, maybe 3:30 is good, right? We don't need more than half an hour today, right? Or do we? Or half an hour would be good enough.

Sadra   17:38
Stick.

Souti Chattopadhyay   17:40
Haha.

Sadra   17:43
To.

Souti Chattopadhyay   17:49
No, no, yeah, I have an husband, yeah.

Sadra   17:50
Big.

Sumit Gulwani   17:51
OK, sounds good. OK, I just send a note to.
Okay, so let's continue right. So Rini, what were you saying? So can you please repeat what you're saying? I'm sorry, I lost the, I forgot the context.

Souti Chattopadhyay   18:01
Oh yeah, so what I'm saying is that we are focusing on summaries, but the point that you raised is like AI summaries, people are already picking up on it. They're trying different formats of doing it. We are saying we'll do it in a more efficient, more user empowered way by giving the user the ability to figure out how they want the summary.

Sumit Gulwani   18:10
Yes, yes, yes.
So, so two things I'm saying, right? So two things I'm saying, right? So one is that you know we'll have this general views, right? But I think the two novel contributions are we will allow mashing it up with private information, which is semi-private information. This is one thing that we talked about, which I think is really novel. No one has talked about it. We should make a big deal about that. And the second thing I'm saying is, let's try to think about processes.

Souti Chattopadhyay   18:21
That is.

Sadra   18:29
So.
SC.

Souti Chattopadhyay   18:34
Yeah.

Sumit Gulwani   18:39
That will, that will make this more efficient, because I might have more and more views, more and more queries, but my number of transcripts keep growing. Am I going to keep, you know, processing all those in 1000, 10,000, you know, conversations over and over again, or how can we make this process efficient? I think, in my mind, those are the three most interesting things. One is views, but it's not how it is novel. We'll have to think about how it is novel, right?

Souti Chattopadhyay   18:45
Yes.
Mmh.
Mhm.

Sumit Gulwani   19:02
But then the part that I'm very clear about is this private mashing of information. And the other one is thinking about organization of these knowledge bases in a way that processing is efficient. And tomorrow, if we have better models, or we have better ideas around how to summarize some information, which we should, by the way, discuss.
Because summarization is not straightforward, we should discuss that more. So once I have more ideas for summarization or better models, I can regenerate my wiki with the same raw information. Raw information does not go away, right? And the other thing also that Sadra talked about yesterday was, you know, deletion, because this information is a timestamp information.

Souti Chattopadhyay   19:33
Mmh.

Sadra   19:33
Yes.

Sumit Gulwani   19:40
And we need to make sure what parts to forget, what parts to delete, and curate, so that this knowledge base does not, you know, grow, you know, uncontrollably, you know, large and so on. So, those might be interesting, right? A summarization thing, right? Let I got another idea from a person, and this is where we need the need it to be. People, we need to allow people to create different workflows. We can provide them some sample workflows.

Souti Chattopadhyay   19:44
And.
Mhm.
Yeah.

Sumit Gulwani   20:07
Oh, Sumit, you're describing me this transcripts game. In my knowledge base, I am actually, so they don't even use this lingo, right? They describe it in some other lingo, but I think they are doing, everyone I think who is doing something interesting is in some sense curating their own knowledge base. They're not using this lingo. This thing is not being, you know, understood, you know, in this way that we are trying to understand now, right? So this person said.

Souti Chattopadhyay   20:24
Yeah.
Right.
Yeah, yeah.

Sumit Gulwani   20:30
that, oh, do you also maintain presentations? And what do you do with those? How do you process them? Well, let me tell you what I do. So after every talk, I store the presentation, and then I ask the AI agent to generate a summary of each slide based upon the transcript. I thought that was quite cute, and that was quite powerful.

Souti Chattopadhyay   20:36
Mhm.
Mhm.

Sumit Gulwani   20:49
So it's not a summary of the entire presentation, but what she does is she asks an AI agent to take the transcript of the speaker, and for each slide, generate a summary of that slide.

Souti Chattopadhyay   20:59
Mhm.

Sumit Gulwani   21:01
That may not be what, you know, an AI somebody would have been doing if you do not provide this guidance. And tomorrow, someone might come up with another idea. Let me give you another idea, right? Instead of generating summary of each slide, I would say, oh, does the slide have an outline? Are there 4 topics in this slide? Three topics or four topics? And for each topic, summarize them.
That might be another interesting job, generating Sumit.
And then, depending upon how you summarize, you might see differences in downstream, you know, processing of that information.

Souti Chattopadhyay   21:33
Mhm.

Sumit Gulwani   21:34
In fact, I have probably I might have told you or not, but what I find is that just repeating the workflow three times leads to better summary.

Souti Chattopadhyay   21:42
Mhm.

Sumit Gulwani   21:43
Now, should we waste compute cycles on that? Or is this more of a temporary phenomenon with a certain model that I am observing? Or it is just that how I ask the model to process, you know, is different? So why does generating three times, you know, somebody, you know, makes a better job, right? Because when I'm summarizing something, what am I doing? If I go in a linear fashion, I will do slide one, slide two, slide three, or I will do transcript one, transcript 2, transcript 3.

Souti Chattopadhyay   21:46
Mhm.
Mhm.

Sumit Gulwani   22:04
But if I ask the system to repeat the process, then what happens is that it already has a summary and that refines that summary by again going through those raw data sets. And what that does is that earlier you did not see slide 3 before slide one. You went sequentially, but now you have seen slide 3 and now you're reprocessing slide one. So you might be able to better understand and interpret and extract some nice meaning out of it.
and so on. So what I'm trying to impress upon is that different ways of summarizing might yield to different results, which is something that I already observed, but I do all of my own adopt processing and so on. But one way to think about this is that I have my own way of distilling the essence out of some of these transcripts or how I am processing them.

Souti Chattopadhyay   22:47
Mhm.
Yeah, yeah, this is interesting. So something that popped into mind, Sadra, a quick note, there is this paper called Memolet, which looks at how human memory stores working, stores information and shifts between working memory, procedural memory, declarative memory, et cetera, and to bring things back and forth into.

Sadra   22:57
Yeah.

Souti Chattopadhyay   23:08
the working buffer, worth looking at regarding something you can throw together for the how to manage deletion, forgetting, et cetera, et cetera.

Sadra   23:14
Call.

Sumit Gulwani   23:15
So this is beautiful. This is beautiful. Now you're talking, you know, really right now you're bringing in some, you know, some very interesting, fascinating points here, right? So, so let me, that reminds me of another topic that I wanted to talk about. I completely forgotten, right? So what really you're talking about is how do we leverage lessons from human sciences, cognitive sciences, to think about some of this, you know, memory management and summarization, right?
Now, so very beautiful, like, so AI, please take note of it. I think that will be another, you know, very interesting area to get get inspirations from. Now, on that note, right, on that note, let me.
Share. Oh, by the way, another example, I'll give it any right. So someone contacted me and said that, oh, you know, I'm submitting this, you know, grant proposal. You know, can I please use your name? And if you're interested in this, you know, you can also help revise the proposal. So I did help them revise the proposal. I said, I don't need any money. You know, you can, I can just help you, you know, as much as I can and you can reward me by making me a co-author on a paper if you believe you have contributed enough, right? So this is what I said, right?

Souti Chattopadhyay   23:54
Hmm.
Mm.

Sumit Gulwani   24:14
Though I am just participating as an unofficial, you know, contributed, so, but then I did help them, you know, with their proposal.

Souti Chattopadhyay   24:18
Mm.

Sadra   24:19
The.

Sumit Gulwani   24:23
And when I held her with the proposal, I thought I had very, very meaty humor points.
But then something looked a little bit odd to me when I was when I was looking at the revision to the proposal.
And then I immediately, you know, realized by mistake and I fixed it. So I said, look.
These 3 sentences seem to come from the paper that Rini had shared with me, which is unaccepted yet.
And I do not want you to include any ideas that are not mine.
that my collaborator is trusting me and it is not even published. So you got to delete it. But if any of this is public information, meaning if you got this thing in that paper that is being referenced, you know, from past paper and so on, then it is okay to do that. So it made that edit.
That was an example of how unintentionally that proposal, you know, got, you know, two or three sentences, which I immediately remembered were coming from the work that you had described, and I asked you to remove that.

Souti Chattopadhyay   25:14
Yeah.

Sumit Gulwani   25:24
Okay, but going back to this thing about connections of human sciences, let me actually share with you a prompt that today I interviewed someone, interviewed meaning no past colleague at MSR and I really wanted him to explain his work to me and I recorded the transcript, right? That's why I'm calling it an interview.
But this is what I asked him, right? So I asked him his methodology.
For processing his logs.
Okay, so you talked about summary, right? We talked about summarizing. Point #1 that I made, that summary can take many different creative workflows. There is no notion of this is the summary, and that is the architecture that we want users to be able to define, right? So our system is not just about views, right? Our system is also about architectures and workflows that can be defined by different people.
To help populate those views.
And I give some examples, and then Rini immediately give another perspective of leveraging wisdom from human sciences. So let me show you another such summarization technique that I learned from someone today, which is inspired by human sciences, and it is their creative work.
Right? It is not like, you know, this is the way to compute somebody, right? Everyone can bring different creative ideas to the table. So let me share with you one such another creative idea inspired by human spine. So I read out the prompt to you.
Okay, and in this case, what they're summarizing is a human-AI agent trajectory. Okay, so we can summarize a human-human conversation, which is what we are doing right now. We can summarize human agent trajectory, which is what I'm going to read out to you. Or we can summarize a polished document like the slides and so on. I feel that most of the documents can be described into three.
Three forms, right? Maybe there are more sub forms, but I think 3 fundamental forms of information are human-human, which is what we are doing, a human agent, which is the right session thing, and the third one is, you know, some polished, you know, documents like papers, slides, which may not even be my own, right? It may be someone else's.
So this one, this prompt is for summarizing.
Human, human agent communication. OK, so I'll hit this side.
I have collected logs for many interactions with Copilot. I want to build a deep understanding of these interactions and I would like to do this by analyzing the logs slowly.
Now pay attention to this. My idea is to apply techniques from grounded theory to do this. And he points to the Wikipedia page about grounded theory.
Andy says that this process will involve dissecting the logs into small fragments, each containing some snippet of user interaction tool use model using steps. And for each such snippet, the grounded theory methodology aims to classify it using a coding scheme, which is developed iteratively as we analyze the data.
The language of codes is open-ended and can evolve as we discover new patterns in the data.
However, some initial codes that I have in mind include blah, blah, blah, which include user intent and some description of that, tool use, model reasoning, user feedback, user expertise, intentional outcomes. But these are just initial ideas, and the actual coding scheme will evolve as we analyze the data.
In the end, I want a comprehensive understanding of this corpus with detailed insights grounded in the data and overall theories, categories, concepts, et cetera. And the end result should be recommendations in the following dimensions. And I think these dimensions that he's describing are the views that he's talking about, right? But
So this is like the nature of the prompt, right? So now if you think about this prompt, he's talking about the views, but it comes at the very end. But before that, he talks about how he wants to analyze and summarize these conversations.
And what he told me was that even though he does not understand this much, but he borrowed this from the HCI literature, and this is what people do. So in HCI, people do these user interviews, which are all these transcripts, human-human transcripts, but I'm taking inspiration from them. I'm taking that the methodology is that HCI people apply to human-human raw interviews to human AI.
And the way people typically analyze open-ended interviews is by using this methodology. So do you know about this already, Rini? You are in the field, you probably might know about all this grounded theory concepts.

Souti Chattopadhyay   29:49
Yeah, yeah.

Sumit Gulwani   29:52
So I made one request to him. I said, can you please, you know, reanalyze your logs without pointing the agent to grounded theory concepts and then see what happens. And then probably he will let me know. And that will let us know whether it really made a difference for me, right? So that is another interesting opportunity. A good idea.

Souti Chattopadhyay   30:00
And.
Yeah, mhm, yeah, but.
No, I would say sometimes the agent already knows what is bounded theory, so that will be interesting to see if explicitly asking it to follow this pattern made a difference.

Sumit Gulwani   30:18
Yeah.

Souti Chattopadhyay   30:19
Okay.
Yeah, this is cool.
Cycle.

Sumit Gulwani   30:25
Okay, so Sadra, if I were to then get back to the Thursday presentation, right? Then there's one thing about letting the user define the views, and we can give some examples there. And I think you already have some views that talk about it, but you don't make it make it parameterizable to the user, right? That is a change that we will need in the demo, right? So you have some existing views, but then you show how those views have occurred. Right now, it's some hidden problem that you have.
But then those views should make those prompts explicit, so that's fun. And then the other facility that we might want to provide to someone is that you can provide more detailed guidance to the system on how to process this information to populate a view. So you can leave it empty or you can provide more detailed, you know.

Sadra   30:50
The.

Sumit Gulwani   31:07
guidance to the system. So that's probably also an opportunity there. So it would be good to showcase just the view or maybe, you know, potential of describing this, some ideas around how to populate the view. And then I would say another interesting aspect to demonstrate would be mashing it up with some private information that is, you know, semi-private, call it semi-private, semi-private means that overall.

Sadra   31:10
The.
I.
St.

Sumit Gulwani   31:29
information source is private, but some parts of it are okay to be shared with this group. So that's what I'm calling semi-private. And then the third is how do you do it efficiently? That 1 I have not thought much about, right? But what kind of information somebody you can create and for any new query that comes in, how do you decide you need to go and analyze it all over again? Or can you reuse, you know, existing different summaries and so on?

Sadra   31:33
Yeah.

Sumit Gulwani   31:51
So those might be interesting. So something interesting about efficiency, right? We just think about how this will scale, right? But there's more and more, and maybe, maybe trimming is part of scaling as well, right? That's also part of the solution to make this process more efficient.

Sadra   32:08
Also, this is, I think, this for this part.
Then we can, like, piggyback on whatever people learn from knowledge graphs and scaling knowledge graphs, because I know that there are some efforts of making knowledge graph out of Wikipedia, which is like the famous one, famous knowledge graph, and if they can make a knowledge graph that's big.

Sumit Gulwani   32:20
Yes.

Souti Chattopadhyay   32:22
Mm.

Sumit Gulwani   32:28
Yes.

Sadra   32:33
I think we can make it.

Sumit Gulwani   32:37
Yes, yes. So how is it different from a typical knowledge graph work in the past, right? Maybe I just try to reflect on that. Maybe the thing that is different this time is that we can allow different users to create customized views. And the second thing that is probably different is that we can now try out, easily try out different kinds of algorithms and ideas. Because previously what would probably happen is that there would be one kind of view and one kind of architecture algorithm that someone decides.

Souti Chattopadhyay   32:39
Okay.

Sumit Gulwani   33:02
An audio graph is constructed, and what I'm observing today is that the density of ideas is so rich, because that's what now people are mostly doing.

Sadra   33:04
Yes.

Sumit Gulwani   33:11
That, depending upon the way that you summarize.
is leading to a lot of difference between what comes out and not.
Like another example I will give you, Rini, that I discussed with Sadra yesterday is that I was in another meeting and then someone talked about AI slot.
And the point was that, oh, you know, I hate reading those things where people are not even verifying and looking at the slop that AI is producing and they are sharing it, you know, here. And the trouble with all of that is that if that becomes the raw pieces of information that AI ingests in the future, then AI gets polluted.
Right, which is a very good point, right? And my perspective, a constructive perspective at that phenomenon is that this AI slop is some derived or derivative information or summary that has been produced out of some sources. And it has not yet been tagged with or user reviewed or user verified.

Souti Chattopadhyay   33:50
Mhm.

Sumit Gulwani   34:08
And as long as we maintain, you know those things, then we'll be good, right? Because AI would know that this was some derivative information computed using this kind of processing from these raw sources, but has not been human verified.

Souti Chattopadhyay   34:19
Mhm.

Sumit Gulwani   34:20
And, accordingly, you know, we will process it in the future, right? So, for example, if you think about the research paper that we have now, that paper is a derivative of, you know, many of the transcripts that we have had in the past, but it has been human-verified, a very deeply human-verified, and human-authored, so we will tag it, tag it that thing, and maybe...
Maybe it can subsume, you know, many transcripts that went into creating that stuff, probably.

Souti Chattopadhyay   34:44
Mmh.

Sumit Gulwani   34:47
So, so as you are creating the summaries, it would be good to also, you know, tag them that, okay, these are all AI created summaries, but have not yet been verified. Some of those, you know, human might look at and verify it, and then we'll again change that tag accordingly, so that kind of dominance tracking is also an important thing, and then the nice thing about this dominance tracking is that even if it is not human verified, right, tomorrow, let's say a new model comes in from the same.
source this AI slot might be turning to an AI beauty, right? And maybe you know human verification is not really needed at that particular point of time. Or when the human verifies, they will notice that very few edits to make.

Souti Chattopadhyay   35:21
Mm.
Yeah, yeah.

Sumit Gulwani   35:24
So, prominence tracking, yeah, yeah.

Souti Chattopadhyay   35:26
No, no, but...

Sumit Gulwani   35:28
And what is happening today is that everyone, right, every creative person is doing some form of this or the other by themselves, right? Because we don't have a good machinery today. And our opportunity is to learn, talk to different people, see what they're doing, and then try to build a framework that generalizes it all and supports, you know, many of those things so that other people don't have to then rebuild all of this, you know, stuff for themselves.

Souti Chattopadhyay   35:49
Yeah.
Yeah, I'm interested to see like hear about once you pitch this is at the other in the insights because I feel like summary is just the beginning point and then there is a lot more to develop on top of this. Sometimes interesting insights that we don't know until we look very closely.
at the meeting notes or something like that. So identifying interesting topics, diverging, conflicting topic topics, et cetera, et cetera, across that. These are all in the, yeah.

Sumit Gulwani   36:20
Yes, yes, and and and and as you are saying this really right, then then what the idea thoughts that is occurring to me is that suppose my goal is to actually help identify maybe one such insight that is most interesting to me, and I want to write my new blog post on that particular topic, right? Because when I create these summaries, then it is like, you know, every everything leads to like 5 or 10 interesting ideas, but my goal is...
to figure out one interesting idea that I want to talk about next.

Souti Chattopadhyay   36:43
Mhm.

Sumit Gulwani   36:44
And even this process, I will be doing with an agent declare agent on top of all the summaries that exist today and so on, and I will ask exactly these kinds of questions that you are asking, right? That, okay, what are some converging and divergent, you know, topics maybe, right? What are some contradictory topics, right? Maybe those are some of the, so that's my creativity, right? So my creativity as someone.
who has general expertise in communication and figuring out where the most spicy and interesting ideas live, I will use this trick that you mentioned, right? Which is maybe if I can find something that for which there is contradictory evidence and maybe some conflicting thing, maybe those are some interesting things to talk about.

Souti Chattopadhyay   37:22
Mhm.

Sumit Gulwani   37:23
And then, and then, you know, sometime I might say that, okay, figure out such topics, right, for which there is some conflicting information, yeah, and that part you might create with my way to actually filter out, you know, the thing that I'm really looking for, but all of this is ephemeral, right? So it is, I'm doing this, you know, for one activity and I will, you know, get it off it, but, but again, it will be an agentic process that I will use to even find the information.

Souti Chattopadhyay   37:29
Yes.
Yeah.

Sumit Gulwani   37:43
that I care about.

Souti Chattopadhyay   37:44
Mhm.
Yeah, so how many slides do you need? You have two minutes, right? So 3, 4 slides.

Sumit Gulwani   37:51
Two minutes, maybe I can ask for 5 minutes probably, but I don't need too many slides here. And in fact, I'm even thinking maybe even if I use a slide through probably one slide, but it will the mode the demo has to probably make sense for itself, right? And maybe I can make it do an interactive demo or I can just open up different tabs and I can just browse between the different tabs. That would be good to showcase. But I think the three concepts that we discussed are to show that.

Souti Chattopadhyay   37:54
Mm.
Yeah.
Yeah.
Yes.

Sumit Gulwani   38:16
the notion of views, user-defined views, and algorithms for summarization, or approaches for summarization, that's one. Messing it up with some semi-private information is another one. And then the need for doing it efficiently and trimming the information. So in my mind, these are the three.
most important things. One talks about what does this support. The second one talk about this this semi-private information and the third one is how to make make the entire process efficient.

Souti Chattopadhyay   38:37
And.
So I think it's difficult to show a live demo of the private information mesh or things like that, but...

Sumit Gulwani   38:51
Yes, yes, so what we should do is, what we should do is, even if I can just have different links, like different tabs open, or maybe I do not know, maybe maybe we can we can say that, okay, can I go back to the state of the wiki now three days ago or something like that? Again, I do not know how easy or difficult to do it. We don't necessarily do it. I can just show these different tabs, different web pages, and that would that would work.

Souti Chattopadhyay   38:55
Yeah.
But for instance, like efficiency and pruning is not yet something that's not.

Sumit Gulwani   39:13
Maybe you're right, right? Efficiency in pooling is something that I can just speak about. I think that will be difficult to demo. Yes, you are right, yes.

Souti Chattopadhyay   39:17
Yeah.
Yeah.
One thing Sadra can do easily would be to do a mock up of this, like the ideas for you to like point out when you're talking about if you need, but the basic functioning of the the tool specifically showing like just for very quickly so you can go over the basic idea and then talk about like the three points, the views and the efficiency and that they so.

Sadra   39:25
Yeah.
Best.

Souti Chattopadhyay   39:44
Uh, that that Sadra can do right, Sadra.

Sumit Gulwani   39:46
Yes, I I love that, I love that, right? So there's a lot of clarity here in Rini what you said, right? So let me go over it, right? So first point that Rini said was that it would be easy to visualize the notion of different views and different algorithms for summarization, or different, let's call it the workflows, right? Different workflows that different people are using for summarization, and then what we want to do is to make it easy to define views and to make it easy to define different workflows, right? So, for example, one workflow might be...

Sadra   40:11
Yes.
Soares.

Sumit Gulwani   40:14
We summarize two different slide decks together, right? And those are all the different algorithms, or workflows you can call it, right? Workflows for populating the views, right? Workflows for populating the views can be empty; user does not have to define it, or you know, they can potentially define it and they can they can construct it by using some basic components, right? As we're thinking about, as you think about how these different different...

Sadra   40:19
S.
Text.
The.

Sumit Gulwani   40:35
architectures will be defined, or different workflows will be defined for populating the views. You can even think about them as some, you know, visual building blocks and so on that we can showcase, you know, combine these things, compute this summary, or repeat this process and so on. So maybe there's a visual language that you can imagine that someone can put up together for defining their workflows for constructing these views. So that's one, and that's very visual, right? And that can be shown. The second part is around.

Sadra   40:42
Chuck.
Soares.

Sumit Gulwani   40:59
Populating it with semi-private information, so that one we don't want to run the processing online, so we just want to make sure that, you know, look, when the user user pointed this wiki to a semi-private information with the right filters, the filters might be that, oh, I spoke to this, here's a transcript or here's a document from this other part. Whatever part in this document is not a novel idea of this paper, but part of related work or pointing out some.
observations you can use. So this would be the example of Rini's paper, right? So my system ended up using Rini's paper to populate the proposal for this other person, but I said no novel thing should go there.

Sadra   41:24
Sing.
Stop.
Yeah.

Sumit Gulwani   41:33
Then, the other example of this was, you know, is doing a conversation with someone on my own personal transcripts you know with conversations, Microsoft people, you know, every such conversation contains a lot of private details, but all of this conversation also contains some general observation that is okay to extract, so, so if you can show this by just means of that, look, you know, when I ingested this information.

Sadra   41:50
So.

Sumit Gulwani   41:54
this Wiki changed like this. So again, this need not be visual or a live demo. I can just mention two different tabs, two different states, and I can just show that when we brought in this information, that look, this new insight emerged, or this new thing actually happened. And that would be good to talk about. But then there has to be a story here, right? And a story that I can explain very quickly that this conversation or document was about this topic.

Sadra   42:00
SN.
Yes.

Sumit Gulwani   42:13
Pick X, the wiki, the view that I, so this wiki is about this group G, and one of the views is view Y.

Sadra   42:18
Two.

Sumit Gulwani   42:20
Then I matched this Wiki or as a person I had access to the semi-private information X and I could match it up to refine the view Y. So that would be the second part of the story. And a third one is just more of a mention that we need to do this efficiently and we need to also have algorithms for trimming or workflows for trimming information or when the information gets invaluated.

Sadra   42:30
Just.
The only part that's so the document that I shared with you already has something for the second part that you mentioned, but I will work on the example to make it simpler, because right now it's like very every one one thing that is not.

Sumit Gulwani   42:56
Yes, exactly, yes.

Sadra   43:01
Here completely for me, and I should think more about this is the first course, and how we can connect the notion of summary to this. For me, what I understand here is that if you're motivating the idea that we need to connect some personal...
Some some semi-private information that is not shareable.
Ohh.
To the like.
In our presentation, and we cannot do it with current tools now, and then this is this is the tool, so like the motivation is more about sharing the how to effectively share the semi-private information.
Elective.
Previous version better that has this.
like notion of we showing different views and how internal information can be present in different views.

Souti Chattopadhyay   44:08
Um...

Sumit Gulwani   44:08
Oh.

Souti Chattopadhyay   44:10
Yeah, sorry, Sadra, there are like 3 contributions that or three emphasis Sumit wants to make, right? One is the different views. So what you have for the different views, we keep it. And that's where he's, Sumit is saying like there's a view Y and then there's a view X maybe which differs, right? The second contribute, the second highlight may be a different tab, a different slide.

Sadra   44:15
Yeah.
The.
Yes.

Souti Chattopadhyay   44:33
would be sort of comparing side by side that, you know, without private, like without any sort of access control, this private information might leak into and be released to a wiki that's to someone that it shouldn't be, but we are going to do it in a way where we have control over what kind of information.

Sadra   44:55
Yes.

Souti Chattopadhyay   44:56
passes to what wiki and then Sumit can use that graphic to sort of explain and talk about what he is trying to, he is trying to say.

Sadra   45:02
Uh.
Exactly, so, so, so I think that this is this is not not not a good motivation for us, because we are basically claiming that we are very like we are providing a tool for verifying that no private information is is passing, but this is something that is very hard to claim, and I think this is not the core contribution. If you if you present it as...
Then this is like a like a sighting that that you're presenting, but this is not should be our core contribution. We we don't know if the.
Digested information in the Wiki; someone with digested information with the Wiki can return back to the actual information or not, so that that's why I think we shouldn't focus on this.

Souti Chattopadhyay   45:45
Right, so we are not claiming that we will do it, but this is, you know, this is sort of like a pitching, high level pitching document, right? Pitching presentation. So, yeah, yeah, it's sort of like to get the buy-in because that is going to be a concern at the high level. So we address it so that they don't immediately reject our idea that, well, this is a limitation and it's going to fail.

Sumit Gulwani   45:53
Yes, yes, yes.
Yes, exactly, yes.

Sadra   46:00
Okay.

Souti Chattopadhyay   46:08
Right, so Sadra, you won't have to implement this, but we have to talk about it to sell the idea.

Sumit Gulwani   46:08
Yes, yes.

Sadra   46:09
So.

Sumit Gulwani   46:11
Yes, yes.

Sadra   46:14
Okay, okay.

Sumit Gulwani   46:15
Exactly. So in the first part, I will say there are two things to talk about, right? One is the views. So maybe we have two different examples of views, and I think I like one example that is more focused on the person and their contributions because everyone in Microsoft will resonate with it when they write these people's reviews and so on, and there's a season going on right now. And then the other one is, you know, some topic for which I want a summary.

Sadra   46:26
This.
So.

Sumit Gulwani   46:35
And then also the second notion here is workflows. Like how do the views get populated? So I might have my own ideas around how I want to summarize and so on. And that may also be worthwhile talking about. We can decide that, right? Maybe a small mention or something. Then the second, so in the first part, there are two dimensions, right? Views and workflows for populating their views. Workflows in the default word can be empty.

Sadra   46:49
I.

Sumit Gulwani   46:57
But in some creative case, in some person might actually creatively define what these, you know, processes are like. I give you very good examples, right? So I give you an example of how grounded theory was used by one person. I give you another example of how one person decided how they want to summarize their slide deck. I give you have given you example of how I produce some of my blog posts, internal Microsoft blog posts, where I...
process the same information over and over again. I do it like three or four times. I repeat that, repeat that process. So these are very different ways of workflows, very different workflows. And we want our system to be flexible enough to let people define these creative workflows. So that's the opportunity. So those are two different things I'd use in workflows. Now for the second part about this meshing about this private information, I'll tell you what all the presentations that I keep seeing around myself, right?
All people are talking about access control. That's what they're talking about, how to implement access control and so on. And I think we're already going to step one step higher. We are saying that this raw information, if you were to just naively try apply access control, the answer would be no. Don't leak any, don't leak this information because this is a private document between Satya and his directs.

Sadra   47:48
Bing.

Sumit Gulwani   48:01
And how can how can this information or for this you know flow into you know other technical things right? But there are maybe there are aspects of that you know conversation which are okay to talk about and which can actually help refine and add value to many other views that are already out there. And that's what we want to facilitate. And this is where the belief that I am saying is that we all understand that the word knowledge.

Sadra   48:01
Yes.

Sumit Gulwani   48:25
is much more than the knowledge that lives inside each clicks. And the word is connected. We know the word is connected. So how can we not leverage that opportunity that we have? We got to leverage that opportunity.

Sadra   48:32
Yes.

Sumit Gulwani   48:37
and having some kind of filters and so on. I do not know how that would be maintained and guaranteed and provided. That we do not know. But one thing that I'm already doing in my workflows with whatever responsible use I can have is by giving simple instructions to the model that take information out, but don't take out information that the author told me not to.
or don't take out information that is Microsoft's IP. Now how do you formally define these kinds of things and so on and verify these kinds of things is very challenging and I'm not getting into that. But what I'm telling you is that this is the place where I add and I immediately bring unparalleled value to any discussion in a very effective and quick way. You got to understand and realize this, right, that when I send you some notes or when I send anyone some notes.

Sadra   48:59
Yeah.
Yes.

Sumit Gulwani   49:21
These are not just coming from that transcript. These are coming from the rest of my knowledge and wisdom that I have distilled and is living into other documents, which I'm not allowed to share with you. That would be a breach of trust and privacy, right? But there is information that is relevant that can be distilled out and is relevant to our conversation, which I should be allowed to and I should. And that's the point I'm making.

Sadra   49:28
Yeah.
Yeah.

Sumit Gulwani   49:43
How do you enforce this is tricky, but what I want to emphasize is that that
We cannot leave this out of the table, right? The way I contribute to our conversation, if I have to do it from scratch all over again, it is not an efficient process. But a lot of Sumit Gulwani lives inside all of those transcripts and these other transcripts, my other part of my life. And how do I help AI, you know, get access to that and use that to enrich my contributions in this group?

Sadra   50:03
So.
Yes.

Sumit Gulwani   50:12
Yeah.

Sadra   50:15
Sister.
I think we we are we are at at 3:30. Can can I have access to the meetings, the transcript, or like summary, or anything like that?

Sumit Gulwani   50:20
Yes, yes.
Yes, yes, I will send you the, you know, give me a few minutes, I'll meet with the other person, and then I will send it, send it to you, yeah.

Sadra   50:31
Is awesome.

Souti Chattopadhyay   50:31
It's awesome. I love how we are all going towards digital twins.

Sumit Gulwani   50:32
Okay.

Sadra   50:36
Yeah.

Sumit Gulwani   50:37
****.

Souti Chattopadhyay   50:41
Yeah, but it's a nice concept. So that giving the knowledge of the tacit knowledge, right, of who to talk to about what, the subtle things that we like internally know, but we never express, like, you know, you know, includes pain, shared experiences, emotions, past, history, interactions, all those things.

Sumit Gulwani   50:42
Okay.
Yes, yes, yes.
Yes, yes.

Sadra   50:58
The.

Sumit Gulwani   51:00
Yes.

Sadra   51:02
Thanks.

Sumit Gulwani   51:03
Love this, love this, love this.

Souti Chattopadhyay   51:03
Not just private information, right? But I know how to talk to you about certain topics and how to talk about it differently with someone based on my past experiences, right? So all that in knowledge, wisdom, and how to actually map that onto the digital twin is interesting.

Sadra   51:16
Which?

Sumit Gulwani   51:22
I, I, I love this. I love this AI. Please take note, right? This thing I found very intriguing what really just said, because this is not just about the technical content, but also some other meta thing about that can also be distilled, you know, from these past interactions, which we know are definitely there, right? The style of speaking, how do I deal with a conflicting situation, or you know, this kind of situation, how do how I have?

Sadra   51:43
Yeah.

Sumit Gulwani   51:43
dealt with it in the past, right? And that's probably no more of my identity than my contribution to a very specific technical topic. And this thing is like, you know, just infused in all of my conversations, right? The way I manage a conversation with a certain group of people in a certain situation and so on. Beautiful. I love this. I love this. And I also love this very specific words that you use, right, which are very evocative, like the pain and so on, right?

Souti Chattopadhyay   51:54
Thanks.
Yeah, yeah.

Sadra   52:04
Yeah.

Sumit Gulwani   52:07
So, we'll make sure that that AI actually know distills that wisdom out.

Souti Chattopadhyay   52:07
Okay.
And.

Sumit Gulwani   52:12
The.
And as you were saying this, there was another thought that came to my mind, but I'm not sure if I recall that now. Give me like a few seconds to see if I can page it in.
Yes, so Sadra, one other thing I loved about, you know, the wiki that you created was that when you said give me some, you know, unique insights, so I don't know what exactly you use, right? That's another thing that we should probably support because that to me is the biggest power of all of this because right now what you're talking about right now all is we are.

Sadra   52:44
The.

Sumit Gulwani   52:45
Saying that, you know, what will take in 100 hours, you know, can probably be done in, you know, one minute, right? But if we bring all this knowledge together and set up the workflows and so on, right? But the other biggest potential that I see here is this around associative thinking, producing new ideas, right? Because when you have an organization of the size of, let's say, 10,000 individuals, right? And all these transcripts and you have the keys, you know, you have multiple wikis being managed together, you know, all those things.

Sadra   52:50
Yes.
Soares.

Sumit Gulwani   53:09
and so on, right? The question that you can ask is that anyone who has access to know all those wikis, right? The question that they can ask is surprise me, right? You know, give us me some unique insights. And it can involve combining ideas from one group and an idea from another group to produce a new idea. And that's how progress happens. If you think about scientific discovery, that's how we do as scientists. Like we produce a new idea, whatever new idea is always

Sadra   53:32
See.

Sumit Gulwani   53:34
typically a combination of two other ideas that we know about. So we'll group them together, we'll combine them together, right? That's one way how creativity works and how progress happens.

Sadra   53:44
Soares.

Sumit Gulwani   53:44
Up until now, humans were doing it, but each human has a certain cognitive constraint. But AI can process much more information there. And when all of this information is organized like this, then you can imagine some very fascinating views that we can create, some very creative views. Because these two views that we talked about, design document for topic X, and you know, what the contributions of a person X, you know, are.
important, mundane, but mundane, I would say, right? The most fascinating views would be along the lines of, you know, come up with some innovative idea that combine these existing ideas. I know what surprised me or who, you know, should talk to whom. And maybe Dini also talked about some such things where she said that, oh.
which ideas are appearing contradictory or tell me the idea that is, you know, most common or something like that, right? You know, some of these meta questions that we can ask, you know, that would be very, very empowering as well. So we can imagine some interesting, we can even, even, you know, even inspire the audience to say that, yes, you know, look, you know, 100 hour of processing becomes, you know, one minute of processing because you can define these will be like X, Y, and Z.

Sadra   54:38
16.
So...
I.

Sumit Gulwani   54:50
But hey, we can also define views which would not have been possible to populate, you know, earlier, just because of the sheer amount of information and those people not even talking to.

Sadra   54:53
This.
Yes.

Souti Chattopadhyay   55:00
Mhm.
A quick note on this, Sadra, a very interesting paper out there in IEEE Viz on basically data processing, but how to pick the best graphs. They were trying to find ones that deviate the most from the user's expectation. Now, expectation is hard to find in terms of give me insights.

Sadra   55:21
Please.

Souti Chattopadhyay   55:21
But we can definitely find how the one that is the farthest from the user's own documents only, right? So you can find ones that are like very different or very like distant from what the user was thinking. And that can get you to the one that you're talking about, which is insight. Insight can be based on surprise or deviation from expectation.

Sadra   55:28
I.

Sumit Gulwani   55:28
Mhm.

Sadra   55:32
Soares.
Yeah, I will, I will use this as a vanilla example to ask the agent directly to see how it works, and yeah.

Souti Chattopadhyay   55:45
Yeah.
Yeah.

Sadra   55:55
Report this song.

Souti Chattopadhyay   55:58
Cool, super cool.

Sumit Gulwani   56:00
Okay, so let the focus be on this Thursday presentation, right? And then whatever you can do for Monday presentation, you know, do that. But as I said, Iran, the two things are just tell them the details and the user study, they should not take much time, you know, to populate, right? But otherwise, let's put all our energy on the Thursday presentation. And as soon as the Thursday presentation is done, let's think about where can we publish this and what experimentation would we need there, right? I think this is really big. This is big, very big, I feel.

Sadra   56:08
Yes.
The.
Soares.
This is.

Sumit Gulwani   56:25
And we want to be one of the first ones to, you know, talk about it.

Souti Chattopadhyay   56:26
Yeah.
Sadra has a series of four vapors planned on this idea, so we'll see.

Sumit Gulwani   56:36
Okay.

Souti Chattopadhyay   56:37
Thanks, Sumit. Thanks for advocating for the work and getting Sadra this much visibility and the work this much visibility. Hopefully this goes really well on your side too. And yeah, listen.

Sumit Gulwani   56:38
OK, then. Thanks, Hosein.
Yeah, yeah, no, I really enjoy chatting, chatting here, and I feel inspired and I become more creative and I talk to you folks.

Sadra   56:53
The.

Souti Chattopadhyay   56:56
Nice.

Sumit Gulwani   56:57
Okay.

Sadra   56:57
Tesco.

Souti Chattopadhyay   56:58
Cool.

Sumit Gulwani   56:59
Okay then, thanks Volz. Have a great weekend, dear. Bye bye.

Souti Chattopadhyay   57:01
Yes, bye-bye.

Sadra   57:01
Template.

Sumit Gulwani stopped transcription
