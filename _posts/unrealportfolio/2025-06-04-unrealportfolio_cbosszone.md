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
- AActor
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
  - 플레이어가 해당 박스 안에 진입하였으면 시네마틱을 실행한다.
  - 시네마틱이 실행하는 동안 플레이어의 UI를 비활성화하고 움직임을 정지시킨다. 
  - 타이머를 이용하여 시네마틱이 종료될 때 종료 설정을 하는 함수를 실행시킨다.

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
시네마틱 종료 처리
</p>

- CinematicFinished()
  - SequenceActor을 제거하고 플레이어의 이동이 가능하도록 상태를 초기화 시킨다.
  - 플레이어의 UI와 보스 UI를 활성화시키고 ToggleBossVisibility()로 보스 설정을 한다.
- ToggleBossVisibility()
  - 보스 액터의 숨김을 해제시키고 충돌과 Tick을 활성화시킨다.
  - 보스의 AIPerception을 활성화하고 보스의 무기도 같은 처리를 해준다.