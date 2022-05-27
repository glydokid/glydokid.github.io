---
layout: post
title: "BeakJoon C 알고리즘 문제풀이 "
date: 2022-05-26
excerpt: "문자열"
tags: [C_BeakJoon]
comments: true
---

> # 문자열
------------------------------------------------------------

> ### 1. 아스키코드 _ 11654

~~~c
#include <stdio.h>

int main() {
	char input;

	scanf("%c", &input);
	printf("%d", input);
}
~~~

> ### 2. 숫자의 합 _ 11720

~~~c
#include <stdio.h>

int main(void) {

    int n, sum = 0;
    char arr[101] = {0};

    scanf("%d", &n);
    scanf("%s", &arr);

    for (int i = 0; i < n; i++) {
        sum += arr[i] - 48;
    }

    printf("%d", sum);
}
~~~

> ### 4. 문자열 반복 _ 2675

~~~c
#include <stdio.h>
#include <string.h>

int main() {

	int T, R;
	char S[20];

	scanf("%d", &T);

	for (int i = 0; i < T; i++) {

		scanf("%d %s", &R, S);

		for (int j = 0; j < strlen(S); j++) {

			for (int k = 0; k < R; k++) {
				printf("%c", S[j]);
			}
		}printf("\n");
	}

	return 0;
}

~~~

> ### 5. 단어 공부 _ 1157

~~~c
#include <stdio.h>
#include <string.h>

int main() {

	char word[1000000]; //최대 단어길이
	int count[26] = {0}; //알파벳의 길이
	int len;
	int result = 0; //단어 중복 누적
	int number; //배열의 값
	int select =0; //최다 사용 단어 저장

	scanf("%s", word);

	len = strlen(word);

	for (int i = 0; i < len; i++) {

		if (word[i] >= 'A' && word[i] <= 'Z')
			number = (word[i] - 'A'); //아스키코드 값상 대문자 A를 빼면 0~26사이 값이 저장
		
		else if(word[i]>='a' && word[i] <= 'z')
			number = (word[i] - 'a');

		count[number]++;
	} 

	int max = count[0];

	for (int i = 1; i < 26; i++) {
		if (max < count[i])
			max = count[i], select = i;
	}

	for (int i = 0; i < 26; i++) {
		if (max == count[i]) 
			result++; 
	}

		if (result > 1) 
			printf("?\n"); 
		else
			printf("%c", select + 'A');

		return 0;
}

~~~

> ### 6. 단어의 개수 _ 1152

~~~c
#include <stdio.h>
#include <string.h>

int main(void) {

	int i, count = 0, len;
	char word[1000000];

	scanf("%[^\n]", word); // 엔터가 나올때까지 문자열을 받음(공백 포함)
	len = strlen(word);

	if (len == 1) { //공백 하나만 입력시 예외문 처리
		if (word[i] == ' ') {
			printf("0\n");
			return 0;
		}
	}

	for (i = 1; i < len-1; i++) {
		if (word[i] == ' ')
			count++;
	}

	printf("%d", count + 1);

	return 0;

}
~~~

> ### 7. 상수 _ 2908

~~~c
#include <stdio.h>
#include <string.h>

int main(void) {

	char A[4], B[4], temp;

	scanf("%s %s", A, B);

	temp = A[2];
	A[2] = A[0];
	A[0] = temp;

	temp = B[2];
	B[2] = B[0];
	B[0] = temp;

	if (strcmp(A, B) > 0)
		printf("%s", A);
	else
		printf("%s", B);

	return 0;
}
~~~

> ### 8. 다이얼 _ 5622

~~~c
#include <stdio.h>
#include <string.h>

int NUM(int n);

int main(void) {

	int sum = 0;
	char word[15];

	scanf("%s", word);

	int len = strlen(word);

	for (int i = 'A'; i <= 'Z'; i++) {

		for (int j = 0; j < len; j++) {
			if (i == word[j])
				sum += NUM(i);
		}
	}

	printf("%d", sum);
	return 0;
}

int NUM(int n) {

	switch (n) {
	case 'A':
	case 'B':
	case 'C':
		return 3;

	case 'D':
	case 'E':
	case 'F':
		return 4;

	case 'G':
	case 'H':
	case 'I':
		return 5;

	case 'J':
	case 'K':
	case 'L':
		return 6;

	case 'M':
	case 'N':
	case 'O':
		return 7;

	case 'P':
	case 'Q':
	case 'R':
	case 'S':
		return 8;

	case 'T':
	case 'U':
	case 'V':
		return 9;

	default:
		return 10;
	}

}
~~~

> ### 9. 크로아티아 알파벳 _ 2941

~~~c
#include <stdio.h>
#include <string.h>

int main(void) {

	char word[100];

	scanf("%s", word);

	int len = strlen(word);
	int count = strlen(word);

	for (int i = 0; i < len; i++) {
		if ((word[i] == 'l' || word[i] == 'n') && word[i + 1] == 'j')
			count--;
		if (word[i] == 'd' && word[i + 1] == 'z' && word[i + 2] == '=')
			count--;
		if (word[i] == '=' || word[i] == '-')
			count--;
	}
	printf("%d", count);

}
~~~



