---
layout: post
title:  "CODING TEST"
date:   2025-05-16 17:35:00 + 0900
categories:
  - codingtest
description: >
  BackJoon - 11720
---
## 숫자의 합

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
문제
</p>
N개의 숫자가 공백 없이 쓰여있다. 이 숫자를 모두 합해서 출력하는 프로그램을 작성하시오.

<br/>

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
입력
</p>
첫째 줄에 숫자의 개수 N (1 ≤ N ≤ 100)이 주어진다. 둘째 줄에 숫자 N개가 공백없이 주어진다.

<br/>

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
출력
</p>
입력으로 주어진 숫자 N개의 합을 출력한다.

<br/>

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
작성 내용
</p>

```C++
#include <iostream>
using namespace std;

int main()
{
	int N;
	string Numbers;
	int Total = 0;

	while(true)
	{
		cin >> N;

		if (N >= 1 && N <= 100)
			break;
	}

	cin >> Numbers;

	for (int i = 0; i < N; i++)
		Total += Numbers[i] - '0';

	cout << Total;

	return 0;
}
```

<br/>

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
정답 내용
</p>

```C++
#include <iostream>
using namespace std;

int main()
{
	int N = 0; 
	string numbers;
	cin >> N;
	cin >> numbers;

	int sum = 0;
	for(int i=0; i<numbers.length(); i++)
	{
		sum += numbers[i] - '0';
	}
	cout << sum << endl;
}
```

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
정답 여부 O
</p>
