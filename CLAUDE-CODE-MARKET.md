# Publishing to Claude Code Market

[Claude Code Market](https://www.ccmarket.dev/) (ccmarket.dev) is a marketplace for **sub-agents** used with [Claude Code](https://code.claude.com/). This repo contains the demo.st deploy agent: a markdown file that guides Claude on when and how to deploy static sites to [demo.st](https://demo.st) via MCP tools.

## What this repo provides

- **Agent file:** `demo-st.md` — When to use demo.st, tool workflow, setup, best practices.
- **MCP server:** demo.st is an HTTP MCP server at `https://demo.st/mcp`. Users must add it in Claude Code and set `DEMO_ST_MCP_TOKEN` for reserve/upload/clear/release.

The agent does not replace the MCP server; it tells Claude how to use the demo.st MCP tools once they are configured.

## How to submit to Claude Code Market

1. **Sign in at Claude Code Market**  
   - Go to [https://www.ccmarket.dev/agents/submit](https://www.ccmarket.dev/agents/submit).  
   - Click **Continue with GitHub** and authorize.

2. **Download URL**  
   - Install command (raw URL from this repo):
     ```bash
     curl -o ~/.claude/agents/demo-st.md "https://raw.githubusercontent.com/demo-stage/demo.st-Claude/main/demo-st.md"
     ```
   - Ensure `demo-st.md` is on the `main` branch so the raw URL works.

3. **Fill out the submission form**  
   Use the following as a starting point (adjust if the form fields differ):

   | Field | Suggested value |
   |-------|------------------|
   | **Agent name** | demo.st — Deploy Agent |
   | **Short description** | Deploy static sites and demos to demo.st: reserve a subdomain, upload a zip, get a live link like yourproject.demo.st. Uses the demo.st MCP server. |
   | **Category** | Deployment / DevOps (or closest available) |
   | **Installation** | `curl -o ~/.claude/agents/demo-st.md "https://raw.githubusercontent.com/demo-stage/demo.st-Claude/main/demo-st.md"` |
   | **Usage** | "Use the demo-st agent to deploy this project to a live link" or "Publish the build to demo.st with subdomain my-app" |
   | **Prerequisites** | Claude Code with the demo.st MCP server configured and DEMO_ST_MCP_TOKEN set. Sign in at https://demo.st and add MCP URL https://demo.st/mcp with Authorization: Bearer \${env:DEMO_ST_MCP_TOKEN}. |

4. **Submit**  
   Submit the form. Once approved, the agent will appear in the marketplace.

## After submission

- Keep `demo-st.md` in this repo in sync with demo.st behavior (new tools or workflow changes).
- If the marketplace allows, add links to https://demo.st, https://demo.st/terms, https://demo.st/privacy in the listing.

## Reference

- **Claude Code Market:** https://www.ccmarket.dev/  
- **Claude Code MCP docs:** https://code.claude.com/docs/en/mcp  
- **demo.st MCP endpoint:** https://demo.st/mcp  
