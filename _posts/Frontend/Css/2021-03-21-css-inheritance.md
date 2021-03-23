---
title:  "CSS 상속" 

categories:
  - Css
tags:
  - [CSS, Frontend]

toc: true
toc_sticky: true

date: 2021-03-21 13:10:10 +1000
last_modified_at: 
---
**repl.it 사이트를 사용하여 코딩 하였습니다.**   
[[repl.it] 바로가기](https://replit.com/){:target="_blank"}
{: .notice--warning}

# 상속

　`CSS` 에는 `상속` 이라는 개념이 있는데 `부모` 요소의 `속성들` 을 `자식` 에게 넘겨주는것을 의미한다 .

```html
<div class="Parent">
  <h1>Heading</h1>
  <p>We are Child</p>
</div>
```

```css
.Parent {
  color: orange;
}
```

![image](https://user-images.githubusercontent.com/50429028/111893249-b7250d00-8a44-11eb-9380-9c8b86e87745.png)

　`.Parent` 의 폰트 색을 `orange` 로 설정해주었고 , `<h1>` 과 `<p>` 에 대해서는 별도로 설정해주지 않았다 .

　그런데도 `<h1>` 과 `<p>` 의 폰트 색이 `orange` 로 설정되었다 .

　그 이유는 `Parent` 의 스타일이 자식들에게 `상속` 되었기 때문이다 .

## 상속되는 속성들

- color
- font-family
- font-size
- font-weight
- line-height
- list-style
- text-align
- visibility

　이외에도 많지만 일단 자주 사용하는 몇 가지 속성들이다 .

　이들도 사실 항상 상속되는 것은 아니며 , `강제` 로 `상속` 을 받아오기 위해서는 `inherit` 값을 쓰면 된다 .

```html
<div class="div1">
  Let's go to <a href="https://google.com" target="_blank">google</a>!
</div>

<div class="div2">
  Let's go to <a href="https://google.com" target="_blank">google</a>!
</div>
```
```css
*{
  text-decoration: none;
}

.div1 {
  color: green;
}

.div2 {
  color: orange;
}

.div2 a {
  color: inherit;
}
```

![image](https://user-images.githubusercontent.com/50429028/111893498-75956180-8a46-11eb-9b8c-16d2f585857a.png)

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}