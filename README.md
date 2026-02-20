# Olostep Plugin for Cursor

Turn any website into clean, LLM-ready markdown or structured data. Olostep integrates powerful web scraping, crawling, search, and AI-powered answers directly into Cursor.

## Features

- **Scrape** — Extract content from any webpage as markdown, HTML, JSON, or text
- **Search** — Search the web and get structured results
- **Crawl** — Autonomously discover and scrape entire websites
- **Map** — Discover all URLs on a site for analysis and planning
- **Batch** — Scrape up to 10,000 URLs in parallel
- **AI Answers** — Get AI-powered answers with citations from live web data

All with automatic JavaScript rendering, anti-bot handling, and proxy rotation built in.

## Installation

Install from the [Cursor Marketplace](https://cursor.com/marketplace/olostep) or add the MCP server manually.

## Setup

After installing, run the `setup` skill or add your API key manually:

1. Get your free API key at [olostep.com/auth](https://olostep.com/auth)
2. Add to Cursor Settings → Features → MCP, or to `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "olostep": {
      "command": "npx",
      "args": ["-y", "olostep-mcp"],
      "env": {
        "OLOSTEP_API_KEY": "your-api-key-here"
      }
    }
  }
}
```

## Available Skills

| Skill | Description |
|-------|-------------|
| `setup` | Configure your Olostep API key |
| `scrape` | Extract content from a single webpage |
| `search` | Search the web for information |
| `crawl` | Crawl an entire website from a start URL |
| `map` | Discover all URLs on a website |
| `batch` | Batch scrape up to 10,000 URLs |
| `answers` | Get AI-powered answers with citations |

## MCP Tools

The following MCP tools are available directly in Cursor chat:

| Tool | Description |
|------|-------------|
| `scrape_website` | Extract content from a single URL |
| `get_webpage_content` | Retrieve a webpage as markdown |
| `search_web` | Search the web with structured results |
| `google_search` | Get Google SERP data |
| `create_crawl` | Autonomously crawl a website |
| `create_map` | Discover all URLs on a site |
| `batch_scrape_urls` | Batch scrape up to 10k URLs |
| `answers` | AI-powered answers with citations |
| `get_website_urls` | Search and retrieve relevant URLs |

## Usage Examples

**Scrape a webpage:**
> "Scrape https://example.com and give me the main content"

**Search the web:**
> "Search for the top web scraping APIs in 2026"

**Crawl a site:**
> "Crawl https://docs.example.com up to 50 pages and summarize the content"

**Map a site:**
> "Map https://example.com and find all blog URLs"

**Batch scrape:**
> "Scrape all these 20 product URLs and extract the price and title from each"

**AI Answers:**
> "What are the pricing plans for the top 5 web scraping services? Return as JSON with name and price fields."

## Links

- [Olostep Website](https://olostep.com)
- [API Documentation](https://docs.olostep.com)
- [Get API Key](https://olostep.com/auth)
- [MCP Server on npm](https://www.npmjs.com/package/olostep-mcp)

## License

MIT License — see [LICENSE](LICENSE) for details.
