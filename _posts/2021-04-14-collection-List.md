---
title:  "[Java] List 컬렉션 클래스"
excerpt: ""

categories:
  - Java
tags:
  - [Interview, Collection, List, java]

toc: true
toc_sticky: true
 
date: 2021-04-14
last_modified_at: 2021-04-14
---

# **List 컬렉션 클래스**

List 인터페이스를 구현한 모든 List 클래스는 다음과 같은 특징을 가진다.  

1. 요소의 저장 순서가 유지된다.
2. 같은 요소의 중복 저장을 허용한다.

대표적인 List 컬렉션 클래스에 속하는 클래스는 다음과 같다.

1. ArrayList&#60;E>
2. LinkedList&#60;E>
3. Vector&#60;E>
4. Stack&#60;E>

<br><br>    

## ArrayList&#60;E> 클래스 

ArrayList 클래스는 가장 많이 사용되는 컬렉션 클래스 중 하나로
내부적으로 배열을 이용해서 요소를 저장한다.  

ArrayList 클래스는 배열을 이용하기 때문에 인덱스를 이용해서 배열 요소에 빠르게 접근할 수 있다. 하지만 배열의 크기는 가변적이지 않아서 배열의 크기를 조정하기 위해서는 새로운 배열을 생성하고 기존의 요소를 옮겨야 한다. 이는 작업속도가 매우 느린 단점을 가지고 있다. 

```java
ArrayList<Integer> arrList = new ArrayList<Integer>();

// add() 메소드를 이용한 요소의 저장

arrList.add(40);
arrList.add(20);
arrList.add(30);
arrList.add(10);


// for 문과 get() 메소드를 이용한 요소의 출력

for (int i = 0; i < arrList.size(); i++) {

    System.out.print(arrList.get(i) + " "); // 40 20 30 10 출력됨

} 

// remove() 메소드를 이용한 요소의 제거

arrList.remove(1);

// Enhanced for 문과 get() 메소드를 이용한 요소의 출력

for (int e : arrList) {

    System.out.print(e + " "); // 40 30 10 출력됨 

} 

// Collections.sort() 메소드를 이용한 요소의 정렬(오름차순)

Collections.sort(arrList);

// iterator() 메소드와 get() 메소드를 이용한 요소의 출력

Iterator<Integer> iter = arrList.iterator();

while (iter.hasNext()) {

    System.out.print(iter.next() + " "); // 10 30 40 출력됨

}

// set() 메소드를 이용한 요소의 변경

arrList.set(0, 20);

for (int e : arrList) {

    System.out.print(e + " "); // 20 30 40 출력됨 

} 

// size() 메소드를 이용한 요소의 총 개수

System.out.println("리스트의 크기 : " + arrList.size()); // 리스트의 크기 : 3

```
<br>
<br>

> 자바의 Collection 은 `인터페이스`고 Collections 는 `클래스` 이다. 

<br>

<br>

## LinkedList&#60;E> 클래스
`LinkedList` 클래스는 `ArrayList` 클래스가 배열을 이용하여 요소를 저장함으로써 발생하는 단점을 극복하기 위해 고안된 클래스이다. 
`LinkedList` 는 내부적으로 연결 리스트(linked list)를 이용하여 요소를 저장한다. 

배열은 저장된 요소가 순차적으로 저장된다. 
하지만 연결리스트는 저장된 요소가 비순차적으로 분포되며, 이러한 요소들 사이를 링크(link)로 연결하여 구성한다.  

<br>

![image1](https://user-images.githubusercontent.com/71059456/114704582-ba6c9980-9d61-11eb-8444-0c9fc6743b97.png)

이러한 단일 연결 리스트는 요소의 저장과 삭제 작업이 다음요소를 가리키는 참조만 변경하면 되므로, 아주 빠르게 처리될 수 있다. 하지만 단일 연결 리스트는 현재 요소에서 이전 요소로 접근하기가 매우 힘들다.  
따라서 이전 요소를 가리키는 참조도 가지는 이중 연결 리스트(doubly linked list)가 좀 더 많이 사용된다. 

<br>

![image](https://user-images.githubusercontent.com/71059456/114705234-7928b980-9d62-11eb-8880-d8d3f8f03bae.png) 

`LinkedList` 클래스도 위와 같은 이중 연결 리스트를 내부적으로 구현한 것이다.

또한, `LinkedList` 클래스 역시 List 인터페이스를 구현하므로, `ArrayList` 클래스와 사용할 수 있는 `메소드가 거의 같다`.


<br>

<br>

## Vector&#60;E> 클래스  

<br>

현재의 `Vector` 클래스는 `ArrayList` 클래스와 마찬가지로 `List` 인터페이스를 상속받습니다.

따라서 `Vector` 클래스에서 사용할 수 있는 메소드는 `ArrayList` 클래스에서 사용할 수 있는 메소드와 거의 같습니다.

하지만 현재에는 기존 코드와의 호환성을 위해서만 남아있으므로, `Vector` 클래스보다는 `ArrayList` 클래스를 사용하는 것이 좋습니다.


<br><br>

## List 인터페이스 메소드

List 인터페이스는 Collection 인터페이스를 상속받으므로, collection 인터페이스에서 정의한 메소드도 모두 사용할 수 있다. 

List 인터페이스의 주요 메소드

|메소드|설명|
|---|---|
|boolean add(E e)|해당 리스트(list)에 전달된 요소를 추가함.|
|void add(E e)|해당 리스트의 특정 위치에 전달된 요소를 추가함.|
|void clear()|해당 리스트의 모든 요소를 제거함.|
|boolean contains(Obejct o)|해당 리스트가 전달된 객체를 포함하고 있는지 확인함.|
|boolean equals(Object o)|해당 리스트가 전달된 객체가 같은지를 확인함.|
|E get(int index)|해당 리스트의 index 위치에 존재하는 요소를 반환함.|
|boolean isEmpty()|해당 리스트가 비어있는지 확인함.|
|Iterator&#60;E> iteraor()|해당 리스트의 이터레이터를 반환함.|
|boolean remove(Object o)|해당 리스트에 전달된 객체를 제거함.|
|boolean remove(int index)|해당 리스트의 index 위치에 존재하는 요소를 제거함.|
|E set(int index,E e)|해당 리스트의 index위치에 존재하는 요소를 e 로 대체함|
|int size()|해당 리스트의 요소의 총 개수를 반환함.|
|Object[] toArray()|해당 리스트의 모든 요소를 Object 타입의 배열로 반환함.|