# AgentAvow

The `agentavow` MCP server checks the tools an agent connects to. It covers GitHub repos, live MCP servers, and npm, PyPI, crates, Docker Hub and Hugging Face packages. Every result leads with one of three answers and its reason: Safe to connect, Review before you connect, or Do not connect. Some results add "Certified". Under the answer sit a signed 0-100 trust score and an adoption score. Every result links to a full report and a signed (Ed25519/JWS) attestation that anyone can recompute offline. All tools are read-only and need no account.

When the user asks whether a tool, package, MCP server or repo is safe, or says they are about to install or connect one, run the matching scan:

- `scan_mcp_server`: a live MCP server, by its https URL
- `scan_package`: a published package (registry and name)
- `scan_repo`: a GitHub repo, as `owner/name`

Lead your answer with the result's answer and its reason. Then give the trust score, the adoption score and the top finding.

Do not send localhost or private-network URLs, private repos, or any URL that carries a key or token. Say they were not scanned. The user's own instructions take priority. If they say to skip a scan, skip it.
