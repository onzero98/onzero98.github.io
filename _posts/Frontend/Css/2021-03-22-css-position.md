---
title:  "CSS 포지셔닝" 

categories:
  - Css
tags:
  - [CSS, Frontend]

toc: true
toc_sticky: true

date: 2021-03-22 17:10:10 +1000
last_modified_at: 
---
**repl.it 사이트를 사용하여 코딩 하였습니다.**   
[[repl.it] 바로가기](https://replit.com/){:target="_blank"}
{: .notice--warning}

# Relative 포지션

　태그의 위치를 `원 위치에서` 특정 값만큼 움직이고 싶을때 사용한다 .

```
/* 원 위치에서 100px 만큼 아래로 이동 */
top: 100px 

/* 원 위치에서 100px 만큼 위로 이동 */
bottom: 100px

/* 원 위치에서 100px 만큼 오른쪽 이동 */
left: 100px

/* 원 위치에서 100px 만큼 왼쪽 이동 */
right: 100px
```
![image](https://user-images.githubusercontent.com/50429028/111964726-452df000-8b38-11eb-9c91-5efffc5d9d23.png)

　원래 문장의 흐름을 해치지 않고 `Relative` 포지션으로 지정한 것만 움직이는 것 같다 .

***

# Fixed 포지션

　태그의 위치를 `브라우저 기준` 에서 특정 값만큼 움직이고 싶을때 사용한다 .

![fixed-position](https://user-images.githubusercontent.com/50429028/111969944-1b77c780-8b3e-11eb-99d7-656cd1736690.gif)

　원래 문장에서 사라졌고 , 아무리 `스크롤` 을 해도 그 `자리` 를 `유지` 한다 .

　`브라우저 네비게이션` (상단 메뉴 버튼) 같은 식으로 활용하면 유용할 것 같다 .

***

# Absolute 포지션

　태그의 위치를 가장 가까운 포지셔닝이 된 조상 요소 기준으로 지정한 만큼 움직인다 .

![image](https://user-images.githubusercontent.com/50429028/111973059-7363fd80-8b41-11eb-982b-9fd8ab4b9511.png)

　생성된 `fir` , `sec` ,  `thr` 상자중에서 `sec` 에 `relative` 포지션을 준다 .

![image](https://user-images.githubusercontent.com/50429028/111973194-97274380-8b41-11eb-88e4-00a92ca916d4.png)

　`thr` 상자에 `absolute` 포지셔닝을 해주고 실행하면 가장 가까운 `relative` 가 된 것을 알 수 있다 .

![image](https://user-images.githubusercontent.com/50429028/111973764-2e8c9680-8b42-11eb-9a67-cba111d1733a.png)

　`sec` 의 포지션을 기본 `static` 으로 되돌리고 `fir` 에 `relative` 포지션을 준다 .

![image](https://user-images.githubusercontent.com/50429028/111974097-875c2f00-8b42-11eb-9116-189ffe9fa79a.png)

　이번엔 `fir` 상자의 `relative` 속성을 받아 움직인것을 확인 할 수 있다 .
<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}