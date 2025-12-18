---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - notify
description: >
  CAnimNotify_End_Action
---
## CAnimNotify_End_Action

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CAnimNotify_End_Action.png" width = "1000" height = "400">

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

- 애니메이션의 특정 시점에 트리거 되어 공격 액션을 종료 처리하는 Notify 클래스
- BeginAction과 짝으로 작동되며, DoAction 시스템의 종료 시점을 제어

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Notify 설정
</p>

- Notify(USkeletalMeshComponent* MeshComp, UAnimSequenceBase* Animation, const FAnimNotifyEventReference& EventReference)
  - 공격 애니메이션을 실행한 캐릭터의 메시와 오너가 유효한지 검사하고 무기 데이터를 관리하는 컴포넌트를 찾는다.
  - 현재 장착 무기의 객체를 가져와 해당 객체의 액션 종료를 호출한다.