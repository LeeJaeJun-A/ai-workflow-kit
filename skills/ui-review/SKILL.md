---
name: local-ui-review
description: Review an existing local UI against approved inputs, calculations, error states and user tasks. Do not redesign the algorithm, install a frontend stack, operate a browser automatically, or claim unobserved screen behavior.
---

# Task UI Review

If an existing UI skill is available, focus on review rather than duplicating it. Follow the actual README and RULES.md, including its language policy.

1. Connect the user's core tasks with screen inputs and results.
2. Verify the UI connects to real input flows and calculation results rather than sample data alone.
3. Check loading, empty, invalid-input, calculation-failure, and no-result states.
4. Check that units, reference dates, comparison conditions, estimates versus measurements, and metric meanings are clear.
5. Ensure recalculation does not present stale results as current.
6. Inspect labels, keyboard access, and alternatives to color-only status indicators at code level.
7. Preserve the existing stack and propose only necessary small changes.

## Verification and Boundaries

- Distinguish source review, build/component tests, and screens actually checked by a person.
- Do not automate browser operation. Provide manual steps and expected results when needed.
- UI work does not authorize changes to formulas, data deletion, hard constraints, or core algorithms.
- Do not automatically add external fonts, icons, maps, analytics services, or installations.
- Prioritize correctness, core user flows, and error communication before decoration.
