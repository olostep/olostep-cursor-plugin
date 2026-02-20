---
name: scrape
description: Scrape a single webpage and extract its content as clean markdown, HTML, JSON, or text using Olostep. Handles JavaScript rendering, anti-bot protection, and proxy rotation automatically.
---

# Olostep Scrape

Extract content from a single webpage using Olostep's web scraping API.

## When to use
- Extracting content from a specific URL
- Getting clean markdown from JavaScript-heavy pages
- Scraping pages behind anti-bot protection
- Getting geo-specific content with country routing

## Instructions

When the user provides a URL:

1. Use the `scrape_website` MCP tool with the URL.
2. Default to `markdown` format unless the user specifies otherwise (`html`, `json`, `text`).
3. For JavaScript-heavy pages or SPAs, suggest `wait_before_scraping: 2000`.
4. For geo-targeted content, use a country code (e.g., `US`, `GB`, `CA`).

## Parameters
- **url_to_scrape**: The webpage URL (required)
- **output_format**: `markdown` (default), `html`, `json`, or `text`
- **country**: Country code for geo-targeted scraping (optional)
- **wait_before_scraping**: Milliseconds to wait for JS rendering, 0–10000 (optional)
- **parser**: Specialized parser ID e.g. `@olostep/amazon-product` (optional)

## Examples
- "Scrape https://example.com" → extracts as markdown
- "Get the JSON from https://example.com/product" → uses json format
- "Scrape https://amazon.com/dp/B0... using the amazon-product parser"

## Tips
- Olostep handles JS rendering, anti-bot, and proxies automatically
- Use specialized parsers for Amazon, LinkedIn, and other platforms
- For large batches, use the `batch` skill instead
