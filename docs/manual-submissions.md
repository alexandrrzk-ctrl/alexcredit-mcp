# Manual submissions — copy-paste texts

All values come from [mcp-listing.md](mcp-listing.md). Copy exactly; do not rephrase. After each submission add a row to [distribution-log.md](distribution-log.md).

## Common fields (use everywhere)

- **Name:** AlexCredit — Kazakhstan Microfinance Catalog
- **Slug / short name:** alexcredit-catalog
- **Endpoint (remote, Streamable HTTP):** https://alexcredit.kz/api/mcp
- **Authentication:** none
- **Repository:** https://github.com/alexandrrzk-ctrl/alexcredit-mcp
- **Website:** https://alexcredit.kz
- **Server card:** https://alexcredit.kz/.well-known/mcp/server-card.json
- **Category:** Finance (fallbacks: Data, Search)
- **Tags:** mcp, finance, microfinance, kazakhstan, loans, catalog, read-only, remote
- **Icon:** `assets/icon-512.png` from the repository
- **Contact:** admin@alexcredit.kz
- **Short description (≤160 chars):** Read-only MCP server for the catalog of licensed Kazakhstan microfinance organizations: microloan terms, ARDFM licenses, ratings and reviews.
- **Long description:** Public read-only MCP server exposing the catalog of licensed microfinance organizations (MFOs) of Kazakhstan from alexcredit.kz. Seven tools return microloan terms for new and repeat clients, effective annual rate, legal data (BIN, ARDFM license and a direct link to the regulator's license register), borrower ratings and reviews, catalog selections and the legal context of microlending in Kazakhstan. Every entity carries a canonical_url; attribution to alexcredit.kz is required. No API keys, no OAuth, no mutation tools.
- **Install snippet (generic JSON):**
  ```json
  {"mcpServers":{"alexcredit-catalog":{"type":"streamable-http","url":"https://alexcredit.kz/api/mcp"}}}
  ```

## Smithery — https://smithery.ai/server/alexandr-rzk/alexcredit-catalog (edit listing)

The server is already published from the CLI. Log in as the owner and fill in the listing:

- Display name: AlexCredit — Kazakhstan Microfinance Catalog
- Description: *Long description* above
- Icon: `assets/icon-512.png`
- Homepage: https://alexcredit.kz · Repository: https://github.com/alexandrrzk-ctrl/alexcredit-mcp

## PulseMCP — https://www.pulsemcp.com (Submit)

- Server name: AlexCredit — Kazakhstan Microfinance Catalog
- URL / repo: https://github.com/alexandrrzk-ctrl/alexcredit-mcp
- Remote endpoint: https://alexcredit.kz/api/mcp
- Description: *Long description* above
- Category: Finance
- If the listing already exists (auto-indexed from the official registry): do **not** submit again — claim it as verified owner.

## mcp.so — https://mcp.so (Submit button or GitHub issue)

- Name: AlexCredit — Kazakhstan Microfinance Catalog
- Type: remote / hosted (Streamable HTTP)
- Server URL: https://alexcredit.kz/api/mcp
- GitHub: https://github.com/alexandrrzk-ctrl/alexcredit-mcp
- Description: *Short description*, then *Long description*
- Tags: finance, microfinance, kazakhstan, loans, catalog

## mcpservers.org

- Name, repo, endpoint, category Finance, *Short description*.

## LobeHub MCP marketplace

- Name, repo URL, *Long description*, tags; connection type: Streamable HTTP, URL https://alexcredit.kz/api/mcp, no auth.

## cursor.directory/mcp

- Name, repo URL, *Short description*, install snippet above.

## mcpmarket

- Name, repo URL, endpoint, category Finance, *Long description*.

## Glama — https://glama.ai/mcp/servers

- Do not submit manually. The server is auto-indexed from the official registry within ~24 h of publishing. Then open the listing and **claim** it (verified owner) with the GitHub account alexandrrzk-ctrl.

## Anthropic Claude connectors directory

- Read the current requirements for remote connectors first. If OAuth is mandatory, do not build a fake login — record "not eligible (OAuth required)" in distribution-log.md.

## llms.txt catalogs (llmstxthub.com, llmstxt.site, llmsdirectory.com, llmtxt.app, directory.llmstxt.cloud)

- Site name: AlexCredit
- Website: https://alexcredit.kz
- llms.txt: https://alexcredit.kz/llms.txt
- llms-full.txt: https://alexcredit.kz/llms-full.txt
- Description: Catalog and rating of licensed microfinance organizations of Kazakhstan (ARDFM register): microloan terms, legal data, borrower reviews. Russian-language.
- Category: Finance
- Skip any catalog that is closed or dead; note it in the log.
