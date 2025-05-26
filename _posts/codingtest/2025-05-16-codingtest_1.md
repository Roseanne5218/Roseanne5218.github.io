---
layout: post
title:  "CODING TEST"
date:   2025-05-16 17:35:00 + 0900
categories:
  - codingtest
description: >
  BackJoon - 2750
---
## 수 정렬하기

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
문제
</p>

N개의 수가 주어졌을 때, 이를 오름차순으로 정렬하는 프로그램을 작성하시오.

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
입력
</p>

첫째 줄에 수의 개수 N(1 ≤ N ≤ 1,000)이 주어진다. 둘째 줄부터 N개의 줄에는 수가 주어진다. 이 수는 절댓값이 1,000보다 작거나 같은 정수이다. 수는 중복되지 않는다.

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
출력
</p>

첫째 줄부터 N개의 줄에 오름차순으로 정렬한 결과를 한 줄에 하나씩 출력한다.

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
작성 내용
</p>

```C++
#include <iostream>
using namespace std;

int main()
{
	int TotalNum;
	while (1)
	{
		cin >> TotalNum;
		if (TotalNum > 0 && TotalNum < 1000)
			break;
	}

	int* Num = new int[TotalNum];
	for (int i = 0; i < TotalNum; i++)
		cin >> Num[i];

	for (int i = 0; i < TotalNum; i++)
	{
		for (int l = i + 1; l < TotalNum; l++)
		{
			if (Num[i] > Num[l])
			{
				int temp = Num[i];
				Num[i] = Num[l];
				Num[l] = temp;
			}
		}
	}

	for (int i = 0; i < TotalNum; i++)
		cout << Num[i] << endl;

	return 0;
}
```

---

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
정답 여부 O
</p>
