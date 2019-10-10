---
layout: post
title: 'GitHub Page 만들기'
date: 2019-10-09 11:00
categories: blog
---

소스 관리를 위해서 깃허브를 사용합니다. 관리보다는 여러 장비와 위치에서 소스 공유를 위해서 사용해봤습니다.
블로그는 다른 플랫폼들, 예를들어 티스토리, 브런치를 이용해 본 적이 있습니다.
깃허브에서 제공하는 깃허브 페이지를 만드는데 어려움이 없을 것으로 예상하고 일단 만들어 봅니다.
[GitHub Page](https://pages.github.com/)와 [Jekyll](https://jekyllrb-ko.github.io/) 사이트를 찾아다니면서 시작합니다.
아래는 설치하고 그때 그때 생긴 생각을 정리한 내용입니다. 한번에 깔끔한 설치는 가장 아래 깔끔한 정리를 참고하세요.

# GitHub Page 만들기
깃허브에서 블로그 페이지를 제공한다.

깃허브는 소스관리 도구이다. 개발자들에게 필요한 도구다. 개발을 하면 소스를 복사해서 붙여넣는 기능을 많이 사용한다. 직접 키보드로 타이핑하는 것보다 동작하고 있는 코드를 복사해서 붙여 넣는 방법을 좋아한다. 문서를 작성할 때도 원본 내용을 복사해서 사용할 수 있는 일반 에디터를 좋아한다. 에버노트가 인기있던 이유이기도 하다.

몇가지 장점이 있다.
* 깃허브의 레포지터리를 이용한다. - {username}.github.io
* markdown(.md) 파일을 _posts에 올리면 블로그에 보여준다.

물론 불편한 점도 있다. 
* 문서의 원본파일이 그대로 공개된다. - 블로그 파일 전체를 복사해서 가져올 수 있다.(깃허브의 장점이긴 하다)
* 깃허브 사이트를 이용할 수도 있으나 일반적으로 git 을 사용해야 한다. - 일반 블로그보다 어렵다
* markdown 파일로 작성하므로 문서 디자인에 한계가 있다.

알아야할 내용
* GitHub Pages
* Jekyll - ruby, wsl(windows 10)
* Markdown

## GitHub page 설치
* GitHub Page 설정 - https://pages.github.com/
  - {username}.github.io 레로지토리 생성
  - public repository
  - GitHub Page로 지정 - master branch
  - index.html 파일을 올려서 동작 확인
* jekyll-new 레포지토리 복사(클론)
  - _config.yml 수정
* 블로그 작성
  - _posts 폴더에 .md 파일 작성 
* Jekyll Theme 적용 - [GitHub page의 지킬 설명 참고][Setting-up-a-GitHub-Pages-site-with-Jekyll]
  - GitHub의 github.io 레포지토리에서 Theme를 midnight로 설정
    - _config.yml을 깃헙에서 자동으로 변경함
    - 깃허브 페이지 화면이 나오지 않음. - 이렇게 테마 변경하면 잘 안되는 듯
  - 작성 중

## 깔끔한 설치
사이트 링크를 보고 블로그를 만들지 못해서 정말 쉽게 만드는 방법을 정리했다는 [회복맨님 블로그][recoveryman-blog]를 참고합니다.
Jekyll Theme을 수정하여 나만의 블로그를 만드는 방법은 [디자이너도 만드는 Jekyll Blog - 3편](http://jihyeleee.com/blog/third-designer-can-make-jekyll-blog/) 블로그를 참고해 보세요. 

* git 설치
  - 사용자 등록
  - [질문] git bash와 WSL은 다른 건가? - 
* GitHub 등록
* JeyKyll Theme
  - [지킬 테마](http://jekyllthemes.org/)
  - 선택장애로 테마 고르는게 ~~어려워요.~~ 시간이 오래 걸려요.
    - 원하는 기능같은 항목을 정리하면하면 도움이 됩니다.
    - 디자인 - 원페이지, 두단, 3단, 색상
    - 기능 - 카테고리, 포스팅날짜, 
  - [추천 테마] (https://isme2n.github.io/devlog/2017/03/09/Blog-Jekyll-theme/)
    - [Jasper2]() 선택 - Jasper를 추천하는데, 최근에 Jasper2가 나왔음.
    - GitHub에서 plugin을 지원하지 않으므로 로컬에서 빌드해서 _site/ 폴더를 올려야 함
  - Jastper2를 clone해서 godsman-yang.github.io 에 올렸음
    - CSS, JS가 정상적으로 동작하지 않아서 화면이 파란글씨로 디자인이 맞지 않게 나옴
    - 개발자도구에서 오류가 난 부분을 확인합니다.
    - _config.yml 에서 baseurl: /jasper2/ 에서 jasper2/를 지우고 / 로 변경합니다.
      - 화면이 제대로 나오고 오류가 3개로 줄어들었습니다.
      - uncaught ReferenceError: Prism is not defined at prism-abap.min.js:1
        - 해결안됨.
        - About 페이지 깨짐 발생 -> local build 진행
      - GET https://godsman-yang.github.ioassets/images/favicon.png net::ERR_NAME_NOT_RESOLVED
        - _config.yml 에 url: 이 없었음. url: https://godsman-yang.github.io/ 추가 후 해결됨
    - local build
      - bundle install --path ./vendor/bundle
      - bundle exec jekyll serve
        - local 에서는 about 페이지 깨지지 않음.
  - About page가 깨지는 형태로 일단 운영
    [Jasper2](https://github.com/jekyller/jasper2/watchers) 깃허브에 이슈로 등록
* 블로그 올리기
  - _posts 폴더 아래에 md 파일 업로드
  - YYYY-MM-DD-title.md 파일 작성

## 추가 정보
* 윈도우에 jekyll 설치하기
  - jekyll을 설치하려면 ruby가 필요한데 윈도우즈는 공식적으로 지원하지 않음. rubyinstaller 이용하거나 WSL을 이용
  - rubyinstaller 이용
  - windows 10에서 지원하는 wsl 이용 - 개발자라면 - https://docs.microsoft.com/ko-kr/windows/wsl/wsl2-install
    - powershell 명령어 실행 - 관리자모드, 재부팅
    - wsl ubuntu 설치
    - wsl 2로 업그레이드 하려고 했으나 현재 지원 안함 - insider에서 지원 
  - windows 10 wsl에서 설치 [Installation via Bash on Windows 10][Installation-via-Bash-on-Windows-10]
    - ruby2.5와 ruby2.5-dev 설치 - 현재 2.6까지 나와있음
  - windows 10 wsl에서 설치(rvm 이용) https://scottdorman.blog/2019/02/27/running-jekyll-on-wsl/ 
    - rvm 설치 -> ruby 설치(2.6.3)

[recoveryman-blog]: https://recoveryman.tistory.com/321?category=6357
[Setting-up-a-GitHub-Pages-site-with-Jekyll]: https://help.github.com/en/articles/setting-up-a-github-pages-site-with-jekyll
[Installation-via-Bash-on-Windows-10]: https://jekyllrb.com/docs/installation/windows/#installation-via-bash-on-windows-10