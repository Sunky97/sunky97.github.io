---
title:  "[백준 1110]더하기 사이클"
excerpt: ""

categories:
  - BOJ
tags:
  - [Coding Test, Algorithm, 백준]

toc: true
toc_sticky: true
 
date: 2021-03-15
last_modified_at: 2021-03-16
---

# **문제**
0보다 크거나 같고, 99보다 작거나 같은 정수가 주어질 때 다음과 같은 연산을 할 수 있다. 먼저 주어진 수가 10보다 작다면 앞에 0을 붙여 두 자리 수로 만들고, 각 자리의 숫자를 더한다. 그 다음, 주어진 수의 가장 오른쪽 자리 수와 앞에서 구한 합의 가장 오른쪽 자리 수를 이어 붙이면 새로운 수를 만들 수 있다. 다음 예를 보자.

26부터 시작한다. 2+6 = 8이다. 새로운 수는 68이다. 6+8 = 14이다. 새로운 수는 84이다. 8+4 = 12이다. 새로운 수는 42이다. 4+2 = 6이다. 새로운 수는 26이다.

위의 예는 4번만에 원래 수로 돌아올 수 있다. 따라서 26의 사이클의 길이는 4이다.

N이 주어졌을 때, N의 사이클의 길이를 구하는 프로그램을 작성하시오.
<br><br><br><br><br><br><br>
# **알고리즘**
입력값 n 이 들어온다고 가정하고 n의 `일의자리` 는 `새로운 숫자의 십의자리`로, n의 `일의자리와 십의자리를 더한 숫자의 일의자리`는 `새로운 숫자의 일의자리` 가 되는 구조
<br><br><br><br>

새로 만드는 숫자를 T 라고 하면
```java
// T 의 십의자리
T = (n%10)*10;

// T 의 일의자리
T = ((n/10) + (n%10))%10;
```
<br><br><br><br>
즉 T 는 
```java
T = ((n%10)*10) + (((n/10) + (n%10))%10);
```
<br><br><br>
# **내 코드**
```java
class Main
{
	public static void main (String[] args) throws java.lang.Exception
	{
	    BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
		
		//카운트
		int count = 0;
		
		//입력
	    int n = Integer.parseInt(bf.readLine());
	    
        //입력값 저장
	    int copy = n;

		while(true){
		      
	    n = ((n % 10) * 10) + (((n / 10) + (n % 10)) % 10);

        count++;
	    
	    if(n == copy){
	        break;
	      }
	    }
	    
	    System.out.println(count);
	}
}
```