---
name: map
description: Discover and list all URLs on a website. Use before crawling or batch scraping to understand site structure and plan what to extract.
---

# Olostep Map

Discover all URLs on a website for site analysis, content auditing, and planning.

## When to use
- Before crawling to understand what's on a site
- Auditing website structure
- Finding specific sections of a website
- Discovering URLs to pass to the `batch` skill

## Instructions

When the user wants to map a website:

1. Use the `create_map` MCP tool with the website URL.
2. Use `search_query` to filter URLs by keyword if the user wants specific content.
3. Use `top_n` to limit results for large sites.
4. Present URLs in an organized format grouped by section if possible.

## Parameters
- **website_url**: Website URL to map (required)
- **search_query**: Filter URLs by keyword e.g. "blog" (optional)
- **top_n**: Limit number of URLs returned (optional)
- **include_url_patterns**: Glob patterns to include e.g. `/blog/**` (optional)
- **exclude_url_patterns**: Glob patterns to exclude e.g. `/admin/**` (optional)

## Examples
- "Map https://example.com" → list all URLs
- "Map https://example.com and find only blog URLs"
- "Map https://docs.example.com excluding /api/** paths"

## Tips
- Use before `crawl` or `batch` to plan what to scrape
- Filter with include/exclude patterns for large sites
- Combine discovered URLs with the `batch` skill
