---
name: search
description: Search the web using Olostep and return AI-powered answers with live citations. Use when the user asks a question that needs current web data, wants to research a topic, find the best tools for a job, or get up-to-date information the AI may not know.
---

# Olostep Search

Search the live web and return summarised answers with source citations. Best for research, comparisons, and up-to-date information.

## When to use

- User asks "what is the best X for Y" and needs current results
- User wants to compare tools, libraries, or services
- User needs information that may have changed since the AI's training cutoff
- User wants to find relevant URLs within a specific site

## Workflow

**For open web research** (no specific site):
1. Use `answers` with the question as `task`.
2. If structured output is needed, pass a JSON schema as `json`.
3. Present the answer with its source URLs — offer to scrape any of them for full content.

**For searching within a specific site** (e.g. docs, a company site):
1. Use `get_website_urls` with `url` + `search_query`.
2. Present the ranked URLs, then offer to scrape the most relevant one.

## Real developer workflows

**"Find the best library for this"**
> "What's the best React drag-and-drop library in 2026?"
→ `answers` returns a ranked comparison with sources, then scrape the top result's docs.

**"Research before building"**
> "What are the pros and cons of tRPC vs REST for a Next.js app?"
→ `answers` with JSON schema `{"option": "", "pros": [], "cons": []}` for clean structured output.

**"Find relevant docs pages"**
> "Search the Supabase docs for RLS row-level security examples"
→ `get_website_urls` on `https://supabase.com/docs` with query `"row level security examples"`, then scrape the top results.

**"Competitive pricing research"**
> "What do Firecrawl, Apify, and Browserbase charge for 10k scrapes?"
→ `answers` with schema `{"service": "", "price_per_10k": "", "plan": ""}` returns clean comparable data.

## Parameters

### `answers`
- **task**: Question or research task (required)
- **json**: Output schema e.g. `{"name": "", "price": "", "pros": []}` (optional)

### `get_website_urls`
- **url**: Site to search within (required)
- **search_query**: What to find (required)

## Tips
- Use `answers` for broad research, `get_website_urls` when you know the site
- Always offer to scrape top URLs for full content
- Use a JSON schema with `answers` when you need parseable, structured output
