---
layout: post
title:  "CODING TEST"
date:   2025-05-20 09:00:00 +0900
categories:
  - codingtest
  - backjoon
description: >
  BackJoon - 11660
---
## 구간 합 구하기 5

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
문제
</p>

N×N개의 수가 N×N 크기의 표에 채워져 있다. (x1, y1)부터 (x2, y2)까지 합을 구하는 프로그램을 작성하시오. (x, y)는 x행 y열을 의미한다.

예를 들어, N = 4이고, 표가 아래와 같이 채워져 있는 경우를 살펴보자.

```
1	2	3	4
2	3	4	5
3	4	5	6
4	5	6	7
```

여기서 (2, 2)부터 (3, 4)까지 합을 구하면 3+4+5+4+5+6 = 27이고, (4, 4)부터 (4, 4)까지 합을 구하면 7이다.

표에 채워져 있는 수와 합을 구하는 연산이 주어졌을 때, 이를 처리하는 프로그램을 작성하시오.

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
입력
</p>

첫째 줄에 표의 크기 N과 합을 구해야 하는 횟수 M이 주어진다. (1 ≤ N ≤ 1024, 1 ≤ M ≤ 100,000) 둘째 줄부터 N개의 줄에는 표에 채워져 있는 수가 1행부터 차례대로 주어진다. 다음 M개의 줄에는 네 개의 정수 x1, y1, x2, y2 가 주어지며, (x1, y1)부터 (x2, y2)의 합을 구해 출력해야 한다. 표에 채워져 있는 수는 1,000보다 작거나 같은 자연수이다. (x1 ≤ x2, y1 ≤ y2)

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
출력
</p>

총 M줄에 걸쳐 (x1, y1)부터 (x2, y2)까지 합을 구해 출력한다.

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
	ios::sync_with_stdio(false);
	cin.tie(NULL);
	cout.tie(NULL);

	int N, M;

	while (true)
	{
		cin >> N >> M;

		if (N >= 1 && N <= 1024 && M >= 1 && M <= 100000)
			break;
	}

	vector<vector<int>> Num(N + 1, vector<int>(N + 1, 0));
	vector<vector<int>> Sum(N + 1, vector<int>(N + 1, 0));

	for(int i=1; i<=N; i++)
	{
		for(int j=1; j<=N; j++)
		{
			cin>>Num[i][j];
			
			Sum[i][j] = Sum[i][j - 1] + Sum[i - 1][j] - Sum[i - 1][j - 1] + Num[i][j];
		}
	}

	int X1, Y1, X2, Y2;
	for(int i=0; i<M; i++)
	{
		cin>>X1>>Y1>>X2>>Y2;

		if(X1<=X2 && Y1<=Y2 && X1<=1000 && Y1<=1000 && X2<=1000 && Y2<=1000)
		{
			int area = Sum[X2][Y2] - Sum[X1 - 1][Y2] - Sum[X2][Y1 - 1] + Sum[X1 - 1][Y1 - 1];
			cout << area <<endl;
		}
		else
			i--;
	}

	return 0;
}
```

---

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
정답 내용
</p>

```C++
#include <iostream>
#include <vector>
using namespace std;

int main()
{
	ios::sync_with_stdio(false);
	cin.tie(NULL);
	cout.tie(NULL);

	int N, M;
	cin >> N >> M;

	vector<vector<int>> A(N + 1, vector<int>(N + 1, 0));
	vector<vector<int>> D(N + 1, vector<int>(N + 1, 0));

	for (int i = 1; i <= N; i++)
	{
		for (int j = 1; j <= N; j++)
		{
			cin >> A[i][j];
			D[i][j] = D[i][j - 1] + D[i - 1][j] - D[i - 1][j - 1] + A[i][j];
		}
	}

	for (int i = 0; i < M; i++)
	{
		int x1, y1, x2, y2;
		cin >> x1 >> y1 >> x2 >> y2;

		int result = D[x2][y2] - D[x1 - 1][y2] - D[x2][y1 - 1] + D[x1 - 1][y1 - 1];
		cout << result << endl;
	}
}
```

---

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
정답 여부 X
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
소요 시간 : 45분
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
문제 소감
</p>

- 테스트 케이스가 적어 어디서 오류 나는지 판별이 좀 힘들다. 책에 있는 예시를 그대로 적어도 시간 초과 오류가 나서 다른 책을 풀어볼까 생각 중이다.