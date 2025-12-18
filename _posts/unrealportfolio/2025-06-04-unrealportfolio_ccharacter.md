---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - character
description: >
  CCharacter
---
## CCharacter

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
부모 클래스
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- ACharacter
<p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- IIStatable
<p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
- IGenericTeamAgentInterface
<p>

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CCharacter.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 캐릭터들이 상속받을 코드로 적과 플레이어가 같이 사용할 코드 구현
- 전투 상태 관리
- 패링, 스턴, 처형 가드 브레이크 등 복합 전투 로직 처리
- UI 연동
- 공중 공격 및 시네마틱 전환을 포함한 보스 연출
- 팀 기반 전투 구분 및 아군과 적군 식별
- 물리 반동, 방향 회전, 애니메이션 재생 통합

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
생성자 및 초기화
</p>

- CCharacter()
- BeginPlay()
  - 캐릭터들의 체력 위젯을 설정한다.
- Tick(float DeltaTime)
  - 해당 캐릭터가 공중에 있는지 판단한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
전투 시스템
</p>

- TakeDamage(float DamagePower, FDamageEvent const& DamageEvent, AController* EventInstigator, AActor* DamageCauser)
  - 공격자, 공격 원인, 데미지 이벤트를 저장한다.
  - State를 Damage로 변경한다.
- OnStateTypeChange(EStateType InPrevType, EStateType InNewType)
  - 분기를 이용하여 Damage()나 Dead()를 호출한다.
- Damage()
  - 데미지를 적용하고 상태, 애니메이션, 이펙트, 진동 등을 처리한다.
  - 패링 : 현재 캐릭터가 패링 상태일 경우 패링 몽타주를 재생하고 반격한다. 공격자는 공격이 실패하고 스턴이 걸린다.
  - 가드 : 무기가 가드이고 가드의 체력이 있으면 서브 모션이 실행된다. 가드가 깨지면 가드 파괴 모션과 피해를 적용 후 가드 체력을 초기화한다.
  - 처형 : 체력이 30 이하이면 처형 모션이 실행된다. 적이 공중에 있으면 공중 처형 모션, 땅에 있으면 일반 처형을 한다. 보스가 처형을 당하면 카메라 전환되고 카메라 쉐이크가 실행된다.
  - 피격 : 일반 피격의 경우 데미지 모션이 재생된다. 적이 공중에 있으면 공중 데미지 모션을 재생하고 런치 처리한다. 피격 시 캐릭터 방향 반동 회전 및 밀림을 처리한다.
  - 일반 사망 : 체력이 0 이하이거나 처형 모션이 없으면 일반 사망 처리 한다.
- End_Damage()
  - 피격 상태가 종료되면 상태 복귀 처리한다.
  - 무기가 가드이면 가드 상태로 아니면 Idle 상태로 복귀해 준다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
사망 처리
</p>

- Dead()
  - 사망 애니메이션 실행
- End_Dead()
   - 부착되어 있는 모든 액터를 제거한다.
   - UI 위젯도 제거하고 Destroy()를 호출한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
패링 시스템
</p>

- StartParry()
   - 패링 상태로 전환하고 이미 패링 중이거나 스턴 상태이면 무시한다.
   - 패링 지속시간 이후 EndParry()를 호출한다.
- EndParry()
  - 패링 상태를 종료한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
처형 / 스턴
</p>

- StartExecute()
  - 지상의 처형 애니메이션을 실행한다.
- StartAirExecute()
  - 공중 처형 애니메이션을 실행한다.
- StartStun()
  - 스턴 상태를 진입하고 스턴 모션을 실행하고 데미지를 입는다.
- End_Stun()
  - 스턴이 끝난 후 Idle 상태로 전환한다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
상태 고정 / 해제
</p>

- OwnerFreeze(float InDuration)
  - 중력을 제거하고 이동을 정지시킨다. 
  - 일정 시간 이후 RestoreMovement()를 호출한다.
- RestoreMovement()
  - 원래 기본 설정되어 있는 중력으로 회복시킨다.

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
UI 처리
</p>

- ShowUI()
  - 숨긴 체력바를 보이게 한다.
- HideUI()
  - 체력바를 숨긴다.