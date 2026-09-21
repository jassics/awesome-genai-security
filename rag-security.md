← [Back to main list](README.md)

# RAG Security

Retrieval pipeline risk: vector-DB access control, embedding/index poisoning, and permission bleed through retrieved context.

## Table of Contents
- [Papers & Articles](#papers--articles)
- [Attacks & Incidents](#attacks--incidents)
- [Practice](#practice)

## Papers & Articles
1. [Riding the RAG Trail: Access, Permissions and Context](https://www.lasso.security/blog/riding-the-rag-trail-access-permissions-and-context)
2. [Securing Risks with RAG Architectures](https://ironcorelabs.com/security-risks-rag/)
3. [Mitigating Security Risks in Retrieval Augmented Generation (RAG)](https://cloudsecurityalliance.org/blog/2023/11/22/mitigating-security-risks-in-retrieval-augmented-generation-rag-llm-applications#)
4. [RAG: The Essential Guide](https://www.nightfall.ai/ai-security-101/retrieval-augmented-generation-rag)
5. [RAG Explained: Retrieval Augmented Generation in AI (video)](https://youtu.be/97OwDxvWie8)

## Attacks & Incidents
1. [EchoLeak (CVE-2025-32711): Zero-Click Data Theft in Microsoft 365 Copilot (Jun 2025)](https://checkmarx.com/zero-post/echoleak-cve-2025-32711-show-us-that-ai-security-is-challenging/) - A single crafted email silently exfiltrated organizational data via Copilot's retrieval/grounding pipeline with no user interaction.

See also [GenAI Security Attacks, Breaches & Incidents](README.md#genai-security-attacks-breaches--incidents) for the full cross-category incident timeline.

## Practice
1. [PromptTrace](https://prompttrace.airedlab.com) - Free hands-on labs including a RAG-poisoning gauntlet against real LLMs.

RAG-specific tooling is limited today; most defenses live in the [LLM Security guardrails/tools](llm-security.md#tools) and standard data-access-control practice. Contributions welcome — see [CONTRIBUTING.md](CONTRIBUTING.md).
