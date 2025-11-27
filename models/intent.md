# Intent Model

An **Intent** is the normalized representation of what needs to be done.

It abstracts away:

- the exact wording of the request,
- the agent or UI that produced it,
- transient phrasing and style.

Typical fields in an Intent model include:

- `task` – high-level description of the action,
- `context` – environment, constraints, resources,
- `parameters` – structured inputs,
- `desired_outcome` – how success looks,
- `source` – where this intent came from (user, schedule, event, etc.).

The Intent layer separates *meaning* from *phrasing* and is the entry point into Templates and Playbooks.
