---
layout: post
title:  "VISUAL C++"
date:   2024-11-26 18:00:00 + 0900
categories:
  - language
  - visualc
description: >
  Visual C++
---
## Visual C++

### 컴파일 과정
<img src="img/language/visualc/IMG_v1" width="100" height="100">

### 프로세스
<img src="IMG_v2./image.png", height="100x", width="100px">

### 자료형
```C++
#inlude <stdio.h>
{
  int a = 10; //정수형 - 4 Byte
  float b = 3.14159268f; //실수형 - 4 Byte
  long c = 100; //정수형 - 4 Byte
  unsigned long d = 0xABCDEF01; //부호없음
  double e = 3.14L; //8 바이트
  short f = 100; //2 바이트
  unsigned char g = 0b00000001; //1 바이트
}
```

## 포인터
#### 포인터는 다른 변수나 그 변수의 메모리 공간 주소를 가리키는 변수를 의미한다. 포인터가 가리키는 값을 가져오는 것을 역참조라고 한다.
```C++
#include <stdio.h>

int main()
{
   int a = 10;
   printf("a = %d\n", a);
   printf("&a = %p\n", &a);

   int* p = &a;
   printf("p = %p\n", p);
   printf("*p = %d\n", *p);
   printf("&p = %p\n", &p);

   
   *p = 20;
   printf("*p = %d\n", *p);
   printf("a = %d\n", a);


   int& r = a;
   printf("a = %d\n", a);
   printf("r = %d\n", r);
   printf("&a = %p\n", &a);
   printf("&r = %p\n", &r);

   return 0;
}
```
<img src="IMG_v3./image.png", height="100x", width="100px">

## 메모리 번지
<img src="IMG_v4./image.png", height="100x", width="100px">