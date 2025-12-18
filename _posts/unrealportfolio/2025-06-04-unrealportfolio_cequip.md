---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - weapon
description: >
  CEquip
---
## CEquip

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CEquip.png" width = "1000" height = "400">

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

- 무기와 장비의 장착과 해제 관리
- 장착 시 상태 전환 및 데이터를 기반으로 이동, 회전, 몽타주 재생 처리
- 장착, 해제 타이밍을 델리게이트로 외부와 연동

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자
</p>

- BeginPlay(ACharacter* InOwner, const FEquipDatas& InData)
  - OwnerCharacter 설정과 EquipDatas 저장
  - 움직임과 상태 컴포넌트 설정

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
장착 동작
</p>

- Equip_Implementation()
  - 상태를 Equip으로 전환
  - 데이터에 따라 움직짐 제어
  - 몽타주가 있으면 재생, 없으면 End 처리
- Begin_Equip_Implementation()
  - 장착 시작 활성화
  - 장착 시작 델리게이트 설정
- End_Equip_Implementation()
  - 장착 완료 처리
  - 기본값으로 복구
- Unequip_Implementation()
  - 장착 해제 처리
  - 해제 델리게이트 설정