---
title:  "Python - 사전" 

categories:
  -  Python 초급
tags:
  - [Programming, Python]

toc: true
toc_sticky: true

date: 2021-03-02
last_modified_at: 
---

<br>

## 사전 『Dictionary』

> `키 - 값` 을 쌍으로 받는 자료형 .

　닉네임 - 이일영 , 과 같이 `대응 관계` 를 나타낼 수 있는 자료형을 파이썬에서는   

　사전 `Dictionary` 이라고 한다. `Key` 가 `닉네임` 이라면 `Value` 는 `이일영` 이 될 것이다 .

```python
my_dictionary = {
	5: 25, # Key = 5 , Value = 25
	4: 16,
	3: 9
}

print(my_dictionary[3])
```
```python
9
```

　`리스트 인덱싱` 하듯이 대괄호 안에 키 값을 넣어주면   

　`my_dictionary` 의 `Key 3` 의 `Value 9` 가 출력됨을 볼 수 있다 .

　추가로 새로운 쌍을 추가 하고 싶을때에는

```python
my_dictionary[9] = 81 # Key = 9 , Value = 81

print(my_dictionary)
```
```python
{5: 25, 4: 16, 3: 9, 9: 81}
```

　맨 끝에 `Key 9` 의 `Value 81` 이 정상적으로 추가 된 것을 볼 수 있다 .   

　대충 봤을때 개념이 리스트와 굉장히 `비슷` 하지만 , 사전은 순서라는 개념이 없고   

　리스트의 `인덱스` 는 `0,1,2,3 … ` 의 `정수값` 이지만   

　사전의 `Key` 는 정수형일 필요가 `없다` .
<br>

***
```python
family = {
	'아버지': '김아빠',
	'어머니': '김엄마',
	'형': '김형',
	'막내': '김막내'
}
```

### for문으로 딕셔너리 Key 출력
```python
for key in family.keys():
    print(key)
```
```python
아버지
어머니
형
막내
```

### for문으로 딕셔너리 Value 출력
```python
for value in family.values():
    print(value)
```
```python
김아빠
김엄마
김형
김막내
```

### for문으로 딕셔너리 Key, Value 동시 출력
```python
for key, value in family.items():
    print(key, value)
```
```python
아버지 김아빠
어머니 김엄마
형 김형
막내 김막내
```

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}