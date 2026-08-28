# Claude Code Workflow

Claude Code를 기반으로 개인 개발 워크플로우를 자동화하기 위해 구성한
프레임워크 통합, 커스텀 규칙, 멀티 에이전트 오케스트레이션 설정입니다.

## 구성 개요

### 1. Behavioral Framework 통합 (SuperClaude)
- 8개 행동 모드(Brainstorming, Task Management, Orchestration,
  Token Efficiency, Introspection, Deep Research 등)를 상황별로
  자동 트리거되도록 구성
- 작업 유형(디버깅/설계/UI/문서화 등)에 따라 최적 MCP 서버를
  선택하는 라우팅 규칙 정의

### 2. MCP 서버 오케스트레이션
| 서버 | 용도 |
|---|---|
| Sequential | 복잡한 다단계 추론, 아키텍처 분석 |
| Context7 | 프레임워크 공식 문서 조회 |
| Magic | UI 컴포넌트 생성 |
| Playwright | 브라우저 E2E 테스트 |
| Serena | 심볼 단위 코드 탐색, 세션 메모리 |
| Morphllm | 대량 패턴 기반 코드 수정 |
| Tavily | 실시간 웹 리서치 |

### 3. 멀티 에이전트 협업 규칙
- 작업 실행(Task Execution) 에이전트와 사후 문서화(PM Agent)를
  분리해 지식이 자동으로 축적되도록 설계
- 실패 발생 시 즉시 근본 원인 분석 후 재작업하는 규칙 명문화

### 4. 커스텀 스킬
- `sc:business-panel`: Porter, Christensen, Drucker 등 9인의
  경영 프레임워크를 discussion/debate/socratic 모드로 시뮬레이션하는
  멀티 전문가 분석 시스템
- `sc:research`: 병렬 검색 → 신뢰도 스코어링 → 근거 기반 합성까지
  이어지는 딥리서치 파이프라인

## 왜 이렇게 구성했는가
반복적인 컨텍스트 손실, 임시방편적 코드 수정, 불필요한 verbose 출력
같은 문제를 겪은 뒤, 규칙/모드/에이전트 역할을 명시적으로 분리해
일관되고 검증 가능한 결과를 내도록 설계했습니다.
