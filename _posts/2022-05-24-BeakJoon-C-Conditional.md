---
layout: post
title: "BeakJoon C 알고리즘 문제풀이 "
date: 2022-05-25
excerpt: "조건문"
tags: [C_BeakJoon]
comments: true
---

# 조건문
------------------------------------------------------------

### 1-1. 두 수 비교하기_1330

~~~c
#include <stdio.h>
int main() {
	int A, B;

	scanf("%d %d", &A, &B);
	
	if (A > B) {
		printf(">");
	}
	else if (A < B) {
		printf("<");
	}
	else if (A == B) {
		printf("==");
	}

	return 0;
}
~~~

### 1-2. 시험 성적_9498

~~~c
#include <stdio.h>
int main() {
	int Score;

	scanf("%d", &Score);
	
	if (Score >= 90 ) 
		printf("A");	
	else if (Score >= 80 ) 
		printf("B");	
	else if (Score >= 70 ) 
		printf("C");	
	else if (Score >= 60) 
		printf("D");
	else
		printf("F");
	
	return 0;
}
~~~

### 1-3. 윤년

~~~c
#include <stdio.h>
int main() {
	int year;

	scanf("%d", &year);

	if (1 <= year && year <= 4000) {
		if (year % 4 == 0 && (year %100 != 0 || year % 400 == 0)) {
			printf("1");
		}
		else {
			printf("0");
		}
	}

	return 0;
}
~~~

### 1-4. 사분면 고르기

~~~c
#include <stdio.h>
int main() {
	int num1, num2;

	scanf("%d %d", &num1, &num2);

	if ((-1000 <= num1 <= 1000 && num1 != 0) && (-1000 <= num2 <= 1000 && num2 != 0)) {
		if (num1 > 0 && num2 > 0)
			printf("1");
		else if (num1 < 0 && num2 > 0)
			printf("2");
		else if (num1 < 0 && num2 < 0)
			printf("3");
		else if (num1 > 0 && num2 < 0)
			printf("4");
	}

	return 0;
}
~~~~

### 1-5. 알람시계

~~~c
#include <stdio.h>
int main() {
	int H, M;

	scanf("%d %d", &H, &M);

	if (H == 0) {
		if (M < 45) {
			H = 23;
			M = M + 60 - 45;
			printf("%d %d", H, M);
		}
		else if (M >= 45) {
			M = M - 45;
			printf("%d %d", H, M);
		}
	}
	else if (H > 0) {
		if (M < 45) {
			H = H - 1;
			M = M + 60 - 45;
			printf("%d %d", H, M);
		}
		else if (M >= 45) {
			M = M - 45;
			printf("%d %d", H, M);
		}
	}
	return 0;
}
~~~