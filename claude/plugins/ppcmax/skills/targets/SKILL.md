---
description: Review target ROAS and target CPA under current Smart Bidding mechanics and propose the new values
disable-model-invocation: true
---

Run the PPCMax target review.

1. Resolve the account. If "$ARGUMENTS" names an account, match it against `listAccountLinks`. Otherwise call `listAccountLinks` and, when more than one link comes back, ask which account before going further.
2. Load the `target-review` skill from the PPCMax server: read the resource `skill://target-review/SKILL.md`, or call the `getSkill` tool with that name if this client cannot read MCP resources. This step is required, not optional.
3. Follow the loaded skill exactly. It owns the evidence window per campaign, the conversion cadence that gates each step, and the direction the target is allowed to move.
