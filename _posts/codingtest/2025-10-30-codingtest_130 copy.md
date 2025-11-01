---
layout: post
title:  "CODING TEST"
date:   2025-10-30 09:00:00 +0900
categories:
  - codingtest
  - programmers
  - Lv.2
description: >
  Programmers - 92335
---
## k진수에서 소수 개수 구하기

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
문제 설명
</p>

양의 정수 n이 주어집니다. 이 숫자를 k진수로 바꿨을 때, 변환된 수 안에 아래 조건에 맞는 소수(Prime number)가 몇 개인지 알아보려 합니다.

- 0P0처럼 소수 양쪽에 0이 있는 경우
- P0처럼 소수 오른쪽에만 0이 있고 왼쪽에는 아무것도 없는 경우
- 0P처럼 소수 왼쪽에만 0이 있고 오른쪽에는 아무것도 없는 경우
- P처럼 소수 양쪽에 아무것도 없는 경우
- 단, P는 각 자릿수에 0을 포함하지 않는 소수입니다.
  - 예를 들어, 101은 P가 될 수 없습니다.

예를 들어, 437674을 3진수로 바꾸면 211020101011입니다. 여기서 찾을 수 있는 조건에 맞는 소수는 왼쪽부터 순서대로 211, 2, 11이 있으며, 총 3개입니다. (211, 2, 11을 k진법으로 보았을 때가 아닌, 10진법으로 보았을 때 소수여야 한다는 점에 주의합니다.) 211은 P0 형태에서 찾을 수 있으며, 2는 0P0에서, 11은 0P에서 찾을 수 있습니다.

정수 n과 k가 매개변수로 주어집니다. n을 k진수로 바꿨을 때, 변환된 수 안에서 찾을 수 있는 위 조건에 맞는 소수의 개수를 return 하도록 solution 함수를 완성해 주세요.

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
제한사항
</p>

- 1 ≤ n ≤ 1,000,000
- 3 ≤ k ≤ 10

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
입출력 예
</p>

<img src = "/assets/img/codingtest/92335.png" width = "200" height = "100">

입출력 예 #1
- 문제 예시와 같습니다.

입출력 예 #2
- 110011을 10진수로 바꾸면 110011입니다. 여기서 찾을 수 있는 조건에 맞는 소수는 11, 11 2개입니다. 이와 같이, 중복되는 소수를 발견하더라도 모두 따로 세어야 합니다.

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
작성 내용
</p>

{% raw %}
```cpp
#include <iostream>
#include <vector>

using namespace std;

bool isPrime(long long n)
{
    if(n <= 1) return false;
    if(n == 2) return true;
    if(n % 2 == 0) return false;
    
    for(long long i = 3; i*i <= n; i += 2)
    {
        if(n % i == 0) return false;
    }
    return true;
}

int solution(int n, int k) {
    int answer = 0;
    long long num = 0;
    long long pivot = 1;
    
    while(n > 0)
    {
        num += (n % k) * pivot;
        pivot *= 10;
        n /= k;
    }
    num += n * pivot * 10;

    long temp = 0;
    pivot = 1;

    while(num > 0)
    {
        if(num % 10 == 0)
        {
            if(isPrime(temp)) 
                answer++;
            temp = 0;
            pivot = 1;
        }
        else
        {
            temp += (num % 10) * pivot;
            pivot *= 10;
        }
        num /= 10;
    }
    
    if(isPrime(temp)) 
        answer++;
    
    return answer;
}
```
{% endraw %}

---

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
정답 여부 O
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
소요 시간 : 50분
</p>
