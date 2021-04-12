---
title:  "[Java] 다형성(Polyporhism) 이란?"
excerpt: ""

categories:
  - Java
tags:
  - [Interview, oop, java]

toc: true
toc_sticky: true
 
date: 2021-04-12
last_modified_at: 2021-04-12
---

# **다형성**

객체지향개념에서의 `다형성`이란 `'여러 가지 형태를 가질 수 있는 능력'` 을 의미하며, 자바에서는 한 타입의 참조변수로 여러 타입의 객체를 참조할 수 있도록 함으로써 다형성을 프로그램적으로 구현하였다. 즉, **조상클래스 타입의 참조변수로 자손클래스의 인스턴스를 참조할 수 있도록** 하였다는 것이다. 코드로 살펴보자

```java
class Car{

    public void drive(){
        System.out.println("부릉");
    }

    public void stop(){
        System.out.println("멈춰!");
    }
}

class Ambulance extends Car{

    public void siren(){
        System.out.println("삐융삐융");
    }
}

class Test{

    public static void main(String[] args){

        Car p = new Ambulance();
        Ambulance m = new Ambulance();

        p.drive(); // "부릉" 출력

        
        m.siren(); // "삐융삐융" 출력
        p.siren(); // 컴파일 에러 발생
    }
}
```  

이 코드에서 참조변수 `p` 는 `Car` 클래스에서 정의 되지 않은 `siren()` 은 사용이 불가능하다.
즉 `p` 와 `m` 은 **같은 타입**의 `인스턴스`를 사용하지만 참조변수의 타입이 다르기 때문에 사용할 수 있는 멤버의 개수가 달라졌다.

> 조상타입의 참조변수로 자손타입의 인스턴스를 참조할 수 있다. <br>반대로 자손타입의 참조변수로 조상타입의 인스턴스를 참조할 수는 없다  

<br><br>

## 참조변수의 형변환
서로 상속관계에 있는 클래스들 사이에는 참조변수의 형변환이 가능하다. 자손타입의 참조변수를 조상타입으로, 조상타입의 참조변수를 자손타입의 참조변수로 형변환 할 수 있다.  

> 자손타입 -> 조상타입(Up-casting) : 형변환 생략가능 <br>
자손타입 <- 조상타입(Down-casting) : 형변환 생략불가


```java

Car car = null;
Ambulance m = new Ambulance();
Ambulance m2 = null;

car = m;                // car = (Car)m; 에서 형변환이 생략. 업캐스팅
m2 = (Ambulance)car;    // 형변환 생략 불가. 다운 캐스팅
```