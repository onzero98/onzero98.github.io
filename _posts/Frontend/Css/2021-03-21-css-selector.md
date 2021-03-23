---
title:  "CSS 선택자 정리" 

categories:
  - Css
tags:
  - [CSS, Frontend]

toc: true
toc_sticky: true

date: 2021-03-21 12:10:10 +1000
last_modified_at: 
---
**repl.it 사이트를 사용하여 코딩 하였습니다.**   
[[repl.it] 바로가기](https://replit.com/){:target="_blank"}
{: .notice--warning}

# 태그 이름 (Tag Name)

```html
<h1>Heading 1</h1>
```

```css
/* <h1> 태그 */
h1 {
  color: orange;
}
```

# 클래스 (Class) / 아이디 (ID)

```html
<p class = "highlight"> Paragraph 1 </p>
<p> Paragraph 2 </p>
<p id = "favorite"> Paragraph 3 </p>
```

```css
/* 'highlight'라는 클래스를 갖고 있는 모든 태그 */
.important {
  color: orange;
}

/* 'favorite'라는 아이디를 갖고 있는 태그 */
#favorite {
  color: red;
}
```

# 자식 (Children)

```html
<b>Outside</b>
<div class="box">
  <b>Inside 1</b>
  <p>Hello <b>Inside 2</b></p>
  <b>Inside 3</b>
</div>
```

```css
/* 'box' 클래스를 갖고 있는 요소의 자식 중 모든 <b> 태그 */
.div1 b {
  color: orange;
}
```

# 직속 자식 (Direct Children)

```html
<b>Outside</b>
<div class="box">
  <b>Inside 1</b>
  <p>Hello <b>Inside 2</b></p>
  <b>Inside 3</b>
</div>
```

```css
/* 'box' 클래스를 갖고 있는 요소의 직속 자식 중 모든 <b> 태그 */
.div1 > i {
  color: orange;
}
```

# 복수 선택 (Multi Select)

```html
<p class="one">Outside 1</p>
<p class="two">Outside 2</p>
<div>
  <p class="one">Inside 1</p>
  <p class="two">Inside 2</p>
  <p class="three">Inside 3</p>
  <p class="four">Inside 4</p>
  <p class="five">Inside 5</p>
</div>
```
```css
/* 'two' 클래스를 가지고 있는 태그 모두와 'four' 클래스를 가지고 있는 태그 모두 선택 */
.two, .four {
  color: orange;
}
```

# 여러 조건 (Requirement)

```html
<p class="outside one">Outside 1</p>
<p class="outside two">Outside 2</p>
<div>
  <p class="inside one">Inside 1</p>
  <p class="inside two">Inside 2</p>
  <p class="inside three">Inside 3</p>
  <p class="inside four">Inside 4</p>
  <p class="inside five">Inside 5</p>
</div>
```
```css
/* 'outside' 클래스를 갖고 있으면서 'one' 클래스도 갖고 있는 태그 */
.outside.one {
  color: blue;
}

/* 'inside' 클래스를 갖고 있으면서 'two' 클래스도 갖고 있는 태그 */
.inside.two {
  color: orange;
}
```

# 가상 클래스 (Pseudo Class)

　콜론(:)을 사용하면 몇 가지 '가상 클래스'를 선택할 수 있다 .

```html
<div class="div1">
  <p>Paragraph 1</p>
  <p>Paragraph 2</p>
  <p>Paragraph 3</p>
  <p>Paragraph 4</p>
  <p>Paragraph 5</p>
  <p>Paragraph 6</p>
</div>
```

```css
/* .div1의 자식인 <p> 태그 중 3번째 */
.div1 p:nth-child(3) {
  color: blue;
}

/* .div1의 자식인 <p> 태그 중 첫 번째 */
.div1 p:first-child {
  color: red;
}

/* .div1의 자식인 <p> 태그 중 마지막 */
.div1 p:last-child {
  color: green;
}

/* .div1의 자식 중 마지막 자식이 아닌 <p> 태그 */
.div1 p:not(:last-child) {
  font-size: 150%;
}

/* .div1의 자식 중 첫 번째 자식이 아닌 <p> 태그 */
.div1 p:not(:first-child) {
  text-decoration: line-through;
}
```

# 마우스 호버 (hover)

　마우스를 가져다 대면 색이 변한다 .

```html
<h1>Hello World!</h1>
```

```css
h1 {
  color: orange;
}

/* 마우스가 <h1> 태그에 올라갔을 때 */
h1:hover {
  color: green;
}
```

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}