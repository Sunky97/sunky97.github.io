---
title:  "[Algorithm] 완전탐색(Brute-Force Search / Exhaustive Search) 알고리즘"
excerpt: ""

categories:
  - Algorithm
tags:
  - [Interview, Brute-Force]

toc: true
toc_sticky: true
 
date: 2021-04-01
last_modified_at: 2021-04-01
---

# **완전탐색이란?**

컴퓨터의 **빠른 계산 능력**을 이용하여 가능한 경우의 수를 일일이 나열하면서 답을 찾는 방법을 의미한다. 

'무식하게 푼다'라는 의미인 `Brute-Force (브루트 포스)`라고도 부른다.

<br><br><br>

## **완전 탐색기법**
<hr>

완전 탐색기법 종류는 다음과 같다. 

 - 단순 Brute-Force

 - 비트마스크(Bitmask)

 - 재귀 함수

 - 순열 (Permutation)

 - BFS(넓이우선탐색) / DFS(깊이우선탐색)

 <br>
 <br>
 <br>
 <br>
 <br>
 <br>

## **1. 단순 Brute-Force**

<hr>

어느 기법을 사용하지 않고 단순히 for 문과 if 문 만으로 모든 case 들을 만들어 답을 구하는 방법이다.
모든 경우를 다 검색하기 때문에 시간초과가 날 수 있다.

 <br>
 <br>
 <br>
 <br>

## **2. 비트마스크(Bitmask)**

<hr>

2진수를 이용하는 컴퓨터의 연산을 이용하는 방식. 완전 탐색에서 비트마스크는 문제에서 나올 수 있는 모든 경우의 수가 각가의 원소가 포함되거나, 포함되지 않는 두가지 선택으로 구성되는 경우에 유용하게 사용이 가능하다.

 <br>
 <br>
 <br>
 <br>

 ## **3. 재귀 함수**

<hr>

함수 내에서 함수 자기 자신을 계속해서 호출해서 문제를 해결하는 방식이다.

 <br>
 <br>
 <br>
 <br>

 ## **4. 순열**

<hr>

서로다른 n개의 원소에서 r개의 중복을 허용하지 않고 순서대로 늘어 놓은 수

![순열](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FZNFo3%2Fbtqx8pzxXTF%2FO8L6gG215YDSXYhgHJzin0%2Fimg.png)
 <br>
 <br>
 <br>
 <br>

 ## **5. BFS / DFS**

<hr>

**DFS** : 그래프 탐색 시, 최대한 깊이 내려간 뒤, 더이상 깊이 갈 곳이 없을 경우 다음 분기로 이동하는방식.

![dfs1](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FxC9Vq%2FbtqB8n5A25K%2FGyOf4iwqu8euOyhwtFuyj1%2Fimg.gif)
<label style='font-size:9pt'>출처 <https://developer-mac.tistory.com/64>
</label>
<br><br><br>
예를 들어, 미로찾기를 할 때 최대한 한 방향으로 갈 수 있을 때까지 쭉 가다가 더 이상 갈 수 없게 되면 다시 가장 가까운 갈림길로 들어와서 그 갈림길부터 다시 다른 방향으로 탐색을 진행하는 것

 1. 모든 노드를 방문하고자 하는 경우에 이 방법을 선택함
 2. 너비 우선 탐색(BFS)에 비해 간단함
 3. 검색 속도 자체는 너비 우선 탐색(BFS) 에 비해 느림

![dfs](https://t1.daumcdn.net/cfile/tistory/9983A7335BD0156910)

<br><br><br>

**BFS** : 최대한 넓게 이동한 다음, 더 이상 갈 수 없을 때 아래로 이동하는 방식

![bfs1](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fc305k7%2FbtqB5E2hI4r%2Fea7vFo08tkDYo4c8wkfVok%2Fimg.gif)
<label style='font-size:9pt'>출처 <https://developer-mac.tistory.com/64>
</label>
<br><br><br>
시작점으로부터 가까운 점을 먼저 방문하고 멀리 떨어져 있는 점을 나중에 방문하는 순회 방법이다. 

주로 두 노드 사이의 최단 경로를 찾고 싶을 때 이 방법을 선택한다.

![bfs](https://t1.daumcdn.net/cfile/tistory/99960F405BD01A8D18)

<br><br><br>


### **DFS / BFS 비교**
![dfs/bfs](https://t1.daumcdn.net/cfile/tistory/997C3C3E5BD01AF41D)
 <br>
 <br>
 <br>
 <br>

