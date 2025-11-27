# IntentHub Ecosystem — Unified Specification (v1.1)

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

## 3.1. Intent Memory Engine (Graph)
Graph-based memory using **Triad Topology** (Task ↔ Context ↔ Outcome).

### Triad
Intents are stored as relational triangles:
- **Task** — requested action  
- **Context** — constraints and prerequisites  
- **Outcome** — result or failure pattern  

### Retrieval
Dual-strategy:
- **Fast Strategy** — pattern/regex routing  
- **Smart Strategy** — vector similarity search  

Stores episodes, relationships, embeddings, traces.

## 3.3. Big Context & Context Driver

Mechanism for operating beyond LLM window limits.

### Context Driver
A lightweight orchestrator model that dynamically:
- selects relevant graph nodes  
- streams them into the “hot” context  
- removes irrelevant parts based on the current step  

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

# 6. Feedback & Induction

## 6.1. Feedback Engine  
Aggregates:
- user evaluation  
- automatic correctness checks  
- LLM-based quality estimates  
- metadata from execution logs  

## 6.2. Auto-Builder / Autonomous Induction  
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
  → Preprocess
  → Intent Detection
  → Template Selection
  → Playbook Execution
  → Result
  → Feedback
  → Update
```

Universal pipeline across all systems.

---

# 10. Summary

IntentHub provides:
- the language  
- the structures  
- the security model  
- the memory  
- the routing  
- the execution semantics  
- the evolution mechanisms  

IntentOS is the runtime.  
Together they deliver deterministic AI built on top of stochastic LLMs.

End of specification.
