---
title:  "JS Style" 

categories:
  -  JS Concepts
tags:
  - [Programming, JS 개념]

toc: true
toc_sticky: true

date: 2021-03-28 18:10:10 +1000
last_modified_at: 
---

# 스타일 다루기

　자바스크립트로 `태그` 의 `스타일` 을 다루는 방법에는 크게 두 가지가 있다 .

## Style 프로퍼티

```js
element.style.styleName = 'value';
```

![image](https://user-images.githubusercontent.com/50429028/112749696-02b85780-8fff-11eb-96c5-fdb69d234afd.png)
```js
kor.children[2].style.backgroundColor = '#FFF000';
```
　잘 적용 되는것 처럼 보여도 , 위에 보이는 것처럼 `style` 이 `tag` 에 `직접적` 으로 값이 `삽입` 된다 .

　이는 `style` `우선순위` 가 `높아져` 서 나중에 의도와 다르게 `문제` 가 될 가능성이 생긴다 .

## Class 변경 

　`CSS` 에서 미리 `만들어둔` `stylesheet` 을 가져와서 `적용` 하는 방법 .
```css
.erase{
  opacity: 0.5;
  text-decoration: line-through;
}
```

### ClassName

```js
element.className = 'class';
```
```js
kor.children[1].className = 'erase';
```
![image](https://user-images.githubusercontent.com/50429028/112750056-2bd9e780-9001-11eb-88d3-57bd8206e6f4.png)

　다만 보다 싶이 `list_kor` 의 `item` 이 `ClassName` 변경으로 `erase` 가 되어버렸다 .

　이또한 겉으로 보기엔 멀쩡하지만 , 의도와는 맞지 않다 .

### ClassList

```js
// add , remove , toggle
element.classList.add('class');
```
```js
const item = kor.children[1];
item.classList.add('erase');
```
![image](https://user-images.githubusercontent.com/50429028/112750268-9f302900-9002-11eb-84dd-112369c9f9fa.png)

　클래스 속성값을 `유사배열` 로 다루는 `프로퍼티` 이다 . 

　클래스를 추가하는 `add` , 제거하는 `remove` 

　클래스가 없다면 추가하고 , 있다면 제거하는 `toggle` 메소드를 활용할 수 있다 .

```js
const item = kor.children[1];
item.classList.add('erase', 'color'); 		// erase , color 클래스 추가
item.classList.remove('erase'); 		// erase 클래스 제거
item.classList.toggle('color', true); 		// color 클래스 추가
```
![image](https://user-images.githubusercontent.com/50429028/112750444-a3107b00-9003-11eb-8fd6-1a89a10457ab.png)

|메소드|내용|참고사항|
|-----|-----|-----|
|classList.add|	클래스 추가하기|	여러 개의 값을 전달하면 여러 클래스 추가 가능|
|classList.remove|	클래스 삭제하기|	여러 개의 값을 전달하면 여러 클래스 삭제 가능|
|classList.toggle|	클래스 없으면 추가, 있으면 삭제하기|	하나의 값만 적용 가능하고, 두 번째 파라미터로 추가 또는 삭제 기능을 강제할 수 있음|

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}