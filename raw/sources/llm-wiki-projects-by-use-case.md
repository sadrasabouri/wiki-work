# LLM Wiki Projects Mentioned In Gist Comments

Source comment dump: [[llm-wiki-comments]]

Original gist: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f

This is a curated extraction of comments where people presented tools, workflows, or projects that are explicitly based on, inspired by, or closely adjacent to Karpathy's LLM Wiki idea. I deduplicated repeated release-update comments and skipped generic praise, critique-only comments, and off-topic links.

Important caveat: these notes are based on the GitHub comment text only. I did not independently audit the repositories or verify current project quality.

## For Software Engineers And Coding Agents

These are most relevant if the main problem is: "my coding agent keeps starting from zero", "my repo is too large to re-read", or "I need durable project memory."

| Work | Author | What It Is For |
| --- | --- | --- |
| `.brain` folder workflow | @samflipppy | A local project-root markdown memory layout with `index.md`, architecture, decisions, changelog, deployment notes, schemas, and pipeline notes. No repo link in comment. |
| [llmbase](https://github.com/Hosuke/llmbase) | @Hosuke | Open-source LLM Wiki implementation with a React web UI, model fallback chains, Q&A write-back, and linting. |
| [tracecraft](https://github.com/Arrmlet/tracecraft) | @Arrmlet | Coordination layer for multiple agents ingesting and maintaining a wiki in parallel, using shared memory, messaging, and task claiming. |
| [compound-dev skill](https://github.com/brijoobopanna/ClaudeSkills/tree/main/compound-dev) | @brijoobopanna | Claude Code session memory skill intended to make each dev session build on the last. |
| [contextlattice](https://github.com/sheawinkler/contextlattice) | @sheawinkler | App where agents post learnings/tasks and later search/package context for future work. |
| [Claude-persistent-memory](https://github.com/pjmattingly/Claude-persistent-memory) | @pjmattingly | Persistent memory approach using NotebookLM as the backing wiki layer. |
| [magnus](https://github.com/hrishikeshs/magnus) | @hrishikeshs | Emacs manager with a version of this idea built in; commenter also linked a Claude Code PR. |
| [karpathy-llm-wiki skill](https://github.com/Astro-Han/karpathy-llm-wiki) | @Astro-Han | Plug-and-play skill for Claude Code, Cursor, and Codex: install, then tell the agent to ingest a URL. |
| [hyalo](https://github.com/ractive/hyalo) | @ractive | CLI tool for agents to search markdown knowledge bases, inspect frontmatter, move files, and repair links. |
| [CRATE](https://github.com/GuiminChen/crate) | @GuiminChen | File-first Python CLI with compile, ask, lint, ingest, Obsidian-friendly paths, and OpenAI-compatible providers. |
| [sage-wiki](https://github.com/xoai/sage-wiki) | @xoai | Single Go binary for Obsidian-compatible compilation, search, query, lint, TUI/web UI, and MCP capture from AI conversations. |
| [AgenticResearchWiki](https://github.com/HawHello/AgenticResearchWiki) | @HawHello | Research execution memory for data paths, training configs, eval records, and project write-back. Useful for ML/research engineers. |
| [Palinode](https://github.com/Paul-Kyle/palinode) | @Paul-Kyle | Git-versioned markdown memory with 18 MCP tools, hybrid search, deterministic executor, provenance, and linting. |
| [Freelance](https://github.com/duct-tape-and-markdown/freelance) | @Jwcjwc12 | Provenance-first implementation where propositions track source file hashes and stale status. |
| [ra-h_os](https://github.com/bradwmorris/ra-h_os) | @bradwmorris | SQLite-first version of externalized agent context, positioned as better than filesystem-only at larger scale. |
| [agent-wiki](https://github.com/originlabs-app/agent-wiki) | @originlabs-app | Markdown-only implementation with slash commands, no database, no embeddings, and support for Claude Code, Codex, Cursor, or any agent. |
| [llm-wiki-compiler](https://github.com/atomicmemory/llm-wiki-compiler) | @ethanj | CLI compiler for raw sources into interlinked markdown, incremental rebuilds, saved queries, provenance, exports, and MCP tools. |
| [MindOS](https://github.com/GeminiLight/MindOS) | @GeminiLight | Multi-agent memory layer where Claude Code, Cursor, Gemini CLI, Codex, etc. share and distill the same wiki. |
| [claude-obsidian](https://github.com/AgriciDaniel/claude-obsidian) | @AgriciDaniel | Claude Code plugin plus Obsidian vault. Adds hot cache, contradiction callouts, linting, and one-command scaffold/ingest. |
| [Quicky Wiki](https://github.com/anzal1/quicky-wiki) | @anzal1 | Zero-config CLI with ingest/query/lint/prune/serve, confidence-scored claims, temporal tracking, dashboard, and MCP server. |
| [remember](https://github.com/remember-md/remember) | @codezz | Turns past AI chat sessions into an Obsidian vault with people, decisions, projects, and tasks. |
| [SwarmVault](https://github.com/swarmclawai/swarmvault) | @waydelyle | Full TypeScript CLI for source ingest, markdown wiki, knowledge graph, search index, code-aware ingestion, MCP, agent memory ledger, and many agent integrations. |
| [sp-context](https://github.com/qiuyanxin/sp-context) | @qiuyanxin | Git repo plus CLI used by a team: `sp doctor` as lint, `sp push` as ingest, `sp search/get` as query. |
| [CodeSight](https://github.com/Houseofmvps/codesight) | @Houseofmvps | Deterministic codebase wiki generator: compiler API for TypeScript and regex detection for other languages; no LLM/API calls. |
| [Aura](https://github.com/ojuschugh1/aura) | @ojuschugh1 | Local-first AI daemon for persistent memory across tools, claim verification, MCP observability, and wiki mode. |
| [sqz](https://github.com/ojuschugh1/sqz) | @ojuschugh1 | Adjacent tool for token savings via content-cache compression across shell, MCP, browser, and IDE surfaces. |
| [llmwiki-cli](https://github.com/doum1004/llmwiki-cli) | @doum1004 | CLI primitives for LLM agents to read, write, search, index, list, and commit markdown wikis. |
| [Lore](https://github.com/cianmarbo/Lore) | @cianmarbo | Generates and updates documentation from Claude Code conversations; positioned for future team infrastructure. |
| [Link](https://github.com/gowtham0992/link) | @gowtham0992 | MCP/wiki tool with demo wiki, doctor, graph tools, context API, local viewer, and release hygiene checks. |
| [per-repo knowledge plugin](https://github.com/theafh/ai-modules/tree/main/plugins/knowledge_management) | @theafh | Per-codebase wiki committed with the repo; captures runbooks, decisions, recurring fixes, lint rules, and cleanup agent. |
| [SeekLink](https://github.com/simonsysun/seeklink) | @simonsysun | Local markdown vault indexer that returns semantic search results and exact `PATH:LINE` windows for agent edits. |
| [Scaffy](https://github.com/ColonelPanicX/scaffy) | @ColonelPanicX | Bootstraps schema/guardrail layers for projects: collaboration contract, session protocols, kanban, agent profiles. |

## For Ideators, Writers, And Personal Knowledge

These are most relevant if the main problem is: "I have years of ideas/notes", "I want a second brain", "I want to develop writing/research threads", or "I want my voice/journal/book notes to compound."

| Work | Author | What It Is For |
| --- | --- | --- |
| [Exocortex write-up](https://jayswamimusic.substack.com/p/i-built-an-exocortex-i-didnt-know) | @jayswami | Indexing sources plus session transcripts, corrections, and reasoning threads until the system begins reflecting the author's voice. |
| [Thinking-Space](https://github.com/anuragrpatil23/Thinking-Space) | @anuragrpatil23 | Local-first AI-native markdown workspace, described as an Obsidian-like IDE for Claude Code/agent-era thinking. |
| [Obsidian Seed](https://github.com/dkushnikov/obsidian-seed) and [Mnemon](https://github.com/dkushnikov/mnemon) | @dkushnikov | Obsidian/Claude Code setup that builds a personalized vault, schema/profile, and query write-back folder. |
| Voice-first PKM system | @peas | Telegram voice memos -> Whisper -> classifier -> interlinked KB nodes; includes KB plus draft-writing layer. Links to related blog posts were provided in the comment. |
| [idea-trace](https://clawhub.ai/lakendocean/idea-trace) | @Lakendocean | OpenClaw skill for tracking how an idea, stance, or method matures over scattered later events. Link was reported 404 by another commenter. |
| [Memex](https://github.com/memex-lab/memex) | @sparkleMing | Open-source mobile app that auto-organizes daily recordings into a P.A.R.A. markdown wiki and life-pattern cards. |
| [IDEA.md](https://github.com/pithpusher/IDEA.md) | @pithpusher | Vendor-neutral "idea intent" file format with thesis/problem/how-it-works/limits/where-to-start sections. |
| [louiswang524 LLM knowledge base](https://github.com/louiswang524/llm-knowledge-base/) | @louiswang524 | Self-managed and self-improving personal LLM knowledge base. |
| [Personal Constitution](https://github.com/thomastron/personal-constitution/) | @thomastron | Knowledge graph of beliefs, meant to make belief changes and integrity visible. |
| [MindFlow](https://github.com/liqing-ustc/mindflow) | @liqing-ustc | Obsidian + Claudian + GitHub workflow for personal knowledge and tracking. |
| [IdeasLake](https://ideaslake.com/) | @wumborti | "Data lake for ideas" that treats long-running idea threads as living artifacts rather than one-off chats. |
| [JournalClaw](https://github.com/quan2005/journal) | @quan2005 | macOS journal app concept where recordings, PDFs, and pasted text trigger immediate wiki updates. URL was plain text in the comment. |
| [MemoOpen book](https://books.apple.com/us/book/memoopen-the-personal-growth-operating-system-in-the-ai-era/id6761299198?l=zh-Hans-CN) | @TengleDeng | Long-horizon personal growth operating system: multimodal, timeline-native, and agent-usable personal data foundation. |
| [llm-context-base](https://github.com/asakin/llm-context-base) | @asakin | Personal operating system with no central index, bold-field metadata, training period, and decision support. |
| [cog](https://github.com/marciopuga/cog) | @marciopuga | Personal-knowledge project inspired by Memex/associative trails over text. |
| [Keel](http://github.com/Keel-Labs/keel) | @medha | Mac app where knowledge stays as plain markdown on disk and the model is swappable. |
| [OpenWiki](https://github.com/kdsz001/OpenWiki) | @kdsz001 | Desktop implementation with source capture and compiled wiki pages; comment reports 1,602 sources -> 161 wiki pages. |
| [Agentic Local Brain](https://github.com/agent-creativity/agentic-local-brain) | @agent-creativity | Local-first personal knowledge system collecting files, webpages, emails, etc. into a private searchable graph. |
| [VLM-wiki](https://github.com/VeniVeci/VLM-wiki) | @VeniVeci | Multimodal extension for photos/videos/audio, extracting scenes, locations, people, and bidirectional wiki links. |

## For Researchers, Students, And Academic Writers

These are especially relevant for reading papers, compiling literature, generating research ideas, and drafting/reviewing papers.

| Work | Author | What It Is For |
| --- | --- | --- |
| [LENS](https://github.com/flyersworder/lens) | @flyersworder | Distills higher-order patterns across papers into contradiction matrices, architecture catalogs, and agentic pattern catalogs. |
| [ELF](https://github.com/ProjectEli/ELF) | @ProjectEli | Eli's Lab Framework: base-delta protocol for incremental experiments and research traceability. |
| [paper-spec](https://github.com/spectralbranding/paper-spec) | @viberesearch | Treats research programs as git repos; adds `.wiki/` for PDFs, datasets, emails, review exchanges, concepts, authors, and methods. |
| [llm-research-wiki](https://github.com/MetamusicX/llm-research-wiki) | @MetamusicX | Academic research template for music/philosophy with concepts, authors, debates, syntheses, ingest/query/lint, and Claude schema. |
| [ScholarAIO](https://github.com/ZimoLiao/scholaraio) | @ZimoLiao | Research system where the wiki becomes an operational substrate for executable workflows and agents. |
| [OmegaWiki](https://github.com/skyllwt/OmegaWiki) | @skyllwt | Full-lifecycle research platform: ingest papers, typed knowledge graph, generate ideas, design experiments, draft papers, respond to reviewers. |
| Google Drive + Claude Code research wiki | @profcraigarmstrong | Research-paper workflow for entrepreneurship/management: Claude Code processes PDFs in Google Drive into article markdown, log, and index. No repo link. |
| [RIS/SPATE write-up](https://zenodo.org/records/19914452) | @BarryEJames | Research Intelligence System with Prompt IDs, provenance registry, and self-constructing taxonomy. |
| [bioacoustics shared fabric](https://github.com/Fly-Carrot/shared-fabric-codex-gemini) | @Fly-Carrot | Bioacoustics ecology workflow combining multi-agent orchestration and standardized Obsidian knowledge. |
| [CKG benchmark paper](https://github.com/Yarmoluk/ckg-benchmark/blob/main/paper/main.pdf) | @Yarmoluk | Benchmark/evaluation-oriented contribution responding to evidence gaps around compiled knowledge graphs. |

## For Teams And Organizations

These are most relevant if the main problem is team memory, onboarding, product documentation, meeting/chat history, internal decisions, or multi-user agent workflows.

| Work | Author | What It Is For |
| --- | --- | --- |
| [Peeps Skill](https://github.com/Know-Your-People/peeps-skill) | @ilyabelikin | People and organization intelligence built from the same idea. |
| Folio production pattern | @bluewater8008 | Production use across multiple related knowledge domains; emphasizes source classification, token budgets, provenance, and cross-domain tags. No repo link. |
| [Centel](https://usecentel.com) | @nutbox-io | Product-documentation use case for PMs; lets Sales, new hires, and customers query product capabilities. |
| [Waykee Cortex](https://waykee.com/) | @earaizapowerera | Team-oriented hierarchical knowledge plus work tracking, with context inheritance across systems/modules/screens and tasks/bugs/milestones. |
| [agent-wiki for software project management](https://github.com/junbjnnn/llm-wiki/) | @junbjnnn | Team wiki inside a project repo; ingests PRDs, meeting notes, API specs, postmortems into summaries, ADRs, runbooks, and entity pages. |
| [Oiya](https://oiya.ai) | @aakarim | Multi-agent knowledge server integration for agent outbox ingestion and knowledge sharing. |
| Enterprise service delivery workflow | @denniscarpio30-jpg | Claude Code + Obsidian for client stakeholder pages, communication preferences, tone rules, and scheduled maintenance. No repo link. |
| [WikiStrata](https://github.com/kogarashi86/WikiStrata) | @kogarashi86 | Confluence-first tool that turns a Confluence tree into a markdown wiki, search index, and MCP layer. |
| [Beever Atlas](https://github.com/Beever-AI/beever-atlas) | @jhkchan / @nghoihin-byte | Team-chat-to-wiki implementation for Slack/Discord/Teams-style corpora; typed graph, semantic store, citations, and MCP server. |
| [MOM](https://github.com/momhq/mom) | @vmarinogg | Memory Oriented Machine: structured memory documents, scopes/access clearance, continuous recording, MCP server, and CLI for agents. |
| [NEXUS](https://github.com/lrdeoliveira/nexus-ai-memory) | @lrdeoliveira | Multi-agent memory system with six AI agents, Wiki.js, Weaviate, Ollama, GraphRAG, skills, session logging, and MCP servers. |
| [Kompl](https://github.com/tuirk/Kompl) | @tuirk | Knowledge compiler for links, files, bookmarks, notes, YouTube, GitHub repos, and exports; local Docker and MCP-native. |
| [llm-wiki-studio](https://github.com/cagataysengor/llm-wiki-studio) | @cagataysengor | Productized RAG-adjacent app: compiles documents into a structured wiki layer with source summaries, topic pages, and saved answers. |
| [Synthadoc](https://github.com/axoviq-ai/synthadoc) | @paulmchen | LLM Wiki style tool with API-key-free Claude Code/OpenCode provider routing, YouTube ingest, web search fan-out, and wiki generation. |
| [IQSource extension write-up](https://www.iqsource.ai/en/blog/karpathy-second-brain-iqsource/) | @iqsource | Services-business operational layer: handoff state machine for action items and source-citation-level contradiction policy. |

## General LLM Wiki Implementations, Templates, And Local Apps

These are broad implementations that can fit multiple use cases depending on the sources you feed them.

| Work | Author | What It Is For |
| --- | --- | --- |
| [browzy.ai](https://github.com/VihariKanukollu/browzy.ai) | @VihariKanukollu | Open-source CLI with ingest, compile, query, lint, FTS5/BM25, incremental compilation, Obsidian links, and provider support. |
| [Commonplace](https://zby.github.io/commonplace/) | @zby | Personal implementation plus a maintained list of related systems. |
| [GitCMS](https://gitcms.dev) | @Waishnav | Markdown CMS/MCP app positioned as a remote alternative for research and note-taking. |
| [Binder](https://github.com/mpazik/binder) | @mpazik | Structured-data-first version: transaction log, SQLite indexing, rendered markdown. |
| [llm-wiki](https://github.com/hellohejinyu/llm-wiki) | @hellohejinyu | CLI for personal LLM-driven wikis with smart ingestion, automatic linking, ReAct query, lint, and list tools. |
| [knowledge-engine](https://github.com/tashisleepy/knowledge-engine) | @tashisleepy | Obsidian markdown layer plus Memvid `.mv2` memory bridge for larger dual-layer retrieval. |
| [LLM-wiki](https://github.com/Ss1024sS/LLM-wiki) | @Ss1024sS | Working tool with bootstrap, generated platform configs, frontmatter provenance, and staleness detection. |
| [obsidian-wiki](https://github.com/Ar9av/obsidian-wiki) | @Ar9av | Easy Obsidian setup that organizes Claude/Antigravity history into an agent-usable wiki. |
| [llm-wiki-template](https://github.com/bashiraziz/llm-wiki-template) | @bashiraziz | Claude-generated template repo based on the idea. |
| [atomic-knowledge](https://github.com/Nimo1987/atomic-knowledge) | @Nimo1987 | Markdown-first work-memory protocol with ingest/query/writeback/maintenance and candidate buffer. |
| [llm-wiki-vault](https://github.com/MirkoSon/llm-wiki-vault) | @MirkoSon | Plain git + bash system with persistent markdown KB, provenance, zero-token linting, and multi-session continuity. |
| [Knowledge Forge](https://github.com/ESJavadex/knowledge-forge) | @ESJavadex | Node.js implementation with ingest, wikilinks, index/log, lint, and web UI. |
| [continuity](https://github.com/uziiuzair/continuity) | @uziiuzair | MCP memory server with immutable chat history, typed memories, version history, relationship graph, and prompt composition. |
| [llm-wikidata](https://github.com/QipengGuo/llm-wikidata) | @QipengGuo | Entity-linking extension using LLMs and ChromaDB to avoid duplicate/hallucinated nodes. |
| [ask-shorty](https://github.com/goatypixel821-hash/ask-shorty) | @goatypixel821-hash | Compresses sources into dense "Shorty" briefs plus entity/triple graph, with multi-layer retrieval. |
| [axiom-wiki](https://github.com/abubakarsiddik31/axiom-wiki) | @abubakarsiddik31 | Open-source CLI aiming to implement the full idea from one tool. |
| [git-wiki](https://github.com/rarce/git-wiki) | @rarce | Agent skill using Git/GitHub as canonical wiki storage with bash, `gh`, and qmd. |
| [obsidian-skills](https://github.com/qhuang20/obsidian-skills) | @qhuang20 | Claude Code plugin that detects Obsidian vaults and injects the LLM Wiki mental model automatically. |
| [mnemovault](https://github.com/kimsiwon-osifa7878/mnemovault) | @kimsiwon-osifa7878 | Local-first LLM Wiki IDE using Ollama and markdown folders. |
| [Sparks](https://github.com/yogirk/sparks) | @yogirk | Go binary that handles wiki plumbing such as hashing, inbox splitting, indexes, and local viewing. |
| [llmwiki-tooling](https://github.com/ilya-epifanov/llmwiki-tooling) and [wikidesk](https://github.com/ilya-epifanov/wikidesk) | @ilya-epifanov | Tooling for lint/link/frontmatter consistency plus client/server research request flow. |
| [ai-memex-cli](https://github.com/zelixag/ai-memex-cli) | @zelixag | Agent-agnostic CLI where the CLI enforces mechanical correctness and the agent handles semantic synthesis. |

## Retrieval, Provenance, Integrity, And Search Add-ons

These are not always full LLM Wiki apps, but they address recurring pain points in the comments: scaling search, provenance, trust, contradiction handling, and graph traversal.

| Work | Author | What It Is For |
| --- | --- | --- |
| [Veritas Acta](https://veritasacta.com) / [Acta wiki](https://acta.today/wiki) | @tomjwxf | Multi-model verification, signed receipts, living Knowledge Units, provenance, and integrity checks. |
| [Zorro](https://codeberg.org/trox/obsidian-zorro) | @trox | Obsidian drift-detection plugin for alignment across Obsidian, Zotero, and cloud storage. |
| [blink-query](https://github.com/arpitnath/blink-query) | @arpitnath | Typed record/search system for markdown corpora; commenter benchmarks against grep on MDN docs. |
| [TreeSearch](https://github.com/shibing624/TreeSearch) | @shibing624 | Structure-first document retrieval using heading trees and SQLite FTS5 rather than chunk/vector-first search. |
| [RTFM](https://github.com/roomi-fields/rtfm) | @roomi-fields | Search/index layer for Obsidian vaults with FTS5, semantic/hybrid search, wikilink graph, generated navigation, and parsers. Link text in comment used malformed slashes. |
| [OMEGA memory](https://github.com/omega-memory/omega-memory) | @singularityjason / @omega-memory | Memory formation and retrieval layer with auto-capture hooks, decay, reranking, and Obsidian plugin. |
| [Keppi](https://github.com/jgoldfed/keppi) | @jgoldfed | Graph traversal layer for markdown wikis; computes relevant note neighborhoods instead of search-only retrieval. |
| [remindb](https://github.com/radimsem/remindb) | @radimsem | Agentic memory database meant to reduce token waste when retrieving context from raw markdown. |
| [robust-llm-wiki](https://github.com/KevinYoung-Kw/robust-llm-wiki) | @KevinYoung-Kw | Schema-first variant focused on red lines and anonymization discipline. |
| [cortex](https://github.com/abbacusgroup/cortex) | @abbacusgroup | MCP server using OWL-RL ontology, Oxigraph SPARQL, SQLite FTS5, and deterministic reasoning for persistent knowledge. |
| [prism](https://github.com/payneio/prism) | @payneio | Tooling for LLMs to maintain wiki frontmatter, links, page splits/merges, tags, roots, and sub-wikis. |
| [CodeDNA](https://github.com/Larens94/codedna) | @Larens94 | In-source protocol where code files carry typed structural metadata; argues for opt-in wiki pointers instead of duplicate generated docs. |
