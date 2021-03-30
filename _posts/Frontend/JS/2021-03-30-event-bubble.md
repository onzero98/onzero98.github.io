---
title:  "JS 이벤트 - 버블링 , 캡쳐링 , 위임" 

categories:
  -  JS Concepts
tags:
  - [Programming, JS 개념]

toc: true
toc_sticky: true

date: 2021-03-30 15:10:10 +1000
last_modified_at: 
---

# 이벤트 버블링

　한 요소의 이벤트가 발생하게 되면 그 요소의 할당된 `이벤트 핸들러` 가 동작하고 

　해당 이벤트가 `Window` 객체를 만날때 까지 더 `상위` 의`(부모 요소)` `이벤트 핸들러` 로 전달한다.

　이 과정이 물속에서 거슬러 올라오는 `거품` 과 비슷하다 해서 `이벤트 버블링` 이라고 불리게 되었다 한다 .

![bubble](https://user-images.githubusercontent.com/50429028/112954001-f3f5b000-9178-11eb-8eb9-27c73a600966.gif)

```html
<body>
  <div id="content">
    content
    <h1 id="title">오늘 할 일</h1>
    <ol id="list">
      list
      <li class="item">자바스크립트 공부</li>
      <li class="item">깃허브 포스팅</li>
      <li class="item">게임</li>
      <li class="item">유튜브</li>
      <li class="item">만화</li>
    </ol>
  </div>
  <script src="index.js"></script>
</body>
```
```js
const content = document.querySelector('#content');
const title = document.querySelector('#title');
const list = document.querySelector('#list');
const items = document.querySelectorAll('.item');

content.addEventListener('click', function(){
  console.log('Content Event');
});

title.addEventListener('click', function(){
  console.log('Title Event');
});

list.addEventListener('click', function(){
  console.log('List Event');
});

for (let item of items){
  item.addEventListener('click', function(){
    console.log('Item Event');
  });
}
```

**Target 프로퍼티**
```js
content.addEventListener('click', function(event){
  console.log('Content Event');
  console.log(event.target);
});
```
　이전 포스팅에서 언급한 `이벤트 객체`의 공통 프로퍼티인 `target` 프로퍼티는 이벤트가 `발생한` 요소 를 반환하는데

　각 `이벤트 핸들러` 가 `버블링` 되면서 동작할 때 각 `이벤트 핸들러` 에 `등록된` 요소가 `target` 이 되는것은 아니다 .

　이벤트 `버블링` 이 일어나도 `target` 은 처음 이벤트가 발생한 `시작점` 을 담고 있다 .

![target](https://user-images.githubusercontent.com/50429028/112956009-f953fa00-917a-11eb-85a6-aa407042e1e7.gif)

**CurrentTarget 프로퍼티**
```js
content.addEventListener('click', function(event){
  console.log('Content Event');
  console.log(event.currentTarget);
});
```
　만약 이벤트 핸들러가 `등록된` 요소에 접근하고 싶다면 `currentTarget` 프로퍼티를 활용하면 된다 .

　이벤트 `버블링` 이 되면서 `이벤트 핸들러` 에 `등록된` 요소가 출력되는 것을 볼 수 있다 .

![curTarget](https://user-images.githubusercontent.com/50429028/112957211-2d7bea80-917c-11eb-9363-2cbdb192f7e5.gif)

## event.stopPropagation()

```js
for (let item of items){
  item.addEventListener('click', function(event){
    console.log('Item Event');
    console.log(event.currentTarget);
    event.stopPropagation();
  });
}
```
　이벤트의 버블링을 멈추고 싶다면 메소드 `stopPropagation()` 를 사용하면 된다 .

　이는 , 해당 요소의 이벤트만 발생시키고 `상위 요소` 로 이벤트를 `전달` 하는 것을 `방해` 한다 .

　다만 `문제점` 은 , `버블링` 이 막혀있다면 `하위 요소` 를 다루는 `상위 요소` 의 `이벤트 핸들러` 로 전달되지 못하기 때문에

　원하는 결과를 얻지 못할 수 있다 .

![stop](https://user-images.githubusercontent.com/50429028/112960592-88fba780-917f-11eb-8915-94b59cf87cc1.gif)

***

# 이벤트 캡쳐링

![bubble](https://user-images.githubusercontent.com/50429028/112977335-e3e9ca80-9190-11eb-85c4-95047de6a0f2.png)

　`DOM` 이벤트는 3가지의 흐름이 있고 위의 `버블링` 단계 , `타깃` 단계 , 그리고 `캡쳐링` 단계가 있다 .

　그 중에서 이벤트 `캡쳐링` 은 `버블링` 의 `반대` 개념으로 , 이벤트가 `하위 요소` 로 전파 되는 단계이다 .

　이벤트가 `발생` 하면 가장 먼저 `window` 객체에서부터 `target` 까지 이벤트 `전파` 가 일어난다 .

　캡처링 단계에서 이벤트를 잡아내려면 `addEventListener` 의 `capture` 옵션을 `true` 로 설정하면 된다 .
```js
for (let element of document.querySelectorAll('*')) {
  // true , {capture: true}
  element.addEventListener("click", function(event){
    console.log(`캡쳐링 단계: ${element.tagName}`);
  }, true);

  // default , false
  element.addEventListener("click", function(event){
    console.log(`버블링 단계: ${element.tagName}`);
  });
}
```

![cap](https://user-images.githubusercontent.com/50429028/112979497-9d499f80-9193-11eb-8cf2-eba8e9089fdb.gif)

***

# 이벤트 위임

　`버블링` 개념에 따라 `부모 요소` 가 `자식 요소` 에서 일어나는 이벤트를 감지할 수 있고 

　`target` 프로퍼티가 이벤트 `발생 위치` 를 담고 있기 때문에 `하위 요소` 에서 각각의 이벤트를 붙이지 않고

　`상위 요소` 에서 `하위 요소` 를 `제어` 하는 방식을 `이벤트 위임` 이라고 한다 .

```js
const list = document.querySelector('#list');

list.addEventListener('click', function(e){
  e.target.classList.toggle('done');
})

const li = document.createElement('li');
li.classList.add('item');
li.textContent = '잠자기';
list.append(li);
```

![위임](https://user-images.githubusercontent.com/50429028/112984663-2368e480-919a-11eb-8c21-8762983b1031.gif)

　다만 이미지에서 보이다 싶이 `상위 요소` 에서 이벤트를 처리하게되니 `list` 마저 `done` 클래스가 추가되면서 

　`의도하지 않은` 동작이 실행되었다 .

　이를 해결하기 위해 , 원하는 요소에서 의도한 동작이 실행 되게 따로 정교하게 처리를 해주어야 한다 .

```js
list.addEventListener('click', function(e){
  // e.target.classList.contains('item')
  if(e.target.tagName === 'LI'){
    e.target.classList.toggle('done');
  }
})
```

　`tagName` 이 `li` 인 것만 `done` 클래스를 추가 하거나 

　`contains` 메소드를 사용하여 `item` 이라는 클래스가 포함된 클래스만 `done` 클래스를 추가한다던가

　<b style="color:orange">여러가지 조건</b>으로 개발자가 원하는 방식으로 해결 할 수 있을 것이다 .
<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}