# PPCMax for Claude Code

Audit and optimize Google Ads campaigns, improve Merchant Center feeds, apply Tag
Manager changes and analyze Google Analytics data without leaving Claude Code.

The plugin connects Claude Code to the hosted PPCMax MCP server at
`https://mcp.ppcmax.pro/mcp`. Tools, approval gates and workflow methodologies
live on the server, so the plugin stays a thin connector and every user gets the
current behavior without reinstalling.

## Requirements

- A PPCMax account with at least one linked Google Ads or Merchant Center
  account. Sign up at [ppcmax.pro](https://www.ppcmax.pro).
- Claude Code signs you in through OAuth on first use. The plugin never asks for
  and never stores credentials.

## Install

```bash
claude plugin marketplace add PPCMax/ppcmax-plugins
claude plugin install ppcmax@ppcmax
```

Then run any command below. Claude Code opens the PPCMax sign-in the first time a
tool is called.

## Commands

| Command                  | What it does                                                                        |
| ------------------------ | ----------------------------------------------------------------------------------- |
| `/ppcmax:search-terms`   | Account-wide search-term triage that accounts for every zloty of wasted spend        |
| `/ppcmax:dsa-waste`      | Dynamic Search Ads waste hunt, URL-level versus query-level exclusions               |
| `/ppcmax:campaign`       | Deep dive into why a campaign dropped or spiked, with evidence for and against       |
| `/ppcmax:targets`        | Target ROAS and target CPA review, gated by conversion cadence                       |
| `/ppcmax:budgets`        | Daily-budget review that separates binding budgets from bleeds                       |

Each command takes an optional account or campaign name, for example
`/ppcmax:budgets acme-store`. Without one, Claude asks which account to use when
you have more than one linked.

You do not have to use the commands. The tools are available to Claude directly,
so plain requests like "find wasted spend in my Ads account" work too. The
commands exist to start the tested workflow rather than an ad-hoc one.

## How the workflows are maintained

The commands are entry points, not methodology. Each one loads its workflow from
the PPCMax server over the MCP skills extension (`skill://<name>/SKILL.md`) and
follows it. Improving a workflow means shipping the server, not shipping the
plugin.

## Writes and approvals

Read-only tools run freely. Every write is gated:

- Google Ads writes are validated against the provider before they are applied,
  and are applied in full or not at all.
- Merchant Center, product feed, agent configuration and memory tools have no
  provider-side dry run, so the first attempt is the real one. Claude asks for
  your approval before calling them.
- Where a tool accepts a schedule, ask for the change later and it is queued
  instead of executed now.

## Links

- Website: [ppcmax.pro](https://www.ppcmax.pro)
- Privacy policy: [ppcmax.pro/pl/privacy-policy](https://www.ppcmax.pro/pl/privacy-policy)
- Terms of service: [ppcmax.pro/pl/terms-of-service](https://www.ppcmax.pro/pl/terms-of-service)

## License

The plugin package in this directory is covered by `LICENSE` at the repository
root. Use of the PPCMax service itself is governed by the terms of service linked
above. The PPCMax name and logos are not covered by that license.
