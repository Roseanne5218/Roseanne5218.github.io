---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - utility
description: >
  FLog
---
## FLog

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 언리얼에서 로그와 화면 출력을 간단하게 출력하기 위한 테스트 코드

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
출력 함수
</p>

- Log(int32 InValue)
  - 정수 값을 UE_LOG로 출력
- Log(float InValue)
  - 실수 값을 UE_LOG로 출력
- Log(const FString& InValue)
  - 문자열을 UE_LOG로 출력
- Log(const FVector& InValue)
  - 백터를 문자열로 변환해 UE_LOG로 출력
- Log(const FRotator& InValue)
  - 로테이터를 문자열로 변환해 UE_LOG로 출력
- Log(const UObject* InValue)
  - UObject의 이름과 Null 여부를 조합해 UE_LOG로 출력
- Print(int32 InValue, int32 InKey, float InDuration, const FColor& InColor)
  - 정수 값을 화면에 메시지로 출력
- Print(float InValue, int32 InKey, float InDuration, const FColor& InColor)
  - 실수 값을 화면에 메시지로 출력
- Print(const FString& InValue, int32 InKey, float InDuration, const FColor& InColor)
  - 문자열을 화면에 메시지로 출력
- Print(const FVector& InValue, int32 InKey, float InDuration, const FColor& InColor)
  - 백터를 문자열로 변환해 화면에 메시지로 출력
- Print(const FRotator& InValue, int32 InKey, float InDuration, const FColor& InColor)
  - 로테이터를 문자열로 변환해 화면에 메시지로 출력
- Print(const UObject* InValue, int32 InKey, float InDuration, const FColor& InColor)
  - UObject의 이름과 Null 여부를 조합해 화면에 메시지로 출력
