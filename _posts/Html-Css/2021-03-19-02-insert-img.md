---
title:  "HTML 이미지" 

categories:
  -  Html Css
tags:
  - [HTML, CSS]

toc: true
toc_sticky: true

date: 2021-03-19
last_modified_at: 
---
**repl.it 사이트를 사용하여 코딩 하였습니다.**   
[[repl.it] 바로가기](https://replit.com/){:target="_blank"}
{: .notice--warning}

# 이미지 삽입

　웹페이지에 단순히 글자만 있으면 밋밋할 것이다 .   

　이번 포스트은 이미지를 html 에 삽입하는 법을 정리한다 .

## 외부에서 이미지 주소를 받아 삽입

　웹사이트에서 원하는 이미지의 주소를 받아서 넣는다 .

　바바라 팔빈은 역시 예쁘다 .

```html
<img src = "https://data2.1freewallpapers.com/detail/barbara-palvin-eyes-face.jpg">
```

![image](https://user-images.githubusercontent.com/50429028/111732968-17d40e80-88ba-11eb-9cad-37025d9b8a88.png)


## 내 파일을 받아 삽입

　내 로컬에서 이미지를 받는 방법이다 .

　이번엔 대한민국 래퍼 비비의 이미지를 올려보자 .

　다만 <u>주의할 점</u>은 이미지를 저장한 <u>폴더의 위치를 계산</u>해주어야 한다 .

　폴더 `folder1` 에 있는 `page3.html` 이 `img` 폴더에 있는 `bibi.jpg` 를 불러 오기 위해서

　주소 접근을 <u>상위 폴더로 한번 이동하고 , img 폴더로 접근</u>해야 한다 .

![image](https://user-images.githubusercontent.com/50429028/111734062-a6e22600-88bc-11eb-8c65-74356cc690b6.png)

```html
<img src = "../img/bibi.jpg">
```

![image](https://user-images.githubusercontent.com/50429028/111734115-cd07c600-88bc-11eb-8cfd-12aa933a2c0d.png)

## 리사이즈

　`bibi.jpg` 파일이 예상과는 다르게 너무 크다 !

　물론 큰 이미지를 좋아하는 사람도 있겠지만 , 개발자가 의도한 사이즈가 아닐 경우 리사이즈를 해야 할 것이다 .

　리사이즈를 하는 법은 `width` 나 `height` 속성을 사용하면 된다 .

　속성을 `1개` 만 사용하면 `원본의 비율에 맞게` 나머지 속성이 리사이즈 되고

　`2개` 의 속성을 다 사용하면 `원하는 크기` 로 사용자가 리사이즈 할 수 있다 .

```html
<img src = "../img/bibi.jpg" width="1080">
```

![image](https://user-images.githubusercontent.com/50429028/111734787-20c6df00-88be-11eb-8ab8-de6697e55205.png)

## 이미지 정렬

> 왼쪽 정렬

![image](https://user-images.githubusercontent.com/50429028/111735485-7354cb00-88bf-11eb-90d6-5cc0daa135eb.png)

```html
<style>
  img{
    display: block;
    margin-right: auto;
  }
</style>
```

> 오른쪽 정렬

![image](https://user-images.githubusercontent.com/50429028/111735547-8c5d7c00-88bf-11eb-81e0-968619a268c0.png)

```html
<style>
  img{
    display: block;
    margin-left: auto;
  }
</style>
```

> 가운데 정렬

![image](https://user-images.githubusercontent.com/50429028/111735608-a72ff080-88bf-11eb-931a-75566ccee11d.png)

```html
<style>
  img{
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
</style>
```

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}