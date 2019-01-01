---
layout: post
title:  "jekyll로 github.io 블로그 만들기 - 1"
date:   2019-01-01 22:06:00 +0900
categories: blog
---

## 1. gihub.io repository 세팅하기
***
&nbsp;  
기본적으로 [github.io](https://pages.github.com/) 페이지의 설명을 따라 세팅하면 된다.  
&nbsp;
### 1) [git-scm](https://git-scm.com/)에서 git을 설치한다.
![git-scm.png](/images/git-scm.PNG)
설치를 하다보면 여러 설정들을 하는 체크박스들이 있는데 기본 설정으로 해도 무관한 듯 싶다. 개발자의 경우 개행문자에 대한 세팅 정도를 신경 써주면 좋을 것 같다.  
&nbsp;  
### 2) git repository 세팅
![repo-create](/images/repo_create.PNG)
github 계정이 없는 경우엔 가입을 하고나서 New Repository 버튼을 이용해 Repository 생성 화면으로 넘어 온다.

Repository 이름은 다음과 같은 포맷으로 작성해 준다.   

    ``` {USER_NAME}.github.io ```  

나의 경우 lemonclown.github.io 가 되겠다. 꼭 자신의 user 이름을 사용하지 않아도 이용하는데는 무리가 없는 것 같다.

마지막 체크박스엔 README 초기화 체크박스는 체크하지 않는다. 여기서는 ruby, gem 을 이용해 jekyll을 먼저 세팅 후에 push할 예정이기 때문이다.
