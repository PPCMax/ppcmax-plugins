---
description: Review Google Ads daily budgets and decide where to raise, hold or cut
disable-model-invocation: true
---

Run the PPCMax budget review.

1. Resolve the account. If "$ARGUMENTS" names an account, match it against `listAccountLinks`. Otherwise call `listAccountLinks` and, when more than one link comes back, ask which account before going further.
2. Load the `budget-review` skill from the PPCMax server: read the resource `skill://budget-review/SKILL.md`, or call the `getSkill` tool with that name if this client cannot read MCP resources. This step is required, not optional.
3. Follow the loaded skill exactly. It owns the test for a genuinely binding budget and the plan arithmetic every recommendation has to carry.
