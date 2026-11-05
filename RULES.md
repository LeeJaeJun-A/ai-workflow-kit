# 공통 작업 원칙

## 적용 범위

- 플랫폼의 최신 제한과 프로젝트 기존 지침을 따른다. 이 문서는 이를 우회하거나 대체하지 않는다.
- 요구사항의 근거는 실제 README와 제공 자료다. 가정·확인된 사실·추가 제안을 구분한다.
- AI 사용이 허용된 개발 단계에서만 사용한다. AI 금지 단계의 답안을 생성하거나 대리 작성하지 않는다.

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
- Request my approval before installing dependencies,
  accessing external endpoints, making destructive changes,
  or changing major project configuration.
- If a permission is denied, explain the blocker and suggest
  a compliant alternative.
- Never bypass a denied permission or security control.

## 작업별 모델·사고 수준 추천

- 이 키트의 MODEL_GUIDE.md를 참고해 작업 시작과 난도 변화 시 `추천: 모델 / 사고 수준 — 이유`를 한 줄로 안내한다.
- 후보는 Sol 6.1, Terra 5.6, Luna 6, Sol 6.0이다. 각 작업과 실제로 제공되는 사고 옵션에 맞춰 추천한다.
- 추천과 현재 설정을 구분한다. 현재 설정을 확인할 수 없으면 미확인으로 표시한다.
- 추천 때문에 승인된 작업을 멈추지 않는다. 모델 추천만 요청받은 경우에는 추천만 한다.
- 이 문서를 근거로 설정을 자동 변경하거나 별도 에이전트를 실행하지 않는다. Extra High는 구체적인 필요가 있을 때 추천한다.

## 자율 작업과 사람의 결정

- 승인된 설계의 일반 구현·테스트·국소 버그 수정은 자율적으로 진행할 수 있다.
- 목표, 하드 제약, 데이터 의미, 삭제·보정 정책, 핵심 알고리즘, 외부 의존성을 바꾸려면 이유와 영향을 먼저 제시한다.
- 중요한 선택만 묻는다. 사소한 이름·서식·배치마다 승인을 요구하지 않는다.
- 여러 세션은 하나의 구현 책임자를 두고 나머지는 읽기 중심으로 검토한다.
- 사람의 승인이 없는데 승인했다고 기록하지 않는다.

## 검증 피드백 루프

- 요구사항에서 기대 결과를 정한다 → 구현한다 → 실제 실행한다 → 차이를 확인한다.
- 실패 원인을 좁힌다 → 최소 수정한다 → 원래 실패 사례를 재실행한다 → 기존 기능을 회귀 검증한다.
- AI의 완료 보고, 코드 검토, 실제 테스트 통과는 서로 다르다. 구분해서 보고한다.
- 테스트를 구현에 맞추어 약화하지 않는다. 테스트가 틀렸으면 요구사항 근거와 변경 이유를 명시한다.
- 중요한 계산은 작은 수작업 사례나 독립적인 재계산 경로와 대조한다.
- 실행한 것, 확인한 것, 실패한 것, 확인하지 못한 것을 구분한다.
- 같은 수정이 반복 실패하면 무작정 재생성하지 말고 가정과 원인을 재검토한다.

## 이해 확인

- 주요 기능의 입력·처리·출력, 실제 파일/함수, 선택 이유, 검증 결과, 한계를 짧게 연결한다.
- 주석이나 의도만 보지 말고 현재 코드의 동작을 근거로 설명한다.
- 사용자가 먼저 설명하게 하고 실제 코드에 맞춰 교정한다. 모범 답변 암기를 목표로 삼지 않는다.

## 보안과 환경

- 원본 자료·과제 README·기존 지침·평가 도구를 임의로 덮어쓰거나 변경하지 않는다.
- 문제, 입력, 결과물, 로그, 개인정보, 비밀정보를 외부 서버로 전송하지 않는다.
- Git Push, 원격 이슈/PR 작성, 원격 CI 업로드, 클라우드 배포를 수행하지 않는다.
- 외부 AI 연결, 런타임 업데이트, 감독·접근·업로드 제한 우회, 금지된 UI 자동 조작을 수행하지 않는다.
- 외부 도구·의존성은 기존 환경을 우선한다. 추가가 필요하면 허용 여부와 영향을 먼저 확인한다.
- 테스트에서 네트워크 요청, 원본 수정, 데이터베이스 삭제 등 부작용이 있는지 확인한다.
- 로컬 작업 이력도 실제 작업과 일치해야 한다. 가짜 커밋·테스트·장애·개선 결과를 만들지 않는다.
