← [Back to main list](README.md)

# LLM Security

Core model- and prompt-level risk: jailbreaks, prompt injection, model theft, training-data poisoning, and the OWASP/NIST reference material that frames it.

## Table of Contents
- [Papers & Standards](#papers--standards)
- [Attacks & Techniques](#attacks--techniques)
- [Tools](#tools)
- [Attacks, Breaches & Incidents](#attacks-breaches--incidents)
- [Practice & CTFs](#practice--ctfs)

## Papers & Standards
1. [OWASP GenAI LLM Top 10 2026](https://genai.owasp.org/resource/owasp-genai-llm-top-10-2026/) - Latest community-driven refresh of the LLM Top 10 (supersedes the 2025 edition).
2. [OWASP LLM AI Security and Governance Checklist](https://genai.owasp.org/resource/llm-applications-cybersecurity-and-governance-checklist/)
3. [NIST AI RMF Playbook](https://airc.nist.gov/AI_RMF_Knowledge_Base/Playbook)
4. [NIST AI Risk Management Framework (AI RMF)](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf)
5. [NIST Adversarial Machine Learning](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-2e2023.pdf)
6. [Microsoft Failure Models in Machine Learning](https://securityandtechnology.org/wp-content/uploads/2020/07/failure_modes_in_machine_learning.pdf)
7. [Microsoft Threat Modeling AI/ML](https://learn.microsoft.com/en-us/security/engineering/threat-modeling-aiml)
8. [MITRE ATLAS (Adversarial Threat Landscape for AI Systems)](https://atlas.mitre.org/)
9. [OWASP GenAI Security Project](https://genai.owasp.org/) - Hub for all OWASP GenAI Top 10s, guides, and initiatives.
10. [Google Secure AI Framework (SAIF)](https://safety.google/cybersecurity-advancements/saif/)
11. [Anthropic Responsible Scaling Policy](https://www.anthropic.com/index/anthropics-responsible-scaling-policy)
12. [ENISA Multilayer Framework for Good Cybersecurity Practices for AI](https://www.enisa.europa.eu/publications/multilayer-framework-for-good-cybersecurity-practices-for-ai)
13. [Databricks AI Security Framework (DASF) 2.0](https://www.databricks.com/resources/whitepaper/databricks-ai-security-framework-dasf) - Practical controls mapped to AI system components and risks.
14. [Prompt Injection Attacks and Defenses in LLM-Integrated Applications](https://arxiv.org/abs/2310.12815)

## Attacks & Techniques
1. [Prompt injection jailbreaking](https://ogre51.medium.com/security-of-llm-apps-prompt-injection-jailbreaking-fb9fc5c883a8)
2. [LLM Attacks - Universal and Transferable Adversarial Attacks on Aligned LLMs](https://llm-attacks.org/)
3. [Not what you've signed up for: Compromising Real-World LLM-Integrated Applications](https://arxiv.org/abs/2302.12173)
4. [Simon Willison's Blog on Prompt Injection](https://simonwillison.net/series/prompt-injection/)
5. [Embrace the Red - AI Security Blog by Johann Rehberger](https://embracethered.com/)
6. [Trail of Bits - AI/ML Security Research](https://blog.trailofbits.com/categories/machine-learning/)
7. [LLM Security](https://llmsecurity.net/)
8. [Awesome LLM Security](https://github.com/corca-ai/awesome-llm-security) - Deep academic paper tracker (jailbreak/backdoor/defense research) if you need to go beyond this page.

## Tools
### Defensive / Scanning
1. [LLM Guard](https://github.com/protectai/llm-guard) - Information extraction and security for LLMs.
2. [Model Scan](https://github.com/protectai/modelscan) - Scanning models for serialization attacks.
3. [Rebuff](https://github.com/protectai/rebuff) - Prompt injection detection.
4. [NB Defense](https://github.com/protectai/nbdefense) - Notebook security.
5. [LLM Guard Playground](https://huggingface.co/spaces/protectai/llm-guard-playground)
6. [Fickling (Trail of Bits)](https://github.com/trailofbits/fickling) - Decompiler, static analyzer, and safety scanner for malicious pickle/PyTorch model files.
7. [ModelAudit](https://github.com/promptfoo/modelaudit) - Static scanner detecting malicious code/backdoors across 40+ ML model file formats.
8. [AIsbom](https://aisbom.io/) - CLI that scans model files for malware and generates CycloneDX/SPDX AI SBOMs.
9. [Giskard](https://github.com/Giskard-AI/giskard) - Testing and scanning framework for ML/LLM systems.

### Offensive / Red Teaming
1. [AI/ML Exploits](https://github.com/protectai/ai-exploits)
2. [Garak - LLM Vulnerability Scanner](https://github.com/NVIDIA/garak)
3. [PyRIT - Python Risk Identification Toolkit for GenAI (Microsoft)](https://github.com/Azure/PyRIT)
4. [Counterfit - AI Security Testing (Microsoft)](https://github.com/Azure/counterfit)
5. [ART - Adversarial Robustness Toolbox (IBM)](https://github.com/Trusted-AI/adversarial-robustness-toolbox)
6. [promptmap - Prompt Injection Testing](https://github.com/utkusen/promptmap)
7. [Promptfoo - LLM Testing & Red Teaming](https://github.com/promptfoo/promptfoo) - Generates adversarial inputs to find prompt injection, jailbreaks, and data leakage, with CI/CD integration.
8. [Sentinel Scan](https://github.com/Ventrova/sentinel-scan-cli) - CLI for authorized LLM red-team audits: prompt injection, jailbreak, and data-leak probes with a scored report.

### Guardrails & Firewalls
1. [Guardrails AI](https://github.com/guardrails-ai/guardrails) - Input/output validation for LLMs.
2. [NeMo Guardrails (NVIDIA)](https://github.com/NVIDIA/NeMo-Guardrails) - Programmable guardrails for LLM applications.
3. [Vigil - LLM Prompt Injection Detection](https://github.com/deadbits/vigil-llm)
4. [Lakera Guard](https://www.lakera.ai/) - Real-time AI security for prompt injection and data leakage.
5. [Trylon Gateway](https://github.com/trylonai/gateway) - Self-hosted open-source AI firewall/proxy applying custom guardrails (prompt-injection defense, PII redaction).
6. [Bifrost AI Gateway](https://github.com/maximhq/bifrost) - High-performance open-source AI gateway unifying 20+ LLM providers with governance and policy enforcement.
7. [SUNGLASSES](https://github.com/sunglasses-dev/sunglasses) - Open source input firewall for AI agents that runs locally and scans text and files for prompt injection, credential leaks and data exfiltration with 1,554 patterns across 118 categories; it also runs as an MCP server.

## Attacks, Breaches & Incidents
1. [Policy Puppetry: Universal Jailbreak Bypassing All Major LLMs (Apr 2025)](https://www.hiddenlayer.com/research/novel-universal-bypass-for-all-major-llms) - HiddenLayer disclosed a single transferable prompt that bypasses safety guardrails across OpenAI, Google, Anthropic, Meta, DeepSeek, and others.
2. [nullifAI: Malicious ML Models on Hugging Face Evade Picklescan (Feb 2025)](https://www.reversinglabs.com/blog/rl-identifies-malware-ml-model-hosted-on-hugging-face) - ReversingLabs found malicious Pickle-based models using broken/7z-wrapped pickles to bypass scanners and deliver a reverse shell (PoC).
3. [Anthropic: Chinese AI Firms Created 24,000 Fraudulent Accounts For 'Distillation Attacks'](https://in.mashable.com/tech/106230/anthropic-chinese-ai-firms-created-24000-fraudulent-accounts-for-distillation-attacks)
4. [DeepSeek Exposed Database Leaking Chat History and API Keys (Jan 2025)](https://www.wiz.io/blog/wiz-research-uncovers-exposed-deepseek-database-leak) - Wiz found a publicly accessible, unauthenticated DeepSeek ClickHouse database exposing 1M+ log lines including plaintext chats and secrets.
5. [The Day Chevrolet's AI Chatbot Tried to Sell a $70,000 SUV for $1](https://medium.com/@celestineriza/the-day-chevrolets-ai-chatbot-tried-to-sell-a-70-000-suv-for-1-29f4a1e954d9)
6. [Air Canada Chatbot Provides Wrong Info (2024)](https://www.bbc.com/travel/article/20240222-air-canada-chatbot-misinformation-what-travellers-should-know) - Airline held liable for chatbot hallucinating refund policy.
7. [Samsung bans use of generative AI tools like ChatGPT after April internal data leak (2023)](https://techcrunch.com/2023/05/02/samsung-bans-use-of-generative-ai-tools-like-chatgpt-after-april-internal-data-leak/)
8. [AI-powered Bing Chat spills its secrets via prompt injection attack (2023)](https://arstechnica.com/information-technology/2023/02/ai-powered-bing-chat-spills-its-secrets-via-prompt-injection-attack/)
9. [ChatGPT Data Leak Bug (2023)](https://openai.com/index/march-20-chatgpt-outage/) - Bug exposed chat history titles and payment info of other users.
10. [GitHub Copilot Leaking Secrets (2023)](https://blog.gitguardian.com/yes-github-copilot-can-leak-secrets/) - AI code assistant reproducing secrets from training data.
11. [Microsoft Tay Bot Manipulation (2016)](https://en.wikipedia.org/wiki/Tay_(chatbot)) - Twitter chatbot manipulated into generating offensive content.

See also [GenAI Security Attacks, Breaches & Incidents](README.md#genai-security-attacks-breaches--incidents) for the full cross-category incident timeline.

## Practice & CTFs
1. [Gandalf - Lakera AI](https://gandalf.lakera.ai/) - LLM security challenge.
2. [Prompt Airlines](https://promptairlines.com/) - AI security challenges, CTF style.
3. [OWASP WrongSecrets](https://owasp.org/www-project-wrongsecrets/) - Includes an LLM/AI secrets-leakage challenge.
4. [Huntr.com](https://huntr.com/) - World's first bug bounty platform for AI/ML.
5. [HackAPrompt](https://www.aicrowd.com/challenges/hackaprompt-2023) - Prompt hacking competition.
6. [Crucible by Dreadnode](https://crucible.dreadnode.io/) - AI/ML security challenges and CTFs.
7. [AI Goat](https://github.com/dhammon/ai-goat) - Vulnerable LLM CTF built on AWS.
8. [PortSwigger Web Security Academy: Web LLM Attacks](https://portswigger.net/web-security/llm-attacks) - Free official hands-on labs on exploiting LLM APIs, excessive agency, and prompt injection.
9. [Vulnerable LLM apps (GitHub topic)](https://github.com/topics/vulnerable-llm) - Index of intentionally vulnerable LLM apps to practice on.
10. [Certified AI/ML Pentester (C-AI/MLPen) Exam - The SecOps Group](https://pentestingexams.com/certifications/professional/certified-ai-ml-pentester/)
