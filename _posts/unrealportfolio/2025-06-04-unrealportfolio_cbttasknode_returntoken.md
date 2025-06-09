---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - behaviortree
description: >
  CBTTaskNode_ReturnToken
---
## CBTTaskNode_ReturnToken

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CBTTaskNode_ReturnToken.png" width = "1000" height = "400">

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

- AI가 공격 후 후퇴를 할 때 Token을 반환
- AI가 사망할 때 Token을 반환
- 중립 상태를 복귀할 때 공격권 회수

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Task 설정
</p>

- ExecuteTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
  - BlackBoard에 저장되어 있는 토큰 값을 수정하기 위해 BlackBoard의 토큰을 확인한다.
  - 토큰을 가지고 있다면 BlackBoard에 더 이상 해당 AI가 토큰을 보유하지 않고 있음을 명시하고 게임 모드에 돌려준다.
