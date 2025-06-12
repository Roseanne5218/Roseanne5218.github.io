---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - widget
description: >
  CUserWidget
---
## CUserWidget

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CUserWidget.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UInterface
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 플레이어의 체력 수치를 내부적으로 추적하고 UI에 반영
- 힐 스킬 쿨 다운 상태를 관리하며 일정 시간이 지나면 쿨 다운을 해제
- 매 프레임마다 위젯 상태 갱신
- 외부로부터 Damage와 Heal을 호출해 UI을 갱신할 수 있도록 설계

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

- NativeOnInitialized()
  - 언리얼 위젯의 초기화 시점에 호출되어 현재 체력과 최대 체력을 설정한다.
- NativeTick(const FGeometry& MyGeometry, float InDeltaTime)
  - 매 프레임마다 호출되는 함수로 힐 쿨 다운이 활성화된 경우 InDeltaTime 시간만큼 시간 감소한다.
  - 남은 쿨 다운 시간이 0.2초 이하면 자동으로 쿨 다운을 해제한다.
- UpdateHealCoolDown()
  - 힐 쿨 다운을 시작할 때 호출하고 HealCooldownRemain을 최댓값으로 설정하고 쿨 다운이 가능하도록 한다.
- GetHealthPointRatio()
  - 현재 체력을 최대 체력 비율로 나누어 반환한다.
  - 체력 게이지 UI의 퍼센트를 계산할 때 사용한다.
- GetHealCooldownPercent()
  - 남은 힐 쿨 다운 시간의 비율을 0.0 ~ 1.0을 반환한다.
  - UI에서 쿨 다운 게이지에 반영할 수 있도록 사용한다.
- Damage(float InAmount)
  - 지정된 데미지만큼 체력을 감소시키고 0 이하로 떨어지지 않도록 한다.
- Heal(float InAmount)
  - 지정된 양만큼 체력을 회복시키고 최대 체력을 초과하지 않도록 한다.
