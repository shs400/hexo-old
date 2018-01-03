---
title: Git에 Hexo 블로그를 적용해보자! (3)
date: 2017-04-24 15:44:15
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
coverImage: ../../../../images/img.jpg
comments: true
meta: false
actions: false
---

Hexo를 사용하여 git과 연동한 후 블로그를 만들어보자! (3)
<!-- excerpt -->

2장까지는 본인의 Local에 Hexo 블로그를 설치해보았다.
이번장에는 본인의 Git repository에 배포하는 방법을 알아보자.

먼저 github에 deploy 해줄 플러그인을 설치해준다.
※ deploy란 배포를 뜻한다.
``` bash
$ npm install --save hexo-deployer-git
```

설치가 끝난 뒤 Hexo 설정파일 _config.yml에서 아래의 내용을 수정한다.
``` bash
# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: https://shs400.github.io  // https://깃허브계정명.github.io
root: / 
permalink: :year/:month/:day/:title/ 
permalink_defaults:
```
그리고 
``` bash
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repository: https://github.com/본인계정명/본인계정명.github.io.git  // 본인의 Github repository
  branch: master
```

두 부분을 수정한 후 
Github에 만든 blog파일을 deploy해주면 배포가 완료되는데
``` bash
$ hexo clean        #빌드된 public을 삭제한다. (처음에 한번만 해도된다.)
$ hexo generate     #빌드해준다.
$ hexo deploy       #기본 명령어 - 배포
$ hexo d            #축약형 명령어
```
위와 같이 기존 빌드된 내용을 clean(삭제)해주고
generate(빌드)하고난 뒤에 deploy(배포)를 하게되면
Github master에 배포가 되게된다.

배포가 완료되었다면
본인의 https://깃허브계정명.github.io url로 접속하면 블로그가 적용된것을 볼 수 있을것이다.

참고로 필자는 빌드와 배포를 동시에 하기위해 옵션으로 -g를 사용한다. 
``` bash
$ hexo deploy -g    #빌드하고 배포한다.  -g는 generate옵션
```