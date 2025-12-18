---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - behaviortree
description: >
  CBTService_Melee
---
## CBTService_Melee

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CBTService_Melee.png" width = "1000" height = "400">

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
  - 현재 타겟을 가져와 같은 팀에게 공유
  - Action 상태가 아닐 때 토큰을 가지고 있으면 반환
  - 타겟이 없으면 순찰 모드 설정
  - 타겟이 있으면 플레이어 타겟에 집중
  - 무기 장착이 해제되어 있다면 무기 장착 후 공격 가능 설정
  - 타격 설정 거리보다 멀리 있으면 가드 해제 후 액션 모드 진입
  - 액션 거리보다 멀고 스트레이프 거리 안에 있으면 가드 상태 진입
  - 스트레이프 거리 밖에 있으면 플레이어에게 접근하고 Idle로 전환
