---
title:  "[TCP/IP] 서버와 클라이언트"
excerpt: ""

categories:
  - TCP/IP
tags:
  - [Network, WEB, Server]

toc: true
toc_sticky: true
 
date: 2021-03-26
last_modified_at: 2021-03-26
---

# **서버와 클라이언트의 정의**
네트워크에 연결된 컴퓨터들 중 서비스를 **제공** 하는 쪽을 `서버(Server)` 라고 부르고, 그 서비스를 **받는** 쪽은 `클라이언트(clint)` 라고 부른다.
<br><br><br><br><br>
![image](https://user-images.githubusercontent.com/71059456/112635870-af6bcb00-8e7f-11eb-967c-6b2f99949071.png)


서버와 클라이언트의 역할은 하드웨어의 **성능**으로 구분하는 것이 아니라 어떤 역할의 프로그램을 설치하느냐에 따라 결정된다.

<br><br><br>


## **서비스별 서버와 클라이언트의 역할**

<br><br>

|서비스 이름|서버의 역할|클라이언트의 역할|
|---|---|---|
|웹 서비스|클라이언트로부터 요청을 받고 해당하는<br>웹 페이지를 전송한다.|서버에 웹페이지를 요청하고 응답으로 받은<br>웹페이지를 화면에 표시한다.|
|메일 서비스|메일을 전달하는 송신 기능과 받은 메일을<br>저장하는 수신 기능이 있다.|사용자가 작성한 메일을 메일 서버로 보내고<br>다른 사람이 보낸 메일을 받아 화면에<br>표시한다.|
|FTP 서비스|서버 컴퓨터의 하드 디스크 폴더 안으로<br>업로드한 파일을 저장하는 기능과<br>하드 디스크 폴더 안에 있는 파일을<br>다운로드하는 기능이 있다.|클라이언트 PC에 저장된 파일을 서버에<br>업로드하나 서버의 파일을 클라이언트<br>PC에 다운로드 한다.|
|원격 제어 서비스|클라이언트가 내린 명령을 서버에서<br>실행하고 그 결과를 클라이언트에게<br>보여준다.|사용자의 제어 명령을 원격지의 서버에<br>전달하고 그 결과를 받아 화면에 표시한다.|


<br><br><br>
<br>

## **피어 투 피어**
네트워크에 연결된 두 대의 컴퓨터가 클라이언트와 서버의 역할을 **동시에** 할 수 있어서 서로에게 서비스를 주거나 받을 수 있는 통신 방식을 피어 `투 피어(P2P)` 방식이라고 한다.
주로 개인 컴퓨터 간의 파일 공유나 인터넷 전화(VoIP) 등에 활용된다.