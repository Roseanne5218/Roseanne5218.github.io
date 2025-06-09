---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - character
description: >
  CEnemy
---
## CEnemy

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CEnemy.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- ACCharacter
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 메시 / 애니메이션 세팅 자동화
- HP 위젯이 카메라를 따라 회전 처리
- 공중 공격 처리 
- 공중 데미지 연출

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자 및 초기화 
</p>

- ACEnemy()
- BeginPlay()

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
공중 공격 처리 함수
</p>

- LaunchIntoAir()
  - 적이 공중에 있으면 런치를 이용하여 더 위로 밀어올리고 중력 값을 변환시킨다. 
  - 시각적으로 공중 피격을 연출해 준다.
- AirDamage()
  - 공중에서 데미지를 입을 때 사용하는 함수이다. 
  - 타이머를 등록하여 일정 시간 후 중력을 회복시킨다.
  - 캐릭터를 위쪽으로 런치 시켜 튀어 오르는 듯한 연출을 한다.
- StartFalling()
  - 공중 상태에서 떨어질 때 중력을 조절하여 서서히 낙하하도록 한다.
- Landed(const FHitResult& Hit)
  - 착지 시 중력을 초기화하고 공중 상태를 해제시킨다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
데미지 처리 함수 오버라이드
</p>

- Dead()
- End_Dead()
