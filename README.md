# PPCMax plugins

Official plugin packages that connect PPCMax to Claude Code, Codex and ChatGPT.

PPCMax audits and optimizes Google Ads campaigns, improves Merchant Center
feeds, applies Tag Manager changes and analyzes Google Analytics data. Every
package in this repository is a thin connector to the hosted PPCMax MCP server
at `https://mcp.ppcmax.pro/mcp`, which owns the tools, the approval gates and
the workflow skills. Shipping a better workflow means shipping the server, so
you never reinstall to get it.

## Install

**Claude Code**

```bash
claude plugin marketplace add PPCMax/ppcmax-plugins
claude plugin install ppcmax@ppcmax
```

See [`claude/plugins/ppcmax/`](claude/plugins/ppcmax/) for the available
commands and the approval model.

**Codex**

Add this repository as a marketplace and install the `ppcmax` plugin. The Codex
package carries the branded manifest in
[`plugins/ppcmax/`](plugins/ppcmax/).

**ChatGPT**

PPCMax is submitted to the ChatGPT app directory from the same MCP endpoint.
Nothing to install from this repository.

## Requirements

A PPCMax account with at least one linked Google Ads or Merchant Center account.
Sign up at [ppcmax.pro](https://www.ppcmax.pro). Each host signs you in through
OAuth on first use. No package here asks for or stores credentials.

## Layout

| Path                                | Contents                              |
| ----------------------------------- | ------------------------------------- |
| `claude/plugins/ppcmax/`            | Claude Code plugin package            |
| `.claude-plugin/marketplace.json`   | Claude Code marketplace               |
| `plugins/ppcmax/`                   | OpenAI and Codex plugin package       |
| `.agents/plugins/marketplace.json`  | OpenAI and Codex marketplace          |

Each host keeps its own manifest and its own MCP configuration, because the
connection metadata they accept differs. None of them duplicates the skills the
MCP server already serves.

## Links

- Website: [ppcmax.pro](https://www.ppcmax.pro)
- Privacy policy: [ppcmax.pro/pl/privacy-policy](https://www.ppcmax.pro/pl/privacy-policy)
- Terms of service: [ppcmax.pro/pl/terms-of-service](https://www.ppcmax.pro/pl/terms-of-service)

## License

Apache-2.0. See [`LICENSE`](LICENSE) and [`NOTICE`](NOTICE).

The license covers the plugin packages in this repository. Use of the hosted
PPCMax service is governed by the terms of service linked above. The PPCMax name
and logos are trademarks of Catchy Media Sp. z o.o. and are not part of the
license grant.
