---
title:  "[JSP] Servlet LifeCycle(서블릿 생명주기)"
excerpt: ""

categories:
  - JSP
tags:
  - [Interview, servlet, httpservlet, java]

toc: true
toc_sticky: true
 
date: 2021-04-25
last_modified_at: 2021-04-25
---

## Servlet LifeCycle
> 서블릿 객체가 생성되어 서비스하고 소멸되는 과정  

<br>

![image](https://user-images.githubusercontent.com/71059456/115997733-3e0a6e00-a61f-11eb-8a13-6e72314a9f4b.png)

1. 사용자로부터 특정 페이지에 대한 요청이 들어오면 컨테이너로 요청 정보가 전해진다.
2. 컨테이너는 배포서술자(DD:Deployment Descriptor)의 서블릿 맵핑 정보를 참조하여 해당 서블릿을 호출한다.
3. 호출된 MyServlet 이 로딩 > 생성 된다.
4. 서블릿이 초기화 된다. (최초 요청시에만 실행)
5. 요청에 대한 내용을 처리하고 응답해준다.
6. 서블릿이 소멸된다.(서비스 종료시 실행)