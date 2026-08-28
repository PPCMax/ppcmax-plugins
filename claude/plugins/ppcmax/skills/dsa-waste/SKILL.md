---
description: Hunt wasted Dynamic Search Ads spend and decide URL-level versus query-level exclusions
disable-model-invocation: true
---

Run the PPCMax Dynamic Search Ads waste hunt.

1. Resolve the account. If "$ARGUMENTS" names an account, match it against `listAccountLinks`. Otherwise call `listAccountLinks` and, when more than one link comes back, ask which account before going further.
2. Load the `dsa-waste-hunt` skill from the PPCMax server: read the resource `skill://dsa-waste-hunt/SKILL.md`, or call the `getSkill` tool with that name if this client cannot read MCP resources. This step is required, not optional.
3. Follow the loaded skill exactly. It owns the coverage accounting and the rule against double-counting URL-level and query-level waste.
