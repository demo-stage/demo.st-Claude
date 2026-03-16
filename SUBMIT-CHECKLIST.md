# Submit to the official Claude Code plugin marketplace

Use the **official Anthropic** submission form (not third-party sites).

---

## 1. Open the submission form

Use either:

- **Console:** [platform.claude.com/plugins/submit](https://platform.claude.com/plugins/submit)
- **Claude.ai:** [claude.ai/settings/plugins/submit](https://claude.ai/settings/plugins/submit)

Sign in with your Anthropic account if prompted.

---

## 2. What to provide

This repo is a valid Claude Code **plugin**:

- **Plugin structure:** `.claude-plugin/plugin.json`, `agents/deploy.md`, `.mcp.json`
- **Repository URL:** `https://github.com/demo-stage/demo.st-Claude`
- **Name:** `demo-st`
- **Description:** Deploy static sites and demos to demo.st: reserve a subdomain, upload a zip, get a live link like yourproject.demo.st. Uses the demo.st MCP server.

The form may ask for the plugin source (e.g. GitHub repo URL). Use:

```
https://github.com/demo-stage/demo.st-Claude
```

---

## 3. After submitting

The team may review before listing. Once approved, the plugin will appear in Claude Code’s Discover tab and users can install it with `/plugin install demo-st` (or search by name).

---

**Reference:** [Create plugins](https://code.claude.com/docs/en/plugins) · [Submit your plugin to the official marketplace](https://code.claude.com/docs/en/plugins#submit-your-plugin-to-the-official-marketplace)
