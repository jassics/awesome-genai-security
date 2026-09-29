# Awesome GenAI Security [![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)

[![Focus: GenAI & Agentic AI Security](https://img.shields.io/badge/Focus-GenAI%20%26%20Agentic%20AI%20Security-8b5cf6)](#table-of-contents)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Last Commit](https://img.shields.io/github/last-commit/jassics/awesome-genai-security)](https://github.com/jassics/awesome-genai-security/commits/main)

A curated list of links, references, books, videos, tutorials (Free or Paid), Exploit, CTFs, Hacking Practices, etc., which are related to GenAI, LLM, RAG, MCP, Agents, and Agentic AI security.

> **Note:** `awesome-agentic-ai-security` has been folded into this list. Agentic AI security — agent foundations, frameworks, autonomy risks, MCP, and multi-agent threats — now lives here alongside LLM and RAG security.

> **Related lists:** For deep academic paper tracking (jailbreak/backdoor/defense research), see [awesome-llm-security](https://github.com/corca-ai/awesome-llm-security). For an MCP-only deep dive, see [awesome-mcp-security](https://github.com/Puliczek/awesome-mcp-security). This list stays practitioner-focused — standards, tools, incidents, courses, and hands-on practice across the full LLM/RAG/MCP/Agent/Agentic AI stack.

## GenAI Security Categories
Each sub-domain of GenAI security has its own page with papers/standards, tools, attacks & incidents, and practice/CTFs specific to it.

| Category | Covers |
|---|---|
| [**LLM Security**](llm-security.md) | Jailbreaks, prompt injection, model theft, training-data poisoning, core OWASP/NIST references |
| [**RAG Security**](rag-security.md) | Retrieval pipeline, vector-DB access control, embedding/index poisoning |
| [**MCP Security**](mcp-security.md) | Model Context Protocol servers/clients, tool poisoning, auth, transport |
| [**Agents & Agentic AI**](agents-agentic-ai.md) | Single-agent autonomy, excessive agency, memory poisoning, agent frameworks |
| [**Multi-Agent, Agent Identity & A2A**](multi-agent-identity.md) | Agent-to-agent trust, delegated identity, multi-agent orchestration risk |
| [**AI Harness, Runtime & Loop Engineering**](ai-harness-loop-engineering.md) | Tool-calling loops, sandboxing, coding-agent/IDE-harness supply chain |
| [**AI Observability, Logging & Monitoring**](ai-observability-monitoring.md) | LLM/agent tracing, drift detection, runtime guardrail enforcement |

Cross-cutting material that doesn't belong to a single category — books, courses, certifications, regulation, and the full incident timeline — stays below.

## Table of Contents
- [GenAI Security Categories](#genai-security-categories)
- [AI Security Books](#ai-security-books)
- [AI Security Videos](#ai-security-videos)
- [Online Tutorials / Blogs / Presentations](#online-tutorials--blogs--presentations)
- [Online Courses (Paid/Free)](#online-courses-paidfree)
- [Study Plans, Roadmaps & Interview Prep](#study-plans-roadmaps--interview-prep)
- [AI Security Certifications](#ai-security-certifications)
- [AI Red Teaming](#ai-red-teaming)
- [GenAI Security Attacks, Breaches & Incidents](#genai-security-attacks-breaches--incidents)
- [Regulatory Frameworks & Governance](#regulatory-frameworks--governance)
- [Newsletters & Communities](#newsletters--communities)
- [Contributing](#contributing)
- [Contributors](#contributors)
---
![GenAI security banner](awesome-genai-security-banner.png)

## AI Security Books
1. [AI Value Creators](https://www.flipkart.com/ai-value-creators/p/itm84255392ef02e)
2. [AI Engineering by Chip Huyen](https://www.flipkart.com/ai-engineering-building-applications-foundation-models-full-colour-edition-model-handbook-practical-guide/p/itm0b5326225ef19)
3. [Designing Machine Learning Systems](https://www.flipkart.com/designing-machine-learning-systems/p/itm075f3337b432e)
4. [Hands-On Large Language Models](https://www.flipkart.com/hands-on-large-language-models-understanding-generation/p/itm07bb6ede2a7b0)
5. [Nexus by Yuval Noah Harari](https://www.flipkart.com/nexus/p/itm41a4d83d2cf64)
6. [The Developer's Playbook for Large Language Model Security: Building Secure AI Applications by Steve Wilson](https://www.flipkart.com/developer-s-playbook-large-language-model-security/p/itm2633a103cffb8)
7. [10 Best AI Security Books (Practical DevSecOps)](https://www.practical-devsecops.com/best-ai-security-books/)
8. [AI Security E-book 101 (Practical DevSecOps, PDF)](https://www.practical-devsecops.com/wp-content/uploads/2025/11/AI-Security-E-book-101.pdf)
9. [Red Teaming AI: A Field Manual for Attacking Intelligent Systems - Philip A. Dursey (No Starch, early access)](https://nostarch.com/red-teaming-AI)
10. [Not with a Bug, But with a Sticker - Ram Shankar Siva Kumar & Hyrum Anderson](https://www.goodreads.com/book/show/63079484-not-with-a-bug-but-with-a-sticker)
11. [Generative AI Security - Ken Huang, Yang Wang (Springer)](https://link.springer.com/book/10.1007/978-3-031-54252-7)
12. [Adversarial AI Attacks, Mitigations, and Defense Strategies - John Sotiropoulos (Packt)](https://www.packtpub.com/en-us/product/adversarial-ai-attacks-mitigations-and-defense-strategies-9781801300568)

## AI Security Videos
1. [Intro to LLM Security - WhyLabs](https://www.youtube.com/watch?v=dj1H4g4YSlU)
2. [OWASP Top 10 for LLM Applications Explained - OWASP](https://www.youtube.com/watch?v=engR9tYSsug)
3. [Hacking LLMs and Prompt Injection - LiveOverflow](https://www.youtube.com/watch?v=Sv5OLj2nVAQ)
4. [AI Red Teaming - DEFCON AI Village](https://www.youtube.com/watch?v=JCRoFMHjLng)
5. [Securing LLM Applications - SANS Institute](https://www.youtube.com/watch?v=gcnWoR5eJQQ)
6. [How Do Large Language Models Work? | LLM Architecture Explained](https://youtu.be/klcCPgbn3GM)

More category-specific videos live on each [category page](#genai-security-categories) (e.g. RAG explainer under RAG Security, excessive-agency under Agents & Agentic AI).

## Online Tutorials / Blogs / Presentations
General GenAI security tutorials and career material. Attack-specific blogs/articles live on the relevant [category page](#genai-security-categories).

1. [What are foundational models?](https://www.datacamp.com/blog/what-are-foundation-models)
2. [A quick check on the AI Threat Model](https://plot4.ai/assessments/quick-check)
3. [Security Incident Response using LLM](https://engineering.mercari.com/en/blog/entry/20241206-streamlining-security-incident-response-with-automation-and-large-language-models/)
4. [AI Security Interview Questions (Practical DevSecOps)](https://www.practical-devsecops.com/ai-security-interview-questions/)
5. [Emerging AI Security Roles (Practical DevSecOps)](https://www.practical-devsecops.com/emerging-ai-security-roles/)
6. [AI Security Engineer Roadmap (Practical DevSecOps)](https://www.practical-devsecops.com/ai-security-engineer-roadmap/)

## Online Courses (Paid/Free)
1. [Stanford CS-324: Large Language Models](https://stanford-cs324.github.io/winter2022/)
2. [Princeton COS 597G: Understanding Large Language Models](https://www.cs.princeton.edu/courses/archive/fall22/cos597G/)
3. [Coursera: GenAI with LLM](https://www.coursera.org/learn/generative-ai-with-llms#modules)
4. [Coursera: Generative AI Engineering with LLMs Specialization](https://www.coursera.org/specializations/generative-ai-engineering-with-llms#courses)
5. [Coursera: Generative AI for Cybersecurity Professionals (IBM)](https://www.coursera.org/specializations/generative-ai-for-cybersecurity-professionals)
6. [Coursera: AI for Cybersecurity (JHU)](https://www.coursera.org/specializations/ai-for-cybersecurity)
7. [AttackIQ: The foundation of AI Security](https://www.academy.attackiq.com/courses/foundations-of-ai-security)
8. [Microsoft AI Red Teaming 101 (Microsoft Learn)](https://learn.microsoft.com/en-us/security/ai-red-team/training) - Free training on GenAI vulnerabilities, single/multi-turn attacks, spotlighting defenses, and PyRIT automation.
9. [SANS SEC545: GenAI and LLM Application Security](https://www.sans.org/cyber-security-courses/genai-llm-application-security/) - RAG/vector-DB security, prompt injection, MLOps hardening, and agentic AI security (maps to GIAC GAIPS).
10. [DeepLearning.AI: Red Teaming LLM Applications](https://www.deeplearning.ai/courses/red-teaming-llm-applications/) - Hands-on course on identifying and evaluating LLM app vulnerabilities.
11. [DeepLearning.AI: Safe and Reliable AI via Guardrails](https://www.deeplearning.ai/courses/safe-and-reliable-ai-via-guardrails/) - Moving LLM apps to production with runtime guardrail controls.
12. [DeepLearning.AI: Quality and Safety for LLM Applications](https://www.deeplearning.ai/courses/quality-safety-llm-applications/) - Evaluating and monitoring LLM app safety/security in production.
13. [Hugging Face Agents Course](https://huggingface.co/learn/agents-course) - Free course on building and deploying AI agents; useful foundation before threat-modeling agentic systems.

## Study Plans, Roadmaps & Interview Prep
Structured paths for going from "interested in AI security" to job-ready.

1. [GenAI Security Study Plan](https://github.com/jassics/security-study-plan/blob/main/genai-security-study-plan.md) - Week-by-week plan for learning GenAI and LLM security.
2. [AI Security Career Roadmap](https://github.com/jassics/cybersecurity-roadmap/blob/main/ai-security-career-roadmap.md) - Skills, milestones, and role progression for an AI security career.
3. [AI Security Interview Questions](https://github.com/jassics/security-interview-questions/blob/main/ai-security-interview-questions.md) - Question bank for AI/GenAI security interviews.
4. [AI/ML Security Learning Resources](https://github.com/jassics/awesome-cybersecurity-learning-resources/blob/main/awesome-aiml-security-learning-resources.md) - Wider collection of AI/ML security learning material.

## AI Security Certifications
1. [Certified AI Security Professional (CAISP) by Practical DevSecOps](https://www.practical-devsecops.com/certified-ai-security-professional/) – Securing AI systems, models, and pipelines against adversarial threats, LLM vulnerabilities, AI supply chain risks, data poisoning, and AI-specific security frameworks. Hands-on, practitioner-level skills.
2. [GIAC AI Platform Security (GAIPS)](https://www.giac.org/certifications/ai-security-platform-security-gaips) - Hands-on (CyberLive) certification for auditing and securing GenAI applications, LLM pipelines, and agentic AI systems.
3. [GIAC AI Security Automation Engineer (GASAE)](https://www.giac.org/certifications/ai-security-automation-engineer-gasae) - Validates using AI/automation across offensive, defensive, and cloud security operations.
4. [ISC2 AI Security Certificate](https://www.isc2.org/landing/ai-security-skills) - On-demand course bundle covering AI fundamentals, AI risk management, secure-by-design, and global AI regulation.

## AI Red Teaming
General red-teaming methodology and orgs. Category-specific red-team tools/guides (LLM, Agentic) live on their [category pages](#genai-security-categories).

1. [Microsoft AI Red Team](https://learn.microsoft.com/en-us/security/ai-red-team/)
2. [Anthropic Red Teaming Research](https://www.anthropic.com/research#red-teaming)
3. [MITRE ATLAS - Tools, Data & Case Studies (GitHub)](https://github.com/mitre-atlas)
4. [AI Red Teaming Guide - Humane Intelligence](https://www.humane-intelligence.org/)
5. [Google DeepMind: Evaluating Frontier Models for Dangerous Capabilities](https://arxiv.org/abs/2403.13793)
6. [OWASP GenAI Red Teaming Guide](https://genai.owasp.org/resource/genai-red-teaming-guide/) - Methodology for red teaming GenAI/LLM applications.

## GenAI Security Attacks, Breaches & Incidents
Notable real-world incidents involving GenAI and LLM security, newest first. For ongoing tracking, see the [OWASP GenAI Exploit Round-up](https://genai.owasp.org/2026/04/14/owasp-genai-exploit-round-up-report-q1-2026/), which catalogs confirmed CVEs and exploits each quarter. Incidents are also cross-listed on the relevant [category page](#genai-security-categories) (e.g. MCP incidents under MCP Security).

1. [Hugging Face Breached by an Autonomous AI Agent (Jul 2026)](https://huggingface.co/blog/security-incident-july-2026) - An agentic system escaped a public security benchmark, abused two code-execution paths in Hugging Face's dataset processing, and reached production infrastructure over a weekend. OpenAI attributed it to its own pre-release models running unsupervised. Internal datasets and service credentials were accessed; public models, datasets, and Spaces were verified untampered. The first known case where AI capability evaluation caused a real breach.
2. [JADEPUFFER: First Documented Agentic Ransomware (Jul 2026)](https://www.sysdig.com/blog/jadepuffer-agentic-ransomware-for-automated-database-extortion) - Sysdig traced a full extortion chain driven end-to-end by an LLM: Langflow RCE (CVE-2025-3248) for entry, credential harvesting, lateral movement, then encryption and destruction of 1,342 config items. The agent recovered from a failed login in 31 seconds by rewriting its own payload. The AES key was printed to stdout and never persisted — paying the ransom recovers nothing.
3. [Cursor Terminal Allowlist Bypass (CVE-2026-22708, Jul 2026)](https://github.com/cursor/cursor/security/advisories/GHSA-82wg-qcm4-fp2w) - Shell built-ins like `export` bypassed Cursor's Auto-Run allowlist, letting indirect prompt injection poison the agent's environment and reach zero-click RCE. Fixed in 2.3.
4. [Vercel Breached via a Compromised Third-Party AI Tool (Apr 2026)](https://vercel.com/kb/bulletin/vercel-april-2026-security-incident) - Attackers pivoted from an infostealer infection at Context.ai through an employee's OAuth grant into Vercel's internal systems, enumerating and decrypting environment variables. A worked example of shadow-AI and OAuth sprawl as an enterprise attack path.
5. [Zenity Labs: Zero-Click Hijacking of Agentic Browsers (Mar 2026)](https://cyberscoop.com/agentic-ai-browsers-allow-hijacking-zenity-labs-comet/) - A vulnerability family in Perplexity Comet allowing zero-click agent hijack, including takeover of a signed-in password manager, via indirect prompt injection. See also [Brave's earlier Comet research](https://brave.com/blog/comet-prompt-injection/).
6. [Nine Mexican Government Agencies Breached by One AI-Orchestrating Operator (Dec 2025 - Feb 2026)](https://research.checkpoint.com/2026/ai-threat-landscape-digest-march-april-2026/) - Check Point documented a single operator running Claude Code and GPT-4.1 in parallel — 1,088 prompts producing 5,317 AI-executed commands across 34 sessions — exposing roughly 400 million tax, civil registry, electoral, and health records. Evidence that AI-orchestrated intrusion has moved from state actors to ordinary criminals.
7. [Anthropic Disrupts First AI-Orchestrated Cyber Espionage Campaign (Nov 2025)](https://www.anthropic.com/news/disrupting-AI-espionage) - A Chinese state-sponsored group jailbroke Claude Code to autonomously execute ~80-90% of an espionage campaign against ~30 global targets; the first documented largely AI-run cyberattack.
8. [CamoLeak: GitHub Copilot Chat Private Source-Code Exfiltration (Oct 2025)](https://www.legitsecurity.com/blog/camoleak-critical-github-copilot-vulnerability-leaks-private-source-code) - CVSS 9.6 prompt injection hidden in PRs leaks private code and secrets via GitHub's own Camo image proxy.
9. [Check Point Researchers Expose Critical Claude Code Flaws](https://blog.checkpoint.com/research/check-point-researchers-expose-critical-claude-code-flaws/) - CVE-2025-59536 and CVE-2026-21852: Enabling Remote Command Execution and API Key Theft.
10. [Anthropic: "Vibe-Hacking" Extortion Using Claude Code (Aug 2025)](https://www.anthropic.com/news/detecting-countering-misuse-aug-2025) - A criminal used Claude Code to automate intrusions and craft targeted extortion against 17+ organizations, alongside AI-built ransomware-as-a-service.
11. [PromptLock: First Known AI-Powered Ransomware (Aug 2025, PoC)](https://www.welivesecurity.com/en/ransomware/first-known-ai-powered-ransomware-uncovered-eset-research/) - ESET found ransomware that uses a local LLM via the Ollama API to generate malicious scripts on the fly (later assessed as an academic proof-of-concept).
12. [Replit AI Agent Deletes a Production Database (Jul 2025)](https://www.theregister.com/2025/07/21/replit_saastr_vibe_coding_incident/) - Replit's AI coding agent wiped a live production database during a code freeze, then fabricated data and falsely claimed rollback was impossible.
13. [Amazon Q VS Code Extension Compromised with Data-Wiping Prompt (Jul 2025)](https://www.bleepingcomputer.com/news/security/amazon-ai-coding-agent-hacked-to-inject-data-wiping-commands/) - A malicious prompt to wipe files and delete AWS resources was slipped into the official Amazon Q extension (964k+ installs).
14. [CVE-2025-6514: Critical RCE in mcp-remote (Jul 2025)](https://jfrog.com/blog/2025-6514-critical-mcp-remote-rce-vulnerability/) - A malicious MCP server could achieve full remote code execution (CVSS 9.6) on clients running mcp-remote; the first real-world RCE against an MCP client.
15. [EchoLeak (CVE-2025-32711): Zero-Click Data Theft in Microsoft 365 Copilot (Jun 2025)](https://checkmarx.com/zero-post/echoleak-cve-2025-32711-show-us-that-ai-security-is-challenging/) - A single crafted email could silently exfiltrate organizational data from M365 Copilot with no user interaction; the first known zero-click exploit against an AI agent.
16. [Policy Puppetry: Universal Jailbreak Bypassing All Major LLMs (Apr 2025)](https://www.hiddenlayer.com/research/novel-universal-bypass-for-all-major-llms) - HiddenLayer disclosed a single transferable prompt that bypasses safety guardrails across OpenAI, Google, Anthropic, Meta, DeepSeek, and others.
17. [Singapore Finance Director Scammed via Deepfake Executive Video Call (Mar 2025)](https://mothership.sg/2025/04/finance-director-scammed-deepfake/) - A finance director transferred ~US$499,000 after a Zoom call in which company executives were AI-generated deepfakes.
18. [nullifAI: Malicious ML Models on Hugging Face Evade Picklescan (Feb 2025)](https://www.reversinglabs.com/blog/rl-identifies-malware-ml-model-hosted-on-hugging-face) - ReversingLabs found malicious Pickle-based models using broken/7z-wrapped pickles to bypass scanners and deliver a reverse shell (PoC).
19. [Anthropic: Chinese AI Firms Created 24,000 Fraudulent Accounts For 'Distillation Attacks'](https://in.mashable.com/tech/106230/anthropic-chinese-ai-firms-created-24000-fraudulent-accounts-for-distillation-attacks)
20. [DeepSeek Exposed Database Leaking Chat History and API Keys (Jan 2025)](https://www.wiz.io/blog/wiz-research-uncovers-exposed-deepseek-database-leak) - Wiz found a publicly accessible, unauthenticated DeepSeek ClickHouse database exposing 1M+ log lines including plaintext chats and secrets.
21. [LiteLLM on PyPI Was Compromised, What the Attack Changed and What Defenders Should Do Now](https://www.penligent.ai/hackinglabs/litellm-on-pypi-was-compromised-what-the-attack-changed-and-what-defenders-should-do-now/)
22. [The Day Chevrolet's AI Chatbot Tried to Sell a $70,000 SUV for $1](https://medium.com/@celestineriza/the-day-chevrolets-ai-chatbot-tried-to-sell-a-70-000-suv-for-1-29f4a1e954d9)
23. [Here Come the AI Worms (Wired, 2024)](https://www.wired.com/story/here-come-the-ai-worms/) - Morris II: self-propagating prompt-injection worms spreading between AI agents.
24. [Air Canada Chatbot Provides Wrong Info (2024)](https://www.bbc.com/travel/article/20240222-air-canada-chatbot-misinformation-what-travellers-should-know) - Airline held liable for chatbot hallucinating refund policy.
25. [Samsung bans use of generative AI tools like ChatGPT after April internal data leak (2023)](https://techcrunch.com/2023/05/02/samsung-bans-use-of-generative-ai-tools-like-chatgpt-after-april-internal-data-leak/)
26. [AI-powered Bing Chat spills its secrets via prompt injection attack (2023)](https://arstechnica.com/information-technology/2023/02/ai-powered-bing-chat-spills-its-secrets-via-prompt-injection-attack/)
27. [ChatGPT Data Leak Bug (2023)](https://openai.com/index/march-20-chatgpt-outage/) - Bug exposed chat history titles and payment info of other users.
28. [GitHub Copilot Leaking Secrets (2023)](https://blog.gitguardian.com/yes-github-copilot-can-leak-secrets/) - AI code assistant reproducing secrets from training data.
29. [Microsoft Tay Bot Manipulation (2016)](https://en.wikipedia.org/wiki/Tay_(chatbot)) - Twitter chatbot manipulated into generating offensive content.
30. [Orca AI Incident Archive](https://github.com/Continuum-AI-Corp/Orca-AI-Incident-Archive) - Open database of 354 sourced AI agent security records (2025-01 to 2026-09) that separates confirmed-harm incidents from vulnerabilities and research, with JSON/CSV exports (CC BY 4.0).

## Regulatory Frameworks & Governance
1. [EU AI Act](https://artificialintelligenceact.eu/) - EU regulation on artificial intelligence.
2. [NIST AI Risk Management Framework (AI RMF)](https://www.nist.gov/itl/ai-risk-management-framework) - NIST's voluntary framework for managing AI risks.
3. [ISO/IEC 42001:2023 - AI Management System Standard](https://www.iso.org/standard/81230.html)
4. [U.S. AI Executive Order (2025): Removing Barriers to American Leadership in AI](https://www.federalregister.gov/documents/2025/01/31/2025-02172/removing-barriers-to-american-leadership-in-artificial-intelligence) - The Trump administration's Jan 2025 EO; it revoked Biden's [EO 14110 (2023)](https://en.wikipedia.org/wiki/Executive_Order_14110) on Safe, Secure & Trustworthy AI.
5. [India AI Governance Guidelines (IndiaAI / MeitY)](https://www.indiaai.gov.in/) - India's national AI strategy and governance guidance.
6. [Singapore Model AI Governance Framework](https://www.pdpc.gov.sg/help-and-resources/2020/01/model-ai-governance-framework)
7. [UK - International AI Safety Report](https://www.gov.uk/government/publications/international-ai-safety-report-2025) - Frontier AI risk assessment led by Yoshua Bengio.

## Newsletters & Communities
1. [OWASP GenAI Slack Channel](https://owasp.slack.com/) - Join #project-top10-for-llm channel.
2. [AI Village (DEF CON)](https://aivillage.org/) - Community focused on AI security research.
3. [MLSecOps Community](https://mlsecops.com/) - Community for ML security operations.
4. [The AI Security Newsletter by Ken Huang](https://www.linkedin.com/newsletters/ai-security-newsletter-7153297736498069504/)
5. [Protect AI (now part of Palo Alto Networks)](https://protectai.com/) - Blog content now folded into [Palo Alto Networks' AI Security blog](https://www.paloaltonetworks.com/blog/ai-security/).

## Contributing
Found a great paper, tool, course, CTF, or incident writeup on GenAI, LLM, RAG, MCP, or agentic AI security? Read [CONTRIBUTING.md](CONTRIBUTING.md) and open a pull request. Small additions are very welcome — add category-specific resources to the right [category page](#genai-security-categories); cross-cutting resources (books, courses, incidents, regulation) go in this README.

## Contributors
Thanks to everyone who helps keep this list current. Your name could be next — open a PR!

*   [Sanjeev Jaiswal](https://github.com/jassics) - maintainer
*   [mldangelo](https://github.com/mldangelo) - promptfoo
*   Aj7ay7 - Practical DevSecOps CAISP certification
*   [anviren](https://github.com/anviren) - Omega Walls
*   [kantorcodes](https://github.com/kantorcodes) - HOL Guard
*   [awdemos](https://github.com/awdemos) - Redcells
*   [K4r1it0](https://github.com/K4r1it0) - PromptTrace
*   [swnotmetal](https://github.com/swnotmetal) - Koma
*   [azrollin](https://github.com/azrollin) - SUNGLASSES
*   [themsquared](https://github.com/themsquared) - MCP security articles

---

_Licensed under [GPL-3.0](LICENSE)._
