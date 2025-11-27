# Big Context

Big Context is the way IntentHub works with information that does not fit into a single LLM context window.

Instead of trying to “stuff everything into one prompt”, Big Context:

- stores episodes as **Triads** in the Intent Memory Engine,
- lets the **Context Driver** select only the relevant parts for each step,
- refreshes the active context as the conversation or execution progresses.

Key principles:

- **Composable episodes** – you retrieve just enough related triads to answer or act.
- **Step-wise refresh** – different steps of a playbook may need different context slices.
- **Cost awareness** – Big Context must *reduce* token usage, not explode it.

This document describes Big Context at a high level.  
Details of dynamic loading and orchestration live in `context-driver.md`.
