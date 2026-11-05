# Verify: Requirements, Calculations, Execution, and Display

Follow RULES.md, including its language policy. Default: do not edit source code or original data.
Create test-generated temporary files, caches, and local results only within permitted scope.
If verification cannot run, explain why and identify the unverified scope.

## Procedure

1. Compare essential requirements in the actual README with the current implementation.
2. Check command side effects, then run existing tests, builds, and small reproductions.
3. Check input parsing and transformation. Consult ../skills/data-audit/SKILL.md when relevant.
4. Cross-check important calculations with small independent examples: totals, units, denominators, constraints, and comparison conditions.
5. Check normal, boundary, invalid-input, and no-solution/no-result cases. Explain exclusions.
6. Check data preservation and UI integration. Code review alone does not confirm browser behavior.
7. If automated UI operation is prohibited, provide manual steps and expected results for the user.

## Report

Use Korean for the report, including table headings and status labels.

| Requirement/risk | Method/command | Expected result | Actual result/evidence | Status |
|---|---|---|---|---|
| Actual item only | Method executed | Requirements basis | Observed output | Confirmed/failed/unverified |

- Report failures with reproduction input, actual/expected results, relevant files/functions, and impact.
- If a fix is needed, pass the smallest proposed change to the main implementation session.
- After a fix, rerun the original failure and regression tests.
- Do not claim passing tests guarantee complete correctness or global optimality.
- Rereading numbers returned by the code is not independent calculation verification.
- Do not mark manual screen checks complete unless a person actually performed them.
