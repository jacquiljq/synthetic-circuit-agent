---
name: circuit-generator
description: Use this when implementing or extending topology-template-based analog circuit generation for this repository.
---

Workflow:
1. Read AGENTS.md first.
2. Identify target topology family or allowed composition rule.
3. Prefer editing templates or composition rules over adding free-form generation.
4. Ensure generated output can be serialized to the repository netlist format.
5. Do not finalize generation logic without structural validation hooks.
6. Summarize:
   - topology family covered
   - files changed
   - constraints assumed
   - validation path