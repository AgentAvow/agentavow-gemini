# AgentAvow for Gemini CLI

Adds the AgentAvow connector to Gemini CLI. Ask whether a tool is safe before you connect it, for example "Is the npm package left-pad safe?" or "Should I add the DeepWiki MCP server?" Gemini scans it with AgentAvow and answers Safe to connect, Review before you connect, or Do not connect, with the reason. Under the answer you get a signed 0-100 trust score that anyone can recompute offline, an adoption score, and the findings behind them.

## Install

    gemini extensions install https://github.com/AgentAvow/agentavow-gemini

## What it adds

- The remote MCP server `https://agentavow.com/mcp` (streamable HTTP; read-only tools; no account or key)
- Tools: `scan_repo`, `scan_package`, `scan_mcp_server`, `verify_trust`, `check_interaction_safety`, `lookup_identity`, `get_trust_badge`, `about_agentavow`
- A short `GEMINI.md` telling Gemini when to scan and how to read a result

What it scans: GitHub repos (`owner/name`), live MCP servers by https URL, and packages on npm, PyPI, crates, Docker Hub and Hugging Face. Only the URL or name you ask about is sent to agentavow.com.

## Links

- Reports and offline verification: https://agentavow.com
- Connector docs: https://agentavow.com/docs/mcp-connector
- Privacy: https://agentavow.com/legal/privacy
- Issues: https://github.com/AgentAvow/AgentAvow/issues

MIT licensed. Also on npm and PyPI as `agentavow-trust`, and as a Claude Code plugin.
