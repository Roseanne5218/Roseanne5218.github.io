---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - utility
description: >
  FHelpers
---
## FHelpers

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
구현 목적
</p>

- 언리얼에서 반복적으로 사용되는 로직을 정형화하여 재사용성과 가독성을 높이는 정적 유틸리티 모음

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
전처리기 매크로
</p>

- CheckTrue(x)
  - x == true이면 종료
- CheckTrueResult(x, y)
  - x == true이면 y 리턴
- CheckFalse(x)	
  - x == false이면 종료
- CheckFalseResult(x, y)
  - x == false이면 y 리턴
- CheckNull(x)
  - x == nullptr이면 종료
- CheckNullResult(x, y)
  - x == nullptr이면 y 리턴
- CreateTextRenderComponent()
  - UTextRenderComponent를 설정값과 함께 생성

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
정적 함수 목록
</p>

- CreateComponent()
  - CreateDefaultSubobject로 컴포넌트를 생성하고 부모 컴포넌트와 연결한다.
  - 만약 루트가 없으면 루트로 지정한다.
- CreateActorComponent()
  - UActorComponent 기반 컴포넌트를 생성한다.
- GetAsset()
  - ConstructorHelpers를 기반하여 정적으로 로딩한다.
  - Editor 전용 로딩 시 사용한다.
- GetAssetDynamic()
  - StaticLoadObject 기반으로 동적 로딩을 한다.
  - 런타임중에 사용한다.