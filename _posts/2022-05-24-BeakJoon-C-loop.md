---
layout: post
title: "BeakJoon C 알고리즘 문제풀이 "
date: 2022-05-25
excerpt: "반복문"
tags: [C_BeakJoon]
comments: true
---

> # 반복문
------------------------------------------------------------

> ### 1. 구구단 _ 2739

~~~c
#include <stdio.h>
int main() {
	int num, i;

	scanf ("%d", &num);

	for (i = 1; i < 10; ++i) {
		printf("%d * %d = %d\n", num, i, num * i);
	}
	return 0;
}
~~~

> ### 2. A+B -3 _ 10950

~~~c
#include <stdio.h>
int main() {
	int a, b, i, n;

	scanf ("%d", &n);

	for (i = 1; i <= n; ++i) {
		scanf("%d %d\n", &a,&b);
		printf("%d\n", a + b);
	}
	return 0;
}
~~~

>### 3. 합 _ 8393

~~~c
#include <stdio.h>
int main() {
	int i, n, sum = 0;

	scanf ("%d", &n);

	for (i = 1; i <= n; ++i) {
		sum += i;
	}
	printf("%d\n", sum);
	return 0;
}
~~~

>### 5. N 찍기 _ 2741

~~~c
#include <stdio.h>
int main() {
	int a, sum = 0;

	scanf("%d", &a);

	for (int i = 1; i <= a; ++i) {
		sum += 1;
		printf("%d\n",sum);
	}
}
~~~

>### 6.기찍 N _ 2742

~~~c
#include <stdio.h>
int main() {
	int a, sum;

	scanf("%d", &a);

	sum = a+1;

	for (int i = 1; i <= a; ++i) {
		sum -= 1;
		printf("%d\n",sum);
	}
}
~~~

>### 7. A+B - 7 _ 11021

~~~c
#include <stdio.h>
int main() {
	int num1, num2, n;

	scanf("%d", &n);


	for (int i = 1; i <= n; ++i) {
			scanf("%d %d", &num1, &num2);

			if (num1 < 10 && num2 < 10) 
			printf("Case #%d: %d\n", i, num1 + num2);
	}
	return 0;
}
~~~

>### 9. 별찍기 - 1

~~~c
#include <stdio.h>
int main() {
	int a;

	scanf("%d", &a);

	for (int i = 1; i <= a; ++i) {
		
		for (int j = 1; j <= i; ++j) {
			printf("*");
		}

		printf("\n");
	}

	return 0;
}
~~~

>### 11. X보다 작은 수 _ 10871

~~~c
#include<stdio.h>
int main() {
    int N, X, input;

    scanf("%d %d", &N, &X);

    for (int i = 0; i < N; i++) {
        scanf("%d", &input);

        if (X > input)
            printf("%d ", input);
    }
    return 0;
}
~~~

>### 12. A+B - 5 _ 10952

~~~c
#include<stdio.h>
int main() {
    int num1 = 1, num2 = 1;

    while (1) {
        scanf("%d %d", &num1, &num2);
        if (num1 == 0 && num2 == 0)
            break;

        printf("%d\n", num1 + num2);
    }return 0;
}
~~~

>### 13. A+B - 4 _ 10951

~~~c
#include<stdio.h>
int main() {

    int num1, num2;

    while (scanf("%d %d", &num1, &num2) != EOF) {

           printf("%d\n", num1 + num2);

    }return 0;
}
~~~

>### 14. 더하기 사이클 _ 1110

~~~c
#include<stdio.h>
int main() {

    int A,B,C,D;
    int number, result;
    int count = 0;

    scanf("%d", &number);
    result = number;

    while (1) {
        A = number / 10;
        B = number % 10;
        C = (A + B) % 10;
        D = (B * 10) + C;
        number = D;
        count++;

        if (D == result)
            break;
    }
    printf("%d", count);

    return 0;
}
~~~