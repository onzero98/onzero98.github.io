---
title:  "HTML 태그 정리" 

categories:
  -  Html Css
tags:
  - [HTML, CSS]

toc: true
toc_sticky: true

date: 2021-03-18
last_modified_at: 2021-03-20
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

***

# `<div>` 태그

　별다른 기능이 없는 `block` 요소이다 .

　하지만 별다른 기능이 없기 때문에 더 플렉서블하게 사용할 수 있다 .

　애국가만을 기록한 html 파일을 만들어 보자 .
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset = "utf-8">
    <title> 애국가 </title>
    <style>
    </style>
  </head>
  <body>
    <h1> 애국가 </h1>

    <div class = "box">
      <h2 class = "verse"> 1절 </h2>
      <p class = "lyrics">
      동해물과 백두산이 마르고 닳도록<br>
      하느님이 보우하사 우리나라 만세<br>
      무궁화 삼천리 화려강산<br>
      대한 사람 대한으로 길이 보전하세</p>
    </div>

    <div class = "box">
      <h2 class = "verse"> 2절 </h2>
      <p class = "lyrics">
      남산 위에 저 소나무, 철갑을 두른 듯<br>
      바람서리 불변함은 우리 기상 일세<br>
      무궁화 삼천리 화려강산<br>
      대한 사람 대한으로 길이 보전하세</p>
    </div>

    <div class = "box">
      <h2 class = "verse"> 3절 </h2>
      <p class = "lyrics">
      가을 하늘 공활한데 높고 구름 없이<br>
      밝은 달은 우리 가슴 일편단심 일세<br>
      무궁화 삼천리 화려강산<br>
      대한 사람 대한으로 길이 보전하세</p>
    </div>

    <div class = "box">
      <h2 class = "verse"> 4절 </h2>
      <p class = "lyrics">
      이 기상과 이 맘으로 충성을 다하여<br>
      괴로우나 즐거우나 나라 사랑하세<br>
      무궁화 삼천리 화려강산<br>
      대한 사람 대한으로 길이 보전하세</p>
    </div>
  </body>
</html>
```

　이제 여기서 CSS 를 입혀줄때 div 태그로 구역별로 나눴기에 좀 더 편하게 작업할 수 있다 .

```css
.box{
  background-color: #eee;
  border-radius: 20px;
  margin-bottom: 50px;
  padding: 10px;
  width: 500px;
}

.box .verse{
  text-align: center;
}

.box .lyrics{
  text-align: center;
}
```

![image](https://user-images.githubusercontent.com/50429028/111862069-25f75d00-8996-11eb-9a33-3d3dde080545.png)

***

# `<span>` 태그

　문장 내부에서 <div> 태그를 사용하면 `block` 요소 때문에 그 문장은 새로운 줄로 바로 이동 시켜버린다 .

　문단이 이동되는 것이 싫다면 `inline` 요소를 갖고 있는 <span> 태그를 사용하면 된다 .

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}