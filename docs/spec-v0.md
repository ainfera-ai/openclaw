# OpenClaw Spec v0 (draft, Q2 2026)

This is an early sketch. Not implementation guidance.

## Agent definition

An OpenClaw agent is defined by:
- A W3C DID (`did:ainfera:agent:{uuid}`) as canonical identity
- An MCP server describing its tools
- An A2A agent card describing its capabilities to peers
- An Ainfera SDK hook for trust scoring and metered billing

## Minimal agent

```python
from openclaw import Agent
from openclaw.tools import mcp_tool

@mcp_tool
def search_papers(query: str) -> list[dict]:
    ...

agent = Agent(
    name="research-assistant",
    tools=[search_papers],
    did="did:ainfera:agent:auto",  # SDK generates
)

agent.serve()  # exposes MCP server + A2A card
```

## Open questions

- How does OpenClaw handle long-running tasks? (streaming, checkpointing)
- How do we migrate LangChain agents? (adapter layer, shim package)
- What's the policy engine story for multi-tenant scenarios?
