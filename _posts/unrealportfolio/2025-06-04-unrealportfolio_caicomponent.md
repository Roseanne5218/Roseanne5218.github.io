---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - component
description: >
  CAIComponent
---
## CAIComponent

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CAIComponent.png" width = "1000" height = "400">

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

- AI 캐릭터의 전략적 상태 제어를 설계한 컴포넌트
- 블랙보드를 이용해 Behavior Tree와 연계를 강화
- 외부 클래스들이 AI 상태를 Get 하거나 Set 가능

---

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
블랙보드 키 이름 정의
</p>

- AIStateTypeKey = "State"
- TargetKey = "Target"
- PatrolLocationKey = "Patrol"
- PlayerKey = "Player"
- DodgeLocationKEy = "Dodge"


<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
상태 질의 함수
</p>

- IsWaitMode()
- IsEquipMode()
- IsApproachMode()
- IsStrafeMode()
- IsActionMode()
- IsPatrolMode()
- IsGuardMode()
- IsParryingMode()
- IsDamageMode()
- IsAvoidMode()

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
상태 전이 함수
</p>

- SetWaitMode()
- SetEquipMode()
- SetApproachMode()
- SetStrafeMode()
- SetActionMode()
- SetPatrolMode()
- SetGuardMode()
- SetParryingMode()
- SetDamageMode()
- SetAvoidMode()

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
블랙보드 데이터 접근 함수
</p>

- ACharacter* GetTarget()
  - 블랙보드 키값이 Target인 Actor을 반환한다.
- ACPlayer* GetPlayer()
  - 블랙보드 키값이 Player인 Actor을 반환한다.
- GetPatrolLocation()
  - 블랙보드에 저장된 키값인 Patrol 좌표를 가져온다. 
- SetPatrolLocation(const FVector&)
  - 블랙보드의 키값인 Patrol 좌표를 설정한다.
-  GetDodgeLocation()
  - 회피 위치를 반환할 때 사용한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
타입 전환
</p>

- ChangeType(EAIStateType InType)
  - 블랙보드의 상태를 해당 타입으로 전환한다.
  - 이전 상태와 새 상태를 OnAIStateTypeChange 델리게이트로 알려 외부 시스템에 연동 가능하다.