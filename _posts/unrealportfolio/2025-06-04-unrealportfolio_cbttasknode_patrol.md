---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - behaviortree
description: >
  CBTTaskNode_Patrol
---
## CBTTaskNode_Patrol

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CBTTaskNode_Patrol.png" width = "1000" height = "400">

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

- AI 캐릭터가 순찰을 수행하도록 하는 노드
- CPatrolPath가 존재 시 경로 기반 순찰
- 없을 경우 랜덤 지역 순찰

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Task 설정
</p>

- ExecuteTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
  - 지정된 순찰 경로가 있을 경우 경로상의 현재 인덱스를 반환하여 이동 목표를 설정한다.
  - 지정 경로가 없을 경우 NavMesh를 기반으로 임의 위치를 선택한다.
- TickTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory, float DeltaSeconds)
  - AI를 구한 좌표로 이동시키고 그동안 명령을 중복 수행 못하도록 설정한다.
  - 순찰 지점에 이미 도달하였다면 다음 순찰 지점으로 인덱스를 갱신한다.
