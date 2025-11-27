# RFC-0002: Intent Memory Engine

Status: Draft  
Authors: IntentHub Maintainers  
Target: Core Specification

## Motivation

We need a memory system that:

- can scale beyond single-context histories,
- can be queried by task, context, or outcome,
- supports both fast routing and smart semantic lookup.

## Proposal

Adopt the **Triad Topology** for the Intent Memory Engine:

- represent each episode as (Task, Context, Outcome),
- link triads by similarity, shared entities, or causal chains,
- provide two retrieval strategies:
  - Fast Strategy – rule/pattern-based routing,
  - Smart Strategy – vector similarity over embeddings.

The engine is used by:

- the Context Driver (for Big Context),
- the Gateway (for caching/routing),
- the Auto-Builder (for induction).

## Notes

Further details live in `architecture/triad-topology.md` and `architecture/big-context.md`.
