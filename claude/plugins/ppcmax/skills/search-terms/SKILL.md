---
description: Triage account-wide Google Ads search terms and account for every zloty of wasted spend
disable-model-invocation: true
---

Run the PPCMax account-wide search-term triage.

1. Resolve the account. If "$ARGUMENTS" names an account, match it against `listAccountLinks`. Otherwise call `listAccountLinks` and, when more than one link comes back, ask which account before going further.
2. Load the `triage-search-terms-claude` skill from the PPCMax server: read the resource `skill://triage-search-terms-claude/SKILL.md`, or call the `getSkill` tool with that name if this client cannot read MCP resources. This step is required, not optional.
3. Follow the loaded skill exactly. It owns the methodology, the coverage accounting and the gates that must pass before any exclusion. Do not substitute your own thresholds or shortcuts.
