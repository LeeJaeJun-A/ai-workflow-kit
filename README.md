# AI Workflow Kit

요구사항을 읽고, 사람이 중요한 설계를 결정한 뒤, AI로 구현·검증하는 범용 Markdown 작업 템플릿입니다.
완성된 서비스, 특정 과제의 해답, 실제 데이터, 외부 모델 호출, 설치 스크립트는 포함하지 않습니다.

## 언어 정책

AI가 읽는 지침과 복사해서 쓰는 프롬프트는 영어로 작성했습니다.
답변·질문·진행 보고는 한국어로 받으며, 코드·식별자·기술 산출물은 프로젝트 요구가 없으면 영어를 사용합니다.
영어와 한국어 작업 이름을 모두 쓸 수 있습니다. 사용자용 설명은 한국어로 유지합니다.

## 빠른 시작

허용된 방식으로 프로젝트 작업 공간의 별도 `ai-workflow-kit/` 폴더에 가져온 뒤 다음처럼 요청합니다.

```text
Read ai-workflow-kit/START.md and analyze only, using the actual task README.
```

과제의 README와 이 저장소의 README를 혼동하지 않도록, 과제 파일의 위치를 먼저 확인하게 합니다.
프로젝트의 기존 README, AGENTS.md, 설정, 원본 데이터를 덮어쓰지 않습니다.

설계를 확인한 뒤에는 아래처럼 짧게 요청합니다. 이 말들은 Codex 내장 명령어가 아니라,
`START.md`에서 정의한 자연어 작업 이름입니다.

| 말할 내용 | 동작 |
|---|---|
| `build. [approved key choices]` / `구현` | 승인된 설계로 작은 기능 구현 → 테스트 → 수정 → 재검증 |
| `verify` / `검증` | 요구사항·계산·실행·화면 연결을 점검. 기본적으로 코드 수정은 하지 않음 |
| `understand` / `이해` | 실제 코드에 근거한 질문 하나. 먼저 답을 보여주지 않음 |
| `finish` / `마감` | 제출 형식, 실행 가능 여부, 미해결 사항 확인. 제출 자체는 하지 않음 |

큰 설계 변경이 없으면 모든 소소한 코딩 작업마다 승인을 요청하지 않습니다.
다만 데이터 의미·목표·필수 제약·핵심 알고리즘 변경은 사람이 확인합니다.

## 시작 이후 프롬프트 예시

같은 대화에서는 **작업 이름 + 이번 범위 + 완료 조건**을 전달하면 됩니다.
`START.md`는 시작점이며, 그 안에서 참조하는 공통 원칙과 실제 과제 문서도 읽도록 합니다.
매번 전체 지침을 붙일 필요는 없습니다. 아래 예시의 기능과 시간은 실제 작업에 맞게 바꿉니다.

### 1. 분석 결과를 확인한 뒤 구현

분석에서 제안한 중요한 선택을 정하고, 이번에 어디까지 동작해야 하는지 적습니다.

```text
build.
Use option A from your analysis as my approved key choice.
Implement file upload → data processing → result display.
Complete when one real input works end to end and relevant tests pass.
If tests fail, identify the cause, fix it, and reverify.
```

### 2. 구현 결과 검증과 문제 수정

```text
verify.
Compare the actual README's essential requirements with the current implementation.
Run normal-input and important boundary cases.
Report failures with reproduction input, expected/actual results, and code location.
Do not edit source code.
```

문제가 발견되면 수정 범위를 지정해 이어갑니다.

```text
build.
Fix the issues found in the latest verification.
Rerun the original failures and relevant regression tests.
```

### 3. 필요한 기능 추가

```text
build.
Add search and sorting to the result list.
Keep sorting after search and show a message when no results match.
Preserve existing calculation results.
```

### 4. 실제 코드 이해

```text
understand.
Start with the core data-processing flow.
Ask one question at a time based on actual code.
After my answer, explain missing points.
```

### 5. 마감 점검

```text
finish.
Remaining time: 20 minutes.
Check missing essential features, execution errors, and submission format.
Make minimal fixes for critical issues within approved scope and reverify.
List files to submit and incomplete/unverified items.
```

일반적인 순서는 **분석 → 선택하고 구현 → 검증 → 문제 수정 → 마감**입니다.
새 세션에서는 이전 대화를 기억한다고 가정하지 말고,
[PROMPTS.md](PROMPTS.md)의 새 세션 이어가기 예시로 공통 원칙과 실제 작업 기록 경로를 지정합니다.
단계별 상세 프롬프트도 같은 문서에서 복사해 쓸 수 있습니다.

## 작업별 모델과 사고 수준

[MODEL_GUIDE.md](MODEL_GUIDE.md)에 **Sol 6.1, Terra 5.6, Luna 6, Sol 6.0**의 작업별 추천과 전환 기준을 정리했습니다.
시험용 기본 추천은 Sol 6.1 + 보통, 설계·복잡한 오류·핵심 검증은 High, 좁은 반복 작업은 Luna 6 + High입니다.
Extra High는 충분한 근거와 시간이 있는 어려운 문제에 선택적으로 사용합니다.

START.md나 공통 원칙을 읽은 AI는 작업 시작과 난도 변화 시 추천을 한 줄로 안내합니다.
이는 설정 변경이 아니며, 실제 모델·사고 수준은 사용 가능한 선택 UI에서 지정합니다.
[PROMPTS.md](PROMPTS.md)에서 모델 추천, 시험 시작, 구현, 오류 해결, 반례 검증, 세션 재개, 마감 요청을 복사해 쓸 수 있습니다.

## 구성

```text
ai-workflow-kit/
├── README.md
├── START.md
├── RULES.md
├── MODEL_GUIDE.md
├── PROMPTS.md
├── workflows/
│   ├── build.md
│   ├── verify.md
│   ├── understand.md
│   └── finish.md
├── skills/
│   ├── data-audit/SKILL.md
│   └── ui-review/SKILL.md
├── templates/
│   └── LOCAL_STATE.md
├── SOURCES.md
└── .gitignore
```

## 스킬 사용 방식

기본 모드는 **파일 경로를 명시해서 읽는 방식**입니다. 스킬 설치, 플러그인, MCP, 새 CLI가 필요하지 않습니다.
`skills/`를 특정 프로젝트 아래에 내려받았다고 Codex가 자동으로 발견한다고 가정하지 않습니다.

```text
Read ai-workflow-kit/skills/data-audit/SKILL.md and inspect only the supplied data.
Do not change original inputs.
```

```text
Review the current UI code using ai-workflow-kit/skills/ui-review/SKILL.md.
Do not automate the browser. Provide any necessary manual verification steps.
```

현재 일반 Codex의 정식 스킬 등록 경로는 프로젝트의 `.agents/skills/<skill-name>/SKILL.md` 등입니다.
정식 등록은 환경이 지원하고 수정이 허용될 때만 선택적으로 수행합니다.
기존 파일과 충돌 여부를 먼저 확인하고, 인식되지 않는다고 런타임을 업데이트하지 않습니다.
문서 경로 읽기와 정식 스킬 자동 등록은 서로 다른 방식입니다.

## 실전 사용 전 확인

공개 저장소를 쓸 수 있다는 사실만으로 모든 내용·도구·사용 시점이 허용되지는 않습니다.
해당 환경의 최신 안내와 기존 지침을 우선합니다. AI를 사용할 수 없는 단계에서는 이 키트를 사용하지 않습니다.

공개본에는 범용 지침과 빈 템플릿만 둡니다. 비공개 문제·업무 정보·실제 입력 파일·개인정보·결과물·로그·답변을 넣지 않습니다.
프로젝트에서 채운 작업 기록은 이 공개 저장소에 돌려보내지 않습니다.
`.gitignore`는 실수를 줄이는 보조 수단일 뿐, 외부 전송 방지 장치가 아닙니다.

가능하면 사용하려는 공개본의 커밋이나 버전을 기록하고, 실제 사용 전에 스스로 내용을 읽어 봅니다.
새 저장소로 공개할 때에는 압축파일 자체만 올리지 말고 압축을 풀어 폴더 구조를 유지합니다.

## 기존 UI 스킬과 함께 사용

이미 검토한 UI 스킬이 있으면 중복 설치하지 않고 그 역할을 유지할 수 있습니다.
외부 스킬을 추가할 때에는 출처·버전·참조 파일·실행 스크립트·네트워크 의존성을 확인합니다.
이 저장소는 외부 스킬이나 그 라이선스 파일을 재배포하지 않습니다.
UI 작업은 승인된 데이터 계약·계산·필수 제약을 변경하지 않게 합니다.

## 한계

이 키트는 사람이 승인하고 실행 결과를 확인하는 개발 절차를 정리한 문서입니다.
기능적 정확성, 평가 점수, 특정 관리형 플랫폼에서의 실행이나 허용 여부를 보장하지 않습니다.
검증기는 프로젝트의 실제 요구사항과 실행 환경에 맞춰 구현해야 합니다.
