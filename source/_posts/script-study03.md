---
title: javascript - call(),apply(), bind() 메서드
date: 2018-01-02 16:43:50
category:
- javascript
- blog
- study
tags:
- javascript
- blog
disqusIdentifier: shs400
keywords:
- javascript

thumbnailImagePosition: left
autoThumbnailImage: yes
metaAlignment: center
coverCaption: "A beautiful sunrise"
coverMeta: out
coverSize: partial
coverImage: ../../../../images/img.jpg
comments: true
meta: false
actions: false
---

call(),apply(), bind() 메서드
<!-- excerpt -->

앞서 설명하였던 기본적인 this 바인딩 3가지 방법 외에도
메서드를 이용하여 임의적으로 특정 객체에 바인딩 시키는 방법이 3가지 존재한다.

1) apply() 메서드
- apply은 파라미터 중 첫 번째 인자를 함수 내부에서 사용할 this로 만들어준다.
~~~javascript
var Name = function(name){
    this.name = name;
}
var objName = {}
Name.apply(objName,['sim']);
console.log(objName);
//{ name: 'sim' }
~~~

2) call() 메서드
- call은 apply와 기능은 같지만, 두번째 매개변수가 배열이 아닌 각각의 값으로 넘길 수 있다.
~~~javascript
var Name = function(name,age){
    this.name = name;
    this.age = age;
}
var objName = {}
Name.call(objName,'sim',31);
console.log(objName);
//{ name: 'sim', age: 31}
~~~

3) bind() 메서드 ※ es5 문법
- 함수가 가리키는 this만 바꾸고 호출하지는 않음.
- 새 함수를 만드는데 그 this는 bind에 전달된 값. 
~~~javascript
window.color = "red";
 var example = { color : "blue"};
 
 function colorValue() {
     console.log(this.color);
 }
colorValue();
var bindColor = colorValue.bind(example);
bindColor();
// red
// blue
~~~
colorValue 함수의 this는 window 이므로 red 가 출력되고
colorValue에 example 을 bind 해줄시 this가 example 객체를 가리키므로 
this.color 값은 blue가 된다.
