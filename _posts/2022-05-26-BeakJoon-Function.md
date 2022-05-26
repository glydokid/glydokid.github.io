---
layout: post
title: "BeakJoon C 알고리즘 문제풀이 "
date: 2022-05-26
excerpt: "함수"
tags: [C_BeakJoon]
comments: true
---

> # 함수
------------------------------------------------------------

> ### 2. 셀프넘버 _ 4673

~~~c
#include <stdio.h>

int self_number();

int main() {
	self_number();
	return 0;
}

int self_number() {
	int result = 0;
	int arr[10001] = { 0 };

	for (int i = 1; i < 10000; i++) {
		if (i < 10) {
			result = i + i;
			arr[result] = 1;
		}
		else if (i < 100) {
			result = i + (i / 10) + (i % 10);
			arr[result] = 1;
		}
		else if (i < 1000) {
			result = i + (i / 100) + ((i % 100) / 10) + ((i % 100) % 10);
			arr[result] = 1;
		}
		else if (i < 10000) {
			result = i + (i / 1000) + ((i % 1000) / 100) + (((i % 1000) % 100) / 10) + (((i % 1000) % 100) % 10);
			if (result <= 10000)
				arr[result] = 1;
		}
	}

	for (int i = 1; i <= 10000; i++) {
		if (arr[i] != 1)
			printf("%d\n", i);
		}
	return 0;
	}
~~~


