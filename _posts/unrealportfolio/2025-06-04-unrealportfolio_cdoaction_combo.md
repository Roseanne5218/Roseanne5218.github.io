---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - weapon
description: >
  CDoAction_Combo
---
## CDoAction_Combo

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CDoAction_Combo.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- UCDoAction
</p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 공격 입력 타이밍에 따라 다음 콤보로 이어지거나 종료로 흐름 제어
- 공격 중 피격된 대상을 수집해 가장 가까운 타겟을 기준으로 보정

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자
</p>

- UCDoAction_Combo()
  - 공중에서의 조작을 고려하여 AirControl 값 조정
- Tick(float InDeltaTime)
  - 타겟이 있을 경우 플레이어의 화면을 보간하여 회전

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
액션 동작 제어
</p>

- int32 GetIndex(int32 InIndex)
  - 콤보에서 사용할 인덱스 반환
- DoAction()
  - 연계 가능을 판단하여 연계
  - 인덱스를 기준으로 몽타주 실행
- Begin_DoAction()
  - 콤보가 이어질 수 있는 상태면 다음 공격 진행
  - 인덱스를 증가시킴
- End_DoAction()
  - 콤보 종료 시 인덱스 초기화
- SetComboIndex(int Combo)
  - 외부에서 설정한 콤보 수를 내부에 저장
- SetIndex(int InIndex)
  - 특정 인덱스를 사용하기 위해 AnimIndex 설정
- OnAttachEndCollision()
  - 공격 종료 시점에서 고정 카메라에 따라 분기 처리
- OnAttachBeginOverlap(ACharacter* InAttacker, AActor* InAttackCauser, ACharacter* InOther)
  - 타격 대상을 Hitted에 중복 없이 추가
  - 현재 콤보 단계의 데미지를 전송
