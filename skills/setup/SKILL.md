---
name: setup
description: Configure the Olostep API key so the MCP server and all Olostep skills work correctly. Use when the user is setting up Olostep for the first time, has no API key configured, or is getting authentication errors.
---

# Olostep Setup

Help the user configure their Olostep API key so the MCP server tools work correctly.

## Steps

1. Ask the user for their Olostep API key. If they don't have one, direct them to sign up at https://olostep.com/auth to get a free API key.

2. Once they provide the key, update the MCP server configuration. Add or update the following in `.cursor/mcp.json` in the project, or in global Cursor settings (Settings → Features → MCP):

```json
{
  "mcpServers": {
    "olostep": {
      "command": "npx",
      "args": ["-y", "olostep-mcp"],
      "env": {
        "OLOSTEP_API_KEY": "<their-api-key>"
      }
    }
  }
}
```

3. Confirm the setup is complete and suggest they try `/scrape` or `/search` to test.

## Notes
- The free tier includes 100 credits/month
- Get your API key at: https://olostep.com/auth
- Documentation: https://docs.olostep.com
