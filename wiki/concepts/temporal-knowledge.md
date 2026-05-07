---
tags: [concept]
---

# Temporal Knowledge

The KB is not a flat collection of facts but a time-stamped evolution where newer sources supersede older ones. A claim from March may be contradicted or refined by May; without temporal awareness the KB accumulates silent contradictions.

## Key Operations

- **Ingest** — add new knowledge, noting timestamp and source
- **[[purge-operation|Purge]]** — remove information made obsolete by newer sources
- **Percolation** — propagate updates upward through the KB's dependency graph; a fact change at the leaf level should ripple to all pages that cited it

This was articulated in [[T8-2026-05-02-1|the May 2 morning meeting]] (percolation, graph update approaches) and [[T9-2026-05-02-2|the May 2 evening meeting]] (purge as a named operation).

## Contrast with Static KB Systems

Most KB tools (Notion, Confluence) treat pages as independent documents. Temporal knowledge management treats the KB as a graph where facts have timestamps and dependencies. This is closer to a version-controlled codebase — see [[kb-as-codebase]] — than a wiki.

## Versioning

The KB should be queryable at a point in time: "what did we know about views as of March?" This requires either version control (git history) or explicit timestamps on claims, making [[provenance-tracking|provenance]] inseparable from temporal management.

## Alternative: Temporal Navigation via Source Filtering

Proposed in [[T11-2026-05-04-1|the May 4 early morning sync]]: instead of maintaining cached past states or relying on git history, let users filter which input sources participate in a view computation. Filtering out all sources from after a given date = simulating the KB state at that date.

This is a non-destructive, query-time operation — unlike purge (which permanently removes claims). The tradeoff: it requires recomputing the view from scratch against the filtered source set, which is more expensive than reading a cached snapshot but simpler to implement. See [[living-system]] for the broader recalc architecture this belongs to.
