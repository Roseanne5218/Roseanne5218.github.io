---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - weapon
description: >
  CSubAction_Guard
---
## CSubAction_Guard

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CSubAction_Guard.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UCSubAction
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 입력 유지에 따라 서브 액션을 전환하여 가드 상태 제어
- 가드 시작 직후 일정 시간 동안 패링 가능 설정

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자
</p>

- UCSubAction_Guard()
- BeginPlay(ACharacter* InCharacter, UCDoAction* InDoAction)
  - 가드 시작 카운트를 초기화
  - 패링 가능 상태로 전환
- Tick(float InDeltaTime)
  - 타임라인을 이용해 가드 시작 경과를 누적
  - 일정 시간 이후 패링 비활성화

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
입력 제어
</p>

- Pressed()
  - 입력 시작 처리 후 가드 상태로 진입
- Released()
  - 입력 해제 처리 후 가드 상태 해제