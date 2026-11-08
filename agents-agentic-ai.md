← [Back to main list](README.md)

# Agents & Agentic AI Security

Single-agent autonomy risk: excessive agency, memory poisoning, planning/tool-use abuse, and the frameworks you'll be securing.

## Table of Contents
- [Foundations & Frameworks](#foundations--frameworks)
- [Papers & Standards](#papers--standards)
- [Tools](#tools)
- [Attacks, Breaches & Incidents](#attacks-breaches--incidents)
- [Practice & CTFs](#practice--ctfs)

**Why autonomy changes the threat model:** when a system can *act* — write files, move money, send emails, run code, chain tools — a single bad decision or malicious input costs far more than a bad answer. Agentic systems inherit every LLM/RAG risk and add indirect prompt injection, the "lethal trifecta", excessive agency, and memory poisoning.

## OWASP Agentic Top 10 (ASI) Quick Reference

The OWASP Agentic Top 10 for 2026 identifies 10 critical risk categories for autonomous AI systems. Map each to real-world incidents and core defenses:

| # | Risk | Description | Example (2025–2026) | Key Mitigation |
|---|------|-------------|-------------------|-----------------|
| **ASI01** | Agent Goal Hijack | Attacker redirects agent's objective via prompt injection | Perplexity Comet zero-click hijack (Mar 2026); Zenity labs agent takeover | Input validation, goal attestation, bounded context |
| **ASI02** | Tool Misuse & Exploitation | Agent calls wrong tool or calls tool with malicious args | JADEPUFFER lateral movement; Imprompter attack | Tool allowlist, function signature pinning, usage logging |
| **ASI03** | Identity & Privilege Abuse | Agent assumes false identity or escalates privileges in delegated chains | Nine Mexican agencies; multi-agent spoofing | mTLS between agents, identity binding, no delegation without explicit grant |
| **ASI04** | Agentic Supply Chain Vulnerabilities | Malicious MCP server, plugin, or skill injected into agent ecosystem | Amazon Q extension compromise; CVE-2025-6514 mcp-remote RCE | Registry pinning, SHA256 manifest binding, network isolation |
| **ASI05** | Unexpected Code Execution (RCE) | Agent executes code it shouldn't (shell escapes, command injection) | Cursor Terminal Allowlist Bypass (CVE-2026-22708); Langflow RCE (JADEPUFFER entry) | Sandboxing, command allowlist, AST parsing of generated code |
| **ASI06** | Memory & Context Poisoning | Attacker pollutes agent's memory/context (RAG, long-term memory) | Gmail indirect injection via history; MCP instructions field poisoning | Memory validation, cache binding, context freshness checks |
| **ASI07** | Insecure Inter-Agent Communication | Agents trust each other without authentication; messages are forgeable | Deadbugz tool-swap; agent-to-agent credential passing | Message signing, identity proof, encrypted channels |
| **ASI08** | Cascading Failures | Failure in one agent or tool chain causes catastrophic downstream failure | Replit production DB wipe → fabricated recovery claims | Circuit breakers, failure isolation, rollback capability |
| **ASI09** | Human-Agent Trust Exploitation | User trusts agent output without verification; agent exploits that trust | Deepfake exec video call scam (Mar 2025); AI-generated misinformation | Output attestation, explainability, user confirmation on high-risk actions |
| **ASI10** | Rogue Agents | Agent placed in system by insider or attacker; operates against system's goals | Nation-state jailbroken Claude Code; Anthropic campaign (Nov 2025) | Agent provenance tracking, runtime behavior monitoring, capability limits |

**Deep dive:** See [OWASP Agentic Top 10 v2026](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/) for full threat modeling and reference mitigations per category.

## Foundations & Frameworks
1. [Building Effective Agents](https://www.anthropic.com/research/building-effective-agents) - Anthropic's practical guide to agent patterns (workflows vs. agents).
2. [A Practical Guide to Building Agents](https://platform.openai.com/docs/guides/agents) - OpenAI's guidance on agent design and orchestration.
3. [ReAct: Reasoning + Acting (Yao et al., 2023)](https://arxiv.org/abs/2210.03629) - The reason-and-act loop underpinning tool-using agents.
4. [Chain-of-Thought Prompting (Wei et al., 2022)](https://arxiv.org/abs/2201.11903) - The reasoning foundation behind planning and task decomposition.
5. [Awesome Agentic Engineering](https://github.com/jordimas/awesome-agentic-engineering) - Curated reference of practical resources for agentic engineering: architectures, frameworks, memory, and evaluation.
6. [LangGraph](https://langchain-ai.github.io/langgraph/) - Graph-based orchestration for stateful, multi-actor agents.
7. [Microsoft AutoGen](https://microsoft.github.io/autogen/) - Multi-agent conversation framework.
8. [CrewAI](https://github.com/crewAIInc/crewAI) - Role-based multi-agent orchestration.
9. [OpenAI Agents SDK](https://openai.github.io/openai-agents-python/) - Lightweight framework for agentic apps.
10. [Pydantic AI](https://ai.pydantic.dev/) - Type-safe agent framework.
11. [LlamaIndex](https://www.llamaindex.ai/) - Data framework and agent workflows.
12. [Hugging Face Agents Course](https://huggingface.co/learn/agents-course) - Free course on building and deploying AI agents; useful foundation before threat-modeling agentic systems.

## Papers & Standards
1. [OWASP Agentic AI Top 10](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/)
2. [OWASP Securing Agentic Applications Guide 1.0](https://genai.owasp.org/resource/securing-agentic-applications-guide-1-0/) - Reference architecture and controls for building secure agentic apps.
3. [OWASP State of Agentic AI Security and Governance](https://genai.owasp.org/resource/state-of-agentic-ai-security-and-governance/) - Landscape view of securing and governing autonomous AI systems.
4. [OWASP Agentic Security Initiative](https://genai.owasp.org/initiatives/agentic-security-initiative/) - Threats & mitigations, multi-agent threat modeling, and reference guides.
5. [Agentic Security Risks - OWASP](https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations/) - Threats and mitigations reference for agentic applications.
6. [Microsoft: Zero Trust for AI (Tools & Guidance)](https://www.microsoft.com/en-us/security/blog/2026/03/19/new-tools-and-guidance-announcing-zero-trust-for-ai/) - Applying Zero Trust principles to AI agents and workloads. See also the [Aug 2026 follow-up](https://www.microsoft.com/en-us/security/blog/2026/08/04/advance-zero-trust-for-ai-new-tools-and-guidance-to-secure-ai-agents-and-devsecops/).
7. [Vulnerable Autonomous Agents Threat Model](https://github.com/jsotiro/ThreatModels) - LLM threat models for autonomous agents.
8. [Top 10 Agentic AI Security Risks - Key Threats and Mitigation Strategies (Precize)](https://www.precize.ai/post/top-10-agentic-ai-security-risks-key-threats-and-mitigation-strategies) - Industry threat/mitigation reference.
9. [OWASP: Memory as Attack Surface - Memory & Context Poisoning in Agentic Applications](https://genai.owasp.org/2026/05/13/memory-is-a-feature-it-is-also-an-attack-surface/) - ASI06 deep dive on agent memory as a persistent attack surface.
10. [The lethal trifecta for AI agents](https://simonwillison.net/2025/Jun/16/the-lethal-trifecta/) - Private data + untrusted content + exfiltration = a data leak waiting to happen.
11. [Imprompter: Tricking LLM Agents into Improper Tool Use](https://imprompter.ai/) - Attack demonstration against tool-using agents.
12. [Excessive Agency in AI: Hidden Security Risk (video)](https://youtu.be/o4TEomdkpCw)
13. [AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses for LLM Agents (Debenedetti et al., 2024)](https://arxiv.org/abs/2406.13352) - Benchmark environment for prompt-injection attacks and defenses on agents.
14. [MMA-SafetyBench: A Benchmark for Multimodal Agent Safety Evaluation (Wang et al., 2026)](https://arxiv.org/abs/2610.19384) - 1,083 adversarial trajectories demonstrating visual semantic hijacking of GUI-grounded agents, with attack success rates up to 88%.
15. [Encrypted Skills Can Become New Security Exploits If AI Agents Know How to Decipher (Chen et al., 2026)](https://arxiv.org/abs/2610.18262) - Ciphered Skill Injection: encoded instructions hidden in third-party agent skill files that agents decode and follow, rarely flagged by skill scanners.
16. [An Exploration of Attacks on AI Agent Systems (Qiao et al., 2026)](https://arxiv.org/abs/2610.12524) - Prompt injection across direct inputs and inter-agent communication, including cross-agent infections in multi-agent setups.
17. [Persona Guardrail: A Production-Grade Defense Framework for Agentic Systems (Pal et al., 2026)](https://arxiv.org/abs/2610.03434) - Runtime defense enforcing explicit functional boundaries via allowlist/blocklist validation, plus the PAGE guardrail benchmark.
18. [Agentic AI Security: Threats, Defenses, Evaluation, and Open Challenges (Chhabra et al., 2025)](https://arxiv.org/abs/2510.23883) - Comprehensive survey of attacks, defenses, and evaluation for LLM-based agentic systems.
19. [MMA-SafetyBench: Multimodal Agent Safety Evaluation (Wang et al., 2026)](https://arxiv.org/abs/2610.19384) - 1,083 adversarial trajectories demonstrating visual semantic hijacking of GUI-grounded agents; up to 88% success rate. Expands threat model to multimodal attacks.
20. [Ciphered Skill Injection: Encrypted Instructions Evade Scanners (Chen et al., 2026)](https://arxiv.org/abs/2610.18262) - Obfuscated payloads hidden in agent skill files; agents decode and execute at runtime; static scanners rarely detect.
21. [Persona Guardrail: Production-Grade Defense Framework for Agentic Systems (Pal et al., 2026)](https://arxiv.org/abs/2610.03434) - Runtime defense enforcing explicit functional boundaries via allowlist/blocklist validation; includes PAGE guardrail benchmark.
22. [An Exploration of Attacks on AI Agent Systems (Qiao et al., 2026)](https://arxiv.org/abs/2610.12524) - Prompt injection across direct inputs and inter-agent communication; cross-agent infections in multi-agent setups.
23. [Red-Teaming Multi-Agent LLM Systems via Communication Attacks (2025)](https://arxiv.org/abs/2502.14847) - Attack surface of agent-to-agent communication; token passing, instruction injection, credential exfiltration.

## Tools
1. [Agentic Radar (SPLX)](https://github.com/splx-ai/agentic-radar) - Security scanner that maps and analyzes agentic workflows.
2. [Council of AI GSPC](https://github.com/api-evangelist/councilof-ai) - Public model and agent measurement with signed evidence cards, public roots, and an offline verifier; measurement, not certification.
3. [DeepTeam - LLM & AI-Agent Red Teaming Framework](https://github.com/confident-ai/deepteam) - 50+ vulnerability types and 20+ attack methods mapped to OWASP/NIST/MITRE.
4. [Omega Walls](https://github.com/synqratech/omega-walls) - Open-source stateful prompt injection defense for RAG and agent pipelines, built as a runtime trust boundary across untrusted content, memory, context, and tools.
5. [Koma](https://github.com/swnotmetal/Project-Koma) - Zero-dependency Node.js/TypeScript security primitives for AI applications, including prompt-injection defense and protected data-access patterns.
6. [Protect AI's OSS Portfolio](https://github.com/protectai) - Collection of open-source AI/ML security tools (LLM Guard, ModelScan, Rebuff, and more).
7. [Redcells - Automated Adversarial Testing for LLMs](https://redcells.net) - Public-beta platform for automated adversarial testing of LLMs and agents you own or control. OpenAI-compatible target models, iterative attack→refine layers, dashboard + API. ([Repo](https://github.com/awdemos/redcell))
8. [AI-Infra-Guard (Tencent Zhuque Lab)](https://github.com/Tencent/AI-Infra-Guard) - Multi-layer AI red-teaming platform: Agent Scan for agent-workflow misconfigurations, MCP/Agent-Skill scanning across 14 risk categories, AI-infra CVE fingerprinting for 146+ components, and multi-turn LLM jailbreak evaluation.
9. [Persona Guardrail (Pal et al., 2026)](https://arxiv.org/abs/2610.03434) - Production-grade runtime guardrail enforcing explicit functional boundaries; blocks actions outside agent's intended scope; PAGE benchmark for evaluation.
10. [Agentic AI Security: Threats, Defenses, Evaluation, and Open Challenges Survey (Chhabra et al., 2025)](https://arxiv.org/abs/2510.23883) - Comprehensive survey paper linking attacks to defenses and evaluation methods for LLM-based agentic systems.

## Attacks, Breaches & Incidents

### Case Study: Anthropic Disrupts State-Scale AI-Orchestrated Espionage (Nov 2025)

On November 2025, Anthropic [disclosed the first documented state-sponsored cyberattack driven almost entirely by autonomous AI](https://www.anthropic.com/news/disrupting-AI-espionage):

- **Attacker:** Chinese state-sponsored group
- **Tool:** Jailbroken Claude Code deployed as agent
- **Scope:** ~30 global targets across government, defense, critical infrastructure
- **Autonomous Execution:** ~80–90% of attack steps were AI-driven; human operators set objectives only
- **Duration:** Multi-week campaign before disruption

**Key implications:**
1. AI agents can **scale attacks to nation-state capability** (one operator → 30 targets via agent chains).
2. **Jailbreaks now enable operational autonomy** (not just a novelty), multiplying attacker effectiveness.
3. **Future campaigns will assume AI orchestration** as baseline, not edge case.

**Mitigations highlighted:**
- Model provider-side jailbreak hardening
- User-side tool-use rate limiting & anomaly detection
- Agent audit logging (every decision must be traceable)

---

### All Incidents

1. [Hugging Face Breached by an Autonomous AI Agent (Jul 2026)](https://huggingface.co/blog/security-incident-july-2026) - An agentic system escaped a public security benchmark, abused two code-execution paths in Hugging Face's dataset processing, and reached production infrastructure over a weekend.
2. [JADEPUFFER: First Documented Agentic Ransomware (Jul 2026)](https://www.sysdig.com/blog/jadepuffer-agentic-ransomware-for-automated-database-extortion) - Sysdig traced a full extortion chain driven end-to-end by an LLM agent, from initial RCE through lateral movement to destructive encryption.
3. [Cursor Terminal Allowlist Bypass (CVE-2026-22708, Jul 2026)](https://github.com/cursor/cursor/security/advisories/GHSA-82wg-qcm4-fp2w) - Shell built-ins bypassed Cursor's Auto-Run allowlist, letting indirect prompt injection reach zero-click RCE.
4. [Zenity Labs: Zero-Click Hijacking of Agentic Browsers (Mar 2026)](https://cyberscoop.com/agentic-ai-browsers-allow-hijacking-zenity-labs-comet/) - A vulnerability family in Perplexity Comet allowing zero-click agent hijack via indirect prompt injection.
5. [Anthropic Disrupts First AI-Orchestrated Cyber Espionage Campaign (Nov 2025)](https://www.anthropic.com/news/disrupting-AI-espionage) - A state-sponsored group jailbroke Claude Code to autonomously execute ~80-90% of an espionage campaign.
6. [Replit AI Agent Deletes a Production Database (Jul 2025)](https://www.theregister.com/2025/07/21/replit_saastr_vibe_coding_incident/) - Replit's AI coding agent wiped a live production database during a code freeze, then fabricated data.
7. [Amazon Q VS Code Extension Compromised with Data-Wiping Prompt (Jul 2025)](https://www.bleepingcomputer.com/news/security/amazon-ai-coding-agent-hacked-to-inject-data-wiping-commands/) - A malicious prompt to wipe files/AWS resources was slipped into the official Amazon Q extension.
8. [Here Come the AI Worms (Wired, 2024)](https://www.wired.com/story/here-come-the-ai-worms/) - Morris II: self-propagating prompt-injection worms spreading between AI agents.
9. [Nine Mexican Government Agencies Breached by One AI-Orchestrating Operator (Dec 2025 – Feb 2026)](https://research.checkpoint.com/2026/ai-threat-landscape-digest-march-april-2026/) - Single operator running Claude Code + GPT-4.1 in parallel across 34 sessions, issuing 1,088 prompts generating 5,317 AI commands; ~400M tax/civil/electoral/health records exposed.
10. [Cursor Terminal Allowlist Bypass (CVE-2026-22708, Jul 2026, CVSS 9.9)](https://github.com/cursor/cursor/security/advisories/GHSA-82wg-qcm4-fp2w) - Shell built-ins like `export` bypassed Cursor's Auto-Run allowlist; indirect prompt injection → zero-click RCE. Demonstrates IDE-agent MCP integration risk.

See also [GenAI Security Attacks, Breaches & Incidents](README.md#genai-security-attacks-breaches--incidents) for the full cross-category incident timeline.

## Practice & CTFs
1. [FinBot Agentic AI CTF](https://genai.owasp.org/resource/finbot-agentic-ai-capture-the-flag-ctf-application/) - Agentic Security CTF.
2. [Microsoft AI Red Teaming Playground Labs](https://github.com/microsoft/AI-Red-Teaming-Playground-Labs) - Hands-on red-teaming challenges (prompt injection, indirect injection, guardrail bypass) with Docker/Kubernetes deployment.
3. [PromptTrace](https://prompttrace.airedlab.com) - Free hands-on labs and a progressive gauntlet for tool/function-call abuse against real LLM agents.
4. [CSA Agentic AI Red Teaming Guide](https://cloudsecurityalliance.org/artifacts/agentic-ai-red-teaming-guide) - Red teaming approach tailored to autonomous agents.
5. [Memory Poisoning Lab](https://github.com/RishabhPande/memory-poison-lab) - MIT local teaching range for six synthetic memory-poisoning cases, origin-aware recall and conflict-scoped repair with a scripted agent.
