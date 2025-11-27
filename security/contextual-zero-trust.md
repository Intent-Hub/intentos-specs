# Contextual Zero Trust

**Contextual Zero Trust** is the security principle that underpins IntentHub:

> No agent, tool, or model should see more context than it needs for the current step.

In practice this means:

- the **Context Driver** selects a minimal subset of memory for each step,
- tools and skills are invoked with **scoped access** only,
- sensitive information is not “leaked” into generic LLM prompts by default.

This approach:

- reduces risk of accidental data leakage,
- simplifies reasoning about what each component can see,
- aligns with existing Zero Trust ideas, but applied to semantic context.
