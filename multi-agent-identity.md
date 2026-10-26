← [Back to main list](README.md)

# Multi-Agent, Agent Identity & A2A Security

Trust between agents: delegated identity, agent-to-agent authN/authZ, and multi-agent orchestration risk — distinct from single-agent excessive-agency issues covered under [Agents & Agentic AI](agents-agentic-ai.md).

## Table of Contents
- [Standards & Frameworks](#standards--frameworks)
- [Papers & Articles](#papers--articles)
- [Shadow AI & Unauthorized OAuth](#shadow-ai--unauthorized-oauth)
- [Attacks & Incidents](#attacks--incidents)

## Standards & Frameworks
1. [CSA MAESTRO - Agentic AI Threat Modeling Framework](https://cloudsecurityalliance.org/blog/2025/02/06/agentic-ai-threat-modeling-framework-maestro) - Seven-layer threat modeling framework with explicit agent-to-agent and cross-layer trust boundaries; the most mature reference for this category today.
2. [OWASP Agent Control Standard (ACS)](https://genai.owasp.org/resource/agent-control-standard-acs/) - Open standard for agent transparency: middleware hooks and declarative, runtime-enforced safety policies portable across agent frameworks, including inter-agent delegation.
3. [OWASP Agentic Security Initiative](https://genai.owasp.org/initiatives/agentic-security-initiative/) - Includes multi-agent threat modeling guidance alongside single-agent threats.

## Papers & Articles
1. [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) and the [Agent2Agent (A2A) Protocol](https://a2a-protocol.org/) - The two emerging interop standards whose auth models define most current agent-identity attack surface.
2. [Security Analysis: Potential AI Agent Hijacking via MCP and A2A Protocol Insights](https://medium.com/@foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f) - Walks through hijack scenarios where one agent's delegated credentials/tools are abused by another.
3. [An Exploration of Attacks on AI Agent Systems (Qiao et al., 2026)](https://arxiv.org/abs/2610.12524) - Prompt injection across direct inputs and inter-agent communication; cross-agent infections in multi-agent setups.
4. [Red-Teaming Multi-Agent LLM Systems via Communication Attacks (2025)](https://arxiv.org/abs/2502.14847) - Attack surface of agent-to-agent communication; token passing, instruction injection, credential exfiltration between agents.

## Shadow AI & Unauthorized OAuth

**Definition:** Employees installing unauthorized AI tools (ChatGPT, GitHub Copilot, Context.ai, etc.) with OAuth access to corporate cloud; attacker compromises the AI tool → pivots to corporate systems.

### Real-World Example: Vercel April 2026 Breach

1. Employee installed Context.ai (third-party AI coding tool) and granted it OAuth access to personal Google Cloud account with Vercel admin credentials.
2. Attacker compromised Context.ai via infostealer infection or supply-chain attack.
3. Attacker used stolen OAuth token to access employee's GCP account → discovered Vercel API keys → Vercel internal systems.
4. **Result:** Environment variables and service credentials exposed; no model/dataset tampering detected, but blast radius was significant.

### Defense Layers

| Layer | Control | Example |
|-------|---------|---------|
| **Inventory** | Discover all OAuth grants to AI tools (GCP OAuth Audit Log, AWS CloudTrail OIDC events) | Quarterly audit of `accounts.google.com/u/0/security/review-security-settings` |
| **Policy** | Prohibit OAuth grants to unapproved AI tools; enforce zero-trust for coding agents | Require pre-approval before installing Copilot, ChatGPT, etc. |
| **Rate-limit** | Limit token refresh from AI tools to prevent token harvesting | Alert on >5 token-refresh calls/hour from same tool |
| **Scope** | Minimize OAuth scopes granted to AI tools; deny `cloud-platform` scope | Approve only `gcloud.read` if possible; never grant write/delete |
| **Monitoring** | Alert on unusual OAuth scopes, unexpected tool API calls | Alert on env-var read, secrets access, KMS operations from AI tool service accounts |
| **Incident Response** | Immediate revocation of compromised OAuth grant; audit accessed resources | Revoke token, enumerate accessed resources, check for lateral movement |

### Implications for Agentic Systems

Multi-agent systems running in corporate environments must consider:
- Can agents be given OAuth tokens to corporate systems? (Usually: no, requires explicit approval)
- Are agent-to-agent communication channels using OAuth? (If yes: mutual TLS + identity proof required)
- How is token rotation handled in agent chains? (Long-lived tokens = higher compromise risk)
- What happens if an agent's service account is compromised? (Can it read other agents' tokens?)

## Attacks & Incidents
1. [Nine Mexican Government Agencies Breached by One AI-Orchestrating Operator (Dec 2025 - Feb 2026)](https://research.checkpoint.com/2026/ai-threat-landscape-digest-march-april-2026/) - A single operator ran Claude Code and GPT-4.1 in parallel across 34 sessions, evidence of AI-orchestrated multi-session intrusion moving from state actors to ordinary criminals.

**This category is thin because agent-identity and A2A tooling is still emerging** — there's no mature open-source scanner or dedicated CTF yet purpose-built for agent-to-agent trust abuse. If you know of one, please open a PR (see [CONTRIBUTING.md](CONTRIBUTING.md)).
