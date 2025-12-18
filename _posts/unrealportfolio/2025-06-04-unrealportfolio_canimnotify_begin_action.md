---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - notify
description: >
  CAnimNotify_Begin_Action
---
## CAnimNotify_Begin_Action

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CAnimNotify_Begin_Action.png" width = "1000" height = "400">

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

- 공격 혹은 액션 애니메이션의 특정 시점에 삽입하기 위한 클래스
- 애니메이션 재생 도중 특정 프레임에서 Begin_DoAction()을 호출하여 공격을 트리거

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Notify 설정
</p>

- Notify(USkeletalMeshComponent* MeshComp, UAnimSequenceBase* Animation, const FAnimNotifyEventReference& EventReference)
  - 공격 애니메이션을 실행한 캐릭터의 메시와 오너가 유효한지 검사하고 무기 데이터를 관리하는 컴포넌트를 찾는다.
  - 현재 장착 무기의 DoAction을 이용하여 공격을 실행한다. 