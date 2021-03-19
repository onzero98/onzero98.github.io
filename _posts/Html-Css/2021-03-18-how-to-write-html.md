---
title:  "HTML 태그 정리" 

categories:
  -  Html Css
tags:
  - [HTML, CSS]

toc: true
toc_sticky: true

date: 2021-03-18
last_modified_at: 
---
**repl.it 사이트를 사용하여 코딩 하였습니다.**   
[[repl.it] 바로가기](https://replit.com/){:target="_blank"}
{: .notice--warning}

# 기본 태그

- `<!DOCTYPE>` 선언
- `<title>` 태그
- `<heading>` 태그
- `<paragraph>` 태그

## <!DOCTYPE> 선언

> 웹브라우저에서 HTML 버전을 알려주는 역할

```
HTML 파일을 작성할 때는 가장먼저 <!DOCTYPE> 선언을 해야 한다 .   
가장 최신의 HTML5 가 디폴트이다 .
```
```html
<!DOCTYPE html>
```

## `<title>` 태그

> 웹브라우저에서 나타낼 페이지의 제목

```html
<title> 웹사이트 </title> 
```

## `<heading>` 태그

> 머리말

```
한 페이지에서 강조하여 작성하고자 하는 것을 <h1> </h1> 으로 작성하며
최대 6개 까지 작성할 수 있다 .
```
```html
<h1> HTML로 작성한 </h1>
```

## `<paragraph>` 태그

> 문단

```
작성하려는 문장을 <p> </p> 로 작성한다 .
```
```html
<p> Say Your Dream. SYD </p>
```

***

# 옵셔널 태그

- `<html>` 태그
- `<head>` 태그
- `<body>` 태그

```
꼭 써야하는 것은 아니지만 파일의 구조를 이해하기 쉽도록 정리의 목적으로 사용하는 태그 .
보통 아래와 같이 감싼다 .
<title> 👉 <head>
<h> , <p> 👉 <body> 
```
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset = "UTF-8">
    <title> 페이지 1 </title> 
  </head>
  <body>
    <h1> 페이지 1 </h1>

    <p> 이곳은 1 페이지 입니다. </p>
    <p> HTML 공부 하기 위해 만들어졌습니다. </p>
  </body>
</html>
```

![image](https://user-images.githubusercontent.com/50429028/111626202-11e61b00-8831-11eb-8313-9a85f206c40a.png)

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}