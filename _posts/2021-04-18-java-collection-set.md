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

`Set` 인터페이스를 구현한 모든 `Set` 컬렉션 클래스는 다음과 같은 특징을 가진다.

1. 요소의 저장 순서를 유지하지 않음
2. 같은 요소의 중복 저장을 허용하지 않음.

대표적인 `Set` 컬렉션 클래스에 속하는 클래스는 두 가지가 있다.

1. HashSet&#60;E>
2. TreeSet&#60;E>


## HashSet&#60;E> 클래스
`HashSet` 클래스는 `Set` 컬렉션 클래스에서 가장 많이 사용되는 클래스 중 하나로
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

또한, add() 메소드를 사용하여 해당 `HashSet`에 이미 존재하는 요소를 추가하려고 하면, 해당 요소를 저장하지 않고 false를 반환하게 된다.

이때 해당 `HashSet`에 이미 존재하는 요소인지를 파악하기 위해서는 내부적으로 다음과 같은 과정을 거치게 되는데,

1. 해당 요소에서 hashCode() 메소드를 호출하여 반환된 해시값으로 검색할 범위를 결정한다.

2. 해당 범위 내의 요소들을 equals() 메소드로 비교한다.

따라서 `HashSet`에서 add() 메소드를 사용하여 중복 없이 새로운 요소를 추가하기 위해서는 hashCode()와 equals() 메소드를 상황에 맞게 오버라이딩해야 한다.

<br>

## 해시 알고리즘(hash algorithm)

해시 알고리즘(hash algorithm)이란 해시 함수(hash function)를 사용하여 데이터를 해시 테이블(hash table)에 저장하고, 다시 그것을 검색하는 알고리즘이다.

![a](http://tcpschool.com/lectures/img_java_hash_algorithm.png)

자바에서 해시 알고리즘을 이용한 자료 구조는 위의 그림과 같이 배열과 연결 리스트로 구현되는데, 저장할 데이터의 키값을 해시 함수에 넣어 반환되는 값으로 배열의 인덱스를 구한다.

그리고 해당 인덱스에 저장된 연결 리스트에 데이터를 저장하게 된다.

<br>

## TreeSet<E> 클래스
`TreeSet` 클래스는 데이터가 정렬된 상태로 저장되는 이진 검색 트리(binary search tree)의 형태로 요소를 저장한다.

이진 검색 트리는 데이터를 추가하거나 제거하는 등의 기본 동작 시간이 매우 빠르다.

```java

TreeSet<Integer> ts = new TreeSet<Integer>();

// add() 메소드를 이용한 요소의 저장
ts.add(30);
ts.add(40);
ts.add(20);
ts.add(10);

// Enhanced for 문과 get() 메소드를 이용한 요소의 출력
for (int e : ts) {
    System.out.print(e + " ");  // 10 20 30 40 출력
}

// remove() 메소드를 이용한 요소의 제거
ts.remove(40);

// iterator() 메소드를 이용한 요소의 출력
Iterator<Integer> iter = ts.iterator();

while (iter.hasNext()) {
    System.out.print(iter.next() + " "); // 10 20 30 출력
}

// size() 메소드를 이용한 요소의 총 개수
System.out.println("이진 검색 트리의 크기 : " + ts.size()); // 3

 

// subSet() 메소드를 이용한 부분 집합의 출력
System.out.println(ts.subSet(10, 20));  // 10
System.out.println(ts.subSet(10, true, 20, true));  // 10, 20
```

위의 예제처럼 `TreeSet` 인스턴스에 저장되는 요소들은 모두 정렬된 상태로 저장된다.

## Set 인터페이스 메소드
Set 인터페이스는 Collection 인터페이스를 상속받으므로, Collection 인터페이스에서 정의한 메소드도 모두 사용할 수 있다.  

|메소드|설명|
|---|---|
|boolean add(E e)|해당 집합(set)에 전달된 요소를 추가함|
|void clear()|해당 집합의 모든 요소를 제거함|
|boolean contains(Object o)|해당 집합이 전달된 객체를 포함하고 있는지 확인함|
|boolean equals(Object o)|해당 집합과 전달된 객체가 같은지 확인함|
|boolean isEmpty()|해당 집합이 비어있는지를 확인함.|
|boolean remove(Object o)	|해당 집합에서 전달된 객체를 제거함.|
|int size()|해당 집합의 요소의 총 개수를 반환함.|
|Object[] toArray()|해당 집합의 모든 요소를 Object 타입의 배열로 반환함.|