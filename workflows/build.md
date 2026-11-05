# Build: Small Features and Verification Loops

Prerequisite: review START.md analysis and the user's key decisions. Follow RULES.md, including its language policy.
If key choices are unresolved, confirm only those needed to proceed.

1. State the current feature and completion criteria in one or two sentences.
2. Derive a small example's expected result from requirements, not from newly written code.
3. Reuse the existing stack and structure. First connect real input to final output with a minimal working feature.
4. Change only what is needed. UI work must preserve approved data contracts and calculations.
5. Use permitted test/run commands and safe temporary inputs without changing original materials.
6. On failure, inspect actual output and cause, make the smallest fix, then rerun the same case and regression tests.
7. Briefly report each major feature:
   - Actual files/functions and changes.
   - Small input → intermediate processing → output.
   - Choice rationale and limits.
   - Commands, expected results, actual results, and unverified items.
8. Offer an understanding check after important data processing, core calculations, or integration milestones.
   Do not pause for trivial edits. Stop if a decision outside the approved scope is required.

Do not decorate an empty screen with sample data and call it complete.
Verify essential features work before expanding scope.
Do not loosen requirements or discard hidden demand/rows merely to pass verification.
