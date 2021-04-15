---
title:  "[Java] Map 컬렉션 클래스"
excerpt: ""

categories:
  - Java
tags:
  - [Interview, Collection, Map, java]

toc: true
toc_sticky: true
 
date: 2021-04-15
last_modified_at: 2021-04-15
---

# **Map 컬렉션 클래스**

`Map` 인터페이스는 Collection 인터페이스와는 **다른** 저장 방식을 가진다.

`Map` 인터페이스를 구현한 M`ap 컬렉션 클래스들은 `키`와 `값`을 하나의 쌍으로 저장하는 방식(`key-value 방식`)을 사용합니다.

여기서 `키(key)`란 실질적인 `값(value)`을 찾기 위한 이름의 역할을 한다.

`Map` 인터페이스를 구현한 모든 `Map` 컬렉션 클래스는 다음과 같은 특징을 가진다.

1. 요소의 저장 순서를 유지하지 않습니다.
2. 키는 중복을 허용하지 않지만, 값의 중복은 허용합니다. 

대표적인 `Map` 컬렉션 클래스에 속하는 클래스는 다음과 같습니다.

1. HashMap<K, V>
2. Hashtable<K, V>
3. TreeMap<K, V>

## HashMap<K, V> 클래스
`HashMap` 클래스는 `Maps` 컬렉션 클래스에서 가장 많이 사용되는 클래스 중 하나로
해시 알고리즘(hash algorithm)을 사용하여 검색 속도가 매우 빠르다.

`HashMap` 클래스는 `Map` 인터페이스를 구현하므로, 중복된 키로는 값을 저장할 수 없다.
하지만 값의 중복을 허용한다.

```java
HashMap<String, Integer> hm = new HashMap<String, Integer>();

// put() 메소드를 이용한 요소의 저장
hm.put("삼십", 30);
hm.put("십", 10);
hm.put("사십", 40);
hm.put("이십", 20);

// Enhanced for 문과 get() 메소드를 이용한 요소의 출력
System.out.println("맵에 저장된 키들의 집합 : " + hm.keySet()); // [이십, 삼십, 사십, 십] 출력

for (String key : hm.keySet()) {
    System.out.println(String.format("키 : %s, 값 : %s", key, hm.get(key)));
}

// remove() 메소드를 이용한 요소의 제거
hm.remove("사십");

// iterator() 메소드와 get() 메소드를 이용한 요소의 출력
Iterator<String> keys = hm.keySet().iterator();

while (keys.hasNext()) {

    String key = keys.next();

    System.out.println(String.format("키 : %s, 값 : %s", key, hm.get(key)));

}// 사십 이 제거되고 남은 요소들 출력 

// replace() 메소드를 이용한 요소의 수정
hm.replace("이십", 200);

for (String key : hm.keySet()) {

    System.out.println(String.format("키 : %s, 값 : %s", key, hm.get(key)));

} // 이십 의 값이 200 으로 변경되어 출력

// size() 메소드를 이용한 요소의 총 개수
System.out.println("맵의 크기 : " + hm.size()); // 3 출력

```
<br>
<br>

## Hashtable<K, V> 클래스
현재의 `Hashtable` 클래스는 `HashMap` 클래스와 마찬가지로 `Map` 인터페이스를 상속받는다.

따라서 `Hashtable` 클래스에서 사용할 수 있는 메소드는 `HashMap` 클래스에서 사용할 수 있는 메소드와 거의 같다고 볼 수 있다.

하지만 현재에는 기존 코드와의 호환성을 위해서만 남아있으므로, `Hashtable` 클래스보다는 `HashMap` 클래스를 사용하는 것이 좋다.

## TreeMap<K, V> 클래스
`TreeMap` 클래스는 키와 값을 한 쌍으로 하는 데이터를 `이진 검색 트리(binary search tree)`의 형태로 저장한다.

이진 검색 트리는 데이터를 추가하거나 제거하는 등의 기본 동작 시간이 **매우 빠릅니다**.

JDK 1.2부터 제공된 `TreeMap` 클래스는 `NavigableMap` 인터페이스를 기존의 이진 검색 트리의 성능을 향상시킨 `레드-블랙 트리(Red-Black tree)`로 구현한다.


## HashMap<K, V> 메소드

|메소드|설명|
|---|---|
|void clear()|해당 맵의 모든 매핑을 제거함.|
|boolean contatinskey(Object key)|해당 맵이 전달된 키를 포함하고 있는지를 확인.|
|boolean contatinsValue(Object value)|해당 맵이 전달된 값에 해당하는 하나 이상의 키를 포함하고 있는지를 확인함.|
|V get(Ojbect key)|해당 맵에서 전달된 키에 대응하는 값을 반환함. 만약 해당 맵이 전달된 키를 포함한 매핑을 포함하고 있지 않으면 null을 반환함.|
|boolean isEmpty()|해당 맵이 비어있는지를 확인함.|
|Set&#60;K> keySet()|해당 맵에 포함되어 있는 모든 키로 만들어진 Set 객체를 반환함.|
|V put(K key, V value)|해당 맵에 전달된 키에 대응하는 값으로 특정 값을 매핑함.|
|V remove(Object key)|	해당 맵에서 전달된 키에 대응하는 매핑을 제거함.|
|boolean remove(Object key, Object value)|해당 맵에서 특정 값에 대응하는 특정 키의 매핑을 제거함.|
|V replace(K key, V value)|해당 맵에서 전달된 키에 대응하는 값을 특정 값으로 대체함.|
|boolean replace(K key, V oldValue, V newValue)|해당 맵에서 특정 값에 대응하는 전달된 키의 값을 새로운 값으로 대체함.|
|int size()|해당 맵의 매핑의 총 개수를 반환함.|