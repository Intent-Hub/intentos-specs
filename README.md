# IntentHub / IntentOS Specifications

**IntentHub** is the conceptual framework for intent-driven AI systems.  
**IntentOS** is the operational runtime that implements these concepts.

This repository contains the **canonical specifications, models, architecture, and security foundations** of the IntentHub ecosystem.  
It serves as the single source of truth for:

- Intent models  
- Template and Playbook definitions  
- Memory topology (Triad Topology)  
- Big Context mechanisms  
- Context Driver architecture  
- Gateway-level safety (AI Aikido Gateway)  
- Skill Leasing (secure MCP integration)  
- Feedback and Induction pipelines  
- Glossary, RFCs, and roadmap  

If you are building tools, agents, services, or runtimes that operate within the IntentHub ecosystem, this repository is your authoritative reference.

---

## 📘 Key Files

| File                     | Description                                            |
| ------------------------ | ------------------------------------------------------ |
| `INTENTHUB_SPEC_v1.1.md` | Main unified specification — the full conceptual model |
| `index.md`               | Entry point for LLMs and contributors                  |
| `/architecture/`         | Memory, context, topology, pipelines                   |
| `/models/`               | Intent → Template → Playbook → Execution schemas       |
| `/security/`             | Contextual Zero Trust, Skill Leasing model             |
| `/rfc/`                  | Drafts and evolution proposals                         |
| `/glossary/`             | Formal definition of all terms                         |
| `/roadmap/`              | Evolution plan for IntentHub v1 → v2                   |

---

## 🔧 Implementations

IntentHub/IntentOS concepts are implemented (or will be) across multiple runtimes:

- **intentos-core** — graph-based memory engine using Triad Topology  
- **AI Aikido Gateway** — deterministic LLM gateway with cost shields and semantic cache  
- **intent-os** — semantic runtime for intent-driven apps  
- **drop-deck** — reference Local-First implementation  
- **retrodrops-lab** — IntentOS applied to Web3 mission workflows  

These implementations are *not part* of this repository.  
This repo contains **specifications only**.

---

## 📜 License

MIT License.  
Specifications are open for reading, adoption, and extension.

---

## 🤝 Contributions

All improvements must go through `/rfc` proposals.  
See `rfc/README.md` for guidelines.

---

## 🧭 Start Here

Begin with:

```
index.md
```

Everything flows from there.
