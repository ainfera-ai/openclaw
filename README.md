<div align="center">
  <h1>OpenClaw</h1>
  <p><strong>The Ainfera-native agent framework. MCP-first. A2A-first. Trust-scored by default.</strong></p>
  <p>
    <a href="https://ainfera.ai">Ainfera</a> ·
    <a href="https://api.ainfera.ai/docs">API docs</a> ·
    <a href="./docs/spec-v0.md">Spec v0</a>
  </p>
</div>

---

**Status: Design · Alpha arriving Q3 2026**

OpenClaw is the Ainfera-native agent framework. It is optimized for:

1. **MCP-first** — tools defined as [Model Context Protocol](https://modelcontextprotocol.io)
   servers by default, not as framework-specific adapters.
2. **A2A-first** — agents as peers with verifiable W3C DID identities,
   not monoliths with embedded tools.
3. **Trust-scored by default** — every invocation is ATS-scored,
   sandboxed, and metered via the Ainfera SDK. No opt-in, no configuration.
4. **Claude-first ergonomics** — MCP and the Anthropic SDK are the
   primary adapters. Other model providers via adapter layer in Q4 2026.

## This repo

This is the **design repository**. It contains:

- Early design spec ([docs/spec-v0.md](./docs/spec-v0.md))
- Roadmap and principles
- Public comment surface (open an Issue to discuss)

OpenClaw is **not yet released**. The framework will be available as
`pip install openclaw` in Q3 2026.

In the meantime, Ainfera's trust scoring, sandboxing, and metered billing
work with every major agent framework via the Ainfera SDK:

- [`ainfera`](https://github.com/ainfera-ai/cli) — CLI (`pip install ainfera`)
- [`ainfera-sdk`](https://github.com/ainfera-ai/sdk-python) — Python SDK (`pip install ainfera-sdk`)

## Why OpenClaw?

Existing frameworks (LangChain, CrewAI, AutoGen, LlamaIndex) optimize
for rapid prototyping of agentic workflows. They are excellent for
that. OpenClaw optimizes for three things those frameworks deprioritize:

| OpenClaw priority | What others do |
|---|---|
| **MCP as the default tool protocol** | Framework-specific tool decorators |
| **A2A agent cards at `/.well-known/agent-card.json`** | Agents as libraries, not peers |
| **ATS trust score embedded per invocation** | Trust as optional instrumentation |
| **Sandboxing + kill switch by default** | Execution isolation as afterthought |

## Design principles

### 1. Zero-config trust, sandboxing, and metering

Every agent gets:
- W3C DID identity (`did:ainfera:agent:{uuid}`) on registration
- MCP server exposing its tools at `/mcp/{agent-name}`
- A2A agent card at `/.well-known/agent-card.json`
- Automatic ATS trust scoring from execution telemetry
- Redis-flagged kill switch, checked every 100ms (sub-500ms SLA)

No environment variables. No configuration files. Working defaults.

### 2. MCP is the tool protocol

Tools are defined as MCP servers, not as framework-specific classes.
A tool authored for one OpenClaw agent runs in Claude Desktop, Cursor,
the Ainfera marketplace, or any MCP client — unchanged.

### 3. A2A is the agent protocol

Agent-to-agent communication happens over the
[Agent2Agent (A2A)](https://a2aproject.github.io/) protocol, not over
framework-specific calling conventions. Agents can discover, authenticate,
and invoke each other regardless of framework.

### 4. Claude-first, not Claude-only

The primary adapter layer targets Anthropic's SDK and MCP. Adapter layers
for OpenAI, Google, NIM, and open-weight models (via Hugging Face) arrive
in Q4 2026.

## Roadmap

| Quarter | Milestone |
|---|---|
| Q2 2026 | Spec v0 (this repo) · community comment window |
| Q3 2026 | v0.1 alpha · single-agent use cases · Ainfera SDK integration |
| Q4 2026 | v0.2 alpha · A2A multi-agent · Cedar + OPA policy engine · OpenAI/NIM adapters |
| Q1 2027 | v0.5 beta · LangChain/CrewAI migration shim package |
| Q2 2027 | v1.0 stable |

## Roadmap (non-goals)

OpenClaw explicitly does **not** aim to be:

- A general-purpose agent framework (use LangChain/CrewAI)
- A model provider abstraction layer (use LiteLLM/OpenRouter)
- A workflow orchestrator (use Temporal/Prefect)
- An observability platform (use LangSmith/W&B)

OpenClaw is narrow on purpose: MCP tools, A2A peers, ATS-scored
execution. That's the whole thing.

## Contributing

The design is open for comment. Please:

1. Read [docs/spec-v0.md](./docs/spec-v0.md)
2. Open an Issue with any of:
   - Critique of design decisions
   - Use cases not covered
   - Protocol conflicts with A2A or MCP
   - Naming suggestions (the name is not final)

Pull requests during the design phase are accepted only for spec
clarifications and typos. Implementation PRs open in Q3 2026.

## Prior art

- [Model Context Protocol (MCP)](https://modelcontextprotocol.io) —
  Anthropic
- [Agent2Agent (A2A)](https://a2aproject.github.io/) — Google (Linux
  Foundation stewardship)
- [W3C Decentralized Identifiers (DIDs)](https://www.w3.org/TR/did-core/)
- [Verifiable Credentials Data Model](https://www.w3.org/TR/vc-data-model/)

## License

Apache 2.0 — see [LICENSE](./LICENSE).

## Maintainer

Hizrian Raz — founder, Ainfera Pte. Ltd.

---

<sub>© 2026 Ainfera Pte. Ltd. · Singapore</sub>
