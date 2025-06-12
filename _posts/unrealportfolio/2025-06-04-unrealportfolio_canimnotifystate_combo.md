---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - norify
description: >
  CAnimNotifyState_Combo
---
## CAnimNotifyState_Combo

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CAnimNotifyState_Combo.png" width = "1000" height = "400">

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

- 애니메이션 중 지정한 구간에서만 다음 공격 입력을 받음
- 특정 콤보 인덱스 경우 자동으로 DoAction 실행

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Notify State 설정
</p>

- NotifyBegin(USkeletalMeshComponent* MeshComp, UAnimSequenceBase* Animation, float TotalDuration, const FAnimNotifyEventReference& EventReference)
  - 해당 캐릭터가 유효한지 확인하고 캐릭터의 무기 컴포넌트를 가져온다.
  - 콤보 입력을 받을 수 있는 상태로 변경한다. 
  - 현재 콤보 인덱스가 0이 아닌 경우 이미 콤보 입력이 들어온 상태이므로 즉시 액션을 호출하여 다음 공격을 재생한다.
- NotifyEnd(USkeletalMeshComponent* MeshComp, UAnimSequenceBase* Animation, const FAnimNotifyEventReference& EventReference)
  - Begin과 동일하게 장착 중인 무기의 ACAttach 객체를 추출한다.
  - 콤보의 입력을 무시하게 설정한다.
  - Notify State가 끝나는 구간에서 콤보 입력이 들어와도 무시된다.
  - 사용자 입력이 정해진 타이밍을 벗어나면 다음 공격으로 연결되지 않는다.
