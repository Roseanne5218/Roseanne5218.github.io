---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - component
description: >
  CHealthPointComponent
---
## CHealthPointComponent

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CHealthPointComponent.png" width = "1000" height = "400">

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

- 체력 데이터 분리 및 관리
- 캐릭터 본체 클래스에서 체력 관련 로직을 분리하여 재사용 가능
- UI 및 상태 연동

---

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자
</p>

- BeginPlay()
  - 해당 캐릭터의 최대 체력을 설정해 준다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
체력 감소 / 증가 처리
</p>

- Damage(float InAmount)
  - 데미지를 받으면 주어진 값만큼 체력이 감소한다.
  - Clamp를 이용하여 체력이 0 미만으로 떨어지지 않도록 설정한다.
  - 체력 변화 시 델리게이트를 호출하여 UI나 게임 로직에 알려준다.
- Heal(float InAmount)
  - 주어진 값만큼 체력을 증가시킨다.
  - Clamp를 이용하여 최대 체력을 초과하지 않도록 설정한다.
  - 체력 회복 후 외부에 체력이 변경되었음을 알린다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
보조 함수
</p>

- IsDead()
  - 현재 체력이 0 이하인지 확인한다.
- GetHealth()
  - 현재 체력 값을 반환한다.
  - 체력을 UI에 대입할 때 사용한다.
- GetMaxHealth()
  - 처음 설정했던 최대 체력 값을 알려준다.