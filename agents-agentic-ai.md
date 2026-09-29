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

## Foundations & Frameworks
1. [Building Effective Agents](https://www.anthropic.com/research/building-effective-agents) - Anthropic's practical guide to agent patterns (workflows vs. agents).
2. [A Practical Guide to Building Agents](https://platform.openai.com/docs/guides/agents) - OpenAI's guidance on agent design and orchestration.
3. [ReAct: Reasoning + Acting (Yao et al., 2023)](https://arxiv.org/abs/2210.03629) - The reason-and-act loop underpinning tool-using agents.
4. [Chain-of-Thought Prompting (Wei et al., 2022)](https://arxiv.org/abs/2201.11903) - The reasoning foundation behind planning and task decomposition.
5. [Awesome Agentic Engineering](https://github.com/natnew/Awesome-Agentic-Engineering) - A reference stack for production-grade agentic systems.
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
3. [OWASP Agentic Security Initiative](https://genai.owasp.org/initiatives/#agentic) - Threats & mitigations, multi-agent threat modeling, and reference guides.
4. [Agentic Security Risks - OWASP](https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations/) - Threats and mitigations reference for agentic applications.
5. [Microsoft: Zero Trust for AI (Tools & Guidance)](https://www.microsoft.com/en-us/security/blog/2026/03/19/new-tools-and-guidance-announcing-zero-trust-for-ai/) - Applying Zero Trust principles to AI agents and workloads.
6. [Vulnerable Autonomous Agents Threat Model](https://github.com/jsotiro/ThreatModels) - LLM threat models for autonomous agents.
7. [Top 10 Agentic AI Security Risks - Key Threats and Mitigation Strategies (PDF)](https://46710127.fs1.hubspotusercontent-na2.net/hubfs/46710127/Documents/Top%2010%20Agentic%20AI%20Security%20Risks-Key%20Threats%20and%20Mitigation%20Strategies.pdf) - Industry threat/mitigation reference.
8. [OWASP: Memory as Attack Surface - Memory & Context Poisoning in Agentic Applications](https://genai.owasp.org/2026/05/13/memory-is-a-feature-it-is-also-an-attack-surface/) - ASI06 deep dive on agent memory as a persistent attack surface.
9. [The lethal trifecta for AI agents](https://simonwillison.net/2025/Jun/16/the-lethal-trifecta/) - Private data + untrusted content + exfiltration = a data leak waiting to happen.
10. [Imprompter: Tricking LLM Agents into Improper Tool Use](https://imprompter.ai/) - Attack demonstration against tool-using agents.
11. [Excessive Agency in AI: Hidden Security Risk (video)](https://youtu.be/o4TEomdkpCw)

## Tools
1. [Agentic Radar (SPLX)](https://github.com/splx-ai/agentic-radar) - Security scanner that maps and analyzes agentic workflows.
2. [Council of AI GSPC](https://github.com/api-evangelist/councilof-ai) - Public model and agent measurement with signed evidence cards, public roots, and an offline verifier; measurement, not certification.
3. [DeepTeam - LLM & AI-Agent Red Teaming Framework](https://github.com/confident-ai/deepteam) - 50+ vulnerability types and 20+ attack methods mapped to OWASP/NIST/MITRE.
4. [Omega Walls](https://github.com/synqratech/omega-walls) - Open-source stateful prompt injection defense for RAG and agent pipelines, built as a runtime trust boundary across untrusted content, memory, context, and tools.
5. [Koma](https://github.com/swnotmetal/Project-Koma) - Zero-dependency Node.js/TypeScript security primitives for AI applications, including prompt-injection defense and protected data-access patterns.
6. [Protect AI's OSS Portfolio](https://github.com/protectai) - Collection of open-source AI/ML security tools (LLM Guard, ModelScan, Rebuff, and more).
7. [Redcells - Automated Adversarial Testing for LLMs](https://redcells.net) - Public-beta platform for automated adversarial testing of LLMs and agents you own or control. OpenAI-compatible target models, iterative attack→refine layers, dashboard + API. ([Repo](https://github.com/awdemos/redcell))
8. [AI-Infra-Guard (Tencent Zhuque Lab)](https://github.com/Tencent/AI-Infra-Guard) - Multi-layer AI red-teaming platform: Agent Scan for agent-workflow misconfigurations, MCP/Agent-Skill scanning across 14 risk categories, AI-infra CVE fingerprinting for 146+ components, and multi-turn LLM jailbreak evaluation.

## Attacks, Breaches & Incidents
1. [Hugging Face Breached by an Autonomous AI Agent (Jul 2026)](https://huggingface.co/blog/security-incident-july-2026) - An agentic system escaped a public security benchmark, abused two code-execution paths in Hugging Face's dataset processing, and reached production infrastructure over a weekend.
2. [JADEPUFFER: First Documented Agentic Ransomware (Jul 2026)](https://www.sysdig.com/blog/jadepuffer-agentic-ransomware-for-automated-database-extortion) - Sysdig traced a full extortion chain driven end-to-end by an LLM agent, from initial RCE through lateral movement to destructive encryption.
3. [Cursor Terminal Allowlist Bypass (CVE-2026-22708, Jul 2026)](https://github.com/cursor/cursor/security/advisories/GHSA-82wg-qcm4-fp2w) - Shell built-ins bypassed Cursor's Auto-Run allowlist, letting indirect prompt injection reach zero-click RCE.
4. [Zenity Labs: Zero-Click Hijacking of Agentic Browsers (Mar 2026)](https://cyberscoop.com/agentic-ai-browsers-allow-hijacking-zenity-labs-comet/) - A vulnerability family in Perplexity Comet allowing zero-click agent hijack via indirect prompt injection.
5. [Anthropic Disrupts First AI-Orchestrated Cyber Espionage Campaign (Nov 2025)](https://www.anthropic.com/news/disrupting-AI-espionage) - A state-sponsored group jailbroke Claude Code to autonomously execute ~80-90% of an espionage campaign.
6. [Replit AI Agent Deletes a Production Database (Jul 2025)](https://www.theregister.com/2025/07/21/replit_saastr_vibe_coding_incident/) - Replit's AI coding agent wiped a live production database during a code freeze, then fabricated data.
7. [Amazon Q VS Code Extension Compromised with Data-Wiping Prompt (Jul 2025)](https://www.bleepingcomputer.com/news/security/amazon-ai-coding-agent-hacked-to-inject-data-wiping-commands/) - A malicious prompt to wipe files/AWS resources was slipped into the official Amazon Q extension.
8. [Here Come the AI Worms (Wired, 2024)](https://www.wired.com/story/here-come-the-ai-worms/) - Morris II: self-propagating prompt-injection worms spreading between AI agents.

See also [GenAI Security Attacks, Breaches & Incidents](README.md#genai-security-attacks-breaches--incidents) for the full cross-category incident timeline.

## Practice & CTFs
1. [FinBot Agentic AI CTF](https://genai.owasp.org/resource/finbot-agentic-ai-capture-the-flag-ctf-application/) - Agentic Security CTF.
2. [Microsoft AI Red Teaming Playground Labs](https://github.com/microsoft/AI-Red-Teaming-Playground-Labs) - Hands-on red-teaming challenges (prompt injection, indirect injection, guardrail bypass) with Docker/Kubernetes deployment.
3. [PromptTrace](https://prompttrace.airedlab.com) - Free hands-on labs and a progressive gauntlet for tool/function-call abuse against real LLM agents.
4. [CSA Agentic AI Red Teaming Guide](https://cloudsecurityalliance.org/artifacts/agentic-ai-red-teaming-guide) - Red teaming approach tailored to autonomous agents.
