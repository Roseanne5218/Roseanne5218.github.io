---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - weapon
description: >
  CSubAction
---
## CSubAction

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CSubAction.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UObject
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 무기 시스템에서 서브 액션의 입력 상태를 관리
- 서브 액션 동작 확장 기반 마련
- 서브 액션의 입력 유지 여부를 제어

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자
</p>

- UCSubAction()
- BeginPlay(ACharacter* InCharacter, UCDoAction* InDoAction)
  - 서브 액션이 동작할 OwnerCharacter과 연동할 DoAction 설정
  - State, Movement, Weapon 컴포넌트 설정

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
서브액션 동작
</p>

- Pressed()
  - 서브 액션 입력 시작 상태로 설정
- Released()
  - 서브 액션 입력 해제 상태로 설정
