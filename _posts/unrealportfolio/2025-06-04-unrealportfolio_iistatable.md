---
layout: post
title:  "UNREAL PORTFOLIO"
date:   2025-06-04 09:00:00 +0900
categories:
  - unrealportfolio
  - character
description: >
  IIStatable
---
## IIStatable

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
코드 구조
</p>

<img src = "/assets/img/unrealportfolio/IIStatable.png" width = "1000" height = "400">

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

- 다양한 캐릭터 클래스에서 상태별 후처리 로직 공통화
- 상태가 종료되는 타이밍에 Notify를 명확히 호출 가능
-  캐릭터 클래스들이 해당 인터페이스를 구현하여 후속 처리 동작 오버라이딩 가능

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
함수 목록
</p>

- End_Damage()
- End_Dead()
- End_Stun()
- End_Evade()
- End_Jump()
- End_Action()