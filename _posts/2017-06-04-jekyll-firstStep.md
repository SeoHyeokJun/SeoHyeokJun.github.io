---
layout: post
title:  "[jekyll] install, git 기본세팅 (first steps)!"
date:   2017-06-04 23:04:30
categories: jekyll update
category: jekyll
---
Jekyll
---------
>공부한 내용을 정리하기 위해 블로그를 이용하기 위해 여러가지 블로그 플랫폼을 알아보는중, jekyll과 github page를 이용하여 제작된 깔끔한 블로그를 보고 매혹되어 제작하기로 결심

* jekyll 은 정적 웹사이트를 generate하는 툴
* Ruby script로 되어 있으나, 전혀 몰라도 상관 없음
* Markdown으로 작성하여 서버에 올리면 바로 포스팅 할 수 있음
* 자유롭게 나만의 형식으로 블로그를 제작할 수 있음


### 아래부턴 Jekyll 을 시작하기 위한 간단한 스텝들을 정리해 놓았다.
(mac os를 사용하므로, 모든 기준은 mac os임)

1. Jekyll 설치 (Use ruby)
~~~~
$ sudo gem install jekyll
~~~~

2. Jekyll 폴더 구성
~~~~
$ jekyll new username.github.io
~~~~
(여기서 username은 github의 개인 username을 뜻함.)

3. 위 과정을 마치면 username.github.io 이름으로 폴더가 생기는데, 해당 폴더로 이동

4. Jekyll localhost환경에서 확인 (localhost:4000)
~~~~
$ jekyll serve
~~~~

### Git 세팅
 1. Github page 만들기
  * Github main에서 New repository 클릭후 "username.github.io"의 이름으로 repository 생성

 2. jekyll 폴더에 생선된 repository로 원격저장소 등록
~~~~
$ git init
$ git remote add origin remote-repository-url
$ git add .
$ git commit -m 'message'
$ git push origin master
~~~~


* 자신의 페이지 확인하기 (username.github.io)
