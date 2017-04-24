---
title: Git에 Hexo 블로그를 적용해보자! (2)
date: 2017-04-21 14:23:15
category:
- git
- github
- node.js
- blog
tags:
- git
- github
- node.js
- blog
disqusIdentifier: shs400
keywords:
- javascript
- hexo
thumbnailImagePosition: left
autoThumbnailImage: yes
metaAlignment: center
coverCaption: "A beautiful sunrise"
coverMeta: out
coverSize: partial
coverImage: img01.jpg
comments: true
meta: false
actions: false
---
Hexo를 사용하여 git과 연동한 후 블로그를 만들어보자! (2)
<!-- excerpt -->
Hexo를 사용하여 git과 연동한 후 블로그를 만들어보자! (2)

앞선 과정에서 git repository 등록까지 완료되었다면
이제 본격적으로 hexo를 설치해보자.

먼저
``` bash
$ npm install -g hexo-cli
```
npm을 사용하여 hexo-cli을 global( = -g )로 설치한다.
※ hexo-cli는 hexo 명령어를 사용하게 하기위한 npm 패키지이다.

``` bash
$ git clone https://github.com/shs400/shs400.github.io.git
```
1장에서 우리가 만들었던 git repository를 본인 PC에 clone 받는다.
필자는 본인의 git repository를 적어놓았다. 꼭 본인의 repository를 적도록 한다.
(clone 받을 디렉토리는 본인이 생성해주고 해당위치에 가서 clone 받아야한다.)

> ![터미널 경로](/img/hexo-install/img04.jpg )

위의 경로와 같이 자신이 만든 디렉토리(필자는 sblog)에 clone을 받으면 된다. 

``` bash
$ hexo init [folder]
$ cd [folder]
$ npm install
```
hexo를 저장할 folder에 hexo를 초기화 시켜준다.
그리고 해당 folder로 이동하여 npm install하여 기본 파일들을 설치한다.
(필자는 sblog에 git clone하였으므로 folder는 shs400.github.io.git 일것이다.)

기본적인 Setting은 마무리 되었다. 이제
``` bash
$ hexo server  #기본 명령어
$ hexo s       #축약형 명령어
```
웹 브라우저에서 localhost:4000으로 접속하면 hexo가 적용된것을 확인할 수 있다.

다음장에서는 기본적인 초기 Setting 후 본인의 github.io에
본인이 작업한 blog를 등록하는 방법을 알아보자.