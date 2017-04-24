---
title: Git에 Hexo 블로그를 적용해보자! (1)
date: 2017-04-21 10:30:52
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
Hexo를 사용하여 git과 연동한 후 블로그를 만들어보자! (1)
<!-- excerpt -->

Hexo를 사용하여 git과 연동한 후 블로그를 만들어보자! (1)

## 설치
Hexo를 사용하기 위해서는 아래의 두가지가 필요하다.
* [Node.js][nodelink]
   [nodelink]: https://nodejs.org/en/

* [git][gitlink]
   [gitlink]: https://git-scm.com/downloads
    
---

해당 링크에 접속하여 Node.js와 git을 설치하고,
가장먼저 Github repository (깃헙 저장소)를 만들어야한다.

* [Github][githublink]
   [githublink]: https://github.com/
  
---

해당 url에 접속후 github에 가입하고 로그인하면
아래와 같은 화면이 보이게된다.

![github 홈페이지 캡쳐화면](/img/hexo-install/img01.jpg )

오른쪽에 New repository 라는 초록색버튼을 클릭해준다

![github 홈페이지 캡쳐화면](/img/hexo-install/img02.jpg )

본인의 아이디와 같은 이름의 repository name을 설정해준다.
같은 이름으로 생성해 주는이유는 github.io를 사용하기 위해서이고, 
github.io는 계정당 하나만 사용할 수 있다.
(필자의 경우에는 이미 동일한 이름의 repository가 있기때문에 경고가 뜨는것이다.)

repository name을 설정하고 Create repository 버튼을 클릭하게되면

![github 홈페이지 캡쳐화면](/img/hexo-install/img03.jpg )

화면이 나오는데 먼저 터미널을 실행시킨다.
cmd 혹은 우리는 git을 설치하였기에 
git bash를 사용하자.

터미널 사용법은 따로 설명하지 않도록 한다.
해당 git을 clone할 디렉토리 하나를 생성하고 터미널에서 해당 디렉토리로 이동한 후 
``` bash
$ echo "# <본인 repository 이름>" >> README.md
$ git init
$ git add README.md
$ git commit -m "first commit"
$ git remote add origin https://github.com/shs400/ss123.git
$ git push -u origin master
```

위에서 보았던 내용을 하나하나 입력하거나, 오른쪽의 copy버튼을 클릭해서 터미널 창에 붙여넣기하면 repository가 생성된다.


