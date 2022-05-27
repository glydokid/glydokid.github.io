---
layout: post
title: "BeakJoon JAVA 알고리즘 문제풀이 "
date: 2022-05-27
excerpt: "조건문"
tags: [JAVA_BeakJoon]
comments: true
---

># 조건문
------------------------------------------------------------

> ### 1. 두 수 비교하기_1330

~~~java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		
		int A = sc.nextInt();
		int B = sc.nextInt();
		
		if(A>B) {
			System.out.print(">");
		}
		else if(A<B) {
			System.out.print("<");
		}
		else if (A==B) {
			System.out.print("==");
		}
	}
}
~~~

>### 2. 시험 성적_9498

~~~java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);

		int score = sc.nextInt();

		if (score >= 90) {
			System.out.print("A");
		} else if (score >= 80) {
			System.out.println("B");
		} else if (score >= 70) {
			System.out.println("C");
		} else if (score >= 60) {
			System.out.println("D");
		} else
			System.out.println("F");
	}

}
~~~

>### 3. 윤년 _ 2753

~~~java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);

		int y = sc.nextInt();
		sc.close();

		if (y % 4 == 0) {
			if (y % 400 == 0)
				System.out.println("1");
			else if (y % 100 == 0)
				System.out.println("0");
			else
				System.out.println("1");
		} else
			System.out.println("0");
	}
}
~~~


>### 4. 사분면 고르기 _ 14681

~~~java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		
		int a  = sc.nextInt();
		int b = sc.nextInt();
		
		if(a>0) {
			if(b>0) System.out.println("1");
			else System.out.println("4");
		}else {
			if(b>0) System.out.println("2");
			else System.out.println("3");
		}
	}
}
~~~


>### 5. 알람시계 _ 2884

~~~java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		
		int h  = sc.nextInt();
		int m = sc.nextInt();
		
		if(m<45) {
			h--;
			m = 60 - (45-m);
			
			if(h<0)
				h=23;
			
			System.out.println(h+" "+m);
		}else System.out.println(h+" "+(m-45));
	}
}
~~~

>### 6. 오븐시계 _ 2525

~~~java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);

		int H = sc.nextInt();
		int M = sc.nextInt();

		int time = sc.nextInt();

		sc.close();

		int a = H * 60 + M + time;
		H = a / 60;
		M = a % 60;

		if (H >= 24)
			H -= 24;
		System.out.println(H + " " + M);
	}

}
~~~