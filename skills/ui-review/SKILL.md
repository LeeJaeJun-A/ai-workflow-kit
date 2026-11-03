---
name: local-ui-review
description: Review an existing local UI against approved inputs, calculations, error states and user tasks. Do not redesign the algorithm, install a frontend stack, operate a browser automatically, or claim unobserved screen behavior.
---

# 업무 UI 검토

기존 UI 스킬이 있다면 중복 생성보다 검토 역할에 집중한다. 실제 README와 RULES.md를 따른다.

1. 사용자가 완료해야 하는 핵심 작업과 화면의 입력·결과를 연결한다.
2. 예시 데이터가 아닌 실제 입력 흐름과 계산 결과가 연결되어 있는지 확인한다.
3. 로딩, 빈 상태, 잘못된 입력, 계산 실패, 결과 없음 상태의 처리를 점검한다.
4. 단위, 기준 시점, 비교 조건, 추정/실측 구분, 지표 의미가 드러나는지 확인한다.
5. 결과를 다시 계산했을 때 이전 결과를 현재 결과처럼 보여주지 않는지 점검한다.
6. 라벨, 키보드 접근, 색만으로 상태를 전달하지 않는지 코드 수준에서 확인한다.
7. 기존 스택을 유지하고 필요한 작은 변경만 제안한다.

## 검증과 경계

- 소스 검토, 빌드/컴포넌트 테스트, 사람이 확인한 실제 화면을 구분한다.
- 브라우저 자동 조작은 수행하지 않는다. 수동 확인이 필요하면 순서와 기대 결과를 알려준다.
- UI 작업을 이유로 계산식·데이터 삭제·하드 제약·핵심 알고리즘을 바꾸지 않는다.
- 외부 폰트·아이콘·지도·분석 서비스 연결이나 새 설치를 자동으로 추가하지 않는다.
- 정확성·핵심 사용 흐름·오류 전달을 먼저 확인하고 장식은 나중에 검토한다.
