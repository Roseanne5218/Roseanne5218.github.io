---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - notify
description: >
  CAnimNotifyState_Equip
---
## CAnimNotifyState_Equip

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CAnimNotifyState_Equip.png" width = "1000" height = "400">

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

- 애니메이션의 장착 구간과 게임 로직을 연동
- Notify State의 Begin 시점에서 Begin_Equip() 호출
- Notify State의 End 시점에서 End_Equip() 호출

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Notify State 설정
</p>

- NotifyBegin(USkeletalMeshComponent* MeshComp, UAnimSequenceBase* Animation, float TotalDuration, const FAnimNotifyEventReference& EventReference)
  - 해당 캐릭터가 유효한지 확인하고 캐릭터의 무기 컴포넌트를 가져온다.
  - GetEquip을 통해 현재 무기 장착 객체를 가져와 Begin_Equip()을 호출한다.
- NotifyEnd(USkeletalMeshComponent* MeshComp, UAnimSequenceBase* Animation, const FAnimNotifyEventReference& EventReference)
  - Begin과 동일하게 장착 중인 무기의 ACAttach 객체를 추출한다.
  - GetEquip을 통하여 무기 장착이 끝났음을 명시한다.
