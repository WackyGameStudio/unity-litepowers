# Unity Litepowers

Unity Litepowers는 상용 Unity 게임 개발 흐름에 맞춘 token-light AI 코딩 에이전트 스킬팩입니다.

`lite`는 검증이 약하다는 뜻이 아닙니다. 모든 작업에 강한 TDD와 subagent 절차를 강제하지 않고, Unity 표면별 risk-based evidence를 사용한다는 뜻입니다.

## 핵심 흐름

1. `using-litepowers-unity`
2. `unity-bootstrap`
3. `unity-project-idea`
4. `unity-game-planning`
5. `unity-implementation-planning`
6. `risk-based-verification-unity`
7. `executing-unity-plan-lite`
8. `completion-check-unity-lite`

버그 작업은 `systematic-debugging-unity-lite`에서 시작합니다.

## 설계 규칙

- 새 Unity 작업 전 `docs/litepowers`를 읽습니다.
- main docs와 feature docs를 일관되게 유지합니다.
- Unity Editor evidence 기본 경로는 MCPForUnity입니다.
- TDD는 `risk-based-verification-unity`가 required로 판정할 때만 강제합니다.
- scene, prefab, UI, animation, physics, package, settings 변경은 표면별 evidence로 검증합니다.
- 구현 계획은 SOLID와 Unity design pattern fit 관점에서도 검증합니다.
