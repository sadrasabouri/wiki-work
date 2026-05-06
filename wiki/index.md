# Wiki Index

## Concepts

- [[views|Views]] — declarative specs (prompts/templates) applied to raw sources; the unifying concept across both projects
- [[workflows|Workflows]] — constructive specs for HOW to populate a view; creative artifacts with their own design space
- [[steerability|Steerability]] — user ability to redirect AI at granular steps; coined by Sumit in Mar 2026 to replace "granular feedback"
- [[temporal-knowledge|Temporal Knowledge]] — KB as time-stamped evolution; newer sources supersede older; requires percolation and [[purge-operation|purge]]
- [[semi-private-mashing|Semi-Private Mashing]] — filtering private exchanges for a shared KB while preserving privacy; key differentiator
- [[simulation-metaphor|Simulation Metaphor]] — KB as accelerator of individual cognition and team communication
- [[productivity-creativity-tradeoff|Productivity-Creativity Tradeoff]] — LLMs boost productivity but reduce aha moments (Athena's study)
- [[digital-twins|Digital Twins]] — KB's ultimate goal: capturing tacit knowledge and interaction patterns, not just documents
- [[provenance-tracking|Provenance Tracking]] — distinguishing human-verified from AI-generated content; AI slop vs. AI beauty
- [[human-as-api|Human as API]] — human supervision as a tool call; governed by Grice's maxims; interaction.md concept
- [[gulf-of-envisioning|Gulf of Envisioning]] — users can't form stable mental models of non-deterministic AI capabilities
- [[dag-of-computation|DAG of Computation]] — visualizing agent computation as a dependency graph; the "see" in stop/see/steer
- [[agent-lens|Agent Lens]] — "stop, see, steer" framework for spreadsheet verification; named in Mar 16 meeting
- [[scalable-oversight|Scalable Oversight]] — maintaining human oversight as AI capability exceeds human verification capacity
- [[kb-as-codebase|KB as Codebase]] — PRs = adding knowledge, refactoring = trimming, deprecation = purge
- [[purge-operation|Purge Operation]] — removing obsolete information to maintain temporal integrity; requires provenance
- [[self-referential-kb|Self-Referential KB]] — the KB contains transcripts about building the KB; "presentation about itself"
- [[bidirectional-collaboration|Bidirectional Collaboration]] — gap: current AI is unidirectional (human instructs); ideal is mutual proposal
- [[llm-wiki-landscape|LLM-Wiki Landscape]] — ecosystem of wiki-from-notes projects; Karpathy origin; wiki vs. RAG efficiency; known critics (lossiness, scaling, no benchmark)
- [[second-brain-code-method|Second Brain / CODE Method]] — Tiago Forte's pre-LLM PKM framework (Capture, Organize, Distill, Express); the intellectual precedent that LLM wikis automate
- [[information-knowledge-pipeline|Information → Knowledge → Views Pipeline]] — three-layer architecture; wiki as semantic index / hot cache; views run on wiki, not raw data
- [[living-system|Living System]] — always-live recalc model (Excel formula analogy); automated raw data generation; everything-is-a-DAG; temporal source filtering
- [[embedded-views|Embedded Views]] — Option 2: views as prompt-powered holes inside existing applications (Word, PPT, Excel) vs. standalone CLI generation
- [[skills|Skills]] — per-prompt creative methodology (HOW to fill a view hole); renamed from "creative workflows"; includes a gallery / community library
- [[context-base|Context Base vs. Knowledge Base]] — Applied Compute's Remember→Refine→Retrieve architecture (empirically: 16.9% APEX improvement, reasoning-effort amortization); three structural gaps between code and knowledge work; contrast with this project's human-centered KB
- [[semantic-diff|Semantic Diff]] — design primitive for inspectable agents: surface the computational unit (formula, rule), not the artifact surface (highlighted cells); generalizes across spreadsheet, code, document agents
- [[local-first-kb|Local-First KB]] — personal KB as local branch; private processing on-device; PR model for contributing to org KB; matvellosoknowledge as concrete RAG-based instantiation
- [[workiq|Work IQ]] — Microsoft's org-scale context base (Data + Context + Skills/Tools); closest incumbent to the wiki project; gap: surface-level indexing, no knowledge layer, no semi-private contribution model

## People

- [[sadra-sabouri|Sadra Sabouri]] — USC PhD student; primary builder across both projects
- [[sumit-gulwani|Sumit Gulwani]] — Microsoft Research; coined steerability; identified views as unifying concept
- [[souti-chattopadhyay|Souti Chattopadhyay]] — Sadra's advisor; digital twins, human-as-API, creativity research angle
- [[sujay-maladi|Sujay Maladi]] — collaborator on Spreadsheet Verification; must-haves vs. nice-to-haves rubric
- [[athena-saghi|Athena Saghi]] — creativity study researcher; productivity-creativity tradeoff findings and four collaboration modes
- [[tiago-forte|Tiago Forte]] — creator of Building a Second Brain / CODE method / PARA; intellectual predecessor to Karpathy's LLM-wiki pattern
- [[gary-marcus|Gary Marcus]] — AI critic; "GenAI is net negative outside coding and brainstorming" — his carve-out validates the wiki project's domain

## Projects

- [[wiki-kb-project|Wiki KB Project]] — AI-powered KB research; contributions: views, semi-private mashing, intermediate summaries
- [[agent-traceability-steerability|Agent Traceability and Steerability in Spreadsheets]] — Pista; stop/see/steer; 7 features; calibrated trust through participation; semantic diff primitive

## Events

- [[2026-02-20|Feb 20]] — Spreadsheet verification kickoff; data-centric vs. process-centric; scalable oversight framing
- [[2026-03-04|Mar 4]] — Athena's creativity study; productivity-creativity tradeoff; Wallace model; four modes
- [[2026-03-11|Mar 11]] — Co-design session planning; formative study; IRB; workshop design
- [[2026-03-16|Mar 16]] — Steerability coined; views unified across both projects; Agent Lens named; DAG view
- [[2026-04-03|Apr 3]] — Two Souti meetings: creativity in Excel; human-as-API; Gulf of Envisioning
- [[2026-05-01|May 1]] — Three-way sync; Teams channel example; views taxonomy; digital twins; workflows as creative artifacts
- [[2026-05-02|May 2]] — Simulation metaphor; temporal KB; views/workflows distinction; purge; provenance; self-referential presentation
- [[2026-05-03|May 3]] — Three-way sync; wiki demo to Sumit; semantic index framing; raw→knowledge→views pipeline; embedded views; Karpathy differentiator
- [[2026-05-04|May 4]] — Two 1:1s; full-system provenance DAG; temporal source filtering; living system; everything-is-a-DAG; knowledge graph as alternative foundation
- [[2026-05-05|May 5]] — AI slop diagnosis; workflows→skills rename; view = template with holes; workflow = data dependencies; context base vs. knowledge base; document as view; Satya pitch
- [[2026-05-06|May 6]] — task division (Sadra: presentation, Sumit: pre-read); FlashFill analogy for view authoring; Karpathy gist 700-comment mining (3 categories); WorkIQ action item; wiki vs. RAG compression reframe
