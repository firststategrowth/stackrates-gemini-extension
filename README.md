# StackRates for Gemini CLI

Ask Gemini CLI what a VPS costs today. This extension connects it to the StackRates MCP server
(`https://stackrates.ai/mcp`, Streamable HTTP, read-only, no key, no sign-up).

Each answer gives the plan, its monthly price in US dollars, the date the price was read, and the
provider's own page it was read from.

## Install

```
gemini extensions install https://github.com/firststategrowth/stackrates-gemini-extension
```

## What you can ask

- "Cheapest VPS with 4 GB of RAM"
- "Hetzner vs Vultr for 8 GB in Germany"
- "What does Nextcloud AIO need, and what is the cheapest server that fits?"
- "Which providers have a sale price today?"

A real answer to "OVHcloud's cheapest VPS with 4 GB" (asked 15 Nov 2026):

> OVHcloud VPS-1: 2 vCPU / 4 GB / 40 GB at $5.35/mo, $64.20 over 12 months, read 15 Nov 2026.
> Source: https://us.ovhcloud.com/vps/

## Tools

| Tool | What it returns |
|---|---|
| `ask_vps_prices` | An answer to a plain-language price question |
| `search_vps_plans` | Plans that match a size, budget, provider or location, cheapest first |
| `server_for_app` | The documented requirements of a self-hosted app or game server, and the cheapest plans that meet them |
| `current_vps_offers` | Introductory and sale prices shown on providers' own pages today, each set against the cheapest regular plan with as much memory |
| `advise_vps_choice` | For a buying question in plain words: the matching plans, their cost over the term, and what the data cannot answer |

## Where the data comes from

StackRates reads each provider's pricing page or price API every day and keeps the date and link
for every price. Prices are USD a month and include a separately billed IPv4 address; plans that
need a prepaid term say so. Plans shown as sold out are left out.

The same data is open: https://stackrates.ai/data/ and https://github.com/firststategrowth/vps-prices
(CC BY 4.0, credit "StackRates (stackrates.ai)").

## Who runs this

StackRates, First State Growth LLC. StackRates earns a commission from some providers when someone
signs up through its links; this never changes a price it lists or the order of a list.
Corrections: https://stackrates.ai/about/

The files in this repository are MIT licensed. The price data is CC BY 4.0.
