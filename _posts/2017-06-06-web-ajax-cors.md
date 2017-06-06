---
layout: post
title:  "[Web] CORS란?"
date:   2017-06-06 23:50:32
categories: jekyll update
category: web
---
CORS란?
-----

[CORS](https://www.w3.org/TR/cors/)를 언급하기 전, 먼저 SOP에 대해서 집고 넘어가야한다.

> #### SOP (Same Origin Policy)
 Ajax 통신을 할 때, 현재 domain(origin)에선 같은 domain만 ajax통신을 할 수 있다는 정책

SOP정책은 MS에서 XmlHttpRequest를 만들때 당연하다고 생각하고 만들었으나, 현재로썬 가장 큰 걸림돌이 되었다고 한다. (openAPI등..)


시간이 흘러, CrossDomain끼리.. 통신을 할 수 있는 방법을 만들었는데 그것이 CORS(Cross-Origin Resource Sharing)이다. 사람들은 다양한 편법으로 CrossDomain을 해왔지만...(하나의 예로, JSONP)

CORS를 간단히 말하자면, 서버가 허락한다면 CrossDomain이라도 통신을 할 수 있다 라는 것이다.

그 허락은 클라이언트 측에선 특별히 할건 없고, 서버측에서 Access-Control-Allow-"" header로 허용하는 client를 기재하면 된다.

~~~~
response.header("Access-Control-Allow-Origin" , "*") //모든 client 접근 허용
response.header("Access-Control-Allow-Origin" , "Cross domain") // 특정 domain의 접근 허용
~~~~
