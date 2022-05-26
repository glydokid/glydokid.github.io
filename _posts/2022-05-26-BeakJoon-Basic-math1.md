---
layout: post
title: "BeakJoon C 알고리즘 문제풀이 "
date: 2022-05-26
excerpt: "기본수학 1"
tags: [C_BeakJoon]
comments: true
---

> # 기본수학 1
------------------------------------------------------------

> ### 1.손익분기점 _ 1712

~~~c
#include <stdio.h> 
int main(void) { 

	long A = 0, B = 0, C = 0, X = 1; 

	scanf("%ld %ld %ld", &A, &B, &C); 

	if (B >= C) {
		printf("-1"); return 0;
	}
	
	X = A/(C - B) + 1; 

	printf("%d", X); 

	return 0; 
}
~~~

> ### 2. 벌집 _ 2292

~~~c
#include<stdio.h>

int main(void) {
	int n;
	int i = 2, j = 5;
	int count = 2;

	scanf("%d", &n);

	if (n == 1) {
		printf("%d", 1);
		return 0;
	}

	while (1) {
		if (i <= n && i + j >= n) {
			printf("%d", count);
			break;
		}
		i = i + j + 1;
		j += 6;
		count++;
	}
}
~~~

> ### 3. 분수찾기 _ 1193

~~~c
#include <stdio.h>

int number, d, t; // number 는 몇번쨰 분수, d는 대각선 위치 

int main() {
    scanf("%d", &number);   // 사용자 입력값 받기

    for (; d * (d + 1) / 2 < number; d++) {  // 대각선 하나당 숫자가 1개씩 증가해서 모든 숫자들의 갯수를 더해줘서 몇번째 대각선에 사용자 입력값이 있는지 확인
    }

    t = number - d * (d - 1) / 2;  //  t는 대각선안에 몇번쨰 분수인지 찾아내는 변수
      // 14   -  5 * (4) /2 = 14 - 10 = ( t = 4 )

    if (d % 2 == 0) {  // 짝수번째 대각선은 위에서 아래
        printf("%d/%d", t, d - t + 1);
    }

    else   // 홀수번째 대각선은 아래에서 위부터
        printf("%d/%d", d - t + 1, t);

    return 0;
}
~~~

> ### 4. 달팽이는 올라가고 싶다 _ 2869

~~~c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int A, B, V;
    scanf("%d %d %d", &A, &B, &V);
    int day;

    if ((V - A) % (A - B) == 0)
        day = (V - A) / (A - B);
    else
        day = (V - A) / (A - B) + 1;

    printf("%d\n", day + 1);

}
~~~

> ### 5. ACM 호텔 _ 10250

~~~c
#include <stdio.h>

int main()
{
	int T;
	int H, W, N;

	scanf("%d", &T);

	for (int j = 0; j < T; j++)
	{
		scanf("%d %d %d", &H, &W, &N);

		if (N % H == 0)
			printf("%d\n", H * 100 + N / H);

		else
			printf("%d\n", (N % H) * 100 + N / H + 1);
	}

	return 0;
}
~~~

> ### 7. 설탕 배달 _ 2839 

~~~c
#include <stdio.h>

int main() {
	
	int N;
	int count = 0;

	scanf("%d", &N);

	while (1) {
		if (N % 5 == 0) {
			printf("%d", count + (N / 5));
			break;
		}


		N = N - 3;
		count++;

		if (N < 0) {
			printf("-1");
			break;
		}
	}
}
~~~

