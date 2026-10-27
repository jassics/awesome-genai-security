← [Back to main list](README.md)

# MCP Security

Model Context Protocol servers/clients: tool poisoning, auth, transport, and credential handling.

## Table of Contents
- [Standards & Specs](#standards--specs)
- [Papers & Articles](#papers--articles)
- [Tools](#tools)
- [Attacks, Breaches & Incidents](#attacks-breaches--incidents)
  - [IDE-Agent MCP Integration Risks](#ide-agent-mcp-integration-risks)
  - [MCP as Supply-Chain Attack Vector](#mcp-as-supply-chain-attack-vector)
- [Practice & CTFs](#practice--ctfs)

## Standards & Specs
1. [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) - Open standard for connecting agents to tools and data.
2. [MCP Official Security Best Practices](https://modelcontextprotocol.io/specification/draft/basic/security_best_practices) - The spec's own guidance on confused deputy, token passthrough, and session hijacking.
3. [OWASP: CheatSheet – A Practical Guide for Securely Using Third-Party MCP Servers 1.0](https://genai.owasp.org/resource/cheatsheet-a-practical-guide-for-securely-using-third-party-mcp-servers-1-0/)
4. [OWASP: A Practical Guide for Secure MCP Server Development](https://genai.owasp.org/resource/a-practical-guide-for-secure-mcp-server-development/) - Companion to the cheatsheet above, covering how to build MCP servers securely.
5. [SlowMist MCP Security Checklist](https://github.com/slowmist/MCP-Security-Checklist) - Practical checklist covering server, client, and transport-level MCP hardening.

## Papers & Articles
1. [Pillar Security: MCP Security Research](https://www.pillar.security/blog/the-security-risks-of-model-context-protocol-mcp)
2. [Tool Poisoning Attacks in MCP](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks)
3. [Jumping the Line: How MCP Servers Can Attack You Before You Ever Use Them](https://blog.trailofbits.com/2025/04/21/jumping-the-line-how-mcp-servers-can-attack-you-before-you-ever-use-them/) - Trail of Bits on line-jumping/tool-definition attacks during MCP handshake.
4. [Insecure Credential Storage Plagues MCP](https://blog.trailofbits.com/2025/04/30/insecure-credential-storage-plagues-mcp/) - Survey of how MCP clients mishandle stored tokens/secrets.
5. [Awesome MCP Security](https://github.com/Puliczek/awesome-mcp-security) - Curated, continuously-updated list of MCP-specific papers, incidents, and tooling if you need to go deeper than this page.
6. [MCP Prompt Injection at Connect: Lab + Fixes](https://webofmike.com/mcp-discovery-prompt-injection/) - Reproducible lab showing a hostile MCP server's `instructions` field (sent at `initialize`/`server/discover`) reaching the agent's system prompt before any tool call, including cross-caller poisoning through a `cacheScope: public` cache, with isolation, size-cap, cache-binding, and pinning controls; cites a registry scan in which 5,462 of 8,235 live servers sent `instructions`.
7. [MCP Tool Poisoning: A Name Allowlist Is Not Enough](https://webofmike.com/mcp-tool-poisoning-pin-definitions/) - Docker demo of a mid-session tool-description rug pull (modeled on the Deadbugz campaign) that a tool-name allowlist passes through, and of pinning a digest of each tool's name, description, and inputSchema to reject it.
8. [Fix MCP OAuth 401 and 403 Errors (Praesidia)](https://praesidia.ai/blog/mcp-oauth-troubleshooting-401-403) - Technical guide with a synthetic loopback HTTP teaching fixture for invalid-token and insufficient-scope responses; not an MCP server, OAuth implementation, or production security test.

## Tools
1. [Invariant Labs: MCP Security Notification Tool (mcp-scan)](https://github.com/invariantlabs-ai/mcp-scan)
2. [Cisco MCP Scanner](https://github.com/cisco-ai-defense/mcp-scanner) - Scans MCP servers/tools for poisoning and prompt injection (YARA + LLM-as-judge).
3. [Snyk Agent Scan](https://github.com/snyk/agent-scan) - Inventories and scans AI agents, MCP servers, and skills for 15+ risks (successor to Invariant mcp-scan).
4. [ToolHive (StacklokLabs)](https://github.com/StacklokLabs/toolhive) - Runs MCP servers in locked-down containers with secrets management and network isolation.
5. [mcp-context-protector (Trail of Bits)](https://github.com/trailofbits/mcp-context-protector) - Security wrapper that validates and sandboxes MCP server responses before they reach the LLM.
6. [HOL Guard](https://github.com/hashgraph-online/hol-guard) - Local-first security harness that intercepts tool calls before files change or network is contacted; scans MCP servers, skills, and plugins for supply-chain threats.

## Attacks, Breaches & Incidents

### IDE-Agent MCP Integration Risks

MCP servers integrated into code editors and coding agents introduce a new attack surface. Recent CVEs:

1. [Cursor Terminal Allowlist Bypass (CVE-2026-22708, Jul 2026, CVSS 9.9)](https://github.com/cursor/cursor/security/advisories/GHSA-82wg-qcm4-fp2w) - Shell built-ins like `export` and `function` bypass Cursor's Auto-Run allowlist, allowing indirect prompt injection to reach zero-click RCE. Implications: MCP tool-use restrictions can be circumvented by abusing language features.
2. [Amazon Q VS Code Extension Compromised (Jul 2025, 964k+ installs)](https://www.bleepingcomputer.com/news/security/amazon-ai-coding-agent-hacked-to-inject-data-wiping-commands/) - Malicious prompt injected into official Microsoft marketplace extension, instructing agent to wipe files and delete AWS resources. Shows supply-chain risk: official channels can be compromised.

**Defense implications:**
- IDE-agents need separate thread & capability model from coding LLMs.
- Tool allowlists must account for shell language features, not just command names.
- Extension/MCP server provenance should be verified (signed manifests, registry pinning).

### MCP as Supply-Chain Attack Vector

MCP registries, skill repositories, and plugin ecosystems are now confirmed attack surface. A single compromised or malicious MCP server can:

- **Exfiltrate secrets** from agent environment variables and memory
- **Execute code** on the client machine (CVE-2025-6514 demonstrated CVSS 9.6 remote RCE)
- **Modify tool behavior** mid-session (Deadbugz campaign: tool-definition rug pull)
- **Poison inter-agent communication** (MCP `instructions` field reaches system prompt before any tool call)

**Real-world examples:**
- CVE-2025-6514 (mcp-remote RCE): Attacker-controlled server executes arbitrary code on client.
- Deadbugz campaign: Hostile MCP server swaps tool definitions after initial connection.
- MCP prompt injection at `initialize`: Server's `instructions` field + `cacheScope: public` reaches agent system prompt, bypassing tool-boundary isolation.

**Mitigations (to implement):**
- **Registry pinning:** SHA256 digest of server manifest in agent config; reject servers not matching.
- **Network isolation:** Run MCP servers in locked-down containers (ToolHive, mcp-context-protector).
- **Tool-definition immutability:** Bind tool name, description, and inputSchema to digest; reject mid-session changes.
- **Allowlist server vendors, not just tool names:** Restrict to known-safe registries (Anthropic, OpenAI, etc.).
- **Inspect `instructions` field:** Validate it doesn't contain system-prompt jailbreak attempts.

### All Incidents

1. [CVE-2025-6514: Critical RCE in mcp-remote (Jul 2025)](https://jfrog.com/blog/2025-6514-critical-mcp-remote-rce-vulnerability/) - A malicious MCP server could achieve full remote code execution (CVSS 9.6) on clients running mcp-remote; the first real-world RCE against an MCP client.

See also [GenAI Security Attacks, Breaches & Incidents](README.md#genai-security-attacks-breaches--incidents) for the full cross-category incident timeline.

## Practice & CTFs
1. [Damn Vulnerable MCP Server](https://github.com/harishsg993010/damn-vulnerable-MCP-server) - Deliberately vulnerable MCP implementation.
2. [Vulnerable MCP Servers Lab](https://github.com/appsecco/vulnerable-mcp-servers-lab) - Collection of vulnerable servers.
