---
title:  "[Web] GET 방식과 POST 방식의 차이"
excerpt: ""

categories:
  - Web
tags:
  - [http, Network, Interview]

toc: true
toc_sticky: true
 
date: 2021-03-31
last_modified_at: 2021-03-31
---

# **HTTP의 GET 방식과 POST 방식**

사용자가 브라우저 주소창에 `URL` 을 입력하면 원하는 페이지로 이동하는데 이때 서버 내부에서는 클라이언트의 요청에 응답(웹페이지) 하기 위해서 처리를 해줘야한다. 이때 `클라이언트가 서버로 요청을 보내는 방법`인 HTTP Method 에는 크게 `GET 방식`과 `POST 방식`이 있다. 

<br><br><br>

## **GET 방식**

<hr>

GET 방식은 영어단어 Get 의 뜻과 동일하게 `어떠한 정보를 가져와서 조회하기 위해서 사용되는 방식` 이다 

### **GET방식의 특징**
 - `URL` 에 데이터를 포함시켜서 요청한다.
 
 ```http
www.example.com/request?value1=1&value2=2
 ```
 - 데이터를 `헤더(Header)`에 포함시켜서 요청한다.
 - URL 에 데이터가 노출되어 `보안이 취약`하다. (로그인 등)
 - `캐싱`할 수 있다. 

 <br>
 <br>
 <br>

## **POST 방식**

<hr>

POST 방식또한 영어단어 Post 의 뜻에 빗대어, 우리가 어디에 서류를 부치거나 제출하는 행위와 비슷하게 `데이터를 서버로 제출하여 추가 또는 수정하기 위해서 사용하는 방식` 이다. 

### **POST방식의 특징**
 - `URL` 에 데이터가 노출되지 않고 요청한다.
 
 ```http
www.example.com/request
 ```
 - 데이터를 `바디(Body)`에 포함시켜서 요청한다.
 - URL 에 데이터가 노출되지 않아서 `GET 방식의 보안`에 비해 낫다.
 - `캐싱`이 불가능. 
 <br>

URL 에 데이터가 노출되지 않기때문에 보안이 된다고 생각할 수 있으나
암호화를 하지 않는이상 고만고만하다.

