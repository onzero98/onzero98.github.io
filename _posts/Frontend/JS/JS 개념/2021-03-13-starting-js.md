---
title:  "자바스크립스 시작하기" 

categories:
  -  JS Concepts
tags:
  - [Programming, JS 개념]

toc: true
toc_sticky: true

date: 2021-03-13
last_modified_at: 
---


<br>

# 준비물

> VSCode

　코드 작성 하기 위한 `프로그램`

> Chrome

　프로그래밍을 할 때 코드를 작성하기 `편리한 환경` 을 제공하는 

　`코드편집기` 와 `코드` 를 실행한 결과를 확인할 `웹 브라우저`

***

# Hello JavaScript !

　VSCode 를 사용하여 `index.js` 파일과 `index.html` 파일을 작성한다 .

index.js
```js
console.log('Hello JavaScript !')
```

index.html
```html
<!DOCTYPE html>
<html lang = <"ko">
<head>
    <meta charset = "UTF-8">
    <title>JavaScript</title>
</head>
<body>
    <script src = "./index.js"></script>
</body>
</html>
```

　`index.html` 파일을 이제 Chrome 브라우저에서 열어보면

![image](https://user-images.githubusercontent.com/50429028/111021685-7f4d1280-8411-11eb-9d23-005e73ab0bd5.png)

　흰 배경화면만 보일 것이다 .

　잘못 실행된게 아니라 이제 `F12` 를 눌러 `개발자 도구` 를 실행해보면 `console` 에서 정상 작동한 것을 확인 할 수 있다 .

![image](https://user-images.githubusercontent.com/50429028/111021748-f84c6a00-8411-11eb-9c65-677dc85d98b3.png)


<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}