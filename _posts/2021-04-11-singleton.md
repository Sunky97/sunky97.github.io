---
title:  "[Design Pattern] 싱글톤 패턴(Singleton Pattern)"
excerpt: ""

categories:
  - Design Pattern
tags:
  - [Interview, singleton, java]

toc: true
toc_sticky: true
 
date: 2021-04-11
last_modified_at: 2021-04-11
---

# **싱글톤 패턴이란?**

애플리케이션이 시작될 때 어떤 클래스가 최초 한번만 메모리를 할당하고(static) 그 메모리에 인스턴스를 만들어 사용하는 디자인패턴이다.  
레지스트리 같은 설정 파일의 경우 객체가 여러개 생성되면 설정값이 변경될 위험이 생길 수 있기 때문에 이러한 패턴을 사용한다.

자바에서는 생성자를 private 로 선언하고 getInstance() 로 객체를 받아서 사용한다. 

## 싱글톤 패턴을 사용하는 이유

고정된 메모리 영역을 얻으면서 한번의 new 로 인스턴스를 사용하기 때문에 메모리 낭비를 방지할 수 있음