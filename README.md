# darioa MCP server

Find a web developer with an AI assistant: the four products of darioa (website, booking site, webshop, web app) with fixed prices, real client work, the right product for a described need, and a contact request to Dario Albers in Enschede, the Netherlands.

Official remote [Model Context Protocol](https://modelcontextprotocol.io) server of **darioa** (https://www.darioa.nl/), a one-person web developer.

| | |
|---|---|
| Endpoint | `https://www.darioa.nl/mcp` |
| Transport | Streamable HTTP (MCP 2026-07-28 and 2025-03-26 to 2025-11-25) |
| Authentication | none |
| Official MCP Registry | `nl.darioa/webdev` |
| Agent-to-agent (A2A) | `https://www.darioa.nl/.well-known/agent-card.json`, `https://www.darioa.nl/a2a` |

## Tools

- **list_products** (read-only): the four products with the one-off price, the yearly price, the first-year total, what is included, when you pay and what every yearly price includes. EUR, excluding 21% Dutch VAT.
- **list_work** (read-only): the real client sites darioa built (tyre shop webshop, two chauffeur booking sites, bike rental, restaurant, till system with a scale), what was built, the product, the live site and the case study.
- **get_quote** (read-only): maps a described need (Dutch or English) or a feature list to one product and its price. Unclear needs get questions instead of a guess; anything outside the four products (for example an App Store app) gets no price. Prices come only from the public price list. An indication, not a binding offer.
- **request_contact**: starts a contact request for the user, only after the user has seen what will be sent and agreed (`userConfirmed: true`). Nothing reaches Dario yet: the user first gets an email from darioa with a confirm button, and only their click sends the request (valid 24 hours). The request travels encrypted inside that link, so nothing personal is stored while it waits. Dario then replies personally, usually within one working day. Every result also carries the direct WhatsApp link. Limits: 5 requests per email address a day; throwaway email addresses are refused.

## Agent skill

[`skills/darioa-web-developer/SKILL.md`](skills/darioa-web-developer/SKILL.md) tells an agent when to use this server and how to help. Drop it into your agent's skills folder (e.g. `~/.claude/skills/`).

## Connect

- **Claude**: add a custom connector with the endpoint URL (no authentication).
- **ChatGPT** (Developer mode): add a connector with the endpoint URL, authentication none.
- **Cursor / VS Code / any MCP client**:

```json
{ "mcpServers": { "darioa": { "url": "https://www.darioa.nl/mcp" } } }
```

## Links

- Website: https://www.darioa.nl/ · Prices: https://www.darioa.nl/nl/prijzen
- Agent docs: https://www.darioa.nl/llms.txt · full text: https://www.darioa.nl/llms-full.txt · machine-readable: https://www.darioa.nl/agents.json
- Server card: https://www.darioa.nl/.well-known/mcp/server-card.json
- Terms: https://www.darioa.nl/en/terms · Privacy: https://www.darioa.nl/en/privacy

The server itself runs on darioa's website; this repository holds its public documentation and listing metadata.
