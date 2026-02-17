# Awesome GenAI Security
A curated list of links, references, books, videos, tutorials (Free or Paid), Exploit, CTFs, Hacking Practices, etc., which are related to GenAI, LLM, RAG, MCP, Agents, and Agentic AT security.

![GenAI security banner](awesome-genai-security-banner.png)

## Table of Contents

- [GenAI Security Papers & Standards](#genai-security-papers--standards)
- [Books](#books)
- [Videos](#videos)
- [Online Tutorials / Blogs / Presentations](#online-tutorials--blogs--presentations)
- [Online Courses (Paid/Free)](#online-courses-paidfree)
- [Tools of Trade](#tools-of-trade)
- [Security Practices and CTFs](#security-practices-and-ctfs)
- [GenAI Security Breaches & Incidents](#genai-security-breaches--incidents)
- [Contributors](#contributors)

---

## GenAI Security Papers & Standards
Important papers, standards, and checklists from organizations like OWASP, NIST, and others.

1. [OWASP Top 10 for LLM Application](https://owasp.org/www-project-top-10-for-large-language-model-applications/assets/PDF/OWASP-Top-10-for-LLMs-2023-v1_1.pdf)
2. [OWASP LLM AI Security and Governance Checklist](https://owasp.org/www-project-top-10-for-large-language-model-applications/llm-top-10-governance-doc/LLM_AI_Security_and_Governance_Checklist.pdf)
3. [OWASP Agentic AI Top 10](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/)
4. [NIST AI RMF Playbook](https://airc.nist.gov/AI_RMF_Knowledge_Base/Playbook)
5. [NIST AI Risk Management Framework (AI RMF)](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf)
6. [NIST Adversarial Machine Learning](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-2e2023.pdf)
7. [Microsoft Failure Models in Machine Learning](https://securityandtechnology.org/wp-content/uploads/2020/07/failure_modes_in_machine_learning.pdf)
8. [Microsoft Threat Modeling AI/ML](https://learn.microsoft.com/en-us/security/engineering/threat-modeling-aiml)
9. [OWASP GenAI Security Project](https://genai.owasp.org/)

## Books
1. [AI Value Creators](https://www.flipkart.com/ai-value-creators/p/itm84255392ef02e)
2. [AI Engineering by Chip Huyen](https://www.flipkart.com/ai-engineering-building-applications-foundation-models-full-colour-edition-model-handbook-practical-guide/p/itm0b5326225ef19)
3. [Designing Machine Learning Systems](https://www.flipkart.com/designing-machine-learning-systems/p/itm075f3337b432e)
4. [Hands-On Large Language Models](https://www.flipkart.com/hands-on-large-language-models-understanding-generation/p/itm07bb6ede2a7b0)
5. [Nexus by Yuval Noah Harari](https://www.flipkart.com/nexus/p/itm41a4d83d2cf64)
6. [The Developer's Playbook for Large Language Model Security: Building Secure AI Applications by Steve Wilson](https://www.flipkart.com/developer-s-playbook-large-language-model-security/p/itm2633a103cffb8)

## Videos
1. [Intro to LLM Security - WhyLabs](https://www.youtube.com/watch?v=dj1H4g4YSlU)

## Online Tutorials / Blogs / Presentations
Articles and guides covering LLM, RAG, and general GenAI security.

1. [LLM Security](https://llmsecurity.net/)
2. [What are foundational models?](https://www.datacamp.com/blog/what-are-foundation-models)
3. [A quick check on the AI Threat Model](https://plot4.ai/assessments/quick-check)
4. [Security Incident Response using LLM](https://engineering.mercari.com/en/blog/entry/20241206-streamlining-security-incident-response-with-automation-and-large-language-models/)
5. [OWASP: CheatSheet – A Practical Guide for Securely Using Third-Party MCP Servers 1.0](https://genai.owasp.org/resource/cheatsheet-a-practical-guide-for-securely-using-third-party-mcp-servers-1-0/)

### RAG Security
1. [Riding the RAG Trail: Access, Permissions and Context](https://www.lasso.security/blog/riding-the-rag-trail-access-permissions-and-context)
2. [Securing Risks with RAG Architectures](https://ironcorelabs.com/security-risks-rag/)
3. [Secure your RAG](https://ironcorelabs.com/security-risks-rag/)
4. [Mitigating Security Risks in Retrieval Augmented Generation (RAG)](https://cloudsecurityalliance.org/blog/2023/11/22/mitigating-security-risks-in-retrieval-augmented-generation-rag-llm-applications#)
5. [RAG: The Essential Guide](https://www.nightfall.ai/ai-security-101/retrieval-augmented-generation-rag)
6. [Why RAG is revolutionising GenAI](https://www.immuta.com/guides/data-security-101/retrieval-augmented-generation-rag/)

### LLM Attacks
1. [Web LLM attacks - PortSwigger](https://portswigger.net/web-security/llm-attacks)
2. [Prompt injection jailbreaking](https://ogre51.medium.com/security-of-llm-apps-prompt-injection-jailbreaking-fb9fc5c883a8)

## Online Courses (Paid/Free)
1. [Stanford CS-324: Large Language Models](https://stanford-cs324.github.io/winter2022/)
2. [Princeton COS 597G: Understanding Large Language Models](https://www.cs.princeton.edu/courses/archive/fall22/cos597G/)
3. [Coursera: GenAI with LLM](https://www.coursera.org/learn/generative-ai-with-llms#modules)
4. [Coursera: Generative AI Engineering with LLMs Specialization](https://www.coursera.org/specializations/generative-ai-engineering-with-llms#courses)
5. [Coursera: Generative AI for Cybersecurity Professionals (IBM)](https://www.coursera.org/specializations/generative-ai-for-cybersecurity-professionals)
6. [Coursera: AI for Cybersecurity (JHU)](https://www.coursera.org/specializations/ai-for-cybersecurity)
7. [AttackIQ: The foundation of AI Security](https://www.academy.attackiq.com/courses/foundations-of-ai-security)

## Tools of Trade
Tools for defending, scanning, and auditing GenAI systems.

### Defensive / Scanning
1. [LLM Guard](https://github.com/protectai/llm-guard) - Information extraction and security for LLMs.
2. [Model Scan](https://github.com/protectai/modelscan) - Scanning models for serialization attacks.
3. [Rebuff](https://github.com/protectai/rebuff) - Prompt injection detection.
4. [NB Defense](https://github.com/protectai/nbdefense) - Notebook security.
5. [Protect AI's OSS Portfolio](https://github.com/protectai)
6. [LLM Guard Playground](https://huggingface.co/spaces/protectai/llm-guard-playground)

### Offensive / Exploitation
1. [AI/ML Exploits](https://github.com/protectai/ai-exploits)

## Security Practices and CTFs
Practice your skills with these vulnerable applications and challenges.

1. [Gandalf - Lakera AI](https://gandalf.lakera.ai/) - LLM security challenge.
2. [Prompt Airlines](https://promptairlines.com/) - AI security challenges, CTF style.
3. [Certified AI/ML Pentester Exam](https://secops.group/product/certified-ai-ml-pentester/)
4. [Damn Vulnerable MCP Server](https://github.com/harishsg993010/damn-vulnerable-MCP-server) - Deliberately vulnerable MCP implementation.
5. [Vulnerable MCP Servers Lab](https://github.com/appsecco/vulnerable-mcp-servers-lab) - Collection of vulnerable servers.
6. [FinBot Agentic AI CTF](https://genai.owasp.org/resource/finbot-agentic-ai-capture-the-flag-ctf-application/) - Agentic Security CTF.
7. [OWASP WrongSecrets LLM exercise](https://wrongsecrets.herokuapp.com/challenge/32)
8. [Huntr.com](https://huntr.com/) - World’s first bug bounty platform for AI/ML.

## GenAI Security Breaches & Incidents
*Coming soon.*

## Contributors
*   [Sanjeev Jaiswal](https://github.com/jassics)
