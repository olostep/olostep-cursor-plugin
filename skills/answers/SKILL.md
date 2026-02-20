---
name: answers
description: Get AI-powered answers with citations and sources from live web data using Olostep. Optionally return structured JSON output matching a custom schema.
---

# Olostep AI Answers

Search the web and get AI-powered answers with sources and citations. Supports structured JSON output.

## When to use
- Research questions that need up-to-date web data
- Competitive intelligence and market research
- Fact-checking with source citations
- Extracting structured data (prices, specs, names) from the web

## Instructions

When the user asks a research question:

1. Use the `answers` MCP tool with the question as the `task`.
2. If the user wants structured output, construct a JSON schema for the `json` parameter.
3. Present the answer clearly with its citations and source URLs.

## Parameters
- **task**: The question or task to answer using live web data (required)
- **json**: JSON schema or example object for structured output e.g. `{"price": "", "currency": ""}` (optional)

## Examples
- "What are the top web scraping APIs in 2026 and their pricing?"
- "Find the founders and funding of [company]" with schema `{"founders": [], "funding": ""}`
- "Compare React vs Vue performance in 2026"

## Tips
- Great for competitive analysis, pricing research, and fact-checking
- Use a JSON schema to get consistent, parseable output
- Citations include source URLs — follow up with `scrape` for deeper dives
- Answers use live web data so results reflect current information
