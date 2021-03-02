---
title:  "Python - 추상화" 

categories:
  -  Python level 1
tags:
  - [Programming, Python]

toc: true
toc_sticky: true

date: 2021-02-27
last_modified_at:
---

<br>

## 추상화 『Abstraction』

> 복잡한 내용은 `숨기고` 주요 기능에만 `중시하는` 것 .
   
- 변수 `Variable`   
- 함수 `Function`   
- 객체 `Object`   

　등으로 나뉘게 된다 .   
<br>

***
### 변수 『Variable』

> 값을 저장 .   

```python
x = 254 
y = 317 
print(x + y)
```

- 복잡한 숫자의 값을 알 필요 없이 변수 x, y를 쓰면 된다.   

　예를 들어서 햄버거 가게에서 가격을 계산해야 하는 코드를 짜본다고 하자 .   

　햄버거의 가격은 4900 원, 감자튀김의 가격은 1450 원, 음료수의 가격은 1100 원이다.   
 
```python
print(4900 * 2)
print(4900 * 2 + 1450 * 1 )
print(4900 * 2 + 1450 * 3 + 1100 * 2))
```

　의미를 설명해 주지 않는 이상 다른 사람이 보면 이게 대체 뭘 말하고 싶은건지 이해하기 힘들것이다.   

　고로 각 가격에 대한 변수 burger_price, fries_price, coke_price 를 사용하게 되면   

　다른 사람들도 쉽게 이해하기 쉬워질 것이다.   
 
```python
burger_price = 4900
fries_price = 1450
coke_price = 1100

print(burger_price * 2)
print(burger_price * 2 + fries_price * 1 )
print(burger_price * 2 + fries_price * 3 + coke_price * 2))
```

　또한 가격이 변동하게 된다면 일일히 전부 수정하는것이 아니라    

　변수에서 한번만 수정하면 되니 만일 코드를 수정하게 된다면 더욱 편할것이다.   

<br>

***
### 함수 『Function』

> 명령을 저장 .   

- 내장함수인 print() 함수가 어떻게 동작하는지 모르지만 다들 화면에 `Hello World!` 정도는 쉽게 사용한다.   
- 자신 만의 새 함수를 정의하고 싶을 때에는 `def` 를 사용하는데 함수 정의 첫줄을 `헤더` 라고 한다.

```python 
def hello(name):
    	print("Hello")
	print(name)
	print("Welcome to my blog")
	
hello("onzero98")
```

```python 
Hello
onzero98
Welcome to my blog
```
　name 이라는 파라미터 안에 문자열 "onzero98" 이 들어감으로서 hello() 함수는 내용을 출력할 것이다.   
<br>

***
### 객체 『Object』

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}