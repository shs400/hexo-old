---
title: javascript - clouser(클로저)
date: 2017-12-29 11:04:32
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

clouser(클로저)
<!-- excerpt -->

~~~javascript
function outerFunc() {
   var name = 'SIM';
   
   return function(){
       console.log('My name is '+name);
   }
}

var myName = outerFunc();
myName(); // My name is SIM 
~~~

outerFunc 함수는 함수 내부에 name 지역 변수를 가지고 있고,
return 값으로 익명함수(inner함수라고 생각하자)를 가지고 있다.

아래에서 선언해준 myName 변수에 outerFunc()를 저장한다는 것은
myName은 outerFunc 함수의 return 값인 익명함수를 저장한다는 것이다.

~~~javascript
var myName = function(){
    console.log('My name is '+name);
};
~~~

myName 에는 함수가 담겨있으므로 실행이 가능하고
myName()을 호출하면 'My name is SIM' 라는 문자열이 console.log로 인해 출력된다.
 
여기서 이상한점은 

~~~javascript
var myName = function(){
    console.log('My name is '+name);
};

myName(); // My name is SIM 
~~~

이부분에서 myName을 호출할때 익명함수 안의
console.log('My name is '+name) 의 name은 어디에도 존재하지 않는다.
그렇다면 당연히 not defined 에러가 나야하지만 
실행해보면
'My name is SIM' 을 출력할 것이다.
이것이 Clouser(클로저)이다.

외부함수안의 내부함수를 호출할 때 이미 종료된 외부함수의 환경을 기억하여 사용한다.
즉, outerFunc 함수안의 내부함수(위의 예시의 익명함수)를 호출할 때 
이미 호출되고 종료되어 접근 할 수 없는 outerFunc 함수의 환경을 기억해 
name 값을 사용하는 것이다.