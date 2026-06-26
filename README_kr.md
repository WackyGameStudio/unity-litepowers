# Unity Litepowers

Unity Litepowers는 상용 Unity 게임 개발 흐름에 맞춘 token-light AI 코딩 에이전트 스킬 패키지입니다.

`lite`는 검증이 약하다는 뜻이 아닙니다. 모든 작업에 강한 TDD와 과한 절차를 강제하지 않고, Unity 표면별 risk-based evidence를 사용한다는 뜻입니다.

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
- 재사용 가능한 실패 시도, workaround, skill update 후보는 feature `implementation-log.md`에 남기고 completion-check에서 `skill-feedback.md`로 요약합니다.
- Unity Editor evidence 기본 경로는 MCPForUnity입니다.
- TDD는 `risk-based-verification-unity`가 required로 판정할 때만 강제합니다.
- scene, prefab, UI, animation, physics, package, settings 변경은 표면별 evidence로 검증합니다.
- 구현 계획은 SOLID와 Unity design pattern fit 관점에서도 검증합니다.
- 조건부 Clean C# Architecture Track은 새 public skill이 아니라 기존 흐름 안의 quality track입니다.
- pattern 선택 전에 behavior invariants와 change pressure를 먼저 기록합니다.
- Unity lifecycle, prefab/scene wiring, serialization을 architecture surface로 다룹니다.
- `routine | focused | migration` depth로 local edit은 짧게 유지하고, architecture-sensitive work만 ownership, lifecycle, wiring, selected/rejected approaches, evidence를 기록합니다.
- blanket TDD, pattern quota, interface-per-class, composition-only, blanket plain-C# extraction은 사용하지 않습니다.
- planning, execution, verification, debugging, completion은 같은 pressure-first architecture contract를 따릅니다.
- DOTS/ECS는 scale, CPU, determinism, streaming, multiplayer 압력이 있을 때 suitability gate로 판단합니다.
- 의사결정 질문은 적절한 선택지 2개, 추천안, 이유를 포함합니다.
- 사용자-facing 결과물과 생성 문서는 사용자의 언어에 맞추고, 더 정확한 영어 기술 용어는 그대로 둡니다.
