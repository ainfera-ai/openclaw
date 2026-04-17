# OpenClaw

**Status: Design · Alpha arriving Q3 2026**

OpenClaw is the Ainfera-native agent framework. It is optimized for
MCP-first tool use, A2A-first agent-to-agent communication, and
Ainfera's trust-scoring + metered billing SDK.

OpenClaw is not yet released. This repo contains the early design
spec. The framework will be available as `pip install openclaw` in
Q3 2026. In the meantime, Ainfera works with every major agent
framework via the Ainfera SDK — see
[ainfera-ai/sdk-python](https://github.com/ainfera-ai/sdk-python).

## Why OpenClaw?

Existing frameworks (LangChain, CrewAI, AutoGen, LlamaIndex) optimize
for rapid prototyping. OpenClaw optimizes for three things those
frameworks deprioritize:

1. **MCP-first**: tools defined as MCP servers by default, not as
   framework-specific adapters.
2. **A2A-first**: agents as peers with verifiable identities, not as
   monoliths with embedded tools.
3. **Trust-scored by default**: every invocation is ATS-scored,
   sandboxed, and metered — no opt-in, no configuration.

## Design principles

- Zero-config trust, sandboxing, and metering via Ainfera SDK
- W3C DID-based agent identity out of the box
- Cedar + OPA policy engine for inter-agent authorization (Q4 2026)
- Claude-first tool ergonomics (MCP, Anthropic SDK primary adapter)

## Roadmap

- Q2 2026 — spec draft (this repo)
- Q3 2026 — v0.1 alpha, single-agent use cases
- Q4 2026 — v0.2 alpha, multi-agent A2A + policy engine
- Q1 2027 — v0.5 beta, framework adapter layer for migration from
  LangChain / CrewAI

## License

Apache 2.0 — see [LICENSE](./LICENSE).

## Contact

Maintainer: Hizrian Raz, founder, Ainfera Pte. Ltd.
Website: https://ainfera.ai
