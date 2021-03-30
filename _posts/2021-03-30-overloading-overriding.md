---
title:  "[Java] 오버로딩과 오버라이딩"
excerpt: ""

categories:
  - Java
tags:
  - [Interview]

toc: true
toc_sticky: true
 
date: 2021-03-30
last_modified_at: 2021-03-30
---

# **오버로딩과 오버라이딩의 차이가 뭐죠?**

짧게 말하면 `오버로딩(Overloading)` 은 이름은 같지만 **파라미터 수, 타입**이 다른 메소드를 중복 선언하는 것을 의미하고, `오버라이딩(Overriding)`은 상위클래스를 상속받은 메소드를 자식클래스에서 알맞게 재정의해서 사용하는 것을 의미한다.

<br><br><br>

## **오버로딩(overloading)**

<hr>

오버로딩의 특징  
 1. 메소드 이름이 같아야 한다.  
 2. 리턴형이 같아도 되고 달라도 된다.
 3. 파라미터 개수가 달라야 한다
 4. 파라미터 개수가 같을 경우, 데이터 타입이 달라야 한다.

 ```java
public String insert() { ... }
public String insert(String name) { ... }
public String insert(String name,int age) { ... }
 ```
 <br>
 <br>
 <br>
 <br>
 <br>
 <br>

## **오버라이딩(overriding)**

<hr>

오버라이딩의 특징  
 1. 오버라이드 하고자 하는 메소드가 상위 클래스에 존재해야 한다.
 2. 메소드 이름이 같아야 한다.
 3. 메소드 파타미터 개수, 파라미터의 자료형이 같아야 한다.
 4. 메소드 리턴형이 같아야 한다.
 5. 상위 메소드와 동일하거나 내용이 추가되어야 한다.

 ```java
public class People {
    
    String name;
    int age;

    public People(String name,int age){
        this.name = name;
        this.age = age;
    }

    public void print(){
        System.out.println("내 이름은"+this.name+"이고, 나이는"+this.age+"입니다.");
    }
}

//상속받은 클래스
public class Student extends People{
    
    String job;
    
    @Override
    public void print(){
        System.out.println("내 이름은"+this.name+"이고, 나이는"+this.age+"입니다.");
        //새롭게 추가된 부분
        System.out.println("직업은"+this.job+"입니다.");
    }
}

public class Example{

    public void main(String[] args){

        Student s = new Student("개발자",20);

        //Override 한 Student 객체의 print() 호출
        s.print();
    }
}
 ```


