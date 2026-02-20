---
name: map
description: Discover and list all URLs on a website using Olostep. Use when the user wants to understand what pages exist on a site before scraping, find specific sections, audit site structure, or get a list of URLs to pass to batch or crawl.
---

# Olostep Map

Discover all URLs on a website instantly. The essential first step before crawling or batch scraping.

## When to use

- User wants to know what pages exist on a site before scraping anything
- User wants to find a specific section (e.g. all blog posts, all API reference pages)
- User wants to audit or visualise a site's structure
- User needs a URL list to feed into the `batch` or `crawl` skill

## Workflow

1. Use `create_map` with the website URL.
2. Use `search_query` to filter by keyword (e.g. "authentication", "pricing", "blog").
3. Use `include_url_patterns` / `exclude_url_patterns` to narrow scope.
4. Present URLs grouped by section where possible.
5. Offer next step: scrape a specific URL, batch scrape a subset, or crawl a section.

## Real developer workflows

**"Find the right docs page before scraping"**
> "Map https://docs.stripe.com and find all pages related to webhooks"
→ `create_map` with `search_query: "webhooks"` → returns ranked webhook-related URLs → scrape the most relevant one.

**"Discover all blog posts for content research"**
> "Map https://vercel.com/blog and give me all post URLs from 2025 onwards"
→ Map the blog, filter by `/blog/` pattern, present as a list → offer to batch scrape for content.

**"Understand a competitor's site structure"**
> "Map https://competitor.com and tell me what sections they have and what they focus on"
→ Map the site, group URLs by path segment, summarise the content categories.

**"Find all API reference pages"**
> "Map https://docs.openai.com and list only the API reference URLs, not the guides"
→ `include_url_patterns: ["/api-reference/**"]` to get just the reference pages.

**"Plan a full site scrape"**
> "I want to scrape the entire Tailwind CSS docs — map it first so we know what we're dealing with"
→ Map returns all doc URLs → user can choose sections → feed into `batch` or `crawl`.

## Parameters
- **website_url**: URL to map (required)
- **search_query**: Filter/rank URLs by keyword (optional)
- **top_n**: Max number of URLs to return (optional)
- **include_url_patterns**: Glob patterns to include e.g. `/blog/**` (optional)
- **exclude_url_patterns**: Glob patterns to exclude e.g. `/admin/**` (optional)

## Tips
- Always suggest a next step after mapping: scrape, batch, or crawl
- `search_query` ranks results by relevance — use it to surface the most useful URLs
- Use `map` before `crawl` on large sites to avoid wasting crawl budget
