---
layout: post
title:  "CODING TEST"
date:   2025-05-20 09:00:00 +0900
categories:
  - codingtest
description: >
  Programmers - 12928
---
## 약수의 합

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
문제 설명
</p>
정수 n을 입력받아 n의 약수를 모두 더한 값을 리턴하는 함수, solution을 완성해주세요.

<br/>

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
제한 사항
</p>
n은 0 이상 3000이하인 정수입니다.

<br/>

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
입출력 예
</p>

<img src = "../../assets/img/codingtest/12928.png" width = "150" height = "110">

입출력 예 설명
입출력 예 #1
12의 약수는 1, 2, 3, 4, 6, 12입니다. 이를 모두 더하면 28입니다.

입출력 예 #2
5의 약수는 1, 5입니다. 이를 모두 더하면 6입니다.

<br/>

<p style = "color:#8f7cee; font-size:25px; font-weight:bold">
작성 내용
</p>

```C++
#include <iostream>

using namespace std;

int solution(int n) {
    int answer = 0;
    for(int i=1; i<=n; i++)
    {
        if(n%i ==0)
            answer +=i;
    }
    return answer;
}

int main()
{
    int n;
    while(1)
    {
        cin>>n;
        if(n>=0 && n<=3000)
            break;
    }
    cout<<solution(n)<<endl;
    
    return 0;
}
```

<br/>

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

<br/>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
정답 여부 O
</p>

<p style = "color:#ed9ece; font-size:20px; font-weight:bold">
소요 시간 : 10분
</p>
