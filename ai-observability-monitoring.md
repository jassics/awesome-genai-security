← [Back to main list](README.md)

# AI Observability, Logging & Monitoring

Cross-cutting runtime visibility: tracing LLM/agent calls, detecting drift and anomalous behavior, and enforcing guardrails as a live control plane — distinct from the design-time attacks covered in the other category pages.

## Table of Contents
- [Papers & Articles](#papers--articles)
- [Tools](#tools)
- [Attacks, Breaches & Incidents](#attacks-breaches--incidents)
- [Practice](#practice)

## Papers & Articles
1. [OWASP GenAI Security Project: LLM Applications Logging and Monitoring Cheat Sheet](https://genai.owasp.org/) - Hub page; check current OWASP GenAI resources for the latest logging/monitoring cheat sheet revision.
2. [NIST AI RMF - Manage Function](https://airc.nist.gov/AI_RMF_Knowledge_Base/Playbook) - Continuous monitoring and incident response guidance for deployed AI systems.
3. [Databricks AI Security Framework (DASF) 2.0](https://www.databricks.com/resources/whitepaper/databricks-ai-security-framework-dasf) - Includes controls for logging, monitoring, and audit trails across the AI system lifecycle.
4. [What is LLM Observability?](https://www.datadoghq.com/knowledge-center/llm-observability/) - Overview of tracing, evals, and drift detection for LLM apps in production.

## Tools
### Tracing & Observability Platforms
1. [Langfuse](https://github.com/langfuse/langfuse) - Open-source LLM observability: tracing, evals, prompt management.
2. [Arize Phoenix](https://github.com/Arize-ai/phoenix) - Open-source LLM tracing, evals, and drift/anomaly detection.
3. [Helicone](https://github.com/Helicone/helicone) - Open-source LLM observability proxy with logging and cost/usage monitoring.
4. [OpenLLMetry (Traceloop)](https://github.com/traceloop/openllmetry) - OpenTelemetry-based instrumentation for LLM app observability.
5. [WhyLabs LangKit](https://github.com/whylabs/langkit) - Text/LLM monitoring toolkit for drift, toxicity, and data quality metrics.

### Runtime Guardrail Enforcement
1. [Lakera Guard](https://www.lakera.ai/) - Real-time detection and blocking of prompt injection and data leakage in production traffic.
2. [NeMo Guardrails (NVIDIA)](https://github.com/NVIDIA/NeMo-Guardrails) - Programmable runtime guardrails with logging hooks for policy violations.
3. [Guardrails AI](https://github.com/guardrails-ai/guardrails) - Input/output validation with structured logging of failed validations.

## Attacks, Breaches & Incidents
See [GenAI Security Attacks, Breaches & Incidents](README.md#genai-security-attacks-breaches--incidents) for the full cross-category incident timeline — several (e.g. DeepSeek's exposed logging database) are fundamentally logging/monitoring failures rather than model-level attacks.

## Practice
This category is tooling-and-practice focused rather than CTF-focused; there's no dedicated observability CTF today. If you know of one, please open a PR (see [CONTRIBUTING.md](CONTRIBUTING.md)).
