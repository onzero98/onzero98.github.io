---
title:  "CSS 우선 순위" 

categories:
  -  Html Css
tags:
  - [HTML, CSS]

toc: true
toc_sticky: true

date: 2021-03-21 13:10:10 +1000
last_modified_at: 
---
**repl.it 사이트를 사용하여 코딩 하였습니다.**   
[[repl.it] 바로가기](https://replit.com/){:target="_blank"}
{: .notice--warning}

# 우선 순위

　여러 선택자가 같은 요소를 가리키면 우선 순위를 결정하는 방법은 아래와 같다 .

## 순서 

　완전 똑같은 선택자가 나중에 또 나오면, 이전에 나온 스타일을 덮어쓰게 된다 .

```html
<h1>Heading 1</h1>
```

```css
h1 {
  color: blue;
  text-align: center;
}

h1 {
  color: green;
}
```

![image](https://user-images.githubusercontent.com/50429028/111893620-5e0aa880-8a47-11eb-9e4c-10425c2a26bf.png)

## 명시도 (Specificity)

　같은 요소를 가리키지만 선택자가 다르다면, 명시도 에 따라 우선 순위가 결정된다 .

　명시도 계산 방법은 아래와 같다 .
```
1. 인라인 스타일이 가장 우선 순위가 높다 .
2. 선택자에 id가 많을 수록 우선 순위가 높다 .
3. 선택자에 클래스(class), 속성(attribute), 가상 클래스(pseudo-class) 가 많을 수록 우선 순위가 높다 .
4. 그 다음은 그냥 요소(또는 가상 요소)가 많은 순서이다 .
```

```html
<ul>
  <li><a id="link" href="#">NAVER</a></li>
  <li><a id="link" href="#">NAVER</a></li>
</ul>
```
```css
/* id 1, 가상클래스 1, 일반요소 2 = 112점 */
ul li:first-child #link {
  color: green;
}
/* 가상클래스 1, 일반요소 3 = 13점 */
ul li:first-child a {
  color: orange;
}
```

![image](https://user-images.githubusercontent.com/50429028/111893862-39afcb80-8a49-11eb-8d72-401005e6fa20.png)

　`가상 클래스` 로 지정한 첫번째 요소 `p` 가 `명시도` 가 더 `높은` 선택자의 스타일인 `green` 으로 바뀜을 확인 할 수 있다 .

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}