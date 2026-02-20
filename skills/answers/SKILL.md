---
name: answers
description: Get AI-powered answers with citations from live web data using Olostep. Use when the user needs up-to-date facts, competitive intelligence, pricing comparisons, or wants web-sourced answers returned as structured JSON for use in code.
---

# Olostep AI Answers

Get AI-synthesised answers from live web data with source citations. Supports structured JSON output for use directly in code.

## When to use

- User needs current information the AI's training data may not have
- User wants a structured data object pulled from the web (prices, specs, rankings)
- User is doing competitive research and needs comparable data across multiple sources
- User wants a fact-checked answer with verifiable citations

## Workflow

1. Use `answers` with the user's question as `task`.
2. If the result needs to be used in code or compared in a table, provide a `json` schema.
3. Return the answer with its source URLs.
4. Offer to scrape any source for deeper detail.

## Real developer workflows

**"Populate my comparison table"**
> "Get the pricing for Vercel, Netlify, and Render for a hobby project — return as JSON"
→ `answers` with schema `[{"provider": "", "free_tier": "", "paid_from": ""}]`
→ Returns structured array you can paste directly into code or a markdown table.

**"Research before writing a blog post"**
> "What are the most common mistakes developers make with React useEffect in 2026?"
→ `answers` returns a cited, synthesised answer from multiple current sources.

**"Get company data for a CRM or outreach tool"**
> "Find the CEO, founding year, and last funding round for linear.app"
→ `answers` with schema `{"ceo": "", "founded": "", "last_funding": "", "amount": ""}`

**"Check if a package is still maintained"**
> "Is [npm package] still actively maintained and what's the latest version?"
→ `answers` fetches current GitHub/npm data with citations.

**"Tech stack research"**
> "What tech stack does Notion use for their web app?"
→ `answers` aggregates from engineering blogs, job postings, and tech trackers.

## Parameters
- **task**: Question or task (required)
- **json**: JSON schema or example object for structured output (optional)
  - String: `"return an array of objects with name, price, and features fields"`
  - Object: `{"name": "", "price": "", "features": []}`

## Tips
- The `json` parameter is the most powerful feature — use it to get data you can paste into code
- Citations let you verify and deep-dive — always share source URLs with the user
- Chain with `scrape` to get full content from any cited source
