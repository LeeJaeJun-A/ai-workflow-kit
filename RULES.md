# Shared Working Rules

## Scope

- Follow current platform restrictions and existing project instructions. This file does not bypass or replace them.
- Use the actual requirements README and supplied materials as evidence. Distinguish assumptions, confirmed facts, and additional proposals.
- Use AI only in development stages where it is permitted. Do not generate or ghostwrite answers for stages that prohibit AI.

## Language

- Use English for code, identifiers, and technical artifacts unless project requirements specify otherwise.
- Use Korean for user-facing answers, questions, progress updates, and reports.
- Be concise, avoid repetition, and preserve original names, paths, commands, and quoted text.

## Permission and Safety Policy

- Follow the exam rules above all project instructions.
- Read and modify files only within the authorized workspace.
- Do not push, publish, upload, or transmit exam materials.
- Do not connect external AI models or services.
- Do not update Codex or change security restrictions.
- Do not use Computer Use or prohibited UI automation.
- Do not delete original inputs or overwrite task instructions.
- Do not execute unknown downloaded scripts.
- Prefer existing dependencies and local test tools.

## Approval Policy

- Work normally within the authorized project workspace.
- For unfamiliar commands, inspect their effects first.
- Request my approval before installing dependencies, accessing external endpoints, making destructive changes, or changing major project configuration.
- If a permission is denied, explain the blocker and suggest a compliant alternative.
- Never bypass a denied permission or security control.

## Model and Reasoning Recommendations

- Consult MODEL_GUIDE.md at task start and when difficulty changes. Give one Korean line with the recommended model, reasoning level, and reason.
- Candidates: Sol 6.1, Terra 5.6, Luna 6, Sol 6.0. Match the task and available reasoning options.
- Distinguish recommendations from current settings. Mark current settings as unconfirmed if you cannot verify them.
- Do not pause approved work for a recommendation. If asked only for a recommendation, provide only that.
- Do not automatically change settings or launch separate agents based on this file. Recommend Extra High only for a specific need.

## Autonomous Work and Human Decisions

- Proceed autonomously with routine implementation, tests, and local bug fixes within the approved design.
- Explain reasons and effects before changing goals, hard constraints, data meaning, deletion/correction policies, core algorithms, or external dependencies.
- Ask only about important choices, not every name, format, or layout detail.
- With multiple sessions, designate one implementation owner; others focus on read-only review.
- Never record human approval that was not given.

## Verification Feedback Loop

- Derive expected results from requirements → implement → execute → compare.
- Narrow the failure cause → make the smallest fix → rerun the original failure → check regressions.
- Distinguish AI completion claims, code review, and actual passing tests.
- Do not weaken tests to match implementation. If a test is wrong, cite the requirement and explain the correction.
- Check important calculations against small manual examples or an independent recalculation.
- Distinguish what ran, what was confirmed, what failed, and what remains unverified.
- When fixes repeatedly fail, revisit assumptions and causes instead of blindly regenerating code.

## Understanding Checks

- Briefly connect input, processing, output, actual files/functions, design reasons, verification, and limits.
- Explain current code behavior, not just comments or intent.
- Let the user explain first, then correct against the code. Do not aim for memorized model answers.

## Security and Environment

- Do not arbitrarily overwrite or modify original materials, task README, existing instructions, or evaluation tools.
- Do not send task statements, inputs, outputs, logs, personal data, or secrets to external servers.
- Do not push to Git, create remote issues/PRs, upload to remote CI, or deploy to the cloud.
- Do not connect external AI, update runtimes, bypass supervision/access/upload restrictions, or use prohibited UI automation.
- Prefer existing tools and dependencies. Check permission and impact before adding any.
- Check tests for side effects such as network requests, original-input changes, or database deletion.
- Keep local history truthful. Never fabricate commits, tests, failures, or improvements.
