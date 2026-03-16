# demo.st — Claude Code plugin

A [Claude Code](https://code.claude.com/) plugin that adds a **deploy** subagent and the **demo.st** MCP server. Use it to deploy static sites and demos to [demo.st](https://demo.st): reserve a subdomain, upload a zip, get a live link like `yourproject.demo.st`.

## Install

**From the official marketplace (once listed):**  
In Claude Code, run `/plugin` → Discover → search for **demo-st** → Install.

**From this repo (before or without marketplace):**

```bash
/plugin install https://github.com/demo-stage/demo.st-Claude
```

## Setup

1. **Get your token:** Sign in at [https://demo.st](https://demo.st) → [MCP / token](https://demo.st/api/mcp/token) → copy token.
2. **Set the token:**
   - macOS/Linux: `export DEMO_ST_MCP_TOKEN="your-token"`
   - PowerShell: `$env:DEMO_ST_MCP_TOKEN = "your-token"`
3. The plugin adds the demo.st MCP server automatically; with `DEMO_ST_MCP_TOKEN` set, the tools are available.

## Use

- *"Use the demo-st deploy agent to deploy this project to a live link"*
- *"Publish the build to demo.st with subdomain my-app"*
- Or run `/agents` and choose the **deploy** agent.

## Links

- **demo.st:** https://demo.st  
- **Terms & Privacy:** https://demo.st/terms, https://demo.st/privacy  
