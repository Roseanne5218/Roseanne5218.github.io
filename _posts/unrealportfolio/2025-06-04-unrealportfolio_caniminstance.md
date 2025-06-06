---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:10:00 +0900
categories:
  - unrealportfolio
  - character
description: >
  CAnimInstance
---
## CAnimInstance

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UAnimInstance
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CAnimInstance.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 애니메이션 블루 프린트와 게임 플레이의 데이터 연결
- 정교한 캐릭터 자세 및 동작 계산을 통한 자연스러운 모션 설정
- 상태 기반 애니메이션 전환 제어
- 이벤트 기반 애니메이션 반응 시스템 구축

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
애니메이션 설정
</p>

- NativeBeginPlay()
- NativeUpdateAnimation(float DeltaSeconds)
  - 속도를 계산하여 이동 애니메이션에 기준값을 설정한다.
  - 이동 방향과 시야 방향의 차이를 계산하여 부드럽게 보간한다.
  - 캐릭터 클래스에서 정의한 애니메이션용 상태 플래그를 이용하여 애님 블렌딩 조건으로 사용한다.
  - 회피 상태가 감지되면 일정 시간 후에 회피 종료 함수를 호출한다.

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
무기 상태 전환
</p>

- OnWeaponTypeChange()
  - 전환된 무기 상태 값 설정
