---
layout: post
title:  "CODING TEST"
date:   2025-05-19 09:00:00 +0900
categories:
  - codingtest
  - backjoon
description: >
  BackJoon - 11659
---
## 구간 합 구하기 4

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
문제
</p>

수 N개가 주어졌을 때, i번째 수부터 j번째 수까지 합을 구하는 프로그램을 작성하시오.

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
입력
</p>

첫째 줄에 수의 개수 N과 합을 구해야 하는 횟수 M이 주어진다. 둘째 줄에는 N개의 수가 주어진다. 수는 1,000보다 작거나 같은 자연수이다. 셋째 줄부터 M개의 줄에는 합을 구해야 하는 구간 i와 j가 주어진다.

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
출력
</p>

총 M개의 줄에 입력으로 주어진 i번째 수부터 j번째 수까지 합을 출력한다.

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
작성 내용
</p>

```C++
#include <iostream>
#include <vector>
using namespace std;

int main()
{
	int N, M;

	while (true)
	{
		cin >> N >> M;
		if (N >= 1 && N <= 100000 && M >= 1 && M <= 100000)
			break;
	}

	vector<int> List(N + 1, 0);
	int num;
	for (int i = 0; i < N; i++)
	{
		cin >> num;
		if (i != 0)
			List.push_back(List[i - 1] + num);
		else
			List.push_back(num);
	}

	vector<int> Sum(M, -1);
	int i, j;
	for (int k = 0; k < M; k++)
	{
		cin >> i >> j;

		if (i > 1 && i <= N && i <= j)
		{
			Sum[k] = List[j - 1] - List[i - 2];
		}
		else if (i == 1)
		{
			Sum[k] = List[j - 1];
		}
	}
	List.clear();

	for (int k = 0; k < M; k++)
	{
		if (Sum[k] != -1)
			cout << Sum[k] << endl;
	}

	Sum.clear();

	return 0;
}
```

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
정답 내용
</p>

```C++
#include <iostream>
using namespace std;

int main()
{
	ios::sync_with_stdio(false);
	cin.tie(NULL);
	cout.tie(NULL);

	int suNo, quizNo;
	cin >> suNo >> quizNo;
	int S[100001] = {};

	for(int i=1; i<=suNo; i++)
	{
		int temp;
		cin >> temp;
		S[i] = S[i - 1] + temp;
	}

	for(int i=0; i<quizNo; i++)
	{
		int start, end;
		cin >> start >> end;
		cout << S[end] - S[start - 1] << endl;
	}
}
```

---

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
정답 여부 X
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
소요 시간 : 1시간 15분
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
문제 소감
</p>

- vector를 잘 사용 안 해봐서 NULL을 삽입 시 오류가 나는 현상을 몰랐다.

- 답안에서는 계산 시간을 줄이기 위하여 해당 연산들을 사용하였다.
	```
	ios::sync_with_stdio(false);
	cin.tie(NULL);
	cout.tie(NULL);
	```