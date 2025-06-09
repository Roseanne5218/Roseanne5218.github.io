---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - behaviortree
description: >
  CBTTaskNode_Equip
---
## CBTTaskNode_Equip

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CBTTaskNode_Equip.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UBTTaskNode
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- AI가 공격을 하기 전 무기를 장착하도록 설정
- 행동 트리 기반 전투에서 유연하게 무기 전환을 설계

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Task 설정
</p>

- ExecuteTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
  - 유효성을 검사하여 장비 타입이 Max이거나 같은 무기를 장착 중이면 실패 또는 성공을 반환한다.
  - 무기 장착을 시도하고 상태 진행 중을 반환한다.
- TickTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory, float DeltaSeconds)
  - 무기 장착 여부를 확인하고 상태가 Idle 일 때 완료를 처리한다.
- AbortTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
  - 무기 장착 중 중단된다면 무기 장착을 강제로 종료 처리하고 중단을 반환한다.
