# Model and Reasoning Guide for Exam Tasks

Limit available models to **Sol 6.1, Terra 5.6, Luna 6, and Sol 6.0**.
Default: **Sol 6.1 + Medium**. Use **High** for design, difficult debugging, and core verification.
Consider **Luna 6 + High** for clear, small, repetitive tasks.

These task assignments are exam-oriented recommendations based on official model descriptions, not measured comparisons on this exam or score guarantees.
Adjust for the actual task, remaining time, response speed, and usage. Reference date: 2026-11-05.
Follow RULES.md, including its Korean policy for user-facing responses.

## Model Roles

| User label | Official model ID | Suggested role | Selection rationale |
|---|---|---|---|
| Sol 6.1 | `gpt-6.1-sol` | Requirements analysis, main implementation, complex debugging, final correctness checks | Default based on its official description for complex coding and professional work. [Official documentation](https://developers.openai.com/api/docs/models/gpt-6.1-sol) |
| Terra 5.6 | `gpt-5.6-terra` | Alternative for small implementations with settled specifications and document editing | Earlier generation balancing intelligence and cost. Choose when familiar or advantageous in the actual environment. [Official documentation](https://developers.openai.com/api/docs/models/gpt-5.6-terra) |
| Luna 6 | `gpt-6-luna` | Finding files, structured summaries, repetitive edits, narrow coding tasks | Efficient model for well-scoped repetitive work. [Official documentation](https://developers.openai.com/api/docs/models/gpt-6-luna) |
| Sol 6.0 | `gpt-6-sol` | Continuing existing work; implementation/verification alternative when Sol 6.1 is unavailable | Model for complex coding and agentic work. Keeping a productive existing session is also reasonable. [Official documentation](https://developers.openai.com/api/docs/models/gpt-6-sol) |

Do not reinterpret Terra 5.6 as Terra 6.1 or transfer the latest Terra's properties to it.
Do not infer that Terra 5.6 is cheaper or faster than Sol 6.1 from names alone.
Do not assume exam latency or usage policies match API pricing.

## Choosing a Reasoning Level

Here, Medium (`보통`) means `medium`, High means `high`, and Extra High means `xhigh`.
Official API documentation lists all three for these four models; separately check which options the exam UI exposes.

| Level | Suitable tasks | When to increase |
|---|---|---|
| Medium | Routine implementation with settled specifications, simple fixes, document editing | Use High when tracking multiple files, conditions, or states together, or checking important assumptions |
| High | Requirements interpretation, algorithm choices, joins/units/constraints, complex bugs | Use Extra High if sufficient reproduction evidence and requirements still leave difficult reasoning, and time permits |
| Extra High | Difficult algorithm counterexamples, calculations with interacting constraints, hard-to-isolate causes | Focus on one question; return to Medium or High once resolved |

Official documentation explains that higher reasoning levels can consume more time and tokens.
Use Extra High selectively when quality improvement justifies added latency.
[Official reasoning guidance](https://developers.openai.com/api/docs/guides/reasoning)

This kit starts Luna at High for narrow tasks, aligned with ChatGPT Work/Codex guidance.
Medium can be tried for simple extraction or formatting. The same reasoning label across models does not imply equal speed or capability.
[Model and reasoning selection](https://learn.chatgpt.com/docs/models)

## Quick Task Guide

These are exam starting points. Lower them for simple constraints or raise them for significant correctness risks.

| Task | Model | Reasoning | Scope and switching criteria |
|---|---|---|---|
| Locate files and run commands | Luna 6 | High | Extract locations/facts; switch to Sol 6.1 + High for requirements conflicts |
| Initial analysis, priorities, design choices | Sol 6.1 | High | Requirements and completion criteria in [START.md](START.md) |
| Inspect data structure, missingness, duplicates | Sol 6.1 | Medium | [Data skill](skills/data-audit/SKILL.md); High for join semantics, units, correction policies |
| Routine implementation within approved design | Sol 6.1 | Medium | [Build](workflows/build.md); High for cross-module state or contract changes |
| Small specified functions, repetitive edits | Luna 6 | High | Clear expected results and narrow changes; Terra 5.6 + Medium is an alternative |
| Core algorithms, optimization, constraints | Sol 6.1 | High | Extra High only for difficult, sufficiently specified problems; establish a small baseline first |
| Typos and obvious local bugs | Luna 6 | High | Clear reproduction and fix location; Sol 6.1 + High for unclear causes |
| Repeated failures and integration debugging | Sol 6.1 | High | Minimal reproduction → test hypotheses → smallest fix; gather missing evidence before increasing reasoning |
| Counterexamples, independent calculations, final correctness | Sol 6.1 | High | [Verify](workflows/verify.md); compare execution with a separate reference |
| UI wording, spacing, simple status displays | Luna 6 | High | Small edits with settled calculations and data contracts |
| Review UI/data/calculation/error integration | Sol 6.1 | High | Core flows in the [UI skill](skills/ui-review/SKILL.md) |
| README, summaries, explanation practice | Luna 6 | High | [Understand](workflows/understand.md); Sol 6.1 + High for algorithm guarantees/limits |
| Reconcile state and resume in a new session | Sol 6.1 | Medium | High if records, code, and execution evidence conflict |
| Final files, paths, formats | Sol 6.1 | Medium | [Finish](workflows/finish.md); High if result correctness issues emerge |

If Sol 6.1 is unavailable or slow in the environment, start with **Sol 6.0 + the same reasoning level** as an alternative.
This does not imply equivalent capability. Check results on a familiar small case.
Start Terra 5.6 at Medium for clear tasks and High for complex conditions, then assess results and time.
Preserve a productive main session's context rather than forcing a role for every model.

## Switching During the Exam

1. **Start:** Use Sol 6.1 + High for requirements, hard constraints, and the first implementation plan. Medium may suffice for simple tasks.
2. **Routine implementation:** Once the design is settled, use Sol 6.1 + Medium. Consider Luna 6 + High for short, separable tasks.
3. **Blocked:** First obtain failing input, expected output, and actual output. After two failures based on the same cause guess, use High to narrow the cause again. This threshold is a kit convention.
4. **Extra High:** Use when the question is clear, inputs/evidence are sufficient, and time remains to wait, fix, and verify. Resolve installation failures, missing files, and unclear requirements first.
5. **Finish:** Reduce scope based on user-provided remaining time. Prioritize essentials, critical bugs, core verification, and submission files over new model comparisons. Do not lower all verification indiscriminately when correctness needs deeper reasoning.

Switching models for another review is not independent verification. Separate expected results and actual tests are needed.
Do not start a new session for every short task. If needed, provide the [state template](templates/LOCAL_STATE.md), current code, and failing cases.

## How to Present Recommendations

At task start and when difficulty changes, give one line in Korean containing:
recommended model / reasoning level — reason; current settings (unconfirmed if unknown).
For example, recommend Sol 6.1 / High when table joins and units affect the final calculation, and mark current settings unconfirmed if unverifiable.

- Limit candidates to the four models above and reasoning options reported by the user or verified in the selection UI.
- Without evidence of current settings, mark them unconfirmed. Never record the recommendation as the current setting.
- Consider Medium for simple tasks and High for complex tasks, with Luna's starting-level exception above.
- Do not guess remaining time or usage. Still give task-based recommendations when that information is unavailable.
- Do not pause approved work or repeatedly ask permission to switch. If asked only for a recommendation, provide only that.
- Recommendations do not change settings. This kit does not automatically switch models or launch separate agents.

Use the available model/reasoning selection UI for actual changes; in Codex CLI, selection is available through `/model`.
A model name or "think deeply" in a prompt does not establish that settings changed.
[Official settings guidance](https://learn.chatgpt.com/docs/models)

## Brief Pre-Exam Check

Run a familiar small task with the same inputs and completion criteria to compare correctness, time, and fix counts.
Start with Sol 6.1 Medium/High and Luna 6 High; compare Terra 5.6 and Sol 6.0 if useful.
Do not spend preparation time testing every combination or generalize one task into a universal ranking.
Keep real check records in the actual workspace. Do not populate the public kit with exam inputs or results.
