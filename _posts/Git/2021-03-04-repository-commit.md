---
title:  "레포지토리 & 커밋" 

categories:
  -  Git
tags:
  - [Git, Github]

toc: true
toc_sticky: true

date: 2021-03-04
last_modified_at: 
---

<br>

# Git 을 사용하기 위한 기본 개념

- 레포지토리 『Repository』
- 커밋 『Commit』

## 레포지토리 『Repository』

　어떤 프로그램을 만드는 프로젝트를 한다고 하면 

　`프로젝트 디렉토리` 를 만들게 될 것이다 .

　프로젝트 관련된 `디렉토리`나 `파일` 들을 모두 `프로젝트 디렉토리` 안에 넣게 될 텐데

　이때 `Git` 으로 버전을 `관리` 하기 시작하면 

　원하는 시점마다 어떤 것들이 프로젝트 디렉토리 안에 있엇는지 ,  

　내용이 어떻게 변해가는지를 기록할 수 있다 .

　`Git` 이 이런 정보들을 기록하는 곳을 `레포지토리` 라고 한다 .

　**<big>.git</big>** 디렉토리가 **숨겨져 있는데** 이것이 **레포지토리** 이며  
　**버전 별 프로젝트 모습**과 **버전별 변경 사항**에 대한 **설명**이 담겨있을 것이다.
{: .notice--warning}
<br>

***

### 레포지토리 만들기
```
Git Bash 를 사용해서 레포지토리를 만들어 본다 .
```
![image](https://user-images.githubusercontent.com/50429028/109945001-2c40d480-7d1a-11eb-8d6b-8deee3267d45.png)

![image](https://user-images.githubusercontent.com/50429028/109944227-5b0a7b00-7d19-11eb-8b95-4251d26770b5.png)

```c
// MathTool 디렉토리 생성
$ mkdir MathTool 

// Linux 명령어 : 디렉토리에 있는 파일 목록을 출력
$ ls

// MathTool 디렉토리 안으로 이동
$ cd MathTool/

// git 으로 버전 관리 시작
$ git init
// 비어있는 레포지토리를 생성했음
Initialized empty Git repository in D:/Git/MathTool/.git/

// Linux 명령어 : 숨겨진 파일, 디렉토리 정보를 출력
$ ls -al

// 레포지토리 디렉토리 안으로 이동
$ cd .git

$ ls -al
```
## 커밋 『Commit』

　`프로젝트 디렉토리` 안에서 작업을 하다가

　지금 모습을 `하나의 버전`으로 `레포지토리`에 `저장` 하는 것을 `커밋` 이라고 한다 .

　그 `결과물` 또한 `커밋` 이라고 한다. 

<br>

***

### 커밋 하기
```
Git Bash 를 사용해서 커밋을 해본다 .
```
![image](https://user-images.githubusercontent.com/50429028/109948162-66f83c00-7d1d-11eb-9249-cc4d0609e201.png)
```
간단하게 덧셈, 뺄셈을 정의한 calculator.py 를 MathTool/ 디렉토리 안에 저장한다 .
너무나도 단순하기에 Free License 파일을 만들어 , MathTool/ 디렉토리 안에 저장했다 .
```
![image](https://user-images.githubusercontent.com/50429028/109947484-b2f6b100-7d1c-11eb-8236-a6f4504764cb.png)
```c
// 상위 디렉토리로 이동
$ cd ..

// calculator.py, License 파일이 출력된 것을 확인
$ ls -al

// 깃 커밋을 진행 - 실패
$ git commit -m "Create calculator.py and License"
// Untracked files : - 버전 관리의 대상이 아님 .
// git add 명령어를 통해 커밋할 파일을 지정해 주어야 함 .
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        License
        calculator.py

$ git add calculator.py
$ git add License

// 깃 커밋을 진행 - 성공
$ git commit -m "Create calculator.py and License"
```

<br>

***
개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}