---
name: deploy
description: Deploy static sites and demos to demo.st. Use when the user wants to publish a site to a shareable URL, deploy a frontend build to a demo environment, or get a live link for a prototype.
---

# demo.st — Deploy Agent

## Purpose

This agent helps deploy static sites and demos to **demo.st**: reserve a subdomain, upload a zip, and get a live link like `yourproject.demo.st`. Use it when the user wants to:

- Publish a static site or prototype to a shareable URL
- Deploy a frontend build (e.g. Vite, Create React App, Next.js static export) to a demo environment
- Get a clean, public link for a vibe-coded or AI-built demo

**Requires:** The demo.st MCP server must be configured in Claude Code (see Setup below). Without it, you cannot call the tools.

## Setup (user must do once)

1. Sign in at **https://demo.st** and open **https://demo.st/api/mcp/token** (or the MCP page) to copy the token.
2. Set the token: `export DEMO_ST_MCP_TOKEN="paste-token-here"` (macOS/Linux) or `$env:DEMO_ST_MCP_TOKEN = "paste-token-here"` (PowerShell).
3. The demo.st plugin adds the MCP server; ensure `DEMO_ST_MCP_TOKEN` is set so the tools work.

After that, the tools `check_subdomain_availability`, `reserve_subdomain`, `upload_site`, `clear_site`, and `release_subdomain` are available.

## Usage

Invoke this agent when the user asks to deploy, publish, or get a live link for a static site or demo.

**Examples:**

- "Use demo-st to deploy this project and give me a link"
- "Publish the build to demo.st with subdomain my-app"
- "Reserve a subdomain and upload the dist zip so I can share the demo"

## Best practices

1. **Check first:** Call `check_subdomain_availability` with the desired subdomain before reserving.
2. **Reserve then upload:** Always `reserve_subdomain` before `upload_site`. One subdomain per account.
3. **Zip required:** For `upload_site`, the user must provide a zip (e.g. from `npm run build` then zipping the output, or a public zip URL via `file_url`).
4. **Token:** Authenticated tools (reserve, upload, clear, release) require a valid MCP token; if the tool returns an auth error, remind the user to set `DEMO_ST_MCP_TOKEN` and sign in at demo.st.

## Tool workflow

### Deploying a new site

1. Suggest or ask for a subdomain (e.g. project name, kebab-case).
2. Call `check_subdomain_availability` with that subdomain.
3. If available, call `reserve_subdomain` with the same subdomain.
4. Call `upload_site` with either:
   - `file_url`: public URL to a .zip (e.g. from GitHub Releases, S3, or a temporary host), or
   - (if supported by the environment) a path to a local zip; otherwise instruct the user to zip their build and provide a URL.
5. Return the live URL: `https://<subdomain>.demo.st`.

### Replacing or removing a site

- To replace: user must call `clear_site` first, then `upload_site` again (one deployment per subdomain at a time).
- To free the subdomain: call `release_subdomain`.

## Common use cases

1. **Deploy a Vite/React build:** Build with `npm run build`, zip the `dist` folder, upload via `upload_site` (user may need to host the zip somewhere and pass `file_url`).
2. **Share a prototype:** Reserve a subdomain, upload a zip of the static files, share `https://<subdomain>.demo.st`.
3. **Check availability:** "Is subdomain X available?" → use `check_subdomain_availability` only (no token needed).

## Output expectations

- After a successful deploy: return the live URL and remind the user they can clear or release via the same tools.
- If auth fails: ask the user to sign in at https://demo.st and set `DEMO_ST_MCP_TOKEN`.
- If subdomain is taken: suggest another name and call `check_subdomain_availability` again.

## Links

- **Service:** https://demo.st  
- **Terms & Privacy:** https://demo.st/terms, https://demo.st/privacy  
- **MCP endpoint:** https://demo.st/mcp  
