← [Back to main list](README.md)

# AI Harness, Runtime & Loop Engineering Security

The execution layer *around* the model: tool-calling loops, sandboxing, runtime guardrail enforcement, and supply-chain risk in the harness that drives the LLM (coding agents, autonomous CLIs, IDE extensions). Newer, less-standardized naming than LLM/RAG/MCP/Agents — most current material lives in incident writeups and a handful of new open-source harness-hardening tools rather than formal standards.

## Table of Contents
- [Tools](#tools)
- [Attacks, Breaches & Incidents](#attacks-breaches--incidents)
- [Practice](#practice)

## Tools
1. [HOL Guard](https://github.com/hashgraph-online/hol-guard) - Local-first security harness that intercepts tool calls in AI coding agents before files change or network is contacted. Scans skills, MCP servers, and plugins for supply-chain threats.
2. [Koma](https://github.com/swnotmetal/Project-Koma) - Zero-dependency Node.js/TypeScript security primitives for AI applications, including prompt-injection defense and protected data-access patterns in the tool-call loop.
3. [ToolHive (StacklokLabs)](https://github.com/StacklokLabs/toolhive) - Runs the tools an agent calls (via MCP) in locked-down containers with secrets management and network isolation — a runtime sandboxing layer for the harness.
4. [PyRIT - Python Risk Identification Toolkit for GenAI (Microsoft)](https://github.com/Azure/PyRIT) - Automates multi-turn attack loops against a target harness, useful for testing your own agent's runtime defenses.

## Attacks, Breaches & Incidents
Harness-level failures — where the loop driving tool calls, not the model itself, is the exploited weakness:

1. [Cursor Terminal Allowlist Bypass (CVE-2026-22708, Jul 2026)](https://github.com/cursor/cursor/security/advisories/GHSA-82wg-qcm4-fp2w) - Shell built-ins like `export` bypassed Cursor's Auto-Run allowlist in the tool-call loop, letting indirect prompt injection reach zero-click RCE.
2. [JADEPUFFER: First Documented Agentic Ransomware (Jul 2026)](https://www.sysdig.com/blog/jadepuffer-agentic-ransomware-for-automated-database-extortion) - The agent's own recovery loop rewrote its payload after a failed login and continued autonomously — a harness/loop-level failure, not a single bad prompt.
3. [Check Point Researchers Expose Critical Claude Code Flaws](https://blog.checkpoint.com/research/check-point-researchers-expose-critical-claude-code-flaws/) - CVE-2025-59536 and CVE-2026-21852: RCE and API-key theft via the coding-agent harness.
4. [Anthropic: "Vibe-Hacking" Extortion Using Claude Code (Aug 2025)](https://www.anthropic.com/news/detecting-countering-misuse-aug-2025) - Automated an intrusion-and-extortion loop against 17+ organizations using an agentic coding harness.
5. [Amazon Q VS Code Extension Compromised with Data-Wiping Prompt (Jul 2025)](https://www.bleepingcomputer.com/news/security/amazon-ai-coding-agent-hacked-to-inject-data-wiping-commands/) - A malicious prompt injected into the IDE-extension harness caused destructive tool calls.

See also [GenAI Security Attacks, Breaches & Incidents](README.md#genai-security-attacks-breaches--incidents) for the full cross-category incident timeline.

## Practice
No dedicated CTF or lab exists yet purpose-built for harness/loop-level exploitation (as opposed to prompt-level or MCP-protocol-level). The closest hands-on practice today is:

1. [Microsoft AI Red Teaming Playground Labs](https://github.com/microsoft/AI-Red-Teaming-Playground-Labs) - Docker/Kubernetes-deployed challenges that exercise the tool-call loop, not just the prompt.

If you know of a harness/loop-engineering-specific lab, tool, or paper, please open a PR — see [CONTRIBUTING.md](CONTRIBUTING.md).
