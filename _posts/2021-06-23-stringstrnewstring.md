---
title:  "[Java] String str = ""; 과 new String(); 의 차이"
excerpt: ""

categories:
  - Java
tags:
  - [Interview, , java]

toc: true
toc_sticky: true
 
date: 2021-06-23
last_modified_at: 2021-06-23
---

# String str = ""; 과 new String(); 의 차이

Java 내에서 String 문자열 생성방법에는 두 가지가 있다.
```java
String str = new String("Hello");
String str2 = "Hello";
String str3 = "Hello";
```

<br>
<br>

첫 번째는 new 연산자를 이용한 문자열 생성 방식이고, 두 번째는 문자열 리터럴 생성 방식이다.

두 방식의 차이는 메모리 영역에 있는데, new 연산자를 통해서 String 을 생성하면 `Heap` 영역에 존재하게 되고, 리터럴을 이용할 경우 `string constant pool` 이라는 영역에 존재하게 된다. 
<br>
<br>


![img1](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbAXpvj%2Fbtqw78T1Qz2%2FWlUnX9fa8CDPfxHpyyU2W1%2Fimg.png)
*출처 - (https://haenny.tistory.com/18)*

<br>
<br>


```java
String str = new String("Hello");
String str2 = "Hello";
String str3 = "Hello";

System.out.println(str1.equals(str2)); // true
System.out.println(str1 == str2); // false 
System.out.println(str2 == str3); // true
```
<br>

equals 연산자를 통해 비교하면 true 인데
== 연산자를 통해 비교하면 false 인 이유는 뭘까?
이는 equals 연산자는 단순 문자열을 비교하지만,
== 연산자는 두 객체의 주소값을 비교하기 때문에
서로 저장되는 영역이 다른 str 과 str2 의 주소값이 같을 수 없기 때문이다.