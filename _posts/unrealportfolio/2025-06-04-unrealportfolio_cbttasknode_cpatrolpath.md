---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - behaviortree
description: >
  CPatrolPath
---
## CPatrolPath

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CPatrolPath.png" width = "1000" height = "400">

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

- AI Behavior Tree에서 이동할 목표 위치를 반환
- 다음 순찰 지점 인덱스를 제어
- 주어진 위치에서 가장 가까운 경로 위치 반환

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
경로 설정
</p>

- OnConstruction(const FTransform& Transform)
  - 액터가 에디터에서 생성 / 변경될 때 호출된다.
  - 에디터에서 이름을 보여주고 루프 여부를 설정한다.
- GetLocationFromIndex()
  - 현재 인덱스에 해당되는 지점을 월드 좌표로 반환하여 AI가 움직일 때 목표 지점으로 사용한다.
- SetNextIndex()
  - 현재 인덱스를 기준으로 다음 순찰 지점을 갱신하고 bReverse와 bLoop를 이용하여 역방향 전환 여부와 루프 처리를 자동으로 수행한다.
  - 루프일 때 마지막 지점에 도착하면 첫 지점으로 돌아가 반복 수행하고 아닐 경우 마지막 지점에서 역으로 돌아온다.
- GetClosestLocation(const FVector& InLocation)
  - 외부에서 위치를 전달하면 Spline 상에서 가장 가까운 지점의 위치를 반환한다.