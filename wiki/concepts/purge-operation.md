---
tags: [concept]
---

# Purge Operation

The operation of removing obsolete or superseded information from the KB when newer sources contradict or refine it. Named in [[T9-2026-05-02-2|the May 2 evening meeting]] as a first-class KB operation alongside ingest and query.

## Why Purge Is Necessary

Without purge, a KB accumulates silent contradictions over time. A March transcript describes views as having two components; a May transcript adds a third. Without purging the outdated description, both coexist in the KB — a reader can't tell which is current. The KB gradually becomes unreliable.

## Purge vs. Archive

Purge removes claims from the active KB; archiving moves them to a separate historical record. The distinction matters: [[temporal-knowledge|temporal knowledge]] management requires knowing what was true *when*, so pure deletion is wrong. The right operation is: mark as superseded, note the superseding source, and exclude from active synthesis while retaining in the historical record.

## Precondition: [[provenance-tracking|Provenance]]

You can only safely purge when you know which source each claim came from and when. Without provenance, you can't determine whether a claim is superseded or just coincidentally absent from recent sources. This makes [[provenance-tracking]] a prerequisite for safe purge.

## Connection to [[kb-as-codebase|KB as Codebase]]

In the codebase analogy, purge maps to deprecation + eventual deletion: you first mark a claim as deprecated (superseded), then remove it once no active references depend on it. The KB's [[views|Views]] system creates dependencies — a view that references a superseded claim needs to be updated before the claim can be purged.
