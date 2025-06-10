---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - component
description: >
  CMovementComponent
---
## CMovementComponent

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CMovementComponent.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UActorComponent
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 전후좌우 이동 처리 및 속도 전환
- 카메라 회전을 부드럽고 제한적으로 허용
- 전투시 Yaw값 고정
- 상태 기반으로 카메라와 플레이어의 움직임 제어

---

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
입력 처리 메서드
</p>

- OnMoveForward(float InAxisValue)
  - 캐릭터의 전방 방향으로 이동을 입력 처리한다.
  - Yaw 각도 기준의 정변 벡터를 계산하여 AddMovementInput()을 호출한다.
  - bCanMove가 True 일 때만 움직인다.
- OnMoveRight(float InAxisValue)
  - 캐릭터의 우측 방향으로 이동 입력을 처리한다.
  - Yaw 기준으로 우측 방향 벡터를 계산하고 AddMovementInput()을 호출한다.
  - bCanMove가 True 일 때만 움직인다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
시야 회전 처리
</p>

- OnHorizontalSight(float InAxisValue)
  - Yaw를 HorizontalSight 민감도로 반영한다.
  - bCameraMove가 False 일 때만 시야가 회전된다.
- OnVerticalSight(float InAxisValue)
  - Pitch를 VerticalSight 민감도로 반영한다.
  - bCameraMove가 False 일 때만 시야가 회전된다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
이동 속도 제어
</p>

- SetSpeed(ESpeedType InType)
  - CharacterMovementComponent->MaxWalkSpeed를 해당 타입의 속도로 설정한다.
- OnRun() / OffRun() / OnWalk()
  - 내부적으로 SetSpeed를 호출하여 속도를 전환한다.
  -  OffRun()과 OnWalk는 동일하게 걷기 속도로 설정된다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
이동 제어
</p>

- Move() / Stop()
  - bCanMove를 키거나 꺼서 이동 자체를 차단하거나 허용시킨다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
컨트롤 회전 모드 제어
</p>

- EnableControlRotation()
  - 캐릭터가 컨트롤러의 Yaw 회전에 따라 정면을 유지한다.
- DisableControlRotation()
  - 캐릭터가 이동 방향을 바라보도록 회전한다.