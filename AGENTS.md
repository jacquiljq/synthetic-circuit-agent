# AGENTS.md

## Project
This repository builds a synthetic circuit generation agent for analog amplifier datasets.

The system must:
- generate valid circuit netlists
- cover required single-stage amplifier families
- generate reasonable composite circuits derived from these basic blocks
- compute or estimate poles and zeros when supported
- record outputs in a structured dataset format

## Primary circuit families
Required base families:
- Common Source Stage
- Source Follower
- Common-Gate Stage
- Cascode Stage

## Allowed extensions
The generator may create composite circuits by:
- adding passive elements such as resistors and capacitors
- adding source degeneration or load variants
- adding coupling, bypass, or compensation capacitors
- combining valid stage blocks into larger amplifier circuits
- adding simple conductance / admittance-like passive substructures where meaningful

## Hard rules
- Do not generate a circuit unless it can be mapped to a known topology family or an allowed composition rule.
- Do not emit a final netlist before running structural validation.
- Do not claim poles/zeros are exact unless produced by the designated analysis pipeline.
- Do not silently skip failed analysis; record failure mode explicitly.
- Prefer constrained template-based generation over free-form generation.

## Engineering guidance
- Keep topology templates separate from composition logic.
- Keep structural validation separate from numerical/symbolic analysis.
- Use deterministic scripts for dataset building when possible.
- Minimize broad refactors unless explicitly requested.

## File routing guidance
For topology generation tasks, inspect:
1. src/synthckt/templates/
2. src/synthckt/composition/
3. docs/circuit_grammar.md
4. docs/allowed_topologies.md

For validation tasks, inspect:
1. src/synthckt/validation/
2. tests/test_validation.py
3. docs/output_schema.md

For poles/zeros analysis tasks, inspect:
1. src/synthckt/analysis/
2. docs/references/pole_zero_notes.md

## Validation workflow
Before accepting generated circuits:
1. topology-family check
2. node/connectivity sanity check
3. transistor-role sanity check
4. analysis feasibility check
5. poles/zeros computation or explicit failure logging

## Done means
A task is done only if:
- changed files are summarized
- assumptions are stated
- validation path is described
- output schema compatibility is preserved