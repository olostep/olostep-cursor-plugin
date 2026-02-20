---
name: batch
description: Scrape a list of URLs in parallel using Olostep. Use when the user has multiple URLs to extract content from at once — product pages, job listings, blog posts, search results, or any known list of pages.
---

# Olostep Batch Scrape

Scrape up to 10,000 URLs in parallel. Much faster and more efficient than scraping one-by-one.

## When to use

- User has 3+ URLs they want to extract content from
- User wants to scrape all search results from a query
- User wants to compare multiple product pages, job listings, or pricing pages
- User has a list of URLs from `map` and wants to pull content from all of them

## Workflow

1. Collect all URLs from the user (or from a previous `map` result).
2. Use `batch_scrape_urls` with the URL array.
3. Assign a `custom_id` to each URL for easy result matching.
4. Default to `markdown`. Use `json` with a `parser` for structured product/listing data.
5. After batch completes, synthesise across results — compare, extract, summarise.

## Real developer workflows

**"Compare these competitor landing pages"**
> "Batch scrape these 6 SaaS landing pages and tell me what value props, pricing models, and CTAs each one uses"
→ Batch scrape all 6, then extract and compare key messaging elements.

**"Extract all job listings"**
> "Scrape all these job posting URLs and extract: role title, salary, required skills, and location as JSON"
→ Batch with `output_format: json`, extract structured fields from each listing.

**"Pull all changelogs for a dependency audit"**
> "Scrape the changelogs for these 10 npm packages and flag any breaking changes in the last 6 months"
→ Batch scrape all changelog pages, scan for breaking change keywords.

**"Build a dataset from search results"**
> "Here are 20 product URLs from Amazon — scrape them all and extract name, price, and rating"
→ Batch with `@olostep/amazon-product` parser for clean structured output.

**"Research all speakers at a conference"**
> "Batch scrape these 15 speaker profile pages and extract their name, company, and talk title"
→ Batch all profile URLs with a JSON schema extract.

## Parameters
- **urls_to_scrape**: Array of `{url, custom_id?}` objects, 1–10,000 (required)
- **output_format**: `markdown` (default), `html`, `json`, `text`
- **wait_before_scraping**: ms to wait per URL for JS rendering (optional)
- **country**: Country code (optional)
- **parser**: Specialised parser e.g. `@olostep/amazon-product` (optional)

## Tips
- Use `custom_id` to match results back to your source list
- Combine with `map` — map a site first, then batch scrape the relevant URLs
- Always synthesise across the batch results, don't just return raw content
