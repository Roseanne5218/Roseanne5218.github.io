---
layout: post
title:  "CODING TEST"
date:   2025-05-19 09:00:00 +0900
categories:
  - codingtest
  - backjoon
description: >
  BackJoon - 1546
---
## 평균

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
문제
</p>

세준이는 기말고사를 망쳤다. 세준이는 점수를 조작해서 집에 가져가기로 했다. 일단 세준이는 자기 점수 중에 최댓값을 골랐다. 이 값을 M이라고 한다. 그리고 나서 모든 점수를 점수/M*100으로 고쳤다.

예를 들어, 세준이의 최고점이 70이고, 수학점수가 50이었으면 수학점수는 50/70*100이 되어 71.43점이 된다.

세준이의 성적을 위의 방법대로 새로 계산했을 때, 새로운 평균을 구하는 프로그램을 작성하시오.

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
입력
</p>

첫째 줄에 시험 본 과목의 개수 N이 주어진다. 이 값은 1000보다 작거나 같다. 둘째 줄에 세준이의 현재 성적이 주어진다. 이 값은 100보다 작거나 같은 음이 아닌 정수이고, 적어도 하나의 값은 0보다 크다.

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
출력
</p>

첫째 줄에 새로운 평균을 출력한다. 실제 정답과 출력값의 절대오차 또는 상대오차가 10-2 이하이면 정답이다.

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
	int N, Score;
	int Max = 0;
	float Sum = 0;

	cin >> N;

	while(1)
	{
		if (N > 0 && N <= 1000)
			break;
	}

	vector<int> Scores;
	for(int i=0; i<N; i++)
	{
		cin >> Score;
		
		if (Score >= 0 && Score <= 100)
		{
			Scores.push_back(Score);
			if (Max < Score)
				Max = Score;
		}
		else
			i--;
	}
	
	for (int i = 0; i < N; i++)
		Sum += ((float)Scores[i] / (float)Max * 100);

	cout << Sum / N;

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
	int N = 0;
	int A[1000];
	cin >> N;

	for(int i=0; i<N; i++)
	{
		cin >> A[i];
	}

	long sum = 0;
	long max = 0;

	for(int i=0; i<N; i++)
	{
		if (A[i] > max)
			max = A[i];

		sum = sum + A[i];
	}

	double result = sum * 100.0 / max / N;
	cout << result << endl;
	
	return 0;
}
```

---

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
정답 여부 O
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
소요 시간 : 34분
</p>