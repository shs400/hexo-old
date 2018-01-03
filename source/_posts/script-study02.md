---
title: javascript - this 바인딩
date: 2018-01-02 15:54:29
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

this 바인딩
<!-- excerpt -->

this 바인딩은 기본적으로 3가지 유형이 있다.
this는 함수가 호출되는 패턴에 따라 this가 어디에 바인딩 되는지 결정된다.

1. 전역함수를 호출할 떄 
~~~javascript
var global = 'global'
function Func(){
    var global = 'local'
    console.log('this.global : ',this.global);
    console.log('this : ',this);
}

Func();
// global
// window
~~~
2. 함수가 객체의 속성이고 해당 객체를 통해 함수를 호출할 때
~~~javascript
var obj = {
    func : function(){
        console.log(this);
    }
}
obj.func();
// object ( obj 객체 )
~~~
3. 생성자 함수(new)를 호출할 때 
~~~javascript
var Person = function(name){
    this.name = name || 'empty'
}

var sim = new Person('sim');
console.log(sim.name);
~~~
이외의 방법으로 call(),apply(), bind() 메서드가 존재한다. 

