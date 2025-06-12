---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - else
description: >
  CBossZone
---
## CBossZone

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CBossZone.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UInterface
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 보스 전용 구역에 플레이어가 들어올 경우 
  - 보스 등장 시네마틱 재생
  - UI 숨김 및 플레이어 이동 불가 처리
  - 보스 액터 및 무기 액터 활성화
  - 시네마틱 종료 후 보스 전투 준비

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자
</p>

- ACBossZone()
  - 플레이어가 들어가면 감지할 박스를 생성한다.
- BeginPlay()
  - 월드 내에 Tag가 Boss인 액터를 탐색하여 보스 캐릭터로 등록한다.

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
Zone 진입 확인
</p>

- OnComponentBeginOverlap(UPrimitiveComponent* OverlappedComponent, AActor* OtherActor, UPrimitiveComponent* OtherComp, int32 OtherBodyIndex, bool bFromSweep, const FHitResult& SweepResult)