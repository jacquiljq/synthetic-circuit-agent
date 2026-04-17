---
name: circuit-analysis
description: Use this when implementing or debugging symbolic or numeric pole-zero analysis for supported circuits.
---

Workflow:
1. Read AGENTS.md first.
2. Determine whether the circuit is supported by symbolic analysis, numeric analysis, or neither.
3. Prefer exact/symbolic analysis when the repository supports it for the topology.
4. Otherwise use the designated numeric or simulation-based path.
5. Never label approximate values as exact.
6. Record:
   - analysis method
   - assumptions
   - poles
   - zeros
   - failure mode if analysis is unsupported