---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - character
description: >
  CPlayer
---
## CPlayer

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CPlayer.png" width = "1000" height = "400">

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

- 키 입력 바인딩 처리
- 회피 / 점프 / 힐 스킬과 이펙트 실행
- 무기 변경 및 공격 모드
- 애님 인스턴스 연동을 통한 방향 보정

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자 및 초기화 
</p>

- ACPlayer()
  - 플레이어에게 고정된 카메라, 스프링암, 메시, 애님 인스턴스, 나이아가라, 이동 속도 값을 설정한다.
- BeginPlay()

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
이동 / 입력 처리
</p>

- SetupPlayerInputComponent(UInputComponent* PlayerInputComponent)
  - 모든 키 입력을 바인딩 해준다.
    - 이동 : WASD, 마우스 시야, 줌
    - 액션 : 회피, 힐, 점프, 무기 선택
    - 무기 공격 : 누름, 뗌에 따른 처리
- Tick(float DeltaTime)
  - 트레일 이펙트 활성화 조건을 확인하고 처리한다.
- UpdateTrailEvent()
  - 일정 속도 이상이면 TrailEffect를 활성화하고 조건에 해당하지 않으면 비활성화한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
점프 처리
</p>

- Jump()
  - 점프 실행 조건을 확인하고 LaunchCharacter()를 호출한다.
  - 점프 중 이동이 가능하도록 하고 점프 상태를 설정한다.
- Landed(const FHitResult&)
  - 점프 상태를 해제하고 원래 상태로 복귀한다.
- End_Jump()
  - 점프 종료 시 회전을 제어한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
회피 처리
</p>

- OnEvade()
  - 회피 가능 여부 확인 후 Evade 상태를 설정하고 입력 방향을 기준으로 회피 방향을 계산한다.
  - 애님 인스턴스에 각도를 전달하고 회피 모션이 종료될 때 End_Evade()를 호출한다.
- End_Evade()
  - 이동 속도, 회전 제어, 상태를 복구한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
회복 처리
</p>

- OnHeal()
  - 힐 가능 여부 확인 후 이펙트를 실행한다.
- Heal()
   - 체력을 회복하고 UI에도 적용한다.
- End_Heal()
  - 힐 쿨 다운이 해제되고 재사용이 가능하도록 한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
전투 및 상태 처리
</p>

- Damage() / End_Damage()
  - 데미지 시 움직임을 정지시키고 회복 시 이동을 재개시킨다.
- StartStun() / End_Stun()
  - 스턴 상태 시 이동을 정지시키고 타이머를 자동으로 시작한다.
  - 타이머 종료 시 이동을 재개시킨다.
- StartExecute()

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
애님 상태 연동
</p>

- OnStateTypeChanged(EStateType InPrevType, EStateType InNewType)
  - 상태 변화 이벤트에 따른 움직임 컴포넌트 액션을 수행한다.
