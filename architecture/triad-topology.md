# Triad Topology

Triad Topology is the core graph structure of the Intent Memory Engine.

Instead of storing an intent as a single text node, IntentHub represents it as a **triangle** of three related nodes:

- **Task** – what action was requested or performed.
- **Context** – under which conditions, constraints, or environment the task was handled.
- **Outcome** – what actually happened: result, artifact, error pattern, or side-effect.

Each **Triad** captures one “episode of intent in the world”.  
The memory graph is then built from many interconnected triads, linked by:

- similarity (Task ↔ Task),
- shared resources or entities (Context ↔ Context),
- reused results or failures (Outcome ↔ Outcome).

This topology makes retrieval and learning more robust than plain text logs:  
we can search by *what*, *where/when/how*, or *what happened next* — or any combination.
