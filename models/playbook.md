# Playbook Model

A **Playbook** is a deterministic execution graph that operationalizes an Intent.

Key properties:

- consists of ordered or branched steps,
- each step can call:
  - an LLM,
  - an HTTP/API endpoint,
  - an MCP tool,
  - a local function or script,
- includes budgets (tokens, time, money),
- can be versioned (`playbook@v1`, `@v2`, ...).

Playbooks connect:

- **Intents** (what we want),
- **Templates** (how to talk to tools/LLMs),
- **Execution** (what actually happens in the runtime).

In IntentHub, Playbooks provide the main lever for turning intent semantics into repeatable behavior.
