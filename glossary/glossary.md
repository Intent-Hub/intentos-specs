# Glossary

This glossary defines key terms used across the IntentHub / IntentOS specs.

- **IntentHub** – conceptual framework for intent-driven systems.
- **IntentOS** – runtime implementing IntentHub concepts.
- **Intent** – normalized representation of what needs to be done.
- **Template** – canonical instructions and schemas for handling an intent.
- **Playbook** – deterministic execution graph implementing an intent.
- **Execution** – a single run of a playbook with logs and outcomes.
- **Triad Topology** – memory structure storing episodes as (Task, Context, Outcome).
- **Intent Memory Engine** – graph-based store of triads and their relations.
- **Big Context** – approach to working with information beyond a single LLM window.
- **Context Driver** – orchestrator selecting which memory nodes are visible at each step.
- **Contextual Zero Trust** – principle of minimal necessary context exposure.
- **Skill Leasing** – temporary mounting of external capabilities (MCP/tools) with scoped access.
- **AI Aikido Gateway** – LLM gateway with cost, cache, and safety controls.
- **Layer Infinity (L∞)** – meta-layer for routing, reflection, and meaning construction.

This file is intentionally short.  
New terms should be added here as the spec evolves.
