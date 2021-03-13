---
title:  "숏서킷 연산" 

categories:
  -  Java Concepts
tags:
  - [Programming, JAVA 개념]

toc: true
toc_sticky: true

date: 2021-03-09
last_modified_at: 
---


<br>

# 숏서킷 연산

> 뒤의 연산을 수행하지 않아도 이미 조건을 만족했다면 결과를 반환 .   

```
　결과값이 이미 결정된 경우 미리 멈추는 것을 『숏서킷 연산』 이라고 한다 . 
　논리연산자에서 알아 볼 수 있다 .
```
## And 연산 (&&) 

```java
boolean newBoolean = m1() && m2() && m3();
```

　`newBoolean` 이 `true` 가 되기 위해서는 `m1(), m2(), m3()` 가 모두 `true` 를 리턴해야 한다 .   

　따라서 `m1()` 이 `false` 를 리턴하면 `m2(), m3()` 의 결과와 상관 없이 `newBoolean` 은 `false` 이다 .

　`m1()` 이 `false` 를 리턴하면 `m2(), m3()`를 실행하지 않는다 .

　추가로, `m1()`이 `true` 를 리턴하는데, `m2()` 가 `false` 를 리턴하면 `m3()`는 실행되지 않는다 .

## Or 연산 (||)

```java
boolean newBoolean = m1() || m2() || m3();
```

　`newBoolean` 이 `false` 가 되기 위해서는 `m1(), m2(), m3()` 가 모두 `false` 를 리턴해야 한다 .

　반대로 `true` 이기 위해서는 `m1()` 이 `true` 를 리턴하면 `m2(), m3()` 는 실행되지 않고 `newBoolean` 은 `true` 가 된다 .

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}