# Execution Model

The **Execution Model** describes what happens when a Playbook runs.

It typically captures:

- which Playbook version was used,
- which steps ran and in what order,
- which tools/LLMs were called and with which parameters,
- results and intermediate artifacts,
- cost metrics (tokens, time, API costs),
- errors, retries, and fallbacks,
- feedback attached to this run.

Each Execution can be linked back into the Triad Memory:

- Task – the intent and playbook,
- Context – the conditions of this run,
- Outcome – what actually happened.

This turns every Execution into a learnable episode for future routing and improvements.
