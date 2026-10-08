# PPCMax plugins

Official plugin packages that connect PPCMax to Claude Code, Codex and ChatGPT.

PPCMax audits and optimizes Google Ads campaigns, improves Merchant Center
feeds, applies Tag Manager changes and analyzes Google Analytics data. Every
package in this repository is a thin connector to the hosted PPCMax MCP server
at `https://mcp.ppcmax.pro/mcp`, which owns the tools, the approval gates and
the workflow skills. Workflow logic is maintained on the server. Clients may
cache tool definitions; OpenAI submissions must scan the current endpoint before
review.

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

A PPCMax account with MCP Access enabled and at least one linked Google Ads or
Merchant Center account.
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

## Refresh the OpenAI submission

The OpenAI package is version `1.1.0`. `chatgpt-app-submission.json` reflects
135 tools from PPCMax main `ccf34ddf594a`
(2026-10-08), including workspace discovery, image uploads, negative keyword
conflict checks and scheduled tool calls. It is a review
snapshot, not the runtime tool registry.

1. Open the existing PPCMax draft at [OpenAI Plugins](https://platform.openai.com/plugins).
2. Scan `https://mcp.ppcmax.pro/mcp` with OAuth access and compare the imported
   tools against `chatgpt-app-submission.json`.
3. Import that JSON to refresh tool annotations and the five positive and three
   negative review scenarios. The scenarios describe expected behavior; importing
   the file does not execute them.
4. Check reviewer access, the demo recording and remaining portal requirements.
   Keep reviewer credentials out of this repository and release archives.
5. Submit the saved draft for review. Approval and publication are separate
   portal states; updating this repository does not complete either one.

Resolve account scope with `ppcmax_list_workspaces` and pass its `workspaceId`
to scoped tools. Load bundled workflows with `utils_get_ppcmax_skill`; before the
first workspace read, load saved preferences with `utils_list_memories`.

See [OpenAI submission guidance](https://developers.openai.com/plugins/deploy/submission)
for the current update flow. The Claude package has its own release version.

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
