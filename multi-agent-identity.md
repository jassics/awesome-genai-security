← [Back to main list](README.md)

# Multi-Agent, Agent Identity & A2A Security

Trust between agents: delegated identity, agent-to-agent authN/authZ, and multi-agent orchestration risk — distinct from single-agent excessive-agency issues covered under [Agents & Agentic AI](agents-agentic-ai.md).

## Table of Contents
- [Standards & Frameworks](#standards--frameworks)
- [Papers & Articles](#papers--articles)
- [Attacks & Incidents](#attacks--incidents)

## Standards & Frameworks
1. [CSA MAESTRO - Agentic AI Threat Modeling Framework](https://cloudsecurityalliance.org/blog/2025/02/06/agentic-ai-threat-modeling-framework-maestro) - Seven-layer threat modeling framework with explicit agent-to-agent and cross-layer trust boundaries; the most mature reference for this category today.
2. [OWASP Agent Control Standard (ACS)](https://genai.owasp.org/resource/agent-control-standard-acs/) - Open standard for agent transparency: middleware hooks and declarative, runtime-enforced safety policies portable across agent frameworks, including inter-agent delegation.
3. [OWASP Agentic Security Initiative](https://genai.owasp.org/initiatives/agentic-security-initiative/) - Includes multi-agent threat modeling guidance alongside single-agent threats.
4. [OpenID Foundation: Identity Management for Agentic AI (Oct 2025)](https://openid.net/new-whitepaper-tackles-ai-agent-identity-challenges/) - Whitepaper from the OpenID Foundation's AI Identity Management Community Group on where OAuth and OpenID Connect already secure agents, and where they fall short as agents spawn sub-agents and act across organizational boundaries. ([PDF](https://openid.net/wp-content/uploads/2025/10/Identity-Management-for-Agentic-AI.pdf))
5. [CoSAI: Agentic Identity and Access Management (Mar 2026)](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/blob/main/whitepapers/agentic-identity-and-access-control.md) - Coalition for Secure AI (an OASIS Open Project) paper on treating agents as first-class identities, with failure scenarios, threat themes, and capability-risk classification for agent access.
6. [IETF draft-ietf-wimse-aims: AI Identity Management System](https://datatracker.ietf.org/doc/draft-ietf-wimse-aims/) - IETF WIMSE working-group Internet-Draft (not yet an RFC) describing how existing standards (SPIFFE, WIMSE, OAuth, OpenID SSF) apply to AI agent authentication and authorization, and where gaps remain.
7. [SPIFFE / SPIRE](https://spiffe.io/) - CNCF-graduated standard and reference implementation for verifiable workload identity; the IETF agent draft above uses SPIFFE IDs as agent identifiers and SPIFFE for short-lived agent credentials.

## Papers & Articles
1. [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) and the [Agent2Agent (A2A) Protocol](https://a2a-protocol.org/) - The two emerging interop standards whose auth models define most current agent-identity attack surface.
2. [Security Analysis: Potential AI Agent Hijacking via MCP and A2A Protocol Insights](https://medium.com/@foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f) - Walks through hijack scenarios where one agent's delegated credentials/tools are abused by another.

## Attacks & Incidents
1. [Nine Mexican Government Agencies Breached by One AI-Orchestrating Operator (Dec 2025 - Feb 2026)](https://research.checkpoint.com/2026/ai-threat-landscape-digest-march-april-2026/) - A single operator ran Claude Code and GPT-4.1 in parallel across 34 sessions, evidence of AI-orchestrated multi-session intrusion moving from state actors to ordinary criminals.

**This category is thin because agent-identity and A2A tooling is still emerging** — there's no mature open-source scanner or dedicated CTF yet purpose-built for agent-to-agent trust abuse. If you know of one, please open a PR (see [CONTRIBUTING.md](CONTRIBUTING.md)).
