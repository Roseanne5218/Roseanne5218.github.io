---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - behaviortree
description: >
  CBTTaskNode_Parrying
---
## CBTTaskNode_Parrying

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CBTTaskNode_Parrying.png" width = "1000" height = "400">

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

- 캐릭터의 대응형 행동 시스템에서 사용
- 데미지를 반사하거나 특정 공격을 차단하는 반격적 시스템의 일부

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Task 설정
</p>

- ExecuteTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
  - AI의 이동을 즉시 정지하고 성공을 반환한다.
- TickTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory, float DeltaSeconds)
  - 캐릭터가 현재 패링 상태인지를 지속적으로 확인한다.
  - 패링 상태가 끝났으면 태스크를 완료 처리한다.
