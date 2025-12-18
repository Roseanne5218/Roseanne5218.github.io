---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - weapon
description: >
  ACattach
---
## ACattach

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/ACattach.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- AActor
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 캐릭터에 붙는 무기를 관리하며, 무기의 Collision을 제어

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자
</p>

- ACAttach()
- BeginPlay()

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
메시에 부착
</p>

- AttachTo(FName InSocketName)
  - 캐릭터 메시 소켓에 액터 부착
- AttachToCollision(FName InCollisionName)
  - 특정 컴포넌트를 캐릭터 메시에 부착

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
이벤트 수신
</p>

- OnComponentBeginOverlap(UPrimitiveComponent* OverlappedComponent, AActor* OtherActor, UPrimitiveComponent* OtherComp, int32 OtherBodyIndex, bool bFromSweep, const FHitResult& SweepResult)
  - 오버랩 시작 이벤트 수신
- OnComponentEndOverlap(UPrimitiveComponent* OverlappedComponent, AActor* OtherActor, UPrimitiveComponent* OtherComp, int32 OtherBodyIndex)
  - 오버랩 종료 이벤트 수신

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Collision 관리
</p>

- OnCollision()
  - 모든 Collision 활성화
- OffCollision()
  - 모든 Collision 비활성화