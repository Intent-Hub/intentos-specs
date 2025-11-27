# Skill Leasing

**Skill Leasing** is the model where external capabilities are mounted into IntentOS **temporarily** for a specific task or playbook.

A “skill” can be:

- an MCP server,
- a remote agent,
- a local binary or script,
- a third-party API.

Security aspects:

- access is granted via **scoped JWTs** with short TTL,
- only minimal context required for the skill is exposed,
- skills are treated as potentially untrusted unless explicitly whitelisted,
- logs and outcomes are captured back into the Intent Memory Engine.

Skill Leasing lets IntentHub expand its capabilities without sacrificing control over context and data.
