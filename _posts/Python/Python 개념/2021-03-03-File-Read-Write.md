---
title:  "Python - 파일 읽고 쓰기" 

categories:
  -  Python Concepts
tags:
  - [Programming, Python 개념]

toc: true
toc_sticky: true

date: 2021-03-03
last_modified_at: 
---

<br>

## 파일 읽기 『File Read』

```python
with open('data/Goldfish.txt', 'r', encoding='UTF-8') as f:
```
　`txt` 파일을 준비를 한다. 내가 최근들어 가장 좋아하는 노래 `금붕어의 꿈` 의 `가사` 를 `/data` 폴더 안에 `저장` 했다.   

　`open` 함수를 쓰면 <u>파일을 열 수 있다</u>.    

　첫번째 파라미터로는 `파일경로 / 이름` 을 쓰고, 두번째로는 `문자열 r` 을 쓰면 되는데   

　여기서 `r` 은 `read` 의 약자이다 . 

　`read` 는 <u>파일을 읽어들일수 있게 만들어준다</u> . 읽어들인 파일을 변수 `f` 에 저장한다.

```python
with open('data/Goldfish.txt', 'r', encoding='UTF-8') as f:
    print(type(f))

    for line in f:
        print(line)
```
```
Look at me, my life is lit

헤엄칠 거야 나는 더 멀리

실패는 성공의 어머니라고 해도 너무해

같은 실수를 반복하지

전부 미쳤나 봐

나란 놈은 전생에 나라를 구했나 봐

단단한 것에 머릴 부딪혔나 전부 미쳤나

너무 행복해서 나는 미쳐가버리지 wang

기억력이 금붕어의 brain

근데 오만하긴 어째 마치 뱀

바보처럼 자꾸 같은 잘못해서

본의 아니게도 빠져버려 블랙홀

넘어져도 무릎 털고 wake up

시선이 뭐가 중요해 무대뽀로 하다 보니

사람들이 back up

근데 궁금한 게 하나 있어

왜요

왜 날 좋아해요 왜요

실수투성이인데도

미워하지 않아 감사하게도

Okay KO
```

　라인 대로 출력을 해보면 한줄마다 `엔터` 가 쳐져있는데

　이는 `텍스트`에서 `"Look at me, my life is lit"` 의 가사 다음 줄로 넘어가는 과정에서 

　`파이썬`에서는 `"Look at me, my life is lit\n"` 로 인식이 되어서 한줄 더 엔터가 된것이다 .

　`\n` 과 같은 `Whitespace` 를 지워주려면 `strip()` 함수를 사용 해 주면 된다 .   
<br>

***
### 공백 문자 제거 함수 『Strip』

> 문자열에서 앞 뒤로 있는 Whitespace 를 없애 준다 .  

  - Whitespace 란 `" "` `"\t"` `"\n"` 등 공백들을 의미한다 .
  
```python
#strip
print("                     Hello   World !  \n \t \n")
print("                     Hello   World !  \n \t \n".strip())
```
```python
                     Hello   World !  


Hello   World !
```

　<u>중간에 있는 스페이스를 제외</u>한 `앞 뒤 Whitespace` 들이 전부 `제거` 가 되는 것을 확인 할 수 있다 .    

　`외부 파일` 을 다루거나 `자료 분석` 을 하다 보면 `strip()` 함수를 자주 쓰게 될 것이다 .    

<br>

***
### 문자열 분할 함수 『Split』

> 문자열을 특정 기준으로 잘라서 리스트 타입으로 만듬 .  

```python
my_string = "1. 2. 3. 4. 5"
print(my_string.split(". "))
```
```python
['1', '2', '3', '4', '5']
```

　`". "` 을 기준으로 `my_string` 을 `split` 해서 `리스트`로 만들었다 . 

　<u>헷갈리지 말아야 할 것</u>은 리스트 `내용물` 은 `문자열` 이며, `정수형` 이 `아니다` 라는 것이다 .

```python
numbers = "1. 2. 3. 4. 5".split(". ")

print(numbers[0] + numbers[1])
print(int(numbers[0]) + int(numbers[1]))
```
```python
12
3 
```

## 파일 쓰기 『File Write』

```python
with open('data/new_text.txt', 'w', encoding='UTF-8') as f:
    f.write("Hello Wolrd!")
    f.write("onzero98.github.io")
```
```python
Hello Wolrd!onzero98.github.io
```
　첫번째 파라미터로는 `파일경로 / 이름` 을 쓰고, 두번째로는 `문자열 w` 을 쓰면 되는데   

　여기서 `w` 은 `write` 의 약자이다 .    

　`write` 는 <u>파일을 작성할 수 있도록 만들어준다</u> . 작성한 파일을 변수 `f` 에 저장한다 .   

　다만 결과에 엔터가 안되어서 가독성이 떨어지는데 다시 작성해보면   

```python
with open('data/new_text.txt', 'w', encoding='UTF-8') as f:
    f.write("Hello Wolrd!\n")
    f.write("onzero98.github.io")
```
```python
Hello Wolrd!
onzero98.github.io
```

　기존에 적어둔 `Hello Wolrd!onzero98.github.io` 가 <u>덮어씌워진 것</u>을 확인 할 수 있다 .   

　기존에 쓴 것을 덮어씌우지 않고 `새로 추가` 하고 싶다면 파라미터 두번째 문자열에 `a` 를 쓰면 된다 .   

　여기서 `a` 는 `append` 의 약자이다 . 

　`append` 는 <u>작성한 것에 추가로 작성하도록 한다</u> . 파일 이름이 없을 시에 새로 파일을 만들기도 한다 .

```python
with open('data/new_text.txt', 'a', encoding='UTF-8') as f:
    f.write("\nWelcome to my blog")
```
```python
Hello Wolrd!
onzero98.github.io
Welcome to my blog
```

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}




