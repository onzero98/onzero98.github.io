---
title:  "Minimal Mistake 에서 Utterances 댓글 기능 추가하는 방법" 
excerpt: ""

categories:
  - Blog
tags:
  - [Blog, jekyll, Github, minimal-mistake, Utterances]

toc: true
toc_sticky: true
 
date: 2021-03-11
last_modified_at:
---

---
<br>

# Utterances

> Github Issue 기반의 댓글 서비스

　사용자가 지정한 `repo` 에 `issue` 로 댓글이 등록되는 방식으로 작동하는데 .

　아무리 구글을 찾아봐도 내가 적용한 `jekyll 테마` 인 `Minimal Mistake` 에서랑은 다르게 적용할 뿐이었다 ... .

　여러 시행착오를 겪으면서 적용한 방법을 블로그에 남겨둡니다 .

## Repo 만들기

![image](https://user-images.githubusercontent.com/50429028/110726109-343dce80-825c-11eb-849b-46348d73c3a6.png)

　블로그 댓글이 저장될 `repo` 를 하나 만든다.    

　다른 사람들이 접근 가능하도록 무조건 `public` 으로 만들어줘야 한다.   

## Utterances app 설치

![image](https://user-images.githubusercontent.com/50429028/110726386-a0203700-825c-11eb-8406-a0fd43fad1cb.png)

　[https://github.com/apps/utterances][githublink1] 에서 install 한 뒤

　All repositories 가 아닌, `Only select repositories` 로

　방금 만든 `blog-comment` repo 의 권한을 준다 .

[githublink1]: https://github.com/apps/utterances

## _config.yml 수정

![image](https://user-images.githubusercontent.com/50429028/110726866-89c6ab00-825d-11eb-874e-4946acc2a10b.png)

　`provider` 를 `Utterances` 로 설정한다 .

　맨 아래로 내려서 values : comments 를 `true` 로 설정해준다 .

![image](https://user-images.githubusercontent.com/50429028/110726973-bf6b9400-825d-11eb-862b-ef182d5d0f3e.png)


## utterances.html 수정

　이 부분이 진짜 아무리 구글링을 해도 다른 블로그들이랑은 전혀 달랐다 .

　`_layouts` 의 `post.html` 를 수정한다거나 ... .

　`Minimal Mistake` 의 버전 차이(?) 인가 싶기도 하고 ... .

　아무튼 우리는 `_includes/comments-providers` 폴더 내에 `utterances.html` 파일을 수정해준다.

```html
<script>
  'use strict';

  (function() {
    var commentContainer = document.querySelector('#utterances-comments');

    if (!commentContainer) {
      return;
    }

    var script = document.createElement('script');
    script.setAttribute('src', 'https://utteranc.es/client.js');
    // script.setAttribute('repo', '{{ site.repository }}');
    script.setAttribute('repo', '아이디/blog-comment');
    script.setAttribute('issue-term', 'title');
    script.setAttribute('theme', '{{ site.comments.utterances.theme | default: "github-light" }}');
    script.setAttribute('crossorigin', 'anonymous');

    commentContainer.appendChild(script);
  })();
</script>
```

　위에서 한대로 따라했다면 `'repo'` 의 값을 자신의 `아이디 / blog-comment` 를 파라미터로 주면 끝이다 .

　`테마`, `이슈 맵핑` 등의 설정값들에 대해 자세히 알고 싶다면 이곳으로 [utteranc.es][githublink2]

[githublink2]: https://utteranc.es/ 

## 끝

　`로컬` 에서는 확인이 `불가능` 하니 , git push 해주고 

　블로그에 접속해보면 comment 칸이 생겼을 것이다 !

## 번외. resize

　만약 포스팅 레이아웃이 넓어서 Utterances 댓글 기능의 사이즈가 마음에 안든다면

　`assets/css/main.css` 파일을 열고 아래 코드를 붙여넣어주면 사이즈가 딱 맞게 설정될 것이다 .
```
// comment resize
.utterances {
    max-width: 100% !important;
}
```

<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}