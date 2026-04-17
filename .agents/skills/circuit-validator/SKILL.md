---
name: circuit-validator
description: Use this when checking whether a generated circuit is structurally and functionally plausible under repository rules.
---

Workflow:
1. Read AGENTS.md first.
2. Parse the netlist into the repository internal representation.
3. Check:
   - node/reference consistency
   - device count and connectivity sanity
   - topology-family compatibility
   - allowed-composition-rule compatibility
4. Flag ambiguous or unsupported circuits explicitly.
5. Do not mark a circuit valid unless rule-based checks pass.
6. Output a structured validation summary.