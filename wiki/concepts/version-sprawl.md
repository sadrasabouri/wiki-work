---
tags: [concept]
---

# Version Sprawl

The HCI problem of managing many parallel versions of a creative document while iterating with AI. Articulated by [[sumit-gulwani|Sumit]] in [[T15-2026-05-06|the May 6 sync]] as a real research direction emerging from his own pre-read authoring process.

## The Concrete Frustration

Sumit's account of producing one Microsoft pre-read document:

- V1, V2, V3, V4 — initial revisions
- M1, M2 — when he asked the system to extract a "minimal specification" and regenerate
- N1, N2 — when M failed and he changed the naming scheme
- T — after a "mash-up" because M was already used up
- S1, S2 — when he gave up and started fresh from scratch

Roughly 20 documents total. He has lost track of which is which but knows each contains some part he is unwilling to give up. He is "any point of time going back and forth and pulling things here and there."

## Why This Is an HCI Problem, Not a User Problem

Sumit explicitly resisted self-blame: *"Am I not doing it right? How do people maintain versions? I do not understand."* The version sprawl is downstream of a missing surface, not of bad practice. He named the design target:

> A surface where the system understands the different alternatives for each part and is just very able to easily iterate, you know, just allowing that particular part... and all the versions are maintained there in a hierarchical manner.

In short: **part-level version control with hierarchical history**, scoped to creative drafts.

## Text vs. Image: Why Text Is Tractable

Souti drew the analogy to image-generation re-iteration: ask for "the same village but only this tree changed" and the whole image shifts. Sumit countered that text is more **constructive** — you can pick parts. So the problem is solvable for text in a way it isn't for raster images. The asymmetry suggests text-specific UI primitives (selection, splice, reversion-by-region) rather than generic versioning.

## Connections

- **[[views]]** / **[[skills]]** — A view is a template with prompt-filled holes. Version sprawl arises when iteration happens at the *whole-document* level instead of the *hole* level. A view-native authoring surface should make per-hole iteration the default unit of edit.
- **[[gulf-of-envisioning]]** — Users don't know the surface they need exists. Sumit named the gap only *after* living through 20 versions.
- **[[steerability]]** — Each iteration is a steer; the version graph is the history of those steers. Today the history is lossy (forgotten, overwritten, renamed); steerability requires it to be preserved and navigable.
- **[[wiki-kb-project|Wiki KB Project]]** — The same project that needs to know "which transcript first mentioned this idea" needs to know "which document version introduced this paragraph." Provenance and version history are the same primitive at different scales.

## Status

Open research direction, not yet on either project's roadmap. Sumit framed it as "a separate project to work on on this idea" — acknowledged as significant but parked while the lightning talk is the priority.

## Source

[[T15-2026-05-06]] · Sumit (with Souti's image-generation analogy).
