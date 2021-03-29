---
title:  "JS 이벤트 - 핸들러 , 객체" 

categories:
  -  JS Concepts
tags:
  - [Programming, JS 개념]

toc: true
toc_sticky: true

date: 2021-03-29 12:10:10 +1000
last_modified_at: 
---

# 이벤트

|--------|-----|
|<span style="color:orange"><b>마우스 이벤트</b></span>||
|　mousedown		|　마우스 버튼을 누르는 순간|
|　mouseup			|　마우스 버튼을 눌렀다 떼는 순간|
|　click			|　왼쪽 버튼을 클릭한 순간|
|　dblclick			|　왼쪽 버튼을 빠르게 두 번 클릭한 순간|
|　contextmenu		|　오른쪽 버튼을 클릭한 순간|
|　mousemove		|　마우스를 움직이는 순간|
|　mouseover		|　마우스 포인터가 요소 위로 올라온 순간|
|　mouseout			|　마우스 포인터가 요소에서 벗어나는 순간|
|　mouseenter		|　마우스 포인터가 요소 위로 올라온 순간 (버블링이 일어나지 않음)|
|　mouseleave		|　마우스 포인터가 요소에서 벗어나는 순간 (버블링이 일어나지 않음)|
|<span style="color:orange"><b>키보드 이벤트</b></span>||
|　keydown			|　키보드의 버튼을 누르는 순간|
|　keypress			|　키보드의 버튼을 누르는 순간 ('a', '5' 등 출력이 가능한 키에서만 동작하며, Shift, Esc 등의 키에는 반응하지 않음)|
|　keyup			|　키보드의 버튼을 눌렀다 떼는 순간|
|<span style="color:orange"><b>포커스 이벤트</b></span>||
|　focusin			|　요소에 포커스가 되는 순간|
|　focusout			|　요소로부터 포커스가 빠져나가는 순간|
|　focus			|　요소에 포커스가 되는 순간 (버블링이 일어나지 않음)|
|　blur				|　요소로부터 포커스가 빠져나가는 순간 (버블링이 일어나지 않음)|
|<span style="color:orange"><b>입력 이벤트</b></span>||
|　change			|　입력된 값이 바뀌는 순간|
|　input			|　값이 입력되는 순간|
|　select			|　입력 양식의 하나가 선택되는 순간|
|　submit			|　폼을 전송하는 순간|
|<span style="color:orange"><b>스크롤 이벤트</b></span>||
|　scroll			|　스크롤 바가 움직일 때|
|<span style="color:orange"><b>윈도우 창 이벤트</b></span>||
|　resize			|　윈도우 사이즈를 움직일 때 발생|

***

# 이벤트 핸들러

　HTML의 속성이나 DOM 프로퍼티를 활용해 이벤트를 등록하는 방법 외에도

　addEventListener , removeEventListner 를 통해 이벤트를 등록 / 삭제 할 수 있다 .
```js
let btn1 = document.querySelector('#send1')
let btn2 = document.querySelector('#send2')
```

## 이벤트 핸들러 등록하기

```js
Element.addEventListener('event', handler)
```
```js
function event1(){
  console.log("Hello");
}

function event2(){
  console.log("World");
}

btn1.addEventListener('click', event1);
btn1.addEventListener('click', event2);
```
![1](https://user-images.githubusercontent.com/50429028/112787582-cc78e780-9093-11eb-9126-146c783bc634.gif)

## 이벤트 핸들러 삭제하기

```js
Element.removeEventListener('event', handler)
```
```js
btn1.addEventListener('click', event1);
btn1.addEventListener('click', event2);
btn1.removeEventListener('click', event2);

btn2.addEventListener('click', event2);
```
![2](https://user-images.githubusercontent.com/50429028/112787798-5923a580-9094-11eb-9cc8-fef75405a594.gif)

***

# 이벤트 객체

　이벤트에 대한 상세한 정보 , 

　예를 들어 키보드 이벤트가 발생했다면 어떤 키를 눌렀는지에 대한 정보는 이벤트 객체에 저장된다 .

　이 외에도 이벤트 객체는 이벤트 타입에 따라 갖고 있는 프로퍼티들이 조금씩 다르다 .

　또한 모든 브라우저가 event 객체를 지원하지만, 세부 사항까지는 같지 않다 .

|--------|-----|
|<span style="color:orange"><b>공통 프로퍼티</b></span>||
|　bubbles				|　이벤트가 버블링 단계인지를 판단하는 값|
|　cancelable			|　이벤트의 기본 동작 	취소 가능 여부|
|　currentTarget		|　이벤트 핸들러가 등록된 요소|
|　target				|　이벤트가 발생한 요소|
|　type					|　이벤트 이름 ('click', 'mouseup', 'keydown' 등)|
|　timeStamp			|　이벤트 발생 시각(페이지가 로드된 이후부터 경과한 밀리초)|
|<span style="color:orange"><b>마우스 프로퍼티</b></span>||
|　button				|　누른 마우스의 버튼 (0: 왼쪽, 1: 가운데(휠), 2: 오른쪽)
|　clientX, clientY		|　마우스 커서의 브라우저 표시 영역에서의 위치
|　pageX, pageY			|　마우스 커서의 문서 영역에서의 위치
|　offsetX, offsetY		|　마우스 커서의 이벤트 발생한 요소에서의 위치
|　screenX, screenY		|　마우스 커서의 모니터 화면 영역에서의 위치
|　<span style="opacity:0.6">altKey					|　<span style="opacity:0.6">이벤트가 발생할 때 alt키를 눌렀는지|
|　<span style="opacity:0.6">ctrlKey				|　<span style="opacity:0.6">이벤트가 발생할 때 ctrl키를 눌렀는지|
|　<span style="opacity:0.6">shiftKey				|　<span style="opacity:0.6">이벤트가 발생할 때 shift키를 눌렀는지|
|　<span style="opacity:0.6">metaKey				|　<span style="opacity:0.6">이벤트가 발생할 때 meta키를 눌렀는지 (window는 window키, mac은 cmd키)|
|<span style="color:orange"><b>키보드 프로퍼티</b></span>||
|　key					|　누른 키가 가지고 있는 값|
|　code					|　누른 키의 물리적인 위치|
|　<span style="opacity:0.6">altKey					|　<span style="opacity:0.6">이벤트가 발생할 때 alt키를 눌렀는지|
|　<span style="opacity:0.6">ctrlKey				|　<span style="opacity:0.6">이벤트가 발생할 때 ctrl키를 눌렀는지|
|　<span style="opacity:0.6">shiftKey				|　<span style="opacity:0.6">이벤트가 발생할 때 shift키를 눌렀는지|
|　<span style="opacity:0.6">metaKey				|　<span style="opacity:0.6">이벤트가 발생할 때 meta키를 눌렀는지 (window는 window키, mac은 cmd키)|

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}