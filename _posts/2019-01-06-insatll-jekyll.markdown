---
layout: post
title:  "jekyll로 github.io 블로그 만들기 - 2"
date:   2019-01-06 18:10:00 +0900
categories: blog
---

## 2. Insatlling jekyll(jekyll 설치하기)   
***
&nbsp;   
[jekyll 공식사이트](https://jekyllrb.com/docs/)를 참고해서 진행하면 설치를 진행할 수 있다. 우선 상단 메뉴중 [DOCS](https://jekyllrb.com/docs/)를 통해 설치하는 방법을 볼 수 있다.   
![jekyll_quick_guide](/images/jekyll_quick_guide.PNG)    
우선 jekyll를 설치하기 위헤서는 Ruby와 Gem설치가 필수적이다. Insturctions의 첫번째 [Ruby development environment](https://jekyllrb.com/docs/installation/)를 클릭하면 Ruby와 RubyGems을 설치해준다.    
- [Ruby 설치경로](https://www.ruby-lang.org/en/downloads/)    
- [RubyGems 설치경로](https://rubygems.org/pages/download)    

&nbsp;    
Ruby의 경우 인스톨러로 설치하기 때문에 그대로 다음을 클릭하여 진행할 수 있다. RubyGems의 경우 몇가지 방법이 제시되어 있으나 기 설치된 Gems가 없는 경우엔 소스코드를 받아 Ruby를 통해 설치해야한다. zip이나 tgz의 압축파일 형태를 다운로드 받은 후 압축을 풀면 setup.rb가 있다. 이를 ruby를 통해 실행하면 설치가 진행된다.    
&nbsp;     
![ruby_gems](/images/ruby_gems.PNG)    
``` 
$ ruby setup.rb 
```

***
***    
&nbsp;    
# 명령어가 없다고 나오는 경우
윈도우즈의 경우 환경변수 중 PATH에 등록이 되어있어야 커맨드라인에서 바로 실행 시킬 수 있다. 이를 해결하기 위해서는 두가지 방법이 있는데    
1. 직접 실행 경로를 잡아서 실행하기
    ```
    $ C:\Ruby25-x64\bin\ruby setup.rb
    ```
2. PATH에 등록후 실행하기
    - 내 PC > 화면에서 우클릭 > 속성 > 고급 시스템 설정 > 고급(탭) > 환경 변수 > 시스템 변수 중 Path 편집 > 새로 만들기 > ruby 경로 추가    
&nbsp;    

***
***
&nbsp;    

여기까지하면 [DOCS](https://jekyllrb.com/docs/)의 1.이 끝나고 jekyll을 설치 할 수 있다. 2번 명령어를 통해 jekyll을 설치한다.    
```
$ gem install jekyll bundler
```
모든 과정이 완료되고 나면 jekyll을 이용해 blog를 만들어 볼 수 있다.
```
$ jekyll new myblog
```
여기서 myblog는 원하는 이름을 사용하면 된다. 보통 git을 사용하는 경우 repository의 이름과 디렉토리의 이름을 같게 하기 때문에 맞춰주는 것도 좋다.   
만약 이미 git 설정이 되어 있는 디렉토리에 설정한다면 해당 디렉토리 이름을 넣어 실행하면 해당 디렉토리로 jekyll 설정이 완료된다.

해당 디렉토리를 확인해보면 jekyll의 기본 설정이 완료 된 것을 확인할 수 있다.
![jekyll_setting](/images/jekyll_setting.PNG)    

이제 다음 명령어를 통해 blog 서버를 띄워보도록 한다.
```
$ jekyll serve
```
![jekyll_serve](/images/jekyll_serve.PNG)

위 처럼 출력이 된다면 정상적으로 작동한 것이다. 위 설명에 따라 [http://127.0.0.1:4000/](http://127.0.0.1:4000/)으로 접속하면 jekyll 블로그가 정상 로드 된 것을 확인 할 수 있다.    
다만 이 페이지는 자신의 컴퓨터에서만 동작하는 것이기에 외부에서는 보이지 않는다.

다음으로 실제로 github.io에서 확인할 수 있도록 git을 설정 후 push 해야한다. 그래야 blog를 외부에서도 확인 할 수 있다.    
1. jekyll을 설정한 디렉토리로 이동한다.
2. git 최초 설정을 한다.
```
$ git init
```
git을 완전 처음 하는 경우라면 git 설정도 필요할 수 있다.
```
$ git config --global user.email "{email}"
$ git config --global user.name "{user name}"
```
3. 해당 디렉토리를 추가한다.
```
$ git add .
```
. 은 전체를 의미한다.
4. 내용을 commit 한다.
```
$ git commit -m "{commit message}"
```
'-m'은 메세지를 바로 입력하겠다는 의미이다. commit은 변경 내역을 저장하는 과정으로 commit message에는 어떤 변경 사항이 추가 되었는지 적어 주면 좋다.
```
$ git commit -m "jekyll init"
```
5. 다시 자신의 Repository로 가보면 remote repository 추가 명령어를 할 수 있다.
![git_repo_init](/images/git_repo_init.PNG)
디렉토리에서 설정후 push 하는 경우이기 때문에 첫번째 블럭을 따르면 된다. 현재 commit 까지 완료 되었으므로 4번째 명령어를 실행한다.
```
git remote add origin https://github.com/lemonclown/lemonclown.github.io.git
```
주소의 경우 각자에 맞게 적용하면 된다.
6. 마지막 명령어를 통해 push 한다.
```
git push -u origin master
```

해당 push가 완료 되었는지 github에서 확인 후 정상적으로 push가 되었다면 각 repository이름으로 확인할 수 있다.

예) [https://lemonclown.github.io](https://lemonclown.github.io)

