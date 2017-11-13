---
layout: post
title:  '[jekyll] Category setting'
date:   2017-11-13 23:04:30
category: jekyll
comments : true
---
Jekyll - category setting
---------

* 각 post의 category 별로 게시판 생성


1. post할 글에는 아래와 같이 category를 추가해준다. (원하는 category)
~~~~
  ---
  layout: post
  title:  'TITLE'
  date:   2017-11-13 23:04:30
  category: jekyll
  ---
~~~~

2. category폴더 생성 후 category이름으로 html파일 생성(category/CATEGORY_NAME.html)

3. CATEGORY_NAME.html 코드
~~~~
  ---
  layout: category
  title: Git
  category: git
  ---
~~~~

4. _layouts 폴더엔 category.html 을 생성한다. (각category 클릭시 layout이 된다.)
5. category.html 코드는 custom 하게 만들기
~~~~
  ---
  layout: page
  ---
  {% for post in site.categories[page.category] %}
      <a href="{{ post.url | absolute_url }}">
        <h3 class='post-title'>{{ post.title }}</h3>
      </a>
      <p class='post-date'>{{ post.date | date_to_string }}</p>
  {% endfor %}
~~~~

  - 완성
  ![makecategory](makecategory.png)
