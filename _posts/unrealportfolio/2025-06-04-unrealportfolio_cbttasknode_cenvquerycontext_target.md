---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - behaviortree
description: >
  CEnvQueryContext_Target
---
## CEnvQueryContext_Target

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CEnvQueryContext_Target.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UEnvQueryContext
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- EQS 쿼리를 수행하는 폰을 문맥으로 제공
- Enemy_AI를 기준으로 다른 액터들과의 거리, 위치 비교, 필터링

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
쿼리 설정
</p>

- ProvideContext(FEnvQueryInstance& QueryInstance, FEnvQueryContextData& ContextData) 
  - ContextData에서 QuerierPawn을 Actor 타입 문맥으로 설정한다.
  - 쿼리 내에서 EQS Context는 항상 Enemy_AI 폰을 참조한다.