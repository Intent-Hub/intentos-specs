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
