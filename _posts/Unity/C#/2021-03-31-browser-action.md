---
title:  "C# 변수" 

categories:
  -  C Sharp
tags:
  - [C# 개념]

toc: true
toc_sticky: true

date: 2021-04-08 12:10:10 +1000
last_modified_at: 
---

# 변수

> 데이터를 저장하고 사용하기 위해 배정되는 공간을 지칭하는 이름

　`유니티` 에서 `변수` 는 여러가지 상황에서 쓰이는데 , 단순하게 RPG 게임으로 생각해보자면 

　플레이어의 `이름` , `HP` , `MP` 등 다양한 `정보` 를 `저장` 하고 `사용` 되는게 변수이다 .

## 데이터 형식

<table>
    <thead style="background-color:#ffd24d">
        <tr>
            <th></th>
            <th style="color:black"> 기본 데이터 형식　　</th>
            <th style="color:black"> 복합 데이터 형식　　</th>
        </tr>
    </thead>
    <tbody style="color:#ffd24d">
        <tr>
            <td rowspan=3> 값 형식 </td>
            <td> 정수 int </td>
            <td rowspan="1.5"> 배열 array </td>
        </tr>
        <tr>
            <td> 실수 float </td>
			<td rowspan="1.5"> 구조체 struct </td>
        </tr>
        <tr>
            <td> 논리 bool </td>
        </tr>
        <tr>
            <td rowspan=2> 참조 형식 </td>
			<td> 문자열 string </td>
			<td rowspan="2"> 클래스 class </td>
        </tr>
		<tr>
            <td> 오브젝트 object </td>
        </tr>
    </tbody>
</table>

- 기본 데이터 형식 `Primitive Type`   
　정수 실수 논리 문자열 등 하나의 정보를 가지는 데이터 형식

- 복합 데이터 형식 `Complex Data Type`   
　배열 구조체 클래스 등 기본 데이터 형식, 복합 데이터 형식의 데이터들을 결합해 만든 데이터 형식

- 값 형식 `Value Type`   
　변수가 일반적인 값을 담는 데이터 형식   
　스택 메모리 영역에 데이터 저장

- 참조 형식 `Reference Type`   
　변수가 일반적인 값 대신 값이 있는 곳의 주소 값을 담는 데이터 형식   
　힙 메모리 영역에 데이터 저장

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}