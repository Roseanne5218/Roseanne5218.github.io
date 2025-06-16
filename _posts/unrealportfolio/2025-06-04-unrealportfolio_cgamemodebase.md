---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - else
description: >
  CGameModeBase
---
## CGameModeBase

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CGameModeBase.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- AActor
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 공유 자원을 기반으로 여러 액터 간 동시 작업을 제한
- AI 다중 공격 제한
- 전역에서 공통된 자원 관리를 위해 GameMode 이용

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자
</p>

- ACGameModeBase()
  - 토큰의 개수를 초기화하여 모든 액터가 사용할 수 있는 공용 리소스를 제공한다.

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
토큰 관리
</p>

- GetSharedToken() const
  - 현재 남아 있는 토큰 개수를 반환한다.
- TryConsumeToken()
  - 토큰이 1개 이상 있을 경우 토큰의 개수를 줄이고 true를 반환해 준다.
- ReturnToken()
  - 사용한 토큰을 반환하는 것으로 행동 종료 후 반드시 호출한다.
