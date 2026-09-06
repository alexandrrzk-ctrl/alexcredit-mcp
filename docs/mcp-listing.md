# Metadata pack — single source of naming for every catalog submission

Use these values verbatim in every form. Do not invent alternative names or descriptions.

| Field | Value |
|---|---|
| **Name** | AlexCredit — Kazakhstan Microfinance Catalog |
| **Short name / slug** | `alexcredit-catalog` |
| **Registry name** | `kz.alexcredit/catalog` |
| **One-liner** | Read-only MCP server for the catalog of licensed Kazakhstan microfinance organizations: microloan terms, ARDFM licenses, ratings and reviews. |
| **Description (EN)** | Public read-only MCP server exposing the catalog of licensed microfinance organizations (MFOs) of Kazakhstan from alexcredit.kz. Seven tools return microloan terms for new and repeat clients, effective annual rate, legal data (BIN, ARDFM license and a direct link to the regulator's license register), borrower ratings and reviews, catalog selections and the legal context of microlending in Kazakhstan. Every entity carries a canonical_url; attribution to alexcredit.kz is required. |
| **Categories** | finance, data, search |
| **Tags** | mcp, finance, microfinance, kazakhstan, loans, catalog, read-only, remote, streamable-http |
| **Transport** | Streamable HTTP (remote), stateless |
| **Authentication** | none |
| **Tool count** | 7 (`list_mfo`, `get_mfo`, `search_offers`, `list_categories`, `get_category`, `get_reviews`, `get_market_rules`) |
| **Endpoint** | https://alexcredit.kz/api/mcp |
| **Server card** | https://alexcredit.kz/.well-known/mcp/server-card.json |
| **Repository** | https://github.com/alexandrrzk-ctrl/alexcredit-mcp |
| **Website** | https://alexcredit.kz |
| **Documentation** | https://github.com/alexandrrzk-ctrl/alexcredit-mcp#readme |
| **Icon 512×512** | `assets/icon-512.png` (orange circle with ₸) |
| **License** | Docs: MIT. Data: proprietary, attribution to canonical URLs required. |
| **Rate limit** | 60 requests/min per IP |
| **Contact** | admin@alexcredit.kz |
| **Language of data** | Russian |
