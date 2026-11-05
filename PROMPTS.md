# 시험 중 바로 쓰는 프롬프트

`ai-workflow-kit/`은 실제 키트 경로로, 대괄호 부분은 현재 작업의 값으로 바꾼다.
복사할 요청문은 영어이며, 사용자에게 보여주는 답변·질문·진행 보고는 한국어로 받습니다.
독립 실행과 새 세션에서도 RULES.md의 언어 지침을 따릅니다.
모델 추천은 [MODEL_GUIDE.md](MODEL_GUIDE.md)의 시험용 시작값이다. 실제 모델·사고 수준은 선택 UI에서 설정한다.
사용 가능한 모델은 Sol 6.1, Terra 5.6, Luna 6, Sol 6.0이다.

## 1. 작업별 모델 추천 켜기

현재 대화에서 한 번 전달하고, 새 세션에서는 다시 전달한다.
START.md로 시작한 세션은 공통 원칙을 통해 이 규칙을 함께 읽는다.

```text
Read ai-workflow-kit/MODEL_GUIDE.md.
At task start or when difficulty changes, give one Korean line with the recommended model, reasoning level, and reason.
Limit candidates to Sol 6.1, Terra 5.6, Luna 6, and Sol 6.0.
If current settings cannot be verified, mark them unconfirmed. Do not pause approved work for recommendations.
Do not claim settings changed. Explain Extra High only when needed.
Use Korean for user-facing answers, questions, progress updates, and reports; keep them concise.
```

모델 선택만 먼저 받고 싶을 때:

```text
Using ai-workflow-kit/MODEL_GUIDE.md, recommend only a model and reasoning level for this task.
Task: [task description]
Remaining time: [N minutes or unknown]
Current settings: [model / reasoning level or unknown]
In Korean, give one combination, one sentence explaining why, and one condition for a higher reasoning level.
```

## 2. 시험 시작 — Sol 6.1 / High

```text
Read ai-workflow-kit/START.md and analyze only, using [actual task README path].
Remaining time: [N minutes]. Recommend a model and reasoning level in one line.
Map essential requirements → completion criteria → verification methods.
Propose a minimal implementation from input to final output and the work order.
Use published scoring criteria if available; do not invent them.
Reserve time for verification and submission preparation. Ask at most three important decision questions.
```

## 3. 승인한 기능 구현 — Sol 6.1 / 보통

```text
Read ai-workflow-kit/workflows/build.md and implement.
My approved key choices: [decisions and scope]
Completion criteria for this step: [behavior to verify from input to output]
Use the existing stack to connect a small working flow, then run real tests → make minimal fixes → reverify.
Recommend High in one line if module contracts or core calculations make it useful.
```

## 4. 오류가 반복될 때 — Sol 6.1 / High

```text
Follow ai-workflow-kit/RULES.md. Reproduce and fix this error within the approved scope.
Error or failing case: [relevant details or local file path]
Establish minimal reproduction input and command. Form at most three cause hypotheses.
First run checks that distinguish the hypotheses; make minimal changes supported by evidence.
Rerun the original failure and relevant regression tests.
If you cannot reproduce it, report missing evidence rather than making speculative changes.
Recommend Extra High only if sufficient evidence still leaves a difficult reasoning problem.
```

## 5. 반례와 결과 검증 — Sol 6.1 / High

```text
Read ai-workflow-kit/workflows/verify.md and verify. Do not edit source code.
Derive expected results from requirements and find counterexamples that could break the implementation.
Select relevant boundary, empty-input, duplicate, reordered-input, and no-solution cases.
Cross-check core calculations using small manual examples or separate simple calculations.
Report failures with reproduction input, expected result, actual result, and code location.
Leave unexecuted checks marked unverified.
```

## 6. 새 세션에서 이어가기 — Sol 6.1 / 보통

```text
Read ai-workflow-kit/RULES.md and [actual local state record path].
Your role: [main implementation / read-focused review].
Compare requirements, approved choices, current code, and execution records. Do not assume old records are accurate.
If consistent, continue the next approved task. If there is an important conflict, confirm only the affected decision.
Do not redesign everything from scratch. Recommend a model and reasoning level in one line.
```

## 7. 마감 직전 — Sol 6.1 / 보통, 정확성 문제는 High

```text
Read ai-workflow-kit/workflows/finish.md and check submission readiness. Remaining time: [N minutes].
Prioritize missing essential features, execution failures, incorrect results, then submission format errors.
Make minimal fixes for critical issues within approved scope and rerun core verification.
Defer new features and large refactors. Identify incomplete/unverified items and exact files to submit.
```
