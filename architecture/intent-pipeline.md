# Intent Pipeline

All IntentHub-aligned systems follow the same high-level pipeline:

```text
Raw Signal
  → Preprocess
  → Intent Detection
  → Template Selection
  → Playbook Execution
  → Result (action/data/insight)
  → Feedback
  → Update
```
At each stage:

Raw Signal – unstructured user input, event, job, or external trigger.

Preprocess – light cleaning, normalization, enrichment.

Intent Detection – mapping to a canonical intent (or intent candidate).

Template Selection – choosing a structured prompt/schema for this intent.

Playbook Execution – deterministic multi-step plan runs against tools/LLMs.

Result – something changes in the world: data, state, artifact, decision.

Feedback / Update – the Triad graph and playbooks evolve over time.

This file provides the overview.
More formal definitions reside in the models/ and rfc/ sections.