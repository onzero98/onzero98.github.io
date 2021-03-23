---
title:  "CSS 텍스트 스타일링" 

categories:
  - Css
tags:
  - [CSS, Frontend]

toc: true
toc_sticky: true

date: 2021-03-20 14:10:10 +1000
last_modified_at: 
---
**repl.it 사이트를 사용하여 코딩 하였습니다.**   
[[repl.it] 바로가기](https://replit.com/){:target="_blank"}
{: .notice--warning}

# 텍스트 꾸미기

　CSS 로 텍스트를 꾸밀 수 있다 .

> Underline

```css
h1 {
  text-decoration: underline;
}
```

![image](https://user-images.githubusercontent.com/50429028/111863769-d10d1400-89a0-11eb-91c8-14504423592e.png)


> Overline

```css
h1 {
  text-decoration: overline;
}
```

![image](https://user-images.githubusercontent.com/50429028/111863790-e8e49800-89a0-11eb-98df-d410efea0998.png)


> Line-through

```css
h1 {
  text-decoration: line-through;
}
```

![image](https://user-images.githubusercontent.com/50429028/111863803-f437c380-89a0-11eb-8165-7be39df622d7.png)

> None

```css
h1 {
  text-decoration: none;
}
```

![image](https://user-images.githubusercontent.com/50429028/111863812-0154b280-89a1-11eb-867b-6fe0f282093e.png)

***

# 텍스트 색상 설정

```css
h1{
  color: orange;
}
```

　텍스트 색상 스타일링 하는 방법은 보통 기본 색상을 지정해주는 방식으로 한다 .

　하지만 이중에 자신이 `원하는 색` 이 없을 수도 있는데 그럴 땐 `직접` RGB 를 설정해주면 된다 .

　HTML 에서 사용하는 색상 알아보는 [사이트 바로가기](https://htmlcolorcodes.com/){:target="_blank"}

　`RGB` 값을 주거나 `HEX` 값을 `color` 에 설정해주면 된다 .

![image](https://user-images.githubusercontent.com/50429028/111863010-30b4f080-899c-11eb-8457-e3b55fd2d54a.png)

```css
h1{
  /* 하늘색 */
  color: rgb(45, 136, 245);
}
h2{
  /* 핑크색 */
  color: #E92DF5;
}
```

***

# 텍스트 정렬

　좌, 우, 중앙 정렬을 하는 방법 .

```css
#p1 {
  text-align: left;
}

#p2 {
  text-align: right;
}

#p3 {
  text-align: center;
}
```

```html
<p id="p1">왼쪽</p>
<p id="p2">오른쪽</p>
<p id="p3">중앙</p>
```

***

# 폰트 굵기

　사용 가능한 숫자는 100, 200, 300, 400, 500, 600, 700, 800, 900 으로

　100 이 가장 얇고 , 900 이 가장 굵다 .

　기본 디폴트(normal)는 400 , bold 값은 700을 가진다 .

```css
p {
  font-weight: 400;
}
```

***

# 폰트 크기

- 절대적(Absolute) `px` `pt`

```
pt 는 px의 1.333... 배의 크기 이다 .
```

- 상대적(Relative) `em` `%`

```
1 em = 100 %
상대적인 크기는 분모의 크기를 기준으로 삼는다 .
```
```css
body{
  font-size: 16px;
}
.div1{
  font-size: 100%;
}
.div2{
  font-size: 200%;
}
.div3{
  font-size: 200%;
}
```
```html
<body>
<div class = "div1">
  div1
  <div class = "div2">
    div2
    <div class = "div3">
      div3
    </div>
  </div>
</div>
</body>
```

![image](https://user-images.githubusercontent.com/50429028/111863604-f77e7f80-899f-11eb-904d-c15a169cb4c8.png)


***

# 폰트 설정

## 가지고 있는 폰트 사용 

　가장 먼저 `BMJUA` 체를 찾고 , 없다면 `BMDOHYEON` 체를 찾고 그마저도 없다면 `serif` 체를 사용하라 .

```css
h1{
  font-family: "BMJUA", "BMDOHYEON", serif;
}
```

## 구글에서 폰트 불러와서 사용하는

　[구글 폰트](https://fonts.google.com/?subset=korean){:target="_blank"} 에서 원하는 폰트를 찾아 눌러보면

　+ Select this style 을 누르면 링크가 나온다 .

![image](https://user-images.githubusercontent.com/50429028/111864344-aa041180-89a3-11eb-8aff-9a6ce527e963.png)

　눈치 챘다싶이 링크를 `HTML` 의 `<head>` 부분에 복사해주고 `CSS` 파일에는 `원하는 문단`에 스타일을 입혀주면 된다 .

```html
<link href="style.css" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Do+Hyeon&display=swap" rel="stylesheet">
```

```css
p{
  font-family: 'Do Hyeon', sans-serif;
}
```

![image](https://user-images.githubusercontent.com/50429028/111864538-cbb1c880-89a4-11eb-9f4f-8b7fa2fe1e54.png)

　폰트가 바뀌는것을 확인 할 수 있다 .

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}