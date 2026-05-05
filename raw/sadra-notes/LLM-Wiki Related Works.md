---
date: 2026-05-04
---
The idea for creating a second brain or a wiki out of a raw data information using LLM agents like claude is used first by [[Post by @karpathy on X]]. He shared a prompt which people can use to convert any fleeting notes of them to extract entities out. Entities then connected to each other by their relations and form a wiki view over the information.
Since then people applied the idea into different domain such as finance ([[Claude + Obsidian have to be illegal]]), manager summaries ([[garrytangbrain Garry's Opinionated OpenClawHermes Agent Brain]]), tracking personal vibe sessions ([[cianmarboLore Lore is a living knowledge base powered by Claude Code sessions.]]).
One important distinction that such a system has is its ability to retrieve required information for grounded tasks for agents in a much efficient way than RAG systems ([[cagataysengorllm-wiki-studio A productized RAG app that turns documents and code files into a searchable wiki and AI Q&A workspace.]]) and showing that using such an structure could lead into token usage up to 99% ([[radimsemremindb An agentic memory database that cuts session tokens by 75–99%. One portable SQLite file — your agent's memory, anywhere.]]).

## Critics
+ Since conversion from raw source to wiki format is lossy this is not the ultimate solution. ([[Anatoly Krasnovsky's comment on llm-wiki limitations]])
+ There's a need for wiki-based systems to be benchmarked against RAG ([[Anatoly Krasnovsky's comment on llm-wiki limitations]])
+ In scale when graph gets bigger the tasks became untrivial and maintaining the graph would be a big issue ([[Anatoly Krasnovsky's comment on llm-wiki limitations]])