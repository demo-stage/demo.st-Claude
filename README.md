# demo.st — Claude Code agent

This repo contains the **demo.st** agent for [Claude Code](https://code.claude.com/) and [Claude Code Market](https://www.ccmarket.dev/). The agent guides Claude to deploy static sites and demos to [demo.st](https://demo.st) using the demo.st MCP server.

## Install (Claude Code)

1. **Add the agent file to Claude Code:**
   ```bash
   mkdir -p ~/.claude/agents
   curl -o ~/.claude/agents/demo-st.md https://raw.githubusercontent.com/demo-stage/demo.st-Claude/main/demo-st.md
   ```

2. **Configure the demo.st MCP server** in Claude Code (project `.mcp.json` or user settings):
   - **URL:** `https://demo.st/mcp`
   - **Headers:** `Authorization: Bearer ${env:DEMO_ST_MCP_TOKEN}`

3. **Get your token:** Sign in at [https://demo.st](https://demo.st) → [MCP / token page](https://demo.st/api/mcp/token) → copy token, then:
   - macOS/Linux: `export DEMO_ST_MCP_TOKEN="your-token"`
   - PowerShell: `$env:DEMO_ST_MCP_TOKEN = "your-token"`

4. Use in Claude Code: *"Use the demo-st agent to deploy this project to a live link"* or *"Publish the build to demo.st with subdomain my-app"*.

## Links

- **demo.st:** https://demo.st  
- **Terms & Privacy:** https://demo.st/terms, https://demo.st/privacy  
- **Cursor plugin (main repo):** https://github.com/demo-stage/demo.st  
