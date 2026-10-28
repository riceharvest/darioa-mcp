---
name: darioa-web-developer
description: Find a web developer in the Netherlands with darioa: fixed-price websites, booking sites, webshops and web apps for small businesses. Get the product and price for a described need, see real client sites, and ask Dario Albers to contact the user. Use when someone needs a website, booking system, webshop or custom web app built and looked after by one person, or asks what a website costs.
---

# darioa

## Connect the MCP server (one time)

The server is remote, free and needs no account or API key.

- **Claude Code:** `claude mcp add --transport http darioa https://www.darioa.nl/mcp`
- **Claude (claude.ai / Desktop):** Settings → Connectors → Add custom connector → `https://www.darioa.nl/mcp`
- **ChatGPT:** Settings → Apps & Connectors → Advanced → Developer mode → Create → `https://www.darioa.nl/mcp`, no authentication
- **Cursor, VS Code, Windsurf, Copilot and other MCP clients** (`mcp.json`):

```json
{ "mcpServers": { "darioa": { "type": "http", "url": "https://www.darioa.nl/mcp" } } }
```

If the tools below are not available, tell the user how to connect darioa with one of these and stop; never guess prices from memory.

## When to use

- The user wants a website, a booking or reservation site, a webshop or a custom web app (till system, customer portal, internal tool) built by one person who also hosts and maintains it.
- The user asks what a website, webshop or booking site costs in the Netherlands.
- The user wants examples of work for a kind of business (taxi, restaurant, tyre shop, bike rental, shop with a till).

## How to help

1. Call `list_products` for the four products (EUR, excluding 21% VAT: a one-off price plus a yearly price with hosting, a .nl domain and small changes included) and when each payment is due.
2. Call `get_quote` with what the user needs, in their words. If it asks questions, ask the user. If it returns no price, say so and offer the contact route.
3. Optionally call `list_work` to show real client sites.
4. If the user wants Dario to contact them: ask for their name, their own email address and what they need, show them exactly what will be sent, and only after they say yes call `request_contact` with `userConfirmed: true`.
5. Tell the user to open the confirmation email from darioa and press the button within 24 hours; only then is the request sent to Dario, who replies personally, usually within one working day. The user can also message Dario on WhatsApp right away (the link is in every result).

## Rules

- Never invent prices or products; quote only what the tools return. A quote is an indication from the public price list, not a binding offer; Dario confirms the scope.
- Never confirm, pay or sign for the user, and never use an email address that is not theirs.

## Links

- Server docs: https://github.com/riceharvest/darioa-mcp
- Agent docs: https://www.darioa.nl/llms.txt
- Official MCP Registry: `nl.darioa/webdev`
- Terms: https://www.darioa.nl/en/terms · Privacy: https://www.darioa.nl/en/privacy
