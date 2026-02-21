# Olostep Plugin for Cursor

Give your AI agent a live connection to the web. Olostep lets Cursor scrape any URL, search the web, crawl entire doc sites, and extract structured data — with JavaScript rendering, anti-bot bypass, and residential proxies built in.

No more hallucinated APIs. No stale docs. No copy-pasting from your browser.

## What you can do

- **Scrape** — Extract clean markdown, HTML, JSON, or text from any webpage, including JS-heavy SPAs and bot-protected sites
- **Search** — Get AI-synthesised answers with citations, or raw Google SERP results, from live web data
- **Crawl** — Autonomously follow links and ingest an entire docs site or blog in one call
- **Map** — Discover every URL on a site before you scrape, so you target exactly what you need
- **Batch** — Scrape up to 10,000 URLs in parallel — products, job listings, changelogs, competitor pages
- **AI Answers** — Ask a question, get a cited, structured answer pulled from live web sources

## Setup

1. Get your free API key at [olostep.com/auth](https://olostep.com/auth)
2. Go to **Cursor Settings → Features → MCP Servers**. Find the `olostep` server (installed by this plugin), click the configuration gear, and set your `OLOSTEP_API_KEY`.
3. Restart Cursor — run the `/setup` skill in chat if you need help.

*(Note: If you are installing manually without the plugin, you can add the server directly to your project's `.cursor/mcp.json` instead).*

## Skills

| Skill | Invoke | What it does |
|---|---|---|
| `setup` | `/setup` | Configure your Olostep API key and verify the MCP server is running |
| `scrape` | `/scrape` | Extract content from a single URL |
| `search` | `/search` | Search the web for live, up-to-date information |
| `crawl` | `/crawl` | Crawl an entire website from a start URL |
| `map` | `/map` | Discover all URLs on a site |
| `batch` | `/batch` | Batch scrape up to 10,000 URLs in parallel |
| `answers` | `/answers` | Get AI-powered answers with citations and structured JSON output |
| `docs-to-code` | `/docs-to-code` | Scrape API docs and write working, up-to-date integration code |
| `debug-error` | `/debug-error` | Search GitHub issues and StackOverflow to fix a real error |
| `extract-schema` | `/extract-schema` | Turn any webpage into typed JSON matching your schema |
| `migrate-code` | `/migrate-code` | Scrape a migration guide and automatically update your code |
| `research` | `/research` | Multi-source web research for tool comparisons and technical decisions |

## MCP Tools

These tools are available directly in Cursor chat once the MCP server is running:

| Tool | Description |
|---|---|
| `scrape_website` | Extract content from a single URL — markdown, HTML, JSON, or text |
| `get_webpage_content` | Retrieve a webpage as clean markdown |
| `google_search` | Get structured Google SERP results — organic, knowledge graph, PAA |
| `answers` | AI-powered answers with citations and optional JSON output shape |
| `create_crawl` | Autonomously crawl a website from a start URL |
| `create_map` | Discover all URLs on a site with include/exclude pattern filtering |
| `batch_scrape_urls` | Scrape up to 10,000 URLs in parallel |
| `get_website_urls` | Find and rank URLs within a specific site by relevance to a query |

## Real developer workflows

**"Read the docs and write the integration"**
> "Scrape https://docs.stripe.com/api/payment_intents and write me a TypeScript function to create a payment intent"

**"Fix this error"**
> "I'm getting `Cannot read properties of undefined (reading 'map')` in Next.js 15 — help me fix it"

**"Crawl and learn a new library"**
> "Crawl https://tanstack.com/query/latest/docs and give me a cheat sheet of the key hooks and patterns"

**"Compare competitors before building"**
> "Batch scrape the pricing pages of Vercel, Netlify, and Render — extract plan names, prices, and limits as JSON"

**"Extract structured data"**
> "Scrape this YC directory page and return a JSON array matching my Prisma `Startup` schema"

**"Migrate to a new version"**
> "Scrape the Next.js 15 migration guide and update my layout.tsx"

## Links

- [Olostep Website](https://olostep.com)
- [API Documentation](https://docs.olostep.com)
- [Get API Key](https://olostep.com/auth)
- [MCP Server on npm](https://www.npmjs.com/package/olostep-mcp)
- [Contact](mailto:info@olostep.com)

## License

MIT License — see [LICENSE](LICENSE) for details.
