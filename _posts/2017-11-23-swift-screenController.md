---
layout: post
title:  '[swift] Screen transition'
date:   2017-11-13 23:45:30
category: swift
comments : true
---
Swift - Screen transition (화면전환)
---------


>1. ViewController의 View 위에 다른 View를 가져와 바꾸고 전환
>2. ViewController에서 다른 ViewController를 호출하여 화면 전환
>3. Navigation controller를 이용하여 화면 전환
>4. 화면 전환용 객체 Segueway를 사용하여 전환



1. View를 교체하는 방법은 1개의 ViewController가 2개의 view를 관리해야되어 지양해야 할 것

2. 아래와 같이 전환할 수 있으며, Storyboard ID는 아래 항목에서 설정해준다.
 ```swift
let storyboardInstance = self.storyboard?.instantiateViewController(withIdentifier: "Storyboard ID")
storyboardInstance?.modalTransitionStyle = UIModalTransitionStyle.flipHorizontal
self.present(storyboardInstance!, animated: true, completion: nil)
 ```
 ![swift-screenController]({{site.url}}/2017-11-23-swift-screenController.png)

3. Navigation controller를 이용하여 화면 전환
 - 각 NavigationController를 연결시킨다. (StoryBoard에서 화살표로) => 사이트 [참조](http://blog.naver.com/PostView.nhn?blogId=baek2304&logNo=220885876605&parentCategoryNo=68&categoryNo=&viewDate=&isShowPopularPosts=true&from=search)

4. SegueWay를 사용하는 방법 - Data도 보낼 수 있음
 - 먼저 아래와 같은 코드를 구현하고 보내고 싶은 자료를 아래와 같이 set 한다.
 ```swift
  override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
        if segue.identifier == "startPageSegue" {
            let mainPage = segue.destination as! mainPage
            mainPage.startAnniversary = datePicker // dataPicker 를 보내고 싶어!
        }
      }
```
 - performSegue method를 통해 전송
 ```swift
    self.performSegue(withIdentifier: "startPageSegue", sender: nil)
 ```
 - 아래 그림과 같이 widthIdentifier에 들어갈 parameter를 설정해놓으면, SegueWay를 통해 화면 전환이 가능하다.

 ![swift-screenController2]({{site.url}}/2017-11-23-swift-screenController2.png)
 ![swift-screenController3]({{site.url}}/2017-11-23-swift-screenController3.png)
