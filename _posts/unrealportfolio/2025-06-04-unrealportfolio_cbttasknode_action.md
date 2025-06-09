---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - behaviortree
description: >
  CBTTaskNode_Action
---
## CBTTaskNode_Action

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CBTTaskNode_Action.png" width = "1000" height = "400">

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

- AI가 공격 행동을 수행하도록 명령
- 무기 상태를 확인하여 공격 실행
- 캐릭터 아이디에 따라 다른 공격 설정

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Task 설정
</p>

- ExecuteTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
  - 무기 유효성을 확인하고 이동을 중단시킨다.
  - 분기를 설정하여 DataTable을 바탕으로 적이면 콤보 공격을 보스이면 랜덤 공격을 실행한다.
  - 공격이 성공하면 성공을 반환한다.
- TickTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory, float DeltaSeconds)
  - 매 프레임 호출하여 노드가 종료되었는지 확인하고 조건이 모두 충족되면 성공을 반환한다.
- AbortTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
  - 해당 노드가 강제로 중단되면 호출이 되고 상태가 꼬이지 않도록 해당 노드를 강제 종료 시켜준다.