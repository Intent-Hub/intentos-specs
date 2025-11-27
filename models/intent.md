# Intent Model

An **Intent** is the normalized representation of what needs to be done.

It abstracts away:
- the exact wording of the request,
- the agent or UI that produced it,
- transient phrasing and style.

## 1. Logical Structure

Typical fields in an Intent model include:

- **`task`** – high-level description of the action (The "What").
- **`context`** – environment, constraints, resources (The "Where/Conditions").
- **`desired_outcome`** – how success looks (The "Goal").
- **`parameters`** – structured inputs (specific variables like amounts, addresses).
- **`source`** – where this intent came from (user, schedule, event, etc.).

The Intent layer separates *meaning* from *phrasing* and is the entry point into Templates and Playbooks.

## 2. Mapping to Memory (Triad)

When an Intent is persisted into the **Intent Memory Engine**, its fields map directly to the **Triad Topology**:

| Intent Field      | Graph Node Type  | Role                         |
| :---------------- | :--------------- | :--------------------------- |
| `task`            | **Task Node**    | Entry point for search.      |
| `context`         | **Context Node** | Filters relevance.           |
| `desired_outcome` | **Outcome Node** | Definitive success criteria. |

> **Note:** `parameters` are typically handled at the **Playbook** level, not stored as semantic nodes, to keep the graph generic.