---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - weapon
description: >
  CWeaponAsset
---
## CWeaponAsset

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CWeaponAsset.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UDataAsset
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 무기 구성 요소를 생성하고 초기화하여 하나의 무기 데이터로 묶어 반환
- 이벤트를 연결하여 무기 동작 흐름이 자동으로 연동되도록 설정

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자
</p>

- UCWeaponAsset()
  - Attach, Equip, DoAction, SubAction 클래스 설정
- BeginPlay(ACharacter* InOwner, UCWeaponData** OutWeaponData)
  - 무기 구성 요소들을 생성하고 초기화한뒤 OutWeaponData로 반환
  - Attach 생성
  - Equip 생성
    - attach 존재 시 장착 이벤트를 바인딩
  - DoAction 생성
    - DoAction 클래스가 있으면 UCDoAction 생성
    - 액션, 타격 데이터 초기화
    - attach 존재 시Collision 이벤트 바인딩
    - equip 존재 시 장착 이벤트 바인딩
  - SubAction 생성
    - SubAction 클래스가 있으면 UCSubAction 생성
    - DoAction과 연동
  - WeaponData 생성
  - WeaponType, Attach, Equip, DoAction, SubAction 데이터를 저장하여 무기 설정
