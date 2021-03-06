---
title:  "[TCP/IP] 컴퓨터 네트워크와 계층 모델"
excerpt: ""

categories:
  - TCP/IP
tags:
  - [Network, WEB, Server, Network Layer]

toc: true
toc_sticky: true
 
date: 2021-03-27
last_modified_at: 2021-03-28
---

# **컴퓨터 네트워크를 구성하는 계층들**

컴퓨터 네트워크에서는 다양한 통신 장비와 프로그램이 어울려 통신을 가능하게 한다. 이렇게 통신에 참여하는 여러 장비나 프로그램은 각각 맡은 역할이 있는데, 이 역할들을 이해하기 쉽게 분류하고 추상화한 것을 `계층 모델` 이라고 한다.

|이름|계층의 역할|관련 키워드|
|---|---|---|
|애플리케이션 계층|웹 서비스, 이메일과 같은 서비스를 사용자에게 제공한다.|서버,클라이언트, HTTP, SMPT,POP3, FTP...|
|트랜스포트 계층|애플리케이션 계층과 인터넷 계층 사이에서 데이터가 올바르게 전달되도록 중계한다.|TCP,UDP|
|인터넷 계층|목적지의 IP 어드레스로 데이터를 전달한다.|IP 어드레스, IPv4, IPv6, ICMP, 라우팅 ... |
|네트워크 인터페이스 계층|네트워크 어댑터와 같은   하드웨어를 통해 데이터를 전달한다.|이더넷, 무선 LAN, MAC 어드레스, PPP, FTTx, xDSL ... |

<br><br><br>

## **각 계층을 통과하는 데이터의 형태**
<hr>

![image](https://user-images.githubusercontent.com/71059456/112846940-8a769280-90e1-11eb-96c0-4dff100f4387.png)

<br>
<br>

![image](https://user-images.githubusercontent.com/71059456/112847076-a9752480-90e1-11eb-9658-f77638d08d8d.png)

<br>
<br>

![image](https://user-images.githubusercontent.com/71059456/112848609-3a003480-90e3-11eb-8be5-df7db46d7911.png)




