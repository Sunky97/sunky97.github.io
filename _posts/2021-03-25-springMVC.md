---
title:  "[Spring] 스프링 MVC 구조 정리"
excerpt: ""

categories:
  - Spring
tags:
  - [Java, Spring, Web Application Architecture]

toc: true
toc_sticky: true
 
date: 2021-03-25
last_modified_at: 2021-03-25
---

# **스프링 MVC 와 모델 2** 
스프링 MVC 를 이용하는 이유 : Servlet/JSP 와 개발자의 로직 사이에서 연결 역할을 하기 때문에 HttpServletRequest/HttpServletResponse 등 Servlet/JSP 의 API 를 사용하지 않아도
어노테이션 방식으로 손쉽게 개발이 가능함.

모델 2 : 로직과 화면을 분리
<br><br><br><br>

# **스프링 MVC 의 기본구조**

![KakaoTalk_20210325_233724076](https://user-images.githubusercontent.com/71059456/112490936-2b540d80-8dc3-11eb-9d75-e770098dcfe7.jpg)


1 모든 요청은 `DispatcherServlet` 을 통해서 처리  

2,3 `HandlerMapping` 에서 `@RequestMapping` 어노테이션이 적용된 컨트롤러 중 Request 의 처리를 담당하는 적절한 컨트롤러를 찾아서 `HandlerAdapter` 를 통해 해당 컨트롤러를 `동작` 

4 `Controller` 에서는 실제 Request 를 처리하는 로직을 작성, 해당 Request 를 처리할 `Service` 를 주입(DI) 받아서 Service 에게 위임한다. 그 후 `View` 에 전달하는 데이터는 필요에 따라 Model 객체에 담아서 전달하거나 `ViewResolver` 를 이용해서 다양한 타입의 결과를 반환. 


5 `ViewResolver` 는 `Controller` 가 반환한 결과를 어떤 View 를 통해서 처리하는지 해석하는 역할 (servlet-context.xml 에 정의된 InternalResourceViewResolver 등) 


6,7 `View는` 실제로 응답 보내야 하는 데이터를 `Jsp` 등을 이용해서 생성하는 역할