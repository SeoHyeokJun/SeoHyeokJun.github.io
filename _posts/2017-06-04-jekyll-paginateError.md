---
layout: post
title:  '[jekyll] Paginate 적용후 Dependency error'
date:   2017-06-04 23:05:47
categories: jekyll
category: jekyll
comments : true
---
Paginate적용과정에서의 Dependency Error
-----

> _config.yml 파일 gems에 jekyll-paginate 를 추가후 paginate변수를 사용하려 했으나, jekyll serve를 실행하면 아래와 같은 에러 발생

~~~~
Junui-MacBook-Pro:username.github.io jun$ jekyll serve
Configuration file: /Users/jun/blog/username.github.io/_config.yml
Configuration file: /Users/jun/blog/username.github.io/_config.yml
  Dependency Error: Yikes! It looks like you don't have jekyll-paginate or one of its dependencies installed. In order to use Jekyll as currently configured, you'll need to install this gem. The full error message from Ruby is: 'cannot load such file -- jekyll-paginate' If you run into trouble, you can find helpful resources at https://jekyllrb.com/help/!
~~~~

#### 해결
- jekyll-paginate가 설치되어 있지 않아서 설치
~~~
$ Junui-MacBook-Pro:SeoHyeokJun.github.io jun$ gem install jekyll-paginate
 Successfully installed jekyll-paginate-1.1.0
 Parsing documentation for jekyll-paginate-1.1.0
 Done installing documentation for jekyll-paginate after 0 seconds
 1 gem installed
~~~
- 설치후 Gemfile에 jekyll-pagenate과 version입력
- jekyll serve 정상작동
