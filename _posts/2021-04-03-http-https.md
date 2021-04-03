---
title:  "[Network] HTTP와 HTTPS의 차이는 뭘까?"
excerpt: ""

categories:
  - Network
tags:
  - [Interview, Network, HTTPS, HTTP, protocol]

toc: true
toc_sticky: true
 
date: 2021-04-03
last_modified_at: 2021-04-03
---

# **HTTP와 HTTS의 차이**

## HTTP 란?

> HTTP (HyperText Transfer Protocol)

`HTTP` 는 인터넷에서 웹 서버와 사용자 컴퓨터에 설치면 웹 브라우저 사이에서 문서를 전송하기 위한 통신 규약(Protocol) 이다. 곧, `HTTP` 는 인터넷에서 `하이퍼텍스트(HyperText Transfer)`를 `전송(Transfer)`하기 위해 사용되는 `통신 규약(Protocol)` 이다.

`HTTP` 서버는 기본 포트인 80번 포트에서 서비스 대기 중이며, 클라이언트(웹 브라우저)가 TCP 80포트를 사용해 연결하면 서버는 요청에 응답하면서 자료(정보)를 전송한다. `HTTP` 는 정보를 '**텍스트**'로 주고 받는다. 단순 텍스트를 주고 받기 때문에 네트워크에서 전송 신호를 인터셉트하는 경우 원하지 않는 `데이터 유출`이 발생할 수 있다.

이러한 `HTTP` 의 보안 취약점을 해결하기 위해 나온 것이 `HTTPS` 이다.

## HTTPS 란?

> HTTPS ? HTTP + S(Secure Socket)

`HTTPS는` HTTP에 S(Secure Socket)를 추가한 것이다. 기본 골격이나 사용 목적등은 HTTP 와 거의 동일 하지만, 데이터를 주고 받는 과정에 `'보안'` 요소가 추가된다는 점이 가장 큰 차이점 이다. 쉽게 말해  `HTTPS` 를 사용하면 서버와 클라이언트 사이의 모든 통신 내용이 암호화 된다는 것.

![image](https://user-images.githubusercontent.com/71059456/113478430-bd46cf00-94c3-11eb-9019-6b471f25d06c.png)
▲ 위와 같이 데이터를 주고 받을때 `SSL(보안 소켓 계층)`을 사용함으로써 데이터의 `암호화/복호화` 과정을 거쳐서 `데이터유출`을 막음


`HTTPS는` `HTTP` 에 '보안' 기능이 추가된 만큼 처리 속도가 더 느릴 수 밖에 없고, 웹 서버의 사양(스펙)도 중요한 부분이 된다.

또한 `HTTPS` 는 보안 뿐만 아니라 검색엔전 최적화(SEO)에 있어서도 큰 혜택을 볼 수 있는데. 이는 구글이 `HTTPS` 웹사이트에 가산점을 주는 이유도 있지만, 사용자들이 결국에는 **안전하다고 생각하는 사이트를 더 많이 방문하기 때문**이다.
