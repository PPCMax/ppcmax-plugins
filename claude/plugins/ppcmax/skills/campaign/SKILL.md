---
description: Diagnose why a Google Ads campaign dropped or spiked, with evidence for and against each hypothesis
disable-model-invocation: true
---

Run the PPCMax campaign deep dive.

1. Resolve the account and the campaign. Read both from "$ARGUMENTS" when given. Call `listAccountLinks` for the account and `inspectCampaigns` to identify the campaign. Ask which campaign when the request is ambiguous.
2. Load the `campaign-deep-dive` skill from the PPCMax server: read the resource `skill://campaign-deep-dive/SKILL.md`, or call the `getSkill` tool with that name if this client cannot read MCP resources. This step is required, not optional.
3. Follow the loaded skill exactly. It owns which inspection sections to pull, how to rank hypotheses, and the requirement to name the data gaps you could not close.
