---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - notify
description: >
  CAnimNotify_End_State
---
## CAnimNotify_End_State

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CAnimNotify_End_State.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UAnimNotify
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 애니메이션과 실제 게임 상태의 종료를 정확하게 동기화하기 위한 구조
- 동일한 Notify에서 여러 상태의 종료를 처리 가능
- StateType을 이용한 분기 처리

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Notify 설정
</p>

- Notify(USkeletalMeshComponent* MeshComp, UAnimSequenceBase* Animation, const FAnimNotifyEventReference& EventReference)
  - 공격 애니메이션을 실행한 캐릭터의 메시와 오너가 유효한지 검사한다.
  - Notify가 호출되는 대상이 IIStatable 인터페이스를 구현했는지 확인한다.
  - StateType에 따라 해당 상태 종료 함수를 호출한다.