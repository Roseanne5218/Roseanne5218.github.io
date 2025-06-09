---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - behaviortree
description: >
  CBTTaskNode_GetToken
---
## CBTTaskNode_GetToken

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CBTTaskNode_GetToken.png" width = "1000" height = "400">

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

- 게임 모드에 토큰이 있을 때 해당 토큰 가져와 AI가 전투에 참여하도록 설정
- 동시 전투를 막거나 순차적인 참여를 컨트롤

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Task 설정
</p>

- ExecuteTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
  - 게임 모드를 받아와 남은 토큰이 있다면 하나를 가져와 BlackBoard에 저장한다.
  - 토큰을 받았다면 성공을 못 받았다면 실패를 반환한다.