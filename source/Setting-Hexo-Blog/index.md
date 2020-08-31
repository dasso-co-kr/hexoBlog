---
title: setting hexoBlog
date: 2020-08-31 09:09:17
---
1. hexo setting을 위한 준비

nodejs 설치
ref) https://nodejs.org/ko/download/

git 설치
ref) https://git-scm.com/
(설치 옵션은 모두 default로 가져가고, 편의상 cmd 깃을 사용합니다.)

2. github settings

 기본적으로 repository 2개를 생성합니다.
(하나는 코드용, 하나는 github 페이지용)
github 페이지용 리파지토리 네임은 dasso-co-kr.github.io
처럼 만들어줍니다. (dasso-co-kr 은 본인 아이디로)

github에서 적당한 프로젝트를 clone 합니다.

(해당 부분은 정확한지 기억이 안나지만, 아래와 같이 진행했던 것 같습니다.)

윈도우 탐색기에서 clone 받은 프로젝트의 .git 관련 폴더들을 모두 삭제해줘서, 
리파지토리를 끊습니다.

---

cf) 깃 관련 명령어들
1 로컬에 프로젝트를 만든다.
2  git init : 해당 프로젝트 디렉터리에서 이닛을 한다.
3  git config (--global) user.name "내이름"
    git config (--global) user.email "내 이메일"
// 글로벌은 전역이고 안하면 그냥 개별임.
4  git remote add origin remoteRepo의 주소(" 쌍따옴표는 넣지 않는다.)
5  git push -u origin master : 처음 푸시할 경우 -u 라는 옵션을 넣어주어야 하는 듯 하다.

6 git add . (. 이라는 옵션은 전체다 스테이징 하겠다는 뜻인 듯)
7 git commit -m "커밋 메세지 넣기"
8 git push origin master : 리모트에 푸시하기.

---

cmd에서 npm 명령어로 hexo를 설치합니다. 

npm i -g hexo-cli

npm i

theme 설정 관련해서는 저는 아래의 book theme를 적용했습니다.

ref) https://github.com/kaiiiz/hexo-theme-book

위의 사이트에서 시키는 데로 진행하면 테마에 대한 기본적인 셋팅이 됩니다.

( 
    cmd에서 theme 폴더에 적용할 테마의 폴더로 가서 npm i 를 해주고,
    theme 변경시마다 변경할 테마 폴더로 진입하여 해당 명령어를 실행해주어야 합니다.
    ex) cd themes/transquilpeak && npm run build
)

최상단의 _config.yml 에 아래와 같은 셋팅들을 해줍니다.

'# Site
title: Dasso Blog
subtitle: 
description: 
keywords:
author: Dasso
language: en
timezone:

url: https://dasso-co-kr.github.io
(본인의 github page 주소)

deploy:
  type: git
  repo: https://github.com/dasso-co-kr/dasso-co-kr.github.io
(배포될 github 페이지 경로)

'# Search Generator 
search:
    path: search.xml
    field: post
(검색관련 셋팅인데 현재는 적용이 안되어 있습니다.)

---

cf) hexo 관련 명령어들

아래는 hexo 의 공식 reference 사이트로 hexo 관련 정보들이 망라되어 있습니다. 
ref) https://hexo.io/ko/docs/

cmd에서 블로그 폴더로 진입한 뒤 

(아래의 절차 중 일부는 불필요할 수 있으나, 제가 다음과 같은 절차를 밟았습니다.)

hexo init 으로 hexo 폴더를 init 해줍니다.


hexo new page(post/draft) title
(위의 명령어를 치면 새로운 폴더와 index.md 등이 생성됩니다.)

hexo generate
(정적 파일들이 생성 된답니다.)

hexo server
(로컬 서버로 돌립니다.)

hexo deploy -g
(github 페이지로 배포를 하는데, -g 옵션은 Deploy 하기 전에 generate를 수행합니다.)

---

이제 마크다운 문법에 맞게 글을 작성해주면 됩니다..



