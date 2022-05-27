---
layout: post
title: "BeakJoon C 알고리즘 문제풀이 "
date: 2022-05-26
excerpt: "1차원 배열"
tags: [C_BeakJoon]
comments: true
---

> # 1차원 배열
------------------------------------------------------------

> ### 1. 최소, 최대 _ 10818

~~~c
#include<stdio.h>

int main() {

	int A, Max = -1000000, Min = 1000000;
	int arr[1000000];

	scanf("%d", &A);

	for (int i = 0; i < A; ++i) {
		scanf("%d", &arr[i]);
	}

	for (int i = 0; i < A; ++i)  {
		
		if (Max < arr[i])
			Max = arr[i];

		if (Min > arr[i])
			Min = arr[i];
	}

	printf("%d %d", Min, Max);

	return 0;
}
~~~

> ### 2. 최댓값 _ 2562

~~~c
#include <stdio.h>

int main() {

    int arr[9], max = 0, J;

    for (int i = 0; i < 9; i++)
    {
        scanf("%d", &arr[i]);
        if (arr[i] > max)
        {
            max = arr[i];
            J = i+1;
        }
    }
    printf("%d\n%d", max, J);
}
~~~

> ### 3. 숫자의 개수 _ 2577

~~~c
#include <stdio.h>

int main() {
    int a, b, c;
    int num[10] = { 0 };
    scanf("%d %d %d", &a, &b, &c);
    int result = a * b * c;

    while (result > 0) {
        num[result % 10]++;
        result /= 10;
    }

    for (int i = 0; i < 10; i++) {
        printf("%d\n", num[i]);
    }
    return 0;
}
~~~

> ### 4. 나머지

~~~c
#include <stdio.h>

int main(void) {
	int  index[10], result = 0;

	for (int i = 0; i < 10; i++) {
		scanf("%d", &index[i]);
		index[i] = index[i] % 42;
	}

	for (int i = 0; i < 10; i++) {

		int count = 0;
		for (int j = 0; j < i; j++) {

			if (index[i] == index[j])
				count++;
		}
		if (count == 0) 
			result++;
		
	}

	printf("%d", result);

	return 0;
}
~~~

> ### 5. 평균 _ 1546

~~~c
#include <stdio.h>

int main(void) {
	int arr[1000];
	int size;
	double max_score = 0.0;
	double avg_score = 0.0;

	scanf("%d", &size);


	for (int i = 0; i < size; i++) {
		scanf("%d", &arr[i]);

		if (max_score < arr[i])
			max_score = arr[i];
	}

	for (int i = 0; i < size; i++) {
		avg_score += (double)arr[i] / max_score * 100.0;
	}

	printf("%.2lf", (avg_score/(double)size));

	return 0; 
}
~~~

> ### 6. OX퀴즈 _ 8958

~~~c
#include <stdio.h>
#include <string.h>

int main(void) {
	int a, add, sum;
	char arr[81];

		scanf("%d", &a);

	for (int i = 0; i < a; i++) {

		scanf("%s", arr);

		add = 1;
		sum = 0;

		for (int j = 0; j < strlen(arr); j++) {
			if (arr[j] == 'O') {
				sum += add;
				add ++  ;
			}
			else add = 1;
		}
		printf("%d\n", sum);
	}

	return 0;
}
~~~

> ### 7. 평균은 넘겠지 _ 4344

~~~c
#include <stdio.h>

int main(void) {
	int Test_Case, St_Case, St_sum = 0;
	int score[10000];
	double avg = 0, over_avg = 0;

	scanf("%d", &Test_Case);

	for (int i = 0; i < Test_Case; ++i) {
		scanf("%d", &St_Case);

		for (int j = 0; j < St_Case; j++) {
			scanf("%d", &score[j]);
			St_sum += score[j];
		}

		avg = ((double)St_sum / St_Case);

		for (int k = 0; k < St_Case; k++) {
			if (avg < score[k])
				over_avg++;
		}

		over_avg = over_avg / St_Case*100;

		printf("%.3lf%%\n", over_avg);

		St_sum = 0;
		over_avg = 0;
	}
}
~~~

