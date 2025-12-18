---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - weapon
description: >
  CDoAction
---
## CDoAction

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CDoAction.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UObject
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 무기와 캐릭터의 공격 실행 흐름을 관리
- 액션 상황에 맞춰 상태와 카메라 제어

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자
</p>

- UCDoAction()
- BeginPlay(ACharacter* InOwner, ACAttach* InAttach, UCEquip* InEquip, const TArray<FDoActionDatas>& InDoActionDatas, const TArray<FHitDatas>& InHitDatas)
  - 액션이 동작할 OwnerCharacter과 World 설정
  - 공격 관련 데이터를 내부에 보관

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
액션 동작
</p>

- DoAction()
  - 캐릭터를 Action 상태로 전환
  - 이동과 카메라를 제어
- Begin_DoAction()
  - 실제 동작이 실행될 때 활성화
- End_DoAction()
  - 행동이 종료되면 Idle로 복귀
  - 이동과 카메라를 원래로 복구
