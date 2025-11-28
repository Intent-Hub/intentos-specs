# IntentHub Ecosystem — Unified Specification (v1.2)

IntentHub is the umbrella framework unifying the architecture, principles, and projects inside the IntentOS ecosystem.
Its purpose is to create a shared semantic layer where systems operate on **intents**, not raw text.

This document is the canonical, agent-ready specification.

---

# 1. Purpose & Core Vision

IntentHub defines the conceptual foundations.
IntentOS implements them as a practical runtime.

The ecosystem enables:

- structured intent representation
- deterministic execution on top of stochastic LLMs
- standardized memory architectures
- scalable Big Context mechanisms
- skill leasing with secure boundaries
- feedback-driven evolution of playbooks and templates

Guiding principle: **AI Aikido — using AI to control and assist AI.**

---

# 2. The Intent Stack

## 2.1. Intent Layer
The atomic unit of meaning.
A normalized representation of *what needs to be done*, independent of phrasing.

## 2.2. Template Layer
Canonical instructions and input/output schemas.

## 2.3. Playbook Layer
Deterministic multi-step graph that executes an intent.

Supports:
- LLM calls
- HTTP calls
- MCP tools
- branching logic
- budgets
- versioning

## 2.4. Execution Layer
Actual execution producing results, logs, metrics, and feedback.

---

# 3. Memory & Big Context

## 3.1. Intent Memory Engine (The Brain)
A local-first, deterministic **Directed Graph (DiGraph)** implementing the **Triangle Topology**.

### 3.1.1. Topology & Structure
- **Nodes**: Explicit nodes for **Task**, **Context**, and **Outcome**.
  - *Schema*: ID, Primary Content, Embedding, Aliases (for deduplication).
- **Edges**: Directed, dual-linked connections with **Asymmetric Weights**.
  - *Forward (Task → Outcome)*: High confidence (Execution).
  - *Backward (Outcome → Task)*: Low confidence (Explanation/Reverse Engineering).

### 3.1.2. Traversal Physics (The "Salmon" Algorithm)
Navigation follows a **Semantic Diode** logic:
- **Downstream (Flow)**: Moving along the arrow.
  - Formula: $Score_{next} = Score_{current} \times Weight \times \mu_{flow}$
- **Upstream (Viscosity)**: Moving against the arrow.
  - Formula: $Score_{next} = \text{ReLU}(Score_{current} \times Weight - \text{Barrier})$
  - *Purpose*: Filters noise and prevents "context pollution" from super-nodes.

### 3.1.3. Ingestion Pipeline
1.  **Semantic Gatekeeper**: Checks cosine similarity before creation.
    - If similarity > 0.92 → **Merge** as alias (no new node).
    - If similarity < 0.92 → **Create** new node.
2.  **Edge Creation**: Instantiates dual edges (Forward/Backward).

### 3.1.4. Storage
- **Engine**: Embedded Key-Value Store (**Redb** or **Sled**) for O(1) adjacency lookups.
- **Format**: Binary serialization (**Bincode**) for zero-copy deserialization and minimal footprint.
- **Concurrency**: MVCC-based, lock-free readers for high-throughput search.

## 3.2. Big Context & Context Driver

Mechanism for operating beyond LLM window limits.

### Context Driver
A lightweight orchestrator model that dynamically:
- selects relevant graph nodes using the traversal physics defined above.
- streams them into the “hot” context.
- removes irrelevant parts based on the current step.

### Guarantees
- prevents “lost in the middle”
- keeps token cost low
- enables multi-hop reasoning

### Security Principle
**Contextual Zero Trust** — LLMs and tools receive only the minimal required context.

---

# 4. Gateway Layer — AI Aikido Gateway

Middle layer providing:
- provider proxying
- transparent cost tracking
- semantic + verbatim caching
- multi-tenant authentication
- guard rails
- request history, logs, traces

Implements AI Aikido: constrain, supervise, optimize.

---

# 5. Tools & Skills (MCP / Skill Leasing)

## 5.1. MCP Integration
Gateway can call MCP tools **pre-LLM**, **post-LLM**, or **on-demand**.

## 5.2. Skill Leasing
Temporary access to external abilities.

### Security Model
- Contextual Zero Trust
- Scoped JWT with short TTL
- Minimal possible context exposure
- Isolation boundary between IntentOS and external tools

---

# 6. Feedback & Evolution

## 6.1. Feedback Engine
Aggregates:
- user evaluation (explicit)
- automatic correctness checks (implicit)
- LLM-based quality estimates
- metadata from execution logs

## 6.2. The Gardener (Async Maintenance)
A background process responsible for **Graph Normalization**:
- **Hub Balancing**: Updates edge weights based on node degree (e.g., $\frac{1}{\sqrt{N}}$) to prevents super-node dominance.
- **Pruning**: Removes edges/nodes that fall below validity thresholds over time.

## 6.3. Auto-Builder / Autonomous Induction
Clusters historical data to propose:
- new intents
- updated templates
- new playbooks

Human-in-the-loop required for publishing.

---

# 7. Reference Applications

## 7.1. drop-deck
Local-first pipeline:
- raw signal → farming mission
- uses Ollama/Qwen
- validated with instructor library
- no cloud dependency

## 7.2. RetroDropBot
Intent-driven farming automation.

## 7.3. Signal Poster / Mission Board
Signal → category → mission.

## 7.4. TechJobAlert
A model where successful activation consumes the agent.

---

# 8. Philosophical Foundations

### Intent Engineering
Focus on meaning over phrasing.

### Layer Infinity (L∞)
Meta-layer for routing, meaning-construction, and orchestration.

### Structured Authority
Control over structure → control over meaning → control over execution.

---

# 9. Intent Pipeline

```
Raw Signal
  → Preprocess (Vectorize)
  → Semantic Gatekeeper (Dedup)
  → Intent Detection (Graph Traversal)
  → Template Selection
  → Playbook Execution
  → Result
  → Feedback
  → The Gardener (Weight Update)
```

Universal pipeline across all systems.

---

# 10. Summary

IntentHub provides:
- the language
- the structures
- the security model
- the memory (Redb + DiGraph)
- the routing (Semantic Diode)
- the execution semantics
- the evolution mechanisms (Gardener)

IntentOS is the runtime.
Together they deliver deterministic AI built on top of stochastic LLMs.

End of specification.
