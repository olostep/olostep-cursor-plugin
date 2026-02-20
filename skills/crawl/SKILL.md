---
name: crawl
description: Autonomously crawl an entire website by following links from a starting URL using Olostep. Use when the user wants to ingest an entire docs site, blog, or knowledge base as context for coding, writing, or analysis.
---

# Olostep Crawl

Autonomously discover and scrape multiple pages from a website by following links. Ideal for ingesting entire docs sites, blogs, or knowledge bases.

## When to use

- User wants to understand an entire library or API by crawling its docs
- User wants all blog posts or changelogs from a site as context
- User is building a RAG pipeline and needs a site's full content
- User wants to audit or analyse all content across a site

## Workflow

1. Use `create_crawl` with the starting URL.
2. Start with `max_pages: 10` — ask the user before going higher.
3. Default to `markdown` output.
4. After crawling, synthesise or act on the collected content — summarise, extract patterns, generate code, answer questions.

## Real developer workflows

**"Learn a new library by reading its docs"**
> "Crawl https://docs.tanstack.com/query/latest and give me a cheat sheet of the most important hooks and patterns"
→ Crawl up to 20 pages of the docs, then synthesise a concise reference guide.

**"Generate SDK usage examples from docs"**
> "Crawl the Resend docs and write me 5 practical TypeScript examples covering the most common email sending patterns"
→ Crawl the docs, extract API patterns, write working code examples.

**"Build context before refactoring"**
> "Crawl our internal docs at https://internal.docs.company.com and understand the architecture before I start refactoring the auth system"
→ Crawl internal docs, extract architectural decisions relevant to auth.

**"Content audit"**
> "Crawl our marketing site https://company.com and list every page, its title, and a one-line description"
→ Crawl up to 50 pages, extract metadata into a structured list.

**"Competitive docs analysis"**
> "Crawl https://docs.competitor.com/api and summarise what their API can do that ours can't"
→ Crawl competitor docs, compare capabilities, identify gaps.

## Parameters
- **start_url**: Starting URL (required)
- **max_pages**: Pages to crawl, default 10 — increase carefully (optional)
- **output_format**: `markdown` (default), `html`, `json`, `text`
- **country**: Country code for geo-targeted crawling (optional)
- **parser**: Specialised parser ID (optional)

## Tips
- Always start at 10 pages, confirm before going to 50+
- After crawling, synthesise — don't just dump raw content at the user
- Use `map` first if the user needs to understand site structure before crawling
- For a known list of URLs, `batch` is faster than `crawl`
