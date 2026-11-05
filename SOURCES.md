# 출처와 구성 정보

이 묶음의 절차 문서는 사용자의 범용 작업 요구에 맞춰 새로 작성한 템플릿이다.
외부 스킬의 본문, 실행 코드, 데이터, 특정 과제 결과물을 가져오지 않았다.

아래는 파일 형식과 사용 방식을 확인한 공식 문서다.
특정 관리형 환경의 기능·허용 범위를 보증하는 자료는 아니다.

- Codex의 AGENTS.md: https://learn.chatgpt.com/docs/agent-configuration/agents-md
- Codex 스킬 형식과 탐색 경로: https://learn.chatgpt.com/docs/build-skills
- 작업 절차 파일을 활용하는 예시: https://developers.openai.com/cookbook/examples/codex/iterating-development-workflows-with-codex
- GitHub 공개 저장소 생성: https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository
- GitHub 파일 업로드: https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository

위 형식·사용 방식 자료 확인일: 2026-11-02
키트 버전: 1.1.0

## 모델·사고 수준 가이드

아래 공식 문서를 2026-11-05에 확인했다. MODEL_GUIDE.md의 모델 설명과 사고 수준 설명의 근거다.
작업별 배정·전환 기준과 PROMPTS.md의 요청문은 시험 활용을 위해 작성한 추천이며, 모델 간 실측 성능 비교가 아니다.

- [GPT-6.1 Sol: 복잡한 코딩·업무, 지원 사고 수준](https://developers.openai.com/api/docs/models/gpt-6.1-sol)
- [GPT-5.6 Terra: 모델 특성, 지원 사고 수준](https://developers.openai.com/api/docs/models/gpt-5.6-terra)
- [GPT-6 Luna: 범위가 명확한 반복 작업, 지원 사고 수준](https://developers.openai.com/api/docs/models/gpt-6-luna)
- [GPT-6 Sol: 코딩·에이전트 작업, 지원 사고 수준](https://developers.openai.com/api/docs/models/gpt-6-sol)
- [Reasoning models: 사고 수준과 시간·토큰의 관계](https://developers.openai.com/api/docs/guides/reasoning)
- [Models: Work·Codex의 선택 UI, Luna High 권장, 모델별 사고 수준 차이](https://learn.chatgpt.com/docs/models)

사용 가능 모델 네 개는 사용자가 제시한 시험 환경을 기준으로 한다.
실제 UI의 옵션, 사용량 한도, 응답 시간은 별도 확인 대상이다. API 지원을 시험 플랫폼의 지원 보장으로 해석하지 않는다.

외부 스킬을 별도로 채택할 경우 출처 URL, 커밋/버전, 사용 경로, 필요한 도구,
재배포 조건과 의존 파일을 본인이 확인하고 관리한다. 이 파일에는 민감한 실행 기록을 넣지 않는다.
