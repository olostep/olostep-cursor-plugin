---
name: batch
description: Scrape up to 10,000 URLs in a single parallel batch operation using Olostep. Use when you have a known list of URLs to extract at scale.
---

# Olostep Batch Scrape

Scrape up to 10,000 URLs at once with parallel processing. Ideal for large-scale data extraction.

## When to use
- You have a list of specific URLs to scrape
- Scraping more than 3 URLs (more efficient than scraping one-by-one)
- Large-scale e-commerce or content extraction
- After using `map` to discover URLs

## Instructions

When the user wants to batch scrape URLs:

1. Collect the list of URLs.
2. Use the `batch_scrape_urls` MCP tool with the URL array.
3. Each URL object needs `url` and optionally a `custom_id` for tracking.
4. Default to `markdown` output format unless specified.

## Parameters
- **urls_to_scrape**: Array of `{url, custom_id?}` objects, 1–10,000 (required)
- **output_format**: `markdown` (default), `html`, `json`, or `text`
- **country**: Country code for geo-targeted scraping (optional)
- **wait_before_scraping**: Milliseconds to wait per URL, 0–10000 (optional)
- **parser**: Specialized parser ID (optional)

## Examples
- "Batch scrape these 5 URLs: [url1, url2, url3, url4, url5]"
- "Scrape all the URLs we found from map in JSON format"
- "Batch scrape product pages with the amazon parser"

## Tips
- Combine with `map` to discover URLs first, then batch scrape them
- Use `custom_id` to match results back to your source data
- All URLs are processed in parallel — 10k URLs is as fast as 1k
