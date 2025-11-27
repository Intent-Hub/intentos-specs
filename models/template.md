# Template Model

A **Template** describes how an Intent should be handled in a **canonical** way.

It usually contains:

- instructions for LLMs and tools,
- input and output schemas,
- validation rules,
- metadata (owner, domain, version, status).

Templates are reusable:

- multiple raw signals can map to the same Intent,
- multiple Intents can reuse the same Template (with different parameters),
- Templates can be versioned independently of Playbooks.

You can think of a Template as the “normalized prompt + schema” for a family of tasks.
