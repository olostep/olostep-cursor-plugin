---
name: crawl
description: Autonomously crawl an entire website starting from a URL, following links to discover and scrape multiple pages. Use for documentation sites, blogs, or product catalogs.
---

# Olostep Crawl

Autonomously discover and scrape entire websites by following links from a starting URL.

## When to use
- Extracting content from multiple related pages
- Scraping an entire documentation site or blog
- Building a comprehensive dataset from a website
- When you need comprehensive coverage across a site

## Instructions

When the user wants to crawl a website:

1. Use the `create_crawl` MCP tool with the starting URL.
2. Default to `max_pages: 10` unless specified — warn that high values can be slow.
3. Default to `markdown` output format unless specified.

## Parameters
- **start_url**: Starting URL for the crawl (required)
- **max_pages**: Maximum pages to crawl, default 10 (optional)
- **follow_links**: Whether to follow discovered links, default true (optional)
- **output_format**: `markdown` (default), `html`, `json`, or `text`
- **country**: Country code for geo-targeted crawling (optional)
- **parser**: Specialized parser ID (optional)

## Examples
- "Crawl https://docs.example.com" → crawls docs site (10 pages)
- "Crawl https://example.com/blog up to 50 pages"
- "Crawl https://example.com and get JSON output"

## Tips
- Start small (10 pages) to test, then increase
- Combine with `map` first to understand site structure
- Use `follow_links: false` to only scrape the start URL
