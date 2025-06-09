---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - behaviortree
description: >
  CBTTaskNode_Guard
---
## CBTTaskNode_Guard

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CBTTaskNode_Guard.png" width = "1000" height = "400">

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

- AI의 상황에 따라 가드 행동으로 전환
- 무기가 장착되어 있는 상태에서만 가드 상태 전환
- 가드 상태 전환 실패 시 무기 복귀와 상태 복구

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Task 설정
</p>

- ExecuteTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
  - 무기를 장착 중이고 무기 컴포넌트를 가지고 있으면 무기와 상태를 가드로 전환한다.
- TickTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory, float DeltaSeconds)
  - 성공적으로 가드 상태가 되면 노드를 종료시킨다.
- AbortTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
  - 가드가 중단될 경우 무기를 이전 무기로 돌리고 상태도 Idle로 복귀시킨다.