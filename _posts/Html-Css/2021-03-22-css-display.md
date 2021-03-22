---
title:  "CSS 디스플레이" 

categories:
  -  Html Css
tags:
  - [HTML, CSS]

toc: true
toc_sticky: true

date: 2021-03-22 15:10:10 +1000
last_modified_at: 
---
**repl.it 사이트를 사용하여 코딩 하였습니다.**   
[[repl.it] 바로가기](https://replit.com/){:target="_blank"}
{: .notice--warning}

# Display 종류

　레이아웃을 제대로 이해하기 위해서는 `display` 속성을 먼저 알아야 한다.

- inline 
- block
- inline-block
- list-item
- table
- flex
- none 

　등이 있는데 모든 `html 요소`는 이중 `한가지`만 가질 수 있다 .

　그 중에서 가장 많이 가지는 요소는 inline 과 block 이다 .

## Inline Display

> \<span> \<a> \<b> \<i> \<img> \<button>

```html
<h1>Hello <i>World</i> !</h1>
```

![image](https://user-images.githubusercontent.com/50429028/111954091-ea41cc00-8b2a-11eb-9f2d-4ef750303346.png)

　`inline` 요소들은 다른 요소들과 <u>같은 줄</u>에 머무르려고 하는 성향이 있고

　`background-color` 를 보면 <u>가로 길이</u>는 <u>필요한 만큼</u>만 차지하는 성향이 있다 .

## Block Display

> \<div> \<h1> \<p> \<nav> \<ul> \<li>

```html
<h1>Hello <div>World</div> !</h1>
```

![image](https://user-images.githubusercontent.com/50429028/111954268-2c6b0d80-8b2b-11eb-9bf0-4f61ebcb936a.png)

　`block` 요소들은 다든 요소들과 떨어져서 <u>새로운 줄</u>에 가려는 성향이 있고

　`background-color` 를 보면 <u>가로 길이</u>를 <u>최대한 많이</u> 차지하려고 하는 성향이 있다 .

***

# Display 바꾸기

　정해진 display 값을 바꾸고 싶을때 CSS 를 통해서 이를 바꿀 수 있다 .

## Inline to Block

```css
i{
  display: block;
  background-color: red;
}
```

```html
<h1>Hello <i>World</i> !</h1>
```

![image](https://user-images.githubusercontent.com/50429028/111955879-6d642180-8b2d-11eb-81a1-136a7fd8ae4d.png)


## Block to Inline

```css
div{
  display: inline;
  background-color: red;
}
```

```html
<h1>Hello <div>World</div> !</h1>
```

![image](https://user-images.githubusercontent.com/50429028/111955204-8e784280-8b2c-11eb-980a-db55a3451010.png)

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}