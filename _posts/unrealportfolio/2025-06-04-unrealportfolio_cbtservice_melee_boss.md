---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - behaviortree
description: >
  CBTService_Melee_Boss
---
## CBTService_Melee_Boss

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CBTService_Melee_Boss.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UBTService
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 무기 장착 여부 확인 및 장착 지시
- 처음 등장 시 스트레이프 모드 진입 및 딜레이 공격 준비
- 일정 거리 내 진입 시 공격 가능 플래그 세팅
- 공격 모드로 전환
- 일정 시간 후 다시 공격 가능하게 재설정

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
AI 상태 설정
</p>

- TickNode(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory, float DeltaSeconds)
  - 무기가 장착이 안 되어 있으면 장착 모드를 실행한다.
  - 첫 공격 이전 딜레이 후 공격이 가능하도록 한다.
  - 현재 상태가 공격 불가 상태이면 스트레이프 상태를 유지한다.
  - 거리를 확인하고 일정 거리 내에 들어오면 공격이 가능하도록 하고 공격을 실행한다. 공격이 끝나면 공격 불가 상태가 되고 일정 시간이 지나면 다시 공격 가능 상태가 된다.
