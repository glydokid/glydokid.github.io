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

> ### 1-1. 구구단

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

> ### 1-2. A+B -3

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
