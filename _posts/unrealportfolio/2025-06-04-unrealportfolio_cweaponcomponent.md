---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - component
description: >
  CWeaponComponent
---
## CWeaponComponent

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CWeaponComponent.png" width = "1000" height = "400">

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

- 플레이어 혹은 AI 캐릭터가 다양한 무기를 장착하고 전환
- 무기에 따라 다른 액션을 수행할 수 있도록 통합 무기 관리 시스템 구성
- 무기 상태, 시각적 장착 상태를 포괄적으로 제어

---

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
초기화 및 Tick
</p>

- BeginPlay()
  - DataAssets를 초기화하고 해당 무기 타입의 UCWeaponData를 생성해 데이터를 저장한다.
- TickComponent()
  - 무기의 DoAction, SubAction의 Tick을 프레임마다 실행하여 지속적인 동작이 가능하도록 하였다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
무기 상태 확인 및 참조자
</p>

- IsIdleMode()
  - 현재 상태 컴포넌트가 Idle 상태인지 확인한다.
- IsUnarmedMode()
  - 무기가 장착되지 않은 상태인지 확인한다.
- GetWeaponData(EWeaponType)
  - 특정 타입의 무기 데이터를 참조한다.
- GetAttach() / GetEquip() / GetDoAction() / GetSubAction()
  - 현재 무기에 해당하는 부속 클래스를 참조한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
무기 전환 및 장착 / 해제
</p>

- SetMode(EWeaponType)
  - 지정된 무기 타입으로 변경한다.
  - 동일한 타입이라면 해제를 하고 아니면 이전 무기를 해제하고 새로운 무기를 장착한다.
- SetUnarmedMode() / SetIdleMode()
  - 무기를 해제한다.
- SetSwordMode() / SetGuardMode() / SetScytheMode()
  - 해당 타입별 모드를 설정한다.
- ChangeType(EWeaponType)
  - 타입을 전환하고 델리게이트를 호출한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
공격 및 액션 실행
</p>

- OnActionEvent()
  - 무기 타입에 따라 DoAction()을 수행한다.
- DoAction()
  - 현재 무기의 주 동작을 실행한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
서브 액션 관련
</p>

- SubAction_Pressed()
  - UCSubAction의 Pressed()를 호출하여 플레이어가 패링 동작이 가능하면 패링 함수를 호출한다.
  - 검 모드이면 가드 모드로 전환시킨다.
- SubAction_Released()
  - Released()를 호출하고 가드 모드이면 검 모드로 되돌려준다.
