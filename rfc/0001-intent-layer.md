# RFC-0001: Intent Layer

Status: Draft  
Authors: IntentHub Maintainers  
Target: Core Specification

## Motivation

Different agents and runtimes need a common way to talk about “what the user wants” without relying on raw prompts.  
We need a stable, structured **Intent Layer** that all tools can share.

## Proposal

Define a canonical Intent model that includes:

- task (string / enum-like description),
- context (structured, optional),
- parameters (typed inputs),
- desired_outcome (success criteria),
- source (origin of the intent).

The Intent Layer becomes:

- the entry point into Templates and Playbooks,
- the main key for memory retrieval and routing,
- the shared contract across runtimes.

## Notes

This RFC only outlines the concept.  
Formal schema definitions live in `models/intent.md` and future extended specs.
