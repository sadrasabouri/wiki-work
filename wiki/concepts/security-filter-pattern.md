---
tags: [concept]
---

# Security Filter Pattern (Azure AI Search)

A document-level access control technique for Azure AI Search that trims search results using an OData filter expression rather than relying on built-in ACL support. Documented in [[Security Filter Pattern - Azure AI Search]]; referenced in [[Microsoft Infrastructure for Organizational Brain]] as the legacy access control mechanism that predates [[foundry-iq|Foundry IQ]]'s identity-aware retrieval.

## The Pattern

**Problem:** Azure AI Search has no built-in per-document authorization for scenarios where content must be visible only to specific users or groups.

**Solution:** Store a principal identifier (user ID, group ID, or Microsoft Entra object ID) as a `Collection(Edm.String)` field on each indexed document. At query time, inject a filter expression derived from the caller's group memberships:

```
group_ids/any(g:search.in(g, 'group_id1, group_id2'))
```

This uses the `search.in()` OData function — vastly more efficient than a disjunction of equality expressions (`Id eq 'id1' or Id eq 'id2' ...`), which degrades to multi-second query times for hundreds of identifiers. The `search.in()` approach delivers subsecond responses at arbitrary group-list scale.

**Key schema requirements:**
- Security field must be `filterable: true` and `retrievable: false` (never exposed in search results)
- Documents are loaded with their group IDs at indexing time; updates use `mergeOrUpload` action

## Three Authorization Patterns Compared

This pattern clarifies how authorization granularity differs across Microsoft's retrieval systems:

| Pattern | Mechanism | Who controls access | Granularity |
|---|---|---|---|
| **Security Filter Pattern** (Azure AI Search) | OData `search.in()` filter at query time | Index designer — stores group IDs in documents | Document-level, explicit list |
| **[[foundry-iq\|Foundry IQ]] permission enforcement** | Sync ACLs from source systems; honor Entra identity at retrieval time | Source system owners (SharePoint, OneLake) | Source-system ACL granularity |
| **[[semi-private-mashing\|Semi-Private Mashing]]** (wiki project) | Author-controlled content selection before ingestion | Content author — decides what to share | Passage/concept level, author intent |

The progression reveals a gap: the Security Filter Pattern and Foundry IQ both handle *who may read* already-published content. Neither handles *what the author chooses to contribute* from private content. Semi-private mashing fills this gap — it is not access control on retrieval but editorial selection at ingestion.

## Historical Position in the IQ Stack

[[Microsoft Infrastructure for Organizational Brain]] notes that Azure AI Search is the "legacy version" of the Foundry IQ system, handling a similar retrieval use case. The Security Filter Pattern is evidence: where Foundry IQ's permission enforcement is automatic (identity-synchronized, ACL-derived), Azure AI Search required developers to explicitly design the security field, populate it at index time, and inject the filter at query time. Foundry IQ automates and elevates this to the knowledge-layer level.

The pattern is also worth noting because [[structured-rag|TypeAgent's Structured RAG]] cites Azure AI Search's inverted index infrastructure as a direct precedent — the same index machinery now serves as the foundation for conversation memory retrieval.
