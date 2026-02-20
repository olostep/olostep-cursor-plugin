---
name: search
description: Search the web using Olostep and get structured results. Use when you need to find information across multiple websites without knowing the exact URLs.
---

# Olostep Search

Search the web and get structured results using Olostep's search API.

## When to use
- Finding information when you don't know which website has it
- Researching topics across multiple sources
- Getting localized search results for a specific country

## Instructions

When the user provides a search query:

1. Use the `search_web` MCP tool with the query.
2. Return the structured results including titles, URLs, and snippets.
3. For localized results, use the `country` parameter (default: `US`).
4. For raw Google SERP data, use `google_search` instead.

## Parameters
- **query**: The search query (required)
- **country**: Country code for localized results e.g. `US`, `GB` (default: `US`)

## Examples
- "Search for the latest AI frameworks in 2026"
- "Find competitor pricing for web scraping APIs"
- "Search for React best practices country:GB"

## Tips
- Combine with `scrape` skill to get full content from interesting results
- Use specific queries for best results
- Use country codes for geo-specific searches
