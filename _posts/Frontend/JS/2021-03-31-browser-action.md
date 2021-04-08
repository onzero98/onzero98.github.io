---
title:  "JS 브라우저 동작" 

categories:
  -  JS Concepts
tags:
  - [JS 개념]

toc: true
toc_sticky: true

date: 2021-03-31 18:10:10 +1000
last_modified_at: 
---

# 브라우저 동작

- `<input type="checkbox">` 를 체크/해제
- `keydown` 키를 누르면 텍스트 박스에 글자를 추가
- `link` 마우스 클릭시 해당 링크로 이동하기
- `<input type="submit">` 클릭하거나 Enter를 누르면 이벤트가 발생하고, 브라우저는 폼을 서버로 전송

　등등 대부분의 `이벤트` 는 각 `태그` 혹은 `문서 전체` 에서 `브라우저` 가 기본적으로 가진 `동작` 들을 `수행` 한다 .

# 브라우저 동작 막기

　`event.preventDefault()` 메소드를 사용해서 브라우저 동작 이벤트를 막을 수 있다 .

<script src="https://gist.github.com/onzero98/10df61a35c0cfd685bfcb004aaa554a2.js"></script>

![browser](https://user-images.githubusercontent.com/50429028/113133718-edd80000-925a-11eb-8180-33c3ed4cb3ad.gif)


<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}