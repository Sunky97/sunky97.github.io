---
title:  "[Java] 자바 컬렉션 프레임워크 정리"
excerpt: ""

categories:
  - Java
tags:
  - [Interview, Collection, List,Map,Set, java]

toc: true
toc_sticky: true
 
date: 2021-04-14
last_modified_at: 2021-04-14
---

# **컬렉션 프레임워크 란?**

자바에서 `배열`을 사용할때 발생할 수 있는 여러가지 `문제점`(배열의 크기 고정, 데이터 삭제시 메모리 낭비 등)을 **해결**하기 위해, 널리 알려져 있는 자료구조들을 바탕으로 객체나 데이터들을 효율적으로 관리(추가,삭제,검색,저장)할 수 있는 `자료구조들이 들어있는 라이브러리`를 `컬렉션 프레임워크`라고 한다.  
<br>
<br>

## 컬렉션 프레임워크의 대표 인터페이스
컬렉션 프레임워크에서는 컬렉션을 크게 3가지 타입(`List`, `Map`, `Set`)이 존재한다고 인식하고, 각 컬렉션을 다루는데 필요한 기능을 가진 3가지 인터페이스를 정의했다. 그리고 `List` 와 `Set` 의 공통된 부분을 뽑아서 새로운 인터페이스인 Collection 을 추가로 정의 하였다.

<br><br>

![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fbdy438%2FbtqEjPZKIY0%2Fe5Wm8ZJmdRNza4tKBzaK6k%2Fimg.png)  

<br><br>

인터페이스 `List` 와 `Set` 을 구현한 컬렉션 클래스들은 서로 많은 공통부분이 있어서, 공통된 부분을 다시 뽑아 `Collection` 인터페이스를 정의할 수 있었지만, `Map` 인터페이스는 이들과 전혀 다른 형태로 컬렉션을 다루기 때문에 같은 계층 상속도에 포함되지 못했다.  

<br>
<br>

|인터페이스|구현클래스|특징|
|---|---|---|
|List|ArrayList, LinkedList, Stack, Vector|순서가 있는 데이터의 집합으로 데이터의 중복을 허용한다.|
|Set|순서를 유지하지 않는 데이터의 집합으로 데이터의 중복을 허용하지 않는다.|HashSet, TreeSet|
|Map|키와 값의 쌍으로 이루어진 데이터의 집합으로 순서는 유지되지 않으며, 키는 중복을 허용하지 않고, 값은 중복을 허용한다.|HashMap, TreeMap, HashTable, Properties|