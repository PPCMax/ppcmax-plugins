# PPCMax plugins

Plugin packages for ChatGPT, Codex, and Claude.

## Packages

- `plugins/ppcmax/` contains the OpenAI plugin package.
- `claude/plugins/ppcmax/` contains the Claude Code plugin package.
- `.agents/plugins/marketplace.json` is the OpenAI and Codex marketplace.
- `.claude-plugin/marketplace.json` is the Claude Code marketplace.

Both packages connect to `https://mcp.ppcmax.pro/mcp`. PPCMax tools and skills
remain canonical in the MCP server. The Claude Code package adds slash commands
that load those server-side skills; it does not carry its own copies of them.
