---
title:  "인터페이스 & 추상화" 

categories:
  -  JAVA Concepts
tags:
  - [Programming, JAVA 개념]

toc: true
toc_sticky: true

date: 2021-03-12
last_modified_at: 
---


<br>

# 인터페이스

> 특정 메소드를 반드시 쓰겠다는 계약서

　인터페이스를 따르겠다고 하는 클래스는 <u>특정 메소드를 구현</u>하겠다는 `약속`을 하는 것이다 .

　인터페이스는 변수를 가질수 없고 메소드 또한 `비어있어야` 한다 .

　특정 메소드를 <u>모두 구현을 해야만 오류가 사라진다</u> .

Shape.java
```java
public interface Shape{
    // 넓이
    double getArea();
    // 둘레
    double getPerimeter();
}
```

Circle.java
```java
public class Circle implements Shape{
    // 원주율
    public static final double PI = 3.14;

    // 반지름
    public final double radious;

    // 생성자
    public Circle(double radious){
        this.radious = radious;
    }

    @Override // 구현하지 않으면 오류 !
    public double getArea() {
        return PI * radious * radious;
    }

    @Override // 구현하지 않으면 오류 !
    public double getPerimeter(){
        return PI * radious * 2;
    }
}
```

Main.java
```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args){
        ArrayList<Shape> shapes = new ArrayList<>();
        shapes.add(new Circle(3.0));
		
		for (Shape shape : shapes){
            System.out.println("넓이 :" + shape.getArea());
        }    
	}
}
```
```
넓이 :28.259999999999998
```

***

# 추상화

　인터페이스와 다르게 추상 클래스는 `변수` , `메소드` , `빈 메소드` 를 모두 사용 할 수 있다 .

　코드를 수정해서 추상화를 상속받도록 하고 , 도형의 x , y 좌표를 받도록 해보자 .

Shape.java
```java
public abstract class Shape {
    private double x, y;

    public double getX(){ return x; }

    public double getY(){ return y; }

    public void move(double x, double y){
        this.x = x;
        this.y = y;
    }

    // 넓이
    public abstract double getArea();
    // 둘레
    public abstract double getPerimeter();
}
```

Circle.java
```java
public class Circle extends Shape{
    // 원주율
    public static final double PI = 3.14;

    // 반지름
    public final double radious;

    // 생성자
    public Circle(double radious){
        this.radious = radious;
    }

    @Override // 원의 넓이
    public double getArea() {
        return PI * radious * radious;
    }

    @Override // 원의 둘레
    public double getPerimeter(){
        return PI * radious * 2;
    }
}
```

Main.java
```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args){
        ArrayList<Shape> shapes = new ArrayList<>();
        shapes.add(new Circle(3.0));
		
		for (Shape shape : shapes){
            System.out.println("넓이 :" + shape.getArea());
			shape.move(3, 5);
            System.out.println("x : " + shape.getX() + " y : " + shape.getY());
        }    
	}
}
```
```
넓이 :28.259999999999998
x : 3.0 y : 5.0
```

***

# 정리

![image](https://user-images.githubusercontent.com/50429028/110934416-55441380-8371-11eb-8e1f-dada4108a56b.png)

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}