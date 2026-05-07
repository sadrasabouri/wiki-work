---
tags: [concept]
---

# KB as Codebase

A KB is like a codebase: adding knowledge = making a PR, refactoring knowledge = trimming and reorganizing, deprecating a claim = marking it legacy. Proposed by [[sadra-sabouri|Sadra]] in [[Thursday demo]] and endorsed by [[sumit-gulwani|Sumit]] as a strong closing analogy for the presentation.

## Why the Analogy Works

Both a codebase and a KB are structured collections of information maintained by humans and AI together, subject to evolution over time. Codebases have tooling for this: version control, diffs, review workflows, deprecation markers. KBs currently lack equivalent tooling — but the analogy suggests exactly what to build.

Specific mappings:
- **PR** — contributing personal or meeting knowledge to the shared KB
- **Refactor** — reorganizing KB entities for more efficient representation without losing information
- **Deprecation** — marking claims superseded by newer sources (the [[purge-operation|Purge Operation]] operationalizes this)
- **Diff** — showing what changed between KB states (essential for [[temporal-knowledge|temporal knowledge]] management)

## Coding Analogy Extended

Sumit extended this in [[Thursday demo]]: just as the future of coding involves "specification mechanisms" and "IDEs," the future of knowledge work involves the same questions. One key difference: a KB is *additive* — new information can always be added, and the system must update. Codebases are more often refactored destructively; KBs accumulate.

## Local Branch Model

The analogy extends to the personal ↔ org KB relationship. A personal private KB is a **local branch** — a fork of the org KB that the individual develops privately. When the user wants to contribute knowledge from private sources (1:1 transcripts, personal notes), they submit a PR: select what to include, filter what to exclude, and open for review. [[Personal Knowledge Management]]

This makes [[semi-private-mashing|Semi-Private Mashing]] concrete: the PR boundary is the filter. Only what's in the PR crosses from the private layer to the shared one. The org KB is the upstream main branch; each user maintains their own fork.

## Implication for [[wiki-kb-project|Wiki KB Project]]

If the KB is a codebase, then [[views|Views]] are like build targets: different views are compiled from the same source (raw notes). The raw sources are the source code; the wiki pages are the build artifacts. This suggests the wiki's build process — ingesting sources, generating pages, running lint — maps cleanly to a software CI pipeline.
