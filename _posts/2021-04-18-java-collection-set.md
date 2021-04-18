---
title:  "[Java] Set 컬렉션 클래스"
excerpt: ""

categories:
  - Java
tags:
  - [Interview, Collection, Set, java]

toc: true
toc_sticky: true
 
date: 2021-04-18
last_modified_at: 2021-04-18
---

# **Set 컬렉션 클래스**

Set 인터페이스를 구현한 모든 Set 컬렉션 클래스는 다음과 같은 특징을 가진다.

1. 요소의 저장 순서를 유지하지 않음
2. 같은 요소의 중복 저장을 허용하지 않음.

대표적인 Set 컬렉션 클래스에 속하는 클래스는 두 가지가 있다.

1. HashSet&#60;E>
2. TreeSet&#60;E>


## HashSet&#60;E> 클래스
HashSet 클래스는 Set 컬렉션 클래스에서 가장 많이 사용되는 클래스 중 하나로
요소를 순서에 상관없이 저장하고 중복된 값은 저장하지 않는다.


```java
HashSet<String> hs01 = new HashSet<String>();

HashSet<String> hs02 = new HashSet<String>();

// add() 메소드를 이용한 요소의 저장
hs01.add("홍길동");
hs01.add("이순신");

System.out.println(hs01.add("임꺽정")); // true
System.out.println(hs01.add("임꺽정")); // 중복된 요소의 저장 > false

// Enhanced for 문과 get() 메소드를 이용한 요소의 출력
for (String e : hs01) {
    System.out.print(e + " ");
}

// add() 메소드를 이용한 요소의 저장
hs02.add("임꺽정");
hs02.add("홍길동");
hs02.add("이순신");

// iterator() 메소드를 이용한 요소의 출력
Iterator<String> iter02 = hs02.iterator();

while (iter02.hasNext()) {
    System.out.print(iter02.next() + " ");
}

// size() 메소드를 이용한 요소의 총 개수
System.out.println("집합의 크기 : " + hs02.size()); // 3
```

또한, add() 메소드를 사용하여 해당 HashSet에 이미 존재하는 요소를 추가하려고 하면, 해당 요소를 저장하지 않고 false를 반환하게 된다.

이때 해당 HashSet에 이미 존재하는 요소인지를 파악하기 위해서는 내부적으로 다음과 같은 과정을 거치게 되는데,

1. 해당 요소에서 hashCode() 메소드를 호출하여 반환된 해시값으로 검색할 범위를 결정한다.

2. 해당 범위 내의 요소들을 equals() 메소드로 비교한다.

따라서 HashSet에서 add() 메소드를 사용하여 중복 없이 새로운 요소를 추가하기 위해서는 hashCode()와 equals() 메소드를 상황에 맞게 오버라이딩해야 한다.