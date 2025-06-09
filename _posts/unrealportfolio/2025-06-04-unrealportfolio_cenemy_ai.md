---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - character
description: >
  CEnemy_AI
---
## CEnemy_AI

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CEnemy_AI.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- ACEnemy
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 전투 중 상태 변화에 따른 AI BehaviorTree 상태 전이 처리
- 순찰용 경로를 자동 탐색 및 연결
- 무기 / 상태에 따른 AI 행동 전환 자동화

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자 및 초기화 
</p>

- ACEnemy_AI()
- BeginPlay()
  - PatrolPath를 설정한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
순찰 경로 설정
</p>

- FindAndSetPatrolPath()
  - 일정 거리 내에 있는 모든 PatrolPath를 검색하여 자신의 위치에서 가장 가까운 경로 하나를 변수로 저장한다. 

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
데미지 처리 함수 오버라이드
</p>

- Damage()
  - 캐릭터의 행동 상태를 전환한다.
- End_Damage()
  - 무기 타입이 가드인 경우 무기 모드를 검으로 전환하고 행동 상태를 Wait, 캐릭터 상태를 Idle로 설정한다.
- Dead()
- End_Dead()

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
스턴 및 패링 상태 처리
</p>

- StartStun()
  - 스턴 애니메이션 및 체력 데미지를 적용한다. 현재 상태가 Parrying이 아니면 행동 상태를 Parrying으로 변경한다.
- End_Stun()
  - 행동 상태를 Wait으로 복구하고 AI가 행동을 재개하도록 설정한다.