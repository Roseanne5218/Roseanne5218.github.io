---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - component
description: >
  CStateComponent
---
## CStateComponent

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CStateComponent.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UActorComponent
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 캐릭터가 현재 어떤 행동 상태에 있는지를 추전
- 상태 변경 시 외부 시스템에 이를 알릴 수 있도록 상태 전이 시스템을 구성

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
열거형
</p>

- 상태를 열거형으로 정의하였으며 Idle, Evade, Jump, Equip, Guard, Parrying, Damage, Action, Dead, Max가 있다.
- Max는 범위 체크용으로 사용된다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
상태 전이 함수
</p>

- SetIdleMode()
  - 상태를 Idle로 설정하고 비전투 상태를 의미하고 무기 장착 완료 상태에도 사용한다.
- SetEvadeMode()
  - 상태를 Evade로 설정하고 회피 동작 작동 중에 호출된다.
- SetJumpMode()
  - 상태를 Jump로 설정하고 점프 중에 다른 동작을 차단시킨다.
- SetEquipMode()	
  - 상태를 Equip으로 설정하고 무기를 장착하는 과정에 호출된다.
- SetGuardMode()	
  - 상태를 Guard로 설정하고 방어 중일 때를 나타낸다.
- SetParryingMode()
  - 상태를 Parrying으로 설정하고 플레이어가 반격 중에 사용된다.
- SetActionMode()	
  - 상태를 Action으로 설정하고 무기로 공격 중 사용된다.
- SetDamageMode()	
  - 상태를 Damage로 설정하고 피격 상태에 사용한다.
- SetDeadMode()
  - 상태를 Dead로 설정하고 사망 상태에 사용된다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
내부 상태 변경 로직
</p>

- ChangeType(EStateType InType)
  - 최근 타입을 현재 받아온 타입으로 바꾸고 이전 상태와 현재 상태를 이벤트로 외부에 알려준다.
  - 외부에서 상태 변경을 즉시 알도록 한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
상태 판별 함수
</p>

- IsIdleMode()
  - 현재 상태가 Idle 상태인지 판별한다.
- IsGuardMode()
  - 현재 상태가 Guard 상태인지 판별한다.
- IsParryingMode()
  - 현재 상태가 Parrying 상태인지 판별한다.
- IsDamageMode()
  - 현재 상태가 Damage 상태인지 판별한다.
- IsDeadMode()
  - 현재 상태가 Dead 상태인지 판별한다.
- IsEvadeMode()
  - 현재 상태가 Evade 상태인지 판별한다.
- IsSubActionMode()
  - 현재 상태가 SubAction 상태인지 판별한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
서브 액션 관련
</p>

- SetOnSubAction()
  - 서브 액션이 활성화되었음을 표시한다.
- SetOffSubAtion()
  - 서브 액션이 종료되었음을 표시한다.
