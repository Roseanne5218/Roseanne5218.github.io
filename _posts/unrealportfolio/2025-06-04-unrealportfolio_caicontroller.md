---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - character
description: >
  CAIController
---
## CAIController

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- AAIController
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CAIController.png" width = "1500" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 시야 기반 감지 시스템 설정
- 적 감지 시 BlackBoard 키에 정보 설정
- BehaviorTree 실행 및 BlackBoard 연동
- 같은 팀끼리 타깃 공유하여 자연스러운 집단전 설정

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자
</p>

- CAIController()
  - AI에 감지 거리, 시야각, 감지 대상을 설정하여 Perception을 이용하여 플레이어 또는 적을 감지할 수 있도록 해준다.
- BeginPlay()

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
상태 설정 / 업데이트트
</p>

- OnPossess(APawn* InPawn)
  - AI가 가진 BehaviorTree을 실행하고 AIComponent에 BlackBoard를 연결한다.
- OnPerceptionUpdate(const TArray<AActor*>& UpdatedActors)
  - 감지된 적을 BlackBoard의 키에 저장한다.
  - 감지를 잃으면 타깃 BlackBoard 값을 초기화시킨다.
- ShareTarget(AActor* Target)
  - 같은 팀의 다른 AI에게 타깃을 공유한다.
  - 한 AI가 적을 발견 시, 같은 팀 다른 AI도 해당 적을 추적 가능하도록 한다.

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
AI 설정 값
</p>

| 항목 | 값 | 설명 |
|:-------:|:------:|:------:|
| Sight Radius | 700 | AI가 감지할 수 있는 기본 시야 거리 |
| Lose Sight Radius | 900 | 감지 후 추적이 유지되는 거리 |
| 시야각 | 90도 | 시야 반경 설정 |
| 감지 대상 | Enemy | 중립, 아군은 감지 안 함 |
