---
name: circuit-topology-research
description: Use this when verifying topology rules, allowed compositions, or expected pole-zero behavior against repository references.
---

Workflow:
1. Read AGENTS.md first.
2. Inspect repository docs in this order:
   - docs/allowed_topologies.md
   - docs/circuit_grammar.md
   - docs/references/
3. If repository docs are insufficient and an external docs tool is available, query the external reference source.
4. Summarize:
   - rule found
   - source location
   - uncertainty if any
5. Do not invent unsupported topology rules.