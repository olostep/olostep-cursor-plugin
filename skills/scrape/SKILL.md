---
name: scrape
description: Scrape a single webpage and extract its content as clean markdown, HTML, JSON, or text using Olostep. Use when the user shares a URL and wants to read it, extract content from it, understand its structure, use it as context for coding, or turn a page into data.
---

# Olostep Scrape

Extract clean, LLM-ready content from any URL — including JavaScript-heavy pages, SPAs, and bot-protected sites.

## When to use

- User pastes a URL and says "read this", "summarise this", "use this as context"
- User wants to pull content from a docs page to help write code against that API
- User wants to extract data from a product page, blog post, job listing, or changelog
- User needs page content that their browser can see but the AI cannot

## Workflow

1. Use `scrape_website` with the URL.
2. Default to `markdown` — it's the cleanest format for AI reasoning.
3. Use `wait_before_scraping: 3000` for JS-heavy pages or SPAs (React, Next.js, Vue apps).
4. Use `output_format: json` with a `parser` when extracting structured product/listing data.
5. After scraping, act on the content — summarise it, extract fields from it, use it to write code, answer questions about it.

## Real developer workflows

**"Read the docs and write the integration"**
> "Scrape https://docs.stripe.com/api/payment_intents and write me a TypeScript function to create a payment intent"
→ Scrape the docs page, then write the code using that exact API reference.

**"What changed in this changelog?"**
> "Scrape https://github.com/vercel/next.js/releases and tell me what's new in the last 3 releases"
→ Scrape the releases page, extract and summarise the changes.

**"Pull this job listing into my cover letter context"**
> "Scrape this job posting and tailor my CV summary to match it: https://..."
→ Scrape the listing, extract requirements, generate tailored content.

**"Get this competitor's pricing"**
> "Scrape https://competitor.com/pricing and extract their plan names and prices as JSON"
→ Use `output_format: json` to get structured pricing data.

## Parameters
- **url_to_scrape**: URL to scrape (required)
- **output_format**: `markdown` (default), `html`, `json`, `text`
- **wait_before_scraping**: ms to wait for JS to render, 0–10000 (use 3000 for SPAs)
- **country**: Country code for geo-targeted content e.g. `US`, `GB`
- **parser**: Specialised parser e.g. `@olostep/amazon-product`

## Tips
- Always act on the scraped content, don't just return it raw
- For batches of URLs, use the `batch` skill
- For entire sites, use the `crawl` skill
