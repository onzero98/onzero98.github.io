---
title:  "요소 노드" 

categories:
  -  JS Concepts
tags:
  - [JS 개념]

toc: true
toc_sticky: true

date: 2021-03-27 11:10:10 +1000
last_modified_at: 
---

# 요소 노드 주요 프로퍼티

- innerHTML
- outerHTML
- textContent

```js
const myTag = document.querySelector('#list1');
```

## element.innerHTML

　요소 `안`에 있는 `HTML` 을 `문자열` 로 `리턴` 해준다 .

　태그와 태그 사이에 `줄바꿈` 이나 `들여쓰기` 도 `포함` 한다 .

```js
console.log(myTag.innerHTML);
```
![image](https://user-images.githubusercontent.com/50429028/112707752-f47c1580-8ef0-11eb-933b-8080f012e13a.png)

　내부의 HTML 을 수정할 때 활용된다 .

```
새로 교체하기
```
```js
console.log(myTag.innerHTML);
myTag.innerHTML = '<li> 숫자세기 한글판 </li>'
console.log(myTag.innerHTML);
```
![image](https://user-images.githubusercontent.com/50429028/112707760-0eb5f380-8ef1-11eb-9743-5acd403b5923.png)

```
기존에 더하기
```
```js
console.log(myTag.innerHTML);
myTag.innerHTML += '<li> 숫자세기 한글판 </li>'
console.log(myTag.innerHTML);
```
![image](https://user-images.githubusercontent.com/50429028/112707781-32793980-8ef1-11eb-8b99-c0989d627441.png)


## element.outerHTML

　요소 노드 자체의 `전체`적인 `HTML` 을 `문자열` 로 `리턴` 해준다 .

　내부의 `줄바꿈` 이나 `들여쓰기` 도 `포함` 한다 .
```js
console.log(myTag.outerHTML);
```
![image](https://user-images.githubusercontent.com/50429028/112707856-c0552480-8ef1-11eb-971d-acfaa408c73d.png)

　다만 한번 `수정` 하게 되면 완전히 `새로운 요소` 가 되어버려서 그 이후에 요소를 `다루려고` 한다면

　<u>다시 그 요소의 위치를 새로 찾아주어야 한다/<u> .

## element.textContent

　요소 노드 내용들중 `HTML` 을 `제외`한 `텍스트` 부분만 `문자열` 로 `리턴` 한다 .

　내부의 `줄바꿈` 이나 `들여쓰기` 도 `포함` 한다 .
```js
console.log(myTag.textContent);
```
![image](https://user-images.githubusercontent.com/50429028/112710792-0c5e9400-8f07-11eb-81f3-2ff2f9a7ad8c.png)

　사용법은 `innerHTML` 와 같지만 , `textContent` 는 `텍스트` 만 다루기 때문에 `HTML` 코드도 그냥 `텍스트` 처리해버린다 .

```js
console.log(myTag.textContent);
myTag.textContent += '<li> 숫자세기 한글판 </li>';
console.log(myTag.textContent);
```
![image](https://user-images.githubusercontent.com/50429028/112710779-f6e96a00-8f06-11eb-90b7-b69b6e93f1c6.png)

***

# 요소 노드 추가

　위의 `요소 프로퍼티` 는 기존의 문서를 `덮어쓰는` 방식으로 처리를 하는데 ,

　사용하다보면 기존 내용을 실수로 덮어씌우거나 하는 `문제`들이 있다 .

　이런 문제를 해결하려면 요소 노드를 `생성` 해서 필요한 곳에 추가 하면 된다 .

```js
// 요소 노드 추가하기
const newlist = document.querySelector('#list1');

// 1. 요소 노드 만들기 : document.createElement('태그이름');
const first = document.createElement('li');

// 2. 요소 노드 꾸미기 : textContent, innerHTML ...
first.textContent = 'READY';

// 3. 요소 노드 추가하기: NODE.prepend, append, before, after
// 메소드를 호출한 노드의 처음에 파라미터로 전달한 값을 자식 노드로 추가
newlist.prepend(first);

// 메소드를 호출한 노드의 끝에 파라미터로 전달한 값을 자식 노드로 추가
const last = document.createElement('li');
last.textContent = 'END';
newlist.append(last);

// 메소드를 호출한 노드의 앞에 파라미터로 전달한 값을 형제 노드로 추가
const start = document.createElement('p');
start.textContent = '시작';
newlist.before(start);

// 메소드를 호출한 노드의 뒤에 파라미터로 전달한 값을 형제 노드로 추가
newlist.after('끝');
```
![image](https://user-images.githubusercontent.com/50429028/112712725-70d42000-8f14-11eb-9f8b-f33e1f000e27.png)

***

# 요소 노드 제거

```js
const kor = document.querySelector('#list_kor');
const eng = document.querySelector('#list_eng');
```
![image](https://user-images.githubusercontent.com/50429028/112713334-e988ab80-8f17-11eb-9558-be77d97f9bbf.png)

```
remove(); 로 요소 노드 제거가 가능하다 .
```

![image](https://user-images.githubusercontent.com/50429028/112713406-22288500-8f18-11eb-830f-80aab1fef293.png)

***

# 요소 노드 이동

　앞서 노드 추가할 때 사용한 `prepend` , `append` , `before` , `after` 로 요소 노드를 `이동` 시킬 수 있다 .

![image](https://user-images.githubusercontent.com/50429028/112713539-02de2780-8f19-11eb-96cb-893ea14ca2d2.png)

![image](https://user-images.githubusercontent.com/50429028/112713602-61a3a100-8f19-11eb-9962-87b740dd25b7.png)

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}