---
title: "FabricIQ: How are you using AI capabilities to bring value to the business?"
source: "https://www.reddit.com/r/MicrosoftFabric/comments/1qkd4ii/fabriciq_how_are_you_using_ai_capabilities_to/"
author:
  - "[[Frodan2525]]"
published: 2026-01-22
created: 2026-05-16
description: "I’m very interested in understanding how small to mid-sized businesses are using AI capabilities within Fabric to deliver real business valu"
tags:
  - "clippings"
---
I’m very interested in understanding how small to mid-sized businesses are using AI capabilities within Fabric to deliver real business value. Specifically, what problems are you solving without falling into the “everything must be AI” trap?

---

## Comments

> **ImDanStevens** · [2026-01-23](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o162fts/) · 6 points
> 
> I’ve found a really simple, powerful use case for small/medium sized orgs can be a well configured fabric data agent added as a tool to a copilot studio agent. It exposes insights that would otherwise be challenging for non-technical folks in a conversational way. At the same time, it gets users flexing their copilot muscles and getting used to that interaction. Pick a pointed use case and let them run
> 
> > **MoTechSdi** · [2026-01-23](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o165xf0/) · 1 points
> > 
> > Are you running the data agent on top of a semantic model or other fabric data stores? What is the recommended approach?
> > 
> > > **ImDanStevens** · [2026-01-23](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o167c18/) · 4 points
> > > 
> > > I prefer lakehouse table sources so that example queries can be provided and evaluated which isn’t the case with semantic model data sources. There is still refining you can do with SM sources though. I think the recommended approach would depend on the data sources you have available and what you are most comfortable with.
> > > 
> > > > **MannsyB** · [2026-01-23](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o1a7wd0/) · 1 points
> > > > 
> > > > Hiya. So to clarify -you're ultimately using Copilot surio, but connecting it to the SQL/LH version of Data Agents - that correct? If so, how's it performing? Are you get good /accurate results?
> > > > 
> > > > > **ImDanStevens** · [2026-01-23](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o1a9jsk/) · 2 points
> > > > > 
> > > > > Yes that’s right. I think it’s helpful getting users who may be intimidated to get started with AI acclimated with the copilot UI. It performs great but keep the data agent focused on a specific scope. Things get hairy when you try to reach across many different topics (in my experience)
> > > > > 
> > > > > > **MannsyB** · [2026-01-23](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o1ai77r/) · 1 points
> > > > > > 
> > > > > > Great thanks - we're about to embark on exactly this approach so it's reassuring others are getting gold results. Any ideas how you plan to approach complex queries - e.g. Bringing together data from different models/domains? Or is this intentionally out of scope for your use case?
> > > > > > 
> > > > > > > **ImDanStevens** · [2026-01-23](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o1ak6v6/) · 1 points
> > > > > > > 
> > > > > > > The queries can be relatively complex and you can guide the data agent along with some example queries that would bring those datasets together. But I think you need to think about the set of questions that data agent needs to answer. Are they completely different domains? You might want two separate data agents
> 
> > **adanmisogi** · [2026-01-25](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o1ju9qu/) · 1 points
> > 
> > How do you manage the cost, bro? I tried with Data Agents, but it cost way more than a Lakehouse or any other item.
> > 
> > > **ImDanStevens** · [2026-01-25](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o1jx35y/) · 1 points
> > > 
> > > A really fair point. They are VERY resource hungry to dev and test. I could really see it being worth getting a small dev/test or pay as you go capacity for data agents. The juice is worth the squeeze in my opinion but the testing crushing CUs

> **Dense-Tadpole-6634** · [2026-01-23](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o170ieq/) · 5 points
> 
> I've built copilot agents that have been used internally via Teams. These agents were built using Copilot studio and fabric data agents on Semantic models and lakehouses. Business decision makers need business data but they are not technical enough to do complex data actions so they enjoy using natural language interactions to get these insights real time from a Teams chat with the agent rather than teams chatting with an analyst and having to wait hours to get answers.
> 
> > **Frodan2525** · [2026-01-23](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o172tsc/) · 1 points
> > 
> > This is great, the reason why I added small to mid orgs in there is specifically for this reason. The companies can be small enough that there’s usually only 1 (if not more) DEs and a handful of analysts. So, this has great utility. Has information retrieval ever been a challenge within the business? With RAG models around im wondering if there’s genuine use cases and how to build it for internal use
> > 
> > > **Dense-Tadpole-6634** · [2026-01-23](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o17ae2z/) · 2 points
> > > 
> > > It depends on what information and how they intend for that information to be used. Semantic RAG is usually better from my experience but I've also seen that it's a lot better building agents to handle a specific task so that it is more accurate rather than a generalistic system like ChatGPT. So the Semantic RAG model is trained on a specific set of data structures within a domain. For example, there can be an agent trained on quantitative data processing so it excels in that specific task and another on qualitative data. These agents can then be orchestrated into a multi-agent system for cases where the business user will be interacting in a way that the response should be pulled from different data sources.
> > > 
> > > My aim is to build business users' trust in AI/BI results through high-level of accuracy.
> 
> > **Any\_Championship2409** · [2026-01-23](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o1796wp/) · 1 points
> > 
> > Ah great insight thanks! Does the usage of copilot agents negatively impacts the usage of the power BI reports?
> > 
> > > **Dense-Tadpole-6634** · [2026-01-23](https://reddit.com/r/MicrosoftFabric/comments/1qkd4ii/comment/o17bjfd/) · 3 points
> > > 
> > > BI is now AI-driven. I'd like to see agents as complementary to BI reports. I still build custom dashboards and reports that no current agent can spin up. Agents can help with follow up questions, deeper exploration of BI reports but you first need the BI reports. For example, a good use case is with using Copilot on reports. I find that users prefer to see a report that they can visualize and use as a context for agent interactions.