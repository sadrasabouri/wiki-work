---
timestamp: "2026-05-05T17:10:02-07:00"
source: "[[Sadra-4May2026-TRANSCRIPT2.docx]]"
source_path: "raw/meeting-transcripts/Sadra-4May2026-TRANSCRIPT2.docx"
source_type: "docx"
tags:
  - extracted
---
# Sadra-4May2026-TRANSCRIPT2

Source: [[Sadra-4May2026-TRANSCRIPT2.docx]]

Sadra Sumit sync south-20260504_190126-Meeting Transcript

May 4, 2026, 2:01AM

13m 24s

started transcription

Sumit Gulwani   0:03
Yes, I can hear you. Yes, yes, yes, yes. I was doing some work and I was too tired. I just took a 5 minute break and I thought I'll enter in myself. Like, this is fun fun. This is what makes me really happy, you know, compared to the crap that I'm doing and I have to do for some weird reasons. Okay, now what I was thinking was that this Twitter example that you have, right, you know, this Twitter example you talked about.

Sadra   0:03
Okay.
Ohh.
That's good. That's good.

Sumit Gulwani   0:25
That, ohh, our raw data will also have an ingestion of lots of, you know, tweets, and then some researcher agent, you know, produces those tweets and so on.

Sadra   0:30
Yes.

Sumit Gulwani   0:35
And then from there I will do some.
processing, maybe let's say all these tweets are probably images or whatever you can think. Some of them are images, maybe some of them are text. I don't know what the format would be. But let's say there are images, just between their images, right? So then something has to be extracted from that, right? Some summary has to be created out of that.

Sadra   0:48
Yeah.
Videos, it must be OK.

Sumit Gulwani   0:58
And.
And then from there, you will then create maybe a one-page collection of good stories, right? Or maybe, you know, three, you know, top stories you'll pick up and so on. So this workflow that is there, right, is a provenance that is being maintained here.

Sadra   1:10
Yes.

Sumit Gulwani   1:19
or this data dependencies is what we need to be able to capture. And our knowledge base or knowledge map need to be able to show this. It should be able to show what thing was computed out of there.
And we have talked about this, that we need to understand this, and this is how we'll optimize the process so that, let's say tomorrow, if we add in one more tweet, then it's not like, you know, we repeat the entire entire computation, you know, again, so we should know. So, maybe there are some some basic concepts to be applied from some basic MapReduce, you know, kind of computation and so on, right? So, most of the computations are mostly going to be on MapReduce, not all of them, but most of them.

Sadra   1:33
Yes.

Sumit Gulwani   1:56
So all those optimizations might be in play. So again, let me just summarize, you know, what you have already discussed and what is the new thing that I'm trying to say, right? What you've already discussed is that we need to be able to process the raw information and store it in some more

Sadra   2:08
Mm.

Sumit Gulwani   2:18
refined manner.
And then other things will be created on top of that refined thing.
Maybe a good analogy is even, you know, I do this mining, right? I mine all the different kinds of materials, you know, from earth. But then when I mine all those materials, then they might be in raw form, right? So let's say I do a lot of mining of gold.
Right, so, so there's a process I mine gold, right? But then I convert gold into jewelry later on. So, similarly, it's a two-stage process that we have two-phase process typically that we have talked about, but it but it can be more more phases also, right? It can be more dependencies also and so on. So, similarly, that we, you know, also...

Sadra   2:48
Yeah.
Yes.
I understand you.

Sumit Gulwani   3:08
Will lend itself to such a such a thing, right? So, this is the kind of thing we have talked about, and why is this important? Number one.

Sadra   3:10
So.

Sumit Gulwani   3:15
That this is how computation should be done, and it will lead to better results, as of course to, you know, just asking the system to just process all the raw information and prove the final thing. And second is that this is also going to lead to efficiency. So this is what you discussed in the past. Okay. So now what I'm trying to say, the new thing that I'm trying to say now is that let's also have a graphical view of this information for the user.

Sadra   3:29
Exactly.

Sumit Gulwani   3:39
So that the user knows what exists and what was existed from what.

Sadra   3:45
Yes, relations between.

Sumit Gulwani   3:45
Yeah, maybe exactly, so graphical view of all this, you know, of all the relationships between computation, computational dependencies, right? Computational dependencies, so all these are dr artifacts, right? Some are artifacts, but a lot of them are dr artifacts, and especially this thing also resonate with these other individuals that I was talking to about that, that when we have AI created stuff, right?

Sadra   3:59
Yes.

Sumit Gulwani   4:06
Sometimes it might be just being AI slop and we don't want that to pollute other things. So any AI created artifact also can have a flag, right? Whether it is validated by humans, you know, who has validated it and so on. So all that tracking can also be done. And then once you think about this overall view, right, again, not very different from the Pista project in some sense.

Sadra   4:10
Yes.
Yeah.
Yes.

Sumit Gulwani   4:26
that we want to create views for the users of the system. In this case, the view is going to be that of the, how the information was computed and how the information flow and so on. So can we actually show this kind of view, right? So all the raw facts will be there.

Sadra   4:41
Mhm.

Sumit Gulwani   4:45
All the off actually be there, but then can we show what was say completed from with those?
And can people see that view easily? That would be one interesting thing.

Sadra   4:57
So, you mean...
So, so you mean?
the relations, so we already have the relations of views to the wiki, which is by your analogy, would be mined information or knowledge. And then if you want to have a link from wiki to sources, right?

Sumit Gulwani   5:06
Star.
So, so all the views, right? Because wikis are also a special kind of view, right? But right now, let's just pretend that, you know, there are two different levels, right? What you're calling wiki and then you're calling something as views, right? But wiki is also view, right? But then data dependency between all of them, right? So view came from which wiki and then each entity in the wiki came from, you know, which part of the, which sources, essentially.

Sadra   5:23
Yes, this one.
Yes.
Just.
So.
Yes, we are ready.

Sumit Gulwani   5:37
So being able to see that.

Sadra   5:40
Yeah, we we have have this thing right now, so yeah, we we can do that basically, and we have it right now, yeah.

Sumit Gulwani   5:44
Okay.
Okay, that's wonderful, right? Because now if you want to show, explain this thing to someone, you, let's say if you bring up the view.
the view view, then if I go to this particular, so now I'm using the word view in many ways, in different meanings. But then the person should be able to immediately understand the overall structure of the wiki and the different views, like what led to what and so on. So that's very cool. I have not checked that, but what you're saying is that there will be node called people, there will be node called

Sadra   6:05
Information.

Sumit Gulwani   6:19
project, there will be a node called what is common to the two projects or something. So there will be nodes like this and then I will be able to see the edges between them.

Sadra   6:32
Yes, yes. In fact, one of the views that we already have, I think the view, the timeline view, let me send you the link to timeline view, because that one, I think it was one of the interesting ones. That one has links to...

Sumit Gulwani   6:33
Okay, okay, very nice, very nice.

Sadra   6:50
The.
Yeah, sources. So here's the...
Ohh.
This is the source of the event, but the event here is similar to, yeah, the event then then is sourced to the raw transcript. So if you open this link, you can see this.
Is showing you how the...
idea of views is developed over the time. So this is the view for that. And then in the right, in the source, you can click on the 2026 0 to 20. And then this will give you an event. This is the event which is corresponding to the meeting that we had and you can see the transcript.
I click on the transcript will give you the 404, but this is why the reason is that I I didn't I don't render the transcript, but we have it in the repository anyways.

Sumit Gulwani   8:04
Yes, Sadra, can you hear me? Okay, I was muted actually. So what I'm saying is that generally, in generally the source can, it should be sources, right? Because you're getting multiple things.

Sadra   8:06
Yes.
Yes, yes.

Sumit Gulwani   8:14
OK, OK, so let's just call it sources.

Sadra   8:16
But this is talking about, because this is like timeline view, it will talk about like atomic, each row is like atomic event. That's why it's like this.

Sumit Gulwani   8:35
OK, so I'm not sure you fully fully understood that answer on, but maybe maybe that's not important. And then the other, but then the other thing is that that let's say there are multiple sources also, right? So that's one complication. But then these sources might not be the raw elements, right? They might be more refined objects.

Sadra   8:55
Yes.

Sumit Gulwani   8:55
And those defined objects themselves are made up of something else. So can a user see that holistic view as one, you know, DAG at a time?

Sadra   9:07
Yes.
Yes.

Sumit Gulwani   9:11
OK, and again, yeah, again, all of these desires that I have, right, they all should be prompts in some sense, right? They all should be prompts of what you already have. In fact, this itself is a view, right? This itself is a view that we can show to people. And then a different point is...

Sadra   9:12
We can, we can do it.
Exactly, yeah.
Yeah.
Yeah, exactly.

Sumit Gulwani   9:31
That I am wondering if temporal evolution or going back in time can also be simulated using.
the user having a quick way to filter out the raw sources that should feed into a given view.
Right, so I might have a have a, let's say, it's as simple as, you know, what are the top three key ideas in the project up until now? So let's say I have a view for that. But then if I have a, if I have a facility that I can see all the raw sources that are fed into this,
And then I can filter them out. So I can say, okay, let me see what are the top three ideas the week before.
Then I just filtered out all the transcripts that were created in the last week. I filtered them out. And then the view updates, and then I immediately get to see.
I immediately get to see what are the top three ideas in the week before. So that might be another way for us to recreate time.

Sadra   10:43
Yeah.

Sumit Gulwani   10:43
Not through caching, but maybe through some more computation, but in a more declarative fashion or in a more data-driven fashion.

Sadra   10:50
Yeah.
I think this is something that's...
I haven't thought of, and our structure right now is not fully optimized for, but this could be like a like a different view in like orthogonal to Wiki. This temporal view should be, I think, a different view orthogonal to Wiki.

Sumit Gulwani   11:16
So maybe what I wanted to say was that the temporal view can be just a special case or a side effect of another more general functionality, which is the ability to
which is the ability to let them select which input sources should participate. And so let's say that not all input sources should participate. The default is that all input sources participate. But then sometimes the user might want to filter out some input sources. And when they do that, then depending upon the way they do that, they might be able to simulate temporal view.
out of this provenance that we might give them. Maybe that was what I was trying to say, right? That the moment we give them provenance to select which objects should flow in terms of refreshing a view or computing a view, then by virtue of the user selecting the right
Sources, they can they can simulate the temporal aspect of things.

Sadra   12:19
Mm.
Yes.

Sumit Gulwani   12:24
OK, anyways, you know that was just you know some couple of thoughts. I thought you know just you know call you up and humor us.

Sadra   12:31
Thank you.

Sumit Gulwani   12:32
Yeah.

Sadra   12:33
Did you get my email for the?
For the number of hours thing.

Sumit Gulwani   12:39
Yes, yes, so I informed them already, yes, yes.

Sadra   12:41
Okay, awesome.
Yeah. Thank you.

Sumit Gulwani   12:46
Okay.
And Sadra, let me actually stop the recording and then I'll talk to something else.

Sadra   13:06
Yeah.

Sumit Gulwani   13:10
OK, I can't seem to stop the recording, so let me just...
Disconnect the call and just call you separately. OK, bye.

Sadra   13:21
Okay, okay, bye.

Sumit Gulwani stopped transcription
