---
title:  "Python - 형 변환" 

categories:
  -  Python
tags:
  - [Programming, Python]

toc: true
toc_sticky: true

date: 2021-02-28
last_modified_at:
---

<br>

## 형 변환 『Type Conversion』

> 값을 한 자료형에서 `다른 자료형`으로 바꾸는것을 의미한다 .   
   
　- 정수 `5` => 소수 `5.0`   
　- 문자열 `"7"` => 정수 `7`

　등의 예시를 들수 있다 .   

　자 , 이름과 나이를 출력하는 코드를 짜본다고 생각하자.    

```python
age = 24

print("제 나이는 " + age + "입니다.")
```

　라고 작성하였다면 프로그램 실행시에 

```python
TypeError: cannot concatenate 'str' and 'int' objects
```

　라는 결과가 나왔을 것이다. 문자열과 정수형을 같이 사용할 수 없기 때문이다.   

　이를 해결 하기 위해서는 정수형 `age`를 문자열 `str`로 바꿔주기 위해 `형 변환`을 해주어야 한다.   

```python
age = 24

print("제 나이는 " + str(age) + "입니다.")
```



<br>

## 문자열 포맷팅 『String Formatting』

　형 변환을 한번만 한다면 별 문제 되진 않겠지만 ,    

　여러번 해야 할시에 아래와 같이 코드가 난잡해지고 일일이 치기 번거로움이 있을 수 있다 .

```python
year = 2021
month = 2
day = 28

print("오늘은 " + str(year) + "년 " + str(month) + "월 " + str(day) + "일 입니다.")
```

　이를 해결해 주는 것이 `문자열 포맷팅`이다.

```python
year = 2021
month = 2
day = 28

print("오늘은 {}년 {}월 {}일입니다.".format(year, month, day))
```

　코드가 단순해지고 무엇보다 타이핑 수가 줄어들어 시간을 더 아낄 수 있다 !

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}