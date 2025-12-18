---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - weapon
description: >
  CWeaponStructures
---
## CWeaponStructures

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/CWeaponStructures.png" width = "1000" height = "400">

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 공격과 타격 데이터 설정

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
데이터 설정
</p>

- DoAction(ACharacter* InOwner)
  - Owner의 움직임을 가져와 카메라와 이동 설정
  - 몽타주가 있으면 재생
- SendDamage(ACharacter* InAttacker, AActor* InAttackCauser, ACharacter* InOther)
  - 현재 HitData를 TakeDamage를 통해 데미지 전달
- PlayEnemyHitMotion(ACharacter* InCharacter)
  - EnemyMontage로 일반 적 피격 몽타주 재생
- PlayBossHitMotion(ACharacter* InCharacter)
  - BossMontage로 보스 피격 몽타주 재생
- PlayHitSubActionMotion(ACharacter* InCharacter)
  - SubActionMontage로 서브액션 피격/반응 몽타주 재생
- PlayGuardCrashMotion(ACharacter* InCharacter)
  - CrashMontage로 가드 브레이크/크래시 몽타주 재생 (CrashPlayRate 사용)
- PlayExecuteMontage(ACharacter* InCharacter)
  - ExecuteMontage로 처형 몽타주 재생
- PlayAirMontage(ACharacter* InCharacter)
  - AirMontage로 에어 관련 몽타주 재생
- PlayAirExecuteMontage(ACharacter* InCharacter)
  - AirExecuteMontage로 공중 처형 몽타주 재생
- PlayHitStop(ACharacter* InCharacter)
  - StopTime 동안 레벨 내 Movable Mesh를 가진 Actor들의 CustomTimeDilation을 매우 낮게 설정해 히트스톱 연출
  - 타이머 종료 후 해당 Actor들의 CustomTimeDilation을 1.0으로 복구
- PlayEffect(ACharacter* InCharacter)
  - 캐릭터 위치/회전에 EffectLocation 오프셋을 적용해 Effect를 지정 스케일로 스폰,재생
- PlayCameraShake(ACharacter* InCharacter)
  - 플레이어 카메라 매니저를 통해 CameraShake를 StartCameraShake로 재생