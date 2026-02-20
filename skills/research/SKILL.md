---
name: research
description: Research any topic using live web data — compare tools, analyse competitors, evaluate libraries, or gather structured market intelligence. Use when the user wants a thorough, web-sourced answer before making a technical or product decision.
---

# Olostep Research

Do thorough, cited web research on any topic. Compare tools, evaluate options, and gather structured intelligence — all from live web data.

## When to use

- User is choosing between tools, libraries, or services and wants a fair comparison
- User wants to understand competitors' features, pricing, or positioning
- User is evaluating whether to build vs buy something
- User needs market intelligence before a product, architecture, or hiring decision
- User wants to fact-check a technical claim with current sources

## Workflow

1. Use `answers` with a clear research task and a `json` schema for structured output.
2. For deep dives, also `scrape_website` on the most relevant sources.
3. For competitor analysis, batch scrape their pricing/features pages for direct comparison.
4. Present findings in a structured format: table, list, or JSON — whatever helps the user decide.

## Real developer workflows

**"Help me pick the right tool"**
> "Compare Prisma, Drizzle, and Kysely for a new TypeScript project — which should I use?"
→ `answers` with schema `{"orm": "", "pros": [], "cons": [], "best_for": ""}` → structured comparison table.

**"Competitive feature analysis"**
> "What features do Linear, Jira, and Height have for sprint planning? I'm deciding which to use for my team."
→ `answers` for high-level summary + `batch` scrape of each pricing/features page for detailed comparison.

**"Build vs buy research"**
> "Should I build my own email sending system or use a service? Compare the top 3 email API services vs self-hosting."
→ `answers` synthesises trade-offs from engineering blogs, pricing pages, and community discussions.

**"Evaluate a library before adopting it"**
> "Is Bun production-ready in 2026? Check GitHub activity, known issues, and community sentiment."
→ `answers` aggregates from GitHub, Reddit, blog posts, and release notes with citations.

**"Market sizing for a feature"**
> "How many companies use Slack and what's the average team size? I'm building a Slack integration."
→ `answers` with schema `{"stat": "", "value": "", "source": ""}` returns cited data points.

**"Tech stack research"**
> "What stack does Figma use? I want to understand how they handle real-time collaboration at scale."
→ `answers` + scrape any relevant engineering blog posts for deep technical detail.

## Parameters

### `answers`
- **task**: Research question (required)
- **json**: Output schema for structured results (optional but recommended)

### Supporting tools
- `scrape_website`: Deep-dive into a specific source
- `batch_scrape_urls`: Compare multiple sites side-by-side
- `get_website_urls`: Find specific pages within a site

## Tips
- Always use a JSON schema when the user needs comparable data (tables, CSVs, code variables)
- Share citation URLs — they let the user verify and explore further
- For competitive research, scrape their pricing and features pages directly — `answers` may miss details
- Summarise with a clear recommendation at the end, don't just list facts
