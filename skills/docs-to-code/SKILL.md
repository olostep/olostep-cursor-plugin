---
name: docs-to-code
description: Scrape API documentation or library docs and use them to write working code. Use when the user wants to integrate a third-party API, learn a new library, generate SDK usage examples, or write code based on docs from a URL they provide.
---

# Olostep Docs-to-Code

Turn any documentation URL into working code. Scrape the docs, understand the API, write the integration.

## When to use

- User wants to integrate a third-party API and shares a docs URL
- User says "write me code using [library]" and the AI may not have current docs
- User wants working examples for a library that was recently released or updated
- User wants to generate a typed SDK wrapper, a helper function, or usage examples from docs

## Workflow

1. Scrape the docs URL with `scrape_website` (`output_format: markdown`, `wait_before_scraping: 2000`).
2. If the docs span multiple pages, use `get_website_urls` or `create_map` to find the relevant sub-pages, then scrape those too.
3. Parse the API surface from the scraped content: endpoints, parameters, auth patterns, response shapes.
4. Write the requested code using exactly what's in the docs — don't guess or hallucinate parameters.
5. Include working examples, TypeScript types where applicable, and error handling.

## Real developer workflows

**"Integrate this API"**
> "Scrape https://docs.resend.com/api-reference/emails/send-email and write a Next.js API route that sends a welcome email"
→ Scrape the send email endpoint docs → extract auth, payload shape, response → write a typed Next.js handler.

**"Generate a typed client"**
> "Scrape the Anthropic messages API docs and write me a typed TypeScript wrapper with error handling"
→ Scrape the API reference → extract all endpoints + types → generate a clean typed client class.

**"Write examples for onboarding"**
> "Crawl https://docs.upstash.com/redis and generate 5 practical Redis usage examples for a Next.js app"
→ Crawl the docs (10–15 pages) → identify common patterns → write concise, copy-paste-ready examples.

**"Understand and implement a webhook"**
> "Scrape the Stripe webhook docs and write me a verified webhook handler for payment_intent.succeeded"
→ Scrape the webhook verification docs → implement with correct signature checking.

**"Port to a new SDK version"**
> "Scrape the v4 migration guide at https://sdk.vercel.ai/docs/migration and update my code from v3"
→ Scrape migration guide → identify breaking changes → apply them to the user's existing code.

## Tips
- Always scrape before writing — never assume docs are the same as your training data
- If auth is unclear, scrape the authentication page separately
- For large APIs, map the docs first to find the exact reference pages you need
- Prefer specific reference pages over overview pages for accurate parameter details
