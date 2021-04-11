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

애플리케이션이 시작될 때 어떤 클래스가 `최초 한 번`만 메모리를 할당하고(static) 그 메모리에 인스턴스를 만들어 사용하는 디자인패턴이다.  
레지스트리 같은 설정 파일의 경우 객체가 여러개 생성되면 설정값이 변경될 위험이 생길 수 있기 때문에 이러한 패턴을 사용한다.

자바에서는 `생성자를 private 로 선언`하고 `getInstance()` 로 객체를 받아서 사용한다. 
<br>
<br>
<br>

> 기본적인 싱글톤 패턴 구현
```java
public class SingleObj {
    private static SingleObj singleObj = null;

    // 외부에서 직접 생성하지 못하도록 private 선언
    private SingleObj(){ }

    // 오직 1개의 객체만 생성
    public static SingleObj getInstance(){
        if( singleObj == null ){
            singleObj = new SingleObj();
        }

        return singleObj;
    }
}

```

## 싱글톤 패턴을 사용하는 이유

**한번**의 객체 생성으로 재사용이 가능하기 때문에 메모리 낭비를 방지할 수 있다.
또한 싱글톤으로 생성된 객체는 무조건 한번 생성으로 전역성을 띄기에 다른 객체와 공유가 용이하다.

<br>
<br>
<br>

## 그렇다면 싱글톤 패턴의 문제점은 ??

1. 멀티스레드(Multi-Thread) 환경에서 안전하지 않다. <br> 멀티스레드 환경에서는 여러개의 인스턴스가 발생 할 위험있다. 이 문제는 `synchronized` 를 통해서 어느정도 대처가 가능하지만 고려해야 할 요소가 많고 성능이 현저히 떨어지기 때문에 사용하기 어렵다.

2. 싱글톤 패턴은 프로그램 전체에서 하나의 객체를 공통으로 사용하기 때문에 각 객체간의 `결합도`가 높아지고 변경에 유연하게 대처할 수 없다. (싱글톤 객체가 변경되면 이를 참조하고 있는 모든 값들이 변경되어야 하기 때문에) 이는 객체 지향 설계 원칙 중 개방 폐쇠 원칙(OCP)에 어긋난다.

> 결합도란?  한 모듈이 변경되기 위해서 다른 모듈의 변경을 요구하는 정도 . <br> 결합도가 낮을수록 클래스 간의 상호 의존성이 낮다.