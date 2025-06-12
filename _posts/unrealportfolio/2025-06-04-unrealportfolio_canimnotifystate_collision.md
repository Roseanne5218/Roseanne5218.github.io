---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - norify
description: >
  CAnimNotifyState_Collision
---
## CAnimNotifyState_Collision

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CAnimNotifyState_Collision.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UAnimNotifyState
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 무기 공격 애니메이션 중 일부 구간만 충돌이 감지되어야 함
- 캐릭터가 장착한 무기의 ACAttach 클래스 내부 콜리전 로직을 명확히 제어 

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Notify State 설정
</p>

- NotifyBegin(USkeletalMeshComponent* MeshComp, UAnimSequenceBase* Animation, float TotalDuration, const FAnimNotifyEventReference& EventReference)
  - 해당 캐릭터가 유효한지 확인하고 캐릭터의 무기 컴포넌트를 가져온다.
  - 현재 장착 중인 무기의 ACAttach 객체를 추출하여 콜리전을 활성화시킨다.
- NotifyEnd(USkeletalMeshComponent* MeshComp, UAnimSequenceBase* Animation, const FAnimNotifyEventReference& EventReference)
  - Begin과 동일하게 장착 중인 무기의 ACAttach 객체를 추출한다.
  - 해당 무기의 콜리전을 비활성화한다.
