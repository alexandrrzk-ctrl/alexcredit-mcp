# Distribution log — AlexCredit MCP server

Server: `https://alexcredit.kz/api/mcp` · registry name `kz.alexcredit/catalog` · metadata: [mcp-listing.md](mcp-listing.md)

| Catalog | Date | Status | Listing URL | Notes |
|---|---|---|---|---|
| GitHub showcase repo | 2026-09-07 | done | https://github.com/alexandrrzk-ctrl/alexcredit-mcp | README, tools, install, terms, MIT for docs |
| Official MCP Registry (registry.modelcontextprotocol.io) | 2026-09-07 | live | https://registry.modelcontextprotocol.io/v0/servers?search=alexcredit | `kz.alexcredit/catalog` v1.0.0, status active; namespace verified via DNS TXT `v=MCPv1; k=ed25519; p=…` on alexcredit.kz; published with mcp-publisher (`login dns`). Future schema changes → bump `version` in server.json and publish again |
| awesome-mcp-servers (punkpeye) | 2026-09-07 | branch ready | https://github.com/alexandrrzk-ctrl/awesome-mcp-servers/tree/add-alexcredit-catalog | entry at the end of Finance & Fintech; PR is opened only after the Glama listing exists — the list's bot requires a Glama quality badge |
| Smithery | 2026-09-07 | live | https://smithery.ai/server/alexandr-rzk/alexcredit-catalog | published via CLI as `alexandr-rzk/alexcredit-catalog`, 7 tools detected; display name, description and icon must be filled in the Smithery web UI (see manual-submissions.md) |
| Glama (auto-index from registry) | — | wait 24h | — | check glama.ai/mcp/servers, then claim as owner |
| PulseMCP | — | manual | — | submit form, then claim auto-listing if it appears first |
| mcp.so | — | manual | — | submit form or GitHub issue |
| mcpservers.org | — | manual (tier 2) | — | check auto-listing first |
| LobeHub MCP | — | manual (tier 2) | — | check auto-listing first |
| cursor.directory/mcp | — | manual (tier 2) | — | check auto-listing first |
| mcpmarket | — | manual (tier 2) | — | check auto-listing first |
| Anthropic Claude connectors directory | — | to review | — | if OAuth is mandatory → record refusal (no fake auth) |
| llms.txt catalogs (llmstxthub.com, llmstxt.site, llmsdirectory.com, llmtxt.app, directory.llmstxt.cloud) | — | manual | — | paste texts in manual-submissions.md; skip dead sites |

First monthly check: **2026-10-07** — /api/mcp access log by User-Agent, PulseMCP visitor counter, liveness of every listing above.
