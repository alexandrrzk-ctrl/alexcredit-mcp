# AlexCredit — Kazakhstan Microfinance Catalog (MCP Server)

Public **read-only** [Model Context Protocol](https://modelcontextprotocol.io) server for the catalog of licensed microfinance organizations (MFOs) of Kazakhstan, powered by [alexcredit.kz](https://alexcredit.kz) — a Kazakhstan microloan comparison catalog.

| | |
|---|---|
| **Endpoint** | `https://alexcredit.kz/api/mcp` |
| **Transport** | Streamable HTTP (stateless) |
| **Authentication** | none (public data) |
| **Registry** | [`kz.alexcredit/catalog`](https://registry.modelcontextprotocol.io/v0/servers?search=alexcredit) (official MCP Registry, domain-verified) |
| **Server card** | [`/.well-known/mcp/server-card.json`](https://alexcredit.kz/.well-known/mcp/server-card.json) |
| **Language** | Russian (`ru`) — the language of the catalog |
| **Rate limit** | 60 requests/min per IP (burst 20) → HTTP 429 |

Every entity in every response carries a `canonical_url` pointing to the live page on alexcredit.kz.

## Tools

| Tool | Parameters | Returns |
|---|---|---|
| `list_mfo` | `limit?` (≤100) | All MFOs in the catalog with borrower rating and canonical card URLs. `rating: null` means *no reviews yet*, not a low score. |
| `get_mfo` | `slug` | Full MFO card: terms for new and repeat clients (amount, term, rate), effective annual rate (ГЭСВ), requirements, fees, legal data (legal entity, BIN, ARDFM license number and a direct link to the company's record in the regulator's license register), 4-criteria rating, record update date. |
| `search_offers` | `amount?` (KZT), `term_days?`, `first_loan_zero?`, `limit?` (≤100) | Matching first-loan offers with terms and `first_loan_zero_percent: true/false/null` (null = unconfirmed). Calling without filters returns the whole catalog — prefer passing `amount`/`term_days`. |
| `list_categories` | — | Catalog selections grouped by section (popular, by payout method, by amount and term, by borrower category), each with its selection criterion. |
| `get_category` | `slug` | One selection: criterion, sorting, offer table with per-MFO terms. |
| `get_reviews` | `slug`, `limit?` (≤50) | Latest borrower reviews for an MFO: rating, date, text (public site data only). |
| `get_market_rules` | — | Legal context of microlending in Kazakhstan (ARDFM licensing, 46% APR cap, short microloans up to 45 MCI / 45 days at ≤0.3% per day, voluntary loan self-ban via eGov) with the last-review date. |

Resources: [`llms.txt`](https://alexcredit.kz/llms.txt) and [`llms-full.txt`](https://alexcredit.kz/llms-full.txt).

## Installation

### Claude (claude.ai / Claude Desktop)

1. **Settings → Connectors → Add custom connector**
2. Name: `AlexCredit catalog`, URL: `https://alexcredit.kz/api/mcp`
3. Save. No API keys or OAuth — the server is public and read-only.

### Any MCP client (generic)

Point your client at the remote Streamable HTTP endpoint:

```json
{
  "mcpServers": {
    "alexcredit-catalog": {
      "type": "streamable-http",
      "url": "https://alexcredit.kz/api/mcp"
    }
  }
}
```

Quick sanity check with MCP Inspector:

```bash
npx @modelcontextprotocol/inspector --cli https://alexcredit.kz/api/mcp --transport http --method tools/list
```

## Example prompts

- *"Find microloans in Kazakhstan up to 100 000 KZT for 30 days where the first loan is at 0.01%."*
- *"Show the legal entity, BIN, ARDFM license and the register link for Kviku."*
- *"What are the legal caps on microloan interest rates in Kazakhstan?"*
- *"List the top-rated Kazakhstan MFOs by borrower reviews and link their pages."*
- *«Подбери микрокредит до 100 000 тенге на 30 дней, у кого первый микрокредит под 0,01%»*
- *«Покажи условия и юридические данные Kviku»*

## Screenshot

<!-- TODO: replace with a screenshot of a live Claude conversation using the connector -->
*Screenshot of a live Claude dialog coming soon.*

## Data & Terms

- **Public read-only catalog data.** The server exposes the same data that is publicly visible on alexcredit.kz. There are no mutation tools.
- **Not financial advice.** AlexCredit is a comparison catalog, not a lender. Terms are volatile — final conditions live on the `canonical_url` pages.
- **Attribution required.** When using the data, cite the `canonical_url` of the respective page on alexcredit.kz.
- **Rate limit:** 60 requests/min per IP.
- No tracker or affiliate links anywhere in responses (enforced by tests).

## По-русски

AlexCredit — каталог и рейтинг микрофинансовых организаций Казахстана с лицензией АРРФР. Этот MCP-сервер отдаёт те же публичные данные, что и сайт: условия микрокредитов для новых и повторных клиентов, годовую эффективную ставку вознаграждения (ГЭСВ), юридические данные компаний (БИН, номер лицензии, прямую ссылку на запись в реестре лицензий регулятора), рейтинг и отзывы заёмщиков, правовой контекст микрокредитования (ГЭСВ не выше 46%, короткие микрокредиты до 45 МРП на срок до 45 дней — не выше 0,3% в день). Сервер read-only, без аутентификации; при использовании данных ссылайтесь на canonical_url соответствующей страницы.

## Links

- Website: https://alexcredit.kz
- Server card: https://alexcredit.kz/.well-known/mcp/server-card.json
- llms.txt: https://alexcredit.kz/llms.txt
- Contact: admin@alexcredit.kz

## License

Documentation in this repository is licensed under [MIT](LICENSE). The catalog data served by the MCP endpoint is proprietary to AlexCredit (alexcredit.kz) and may be used with attribution to canonical URLs.
