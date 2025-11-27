# Context Driver

The **Context Driver** is a small, specialized model (or rule-based orchestrator) that decides:

> *Which parts of the memory graph should be visible to the LLM or tool at this step?*

It operates as a router/orchestrator between:

- the **Intent Memory Engine** (Triad graph),
- the **Playbook Execution Engine**,
- and the **LLM Gateway**.

Core responsibilities:

- select a minimal set of triads relevant to the current task/step,
- enforce **Contextual Zero Trust** (no excess context),
- update the “hot” context window as the execution progresses,
- balance Fast vs Smart retrieval strategies.

The Context Driver is where **Big Context** becomes operational:  
it turns a large, long-lived memory into a small, step-local view aligned with the task.
