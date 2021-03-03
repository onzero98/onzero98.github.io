---
title:  "Python - 파일 읽고 쓰기" 

categories:
  -  Python 초급
tags:
  - [Programming, Python]

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
<br>

***
### 공백 문자 제거 함수 『Strip』

> 문자열에서 앞 뒤로 있는 Whitespace 를 없애 준다 .  



## 파일 쓰기 『File Write』












