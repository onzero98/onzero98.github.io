---
title:  "커밋 다루기" 

categories:
  -  Git
tags:
  - [Git, Github]

toc: true
toc_sticky: true

date: 2021-03-06
last_modified_at: 
---

<br>

# 🔔 커밋

- 커밋 히스토리 
- 커밋 수정
- 두 커밋 비교
- HEAD의 의미
<<<<<<< HEAD
- Git Reset
=======
- git reset
>>>>>>> 793b04af077c63ec8b0e02ab64048725d2b8e5ad

## 커밋 히스토리
```bash
여태까지 커밋한 기록들을 확인 하는 명령어는 
$ git log 이다.
```
　`git log` 를 하면 자신이 여태까지 커밋한 로그들이 나오는데 

　`commit 3782fbef02fcceabf0989691a30b620495b7ced9` 라고 되어있는게 `커밋 아이디` 이다. 

　`git show` 커맨드로 해당 `아이디`의 `앞자리 4 개` 를 입력 하면 해당 `커밋`을 `확인` 할 수 있다 .

　이때 `Author` 나 `Date` 등의 값이 `필요하지 않다` 면 `--pretty=oneline` 옵션을 붙여주면   

　커밋을 `한줄로` 더 `깔끔하게` 받아 볼 수 있다 .
### Alias 로 history 커맨드 만들기
```bash
git config alias.history 'log --pretty=oneline'
```
　이렇게 쓰고 실행하면 앞으로 `git history` 라고만 써도 `log --pretty=oneline` 을 실행하게 된다 .

　코드를 간결하게 줄일 수 있어서 편하다 .

## 커밋 수정

> 새로 커밋을 만들지 않고, 가장 최신의 커밋을 수정 .
```bash
$ git commit --amend
```

　코드를 수정하고, `git add .` 를 한 뒤 `git commit` 할 때 사용하는 커맨드로

　`git commit --amend` 를 실행하면 새로운 커밋을 만드는게 아닌 가장 `최신의 커밋을 수정` 한다 .

　그래도 `커밋 아이디`는 `바뀌게` 되니 `주의`하자 .

## 두 커밋 비교

> 커밋들간에 무엇이 바뀌게 되었는지 파악 .
```bash
$ git diff f0d3 3782
```

　`비교` 하고자 하는 `커밋 아이디` 의 앞자리 `4개` 를 입력하면 두 커밋간의 `차이` 가 무엇인지 `확인` 할 수 있다 .   

## HEAD

> 보통 `가장 최근에 한 커밋` 을 가리킴 . 

　매번 더 `새로운 커밋` 을 `기본적으로` 가리킨다 . 

　`$ cat fileName` 으로 파일들을 열어보면 가장 `최신에 커밋한` 파일들을 볼 수 있는데.   

　`HEAD` 가 그 `이전의 커밋` 을 가리키게 된다면 `과거 커밋의 파일` 을 볼 수 있다 .

　`즉` `HEAD` 가 가리키는 커밋에 따라 `working directory` 가 구성 되는 것이다 .

## Git Reset

> 과거 커밋으로 아예 돌아가고 싶을 때 사용 .

```bash
$ git reset --hard 원하는 위치
```

　원하는 위치의 `커밋 아이디` 를 적으면 `그 시점의 커밋` 으로 아예 돌아가 버린다 .

　만약 다시 `복구` 하고 싶다면 

```bash
$ git reflog
```

　`git reflog` 커맨드를 통해 `이전 커밋 내역` 과 `커밋 아이디` 를 확인 후 똑같이 `git reset` 으로 복구 할 수 있다 .

<br>

***
개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}