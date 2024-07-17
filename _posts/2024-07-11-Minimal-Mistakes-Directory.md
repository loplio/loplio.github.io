---
title:  "[Blog] Minimal Mistakes(Jekyll Theme)의 디렉토리 구조를 알아보자."
excerpt: ""

# classes: wide
categories:
  - Blog
tags:
  - [Blog, Jekyll, Minimal Mistakes, Markdown]

toc: true
toc_label: "List"
toc_icon: "bars"
toc_sticky: true
 
date: 2024-07-11
last_modified_at: 2024-07-11
---

<br>

# <span style="color:rgb(0, 180, 180)">Minimal Mistakes Folder</span>

|기본 폴더📁
|:-|:-|:-|:-
|`_data`|`_includes`||`_layouts`
|`_sass`|`asset`||

|생성 폴더📁
|:-
|`_posts`⭐|`_pages`

|기본 파일📜
|:-|:-
|`_config.yml`⭐||`Gemfile`
|`index.html`

## 참고자료
 <u>파일 구조</u>와 <u>내용</u>을 자세히 보고싶다면 **minimal-mistakes의 Git**을 확인해보세요!  
📌 [ Minimal-mistakes Git ](https://github.com/mmistakes/minimal-mistakes) 📌

## 1. 기본 폴더
<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">🌠 `_includes`와 `_layouts`는 파일이 많기 때문에 간략히 소개하겠습니다.</span>
</div>

### _data
테마를 꾸밀 때, 사용되는 데이터를 모은 폴더입니다.  
**파일:** `navigation.yml`, `ui-text.yml`  

#### <span style="font-size: medium;">***navigation.yml📜***</span>
-  블로그 <u>사이드 바</u> or <u>메뉴 바</u> **꾸밀** 수 있습니다.  
-  <u>main</u>은 **상단 메뉴 바**이며, 기본 형식이 적혀 있습니다.
-  docs는 제가 추가한 부분이고, 사이드 바를 넣기 위해 추가했습니다.

```yml
# main links
main:
  - title: "Home"
    url: https://my-blog-url
  - title: "Github"
    url: https://github.com/git-name

# 사이드 바를 위해 직접 작성.
docs:
  - title: C
    children:
      - title: "C Language"
        url: /categories/cpp
  - title: Other
    children:
      - title: "Blog"
        url: /categories/blog
```

#### <span style="font-size: medium;">***ui-text.yml📜***</span>
- 블로그의 <u>UI 텍스트</u>를 **수정**할 수 있습니다.
- 지원하는 모든 언어 별로 설정 가능합니다.

```yml
# Korean
# ------
ko: &DEFAULT_KO
  skip_links                 :
  skip_primary_nav           :
  skip_content               :
  skip_footer                :
  page                       : "페이지"
  pagination_previous        : "이전"
  pagination_next            : "다음"
  breadcrumb_home_label      : "Home"
  breadcrumb_separator       : "/"
  ...
```

### _includes
Include는 **재사용 가능**한 코드 조각을 저장합니다.  
즉, 페이지에서 <u>반복 사용</u>되는 **코드 블록**를 다루는 파일입니다.

```html
<!--_layouts/default.html-->
  <head>
    { % include head.html % }
    { % include head/custom.html % }
    ...
```

### _layouts
레이아웃은 <u>페이지의 형식</u>을 **담은 시트지**입니다.  
언제나 페이지를 출력할 <u>파일(html, md 등)</u>에서 어떤 시트지를 사용할 지 **결정**할 수 있죠.  

#### <span style="font-size: medium;">***default.html📜***</span>
기본 설정은 `default.html`로 설정되어 있으니, 형식을 바꾸고 싶다면 다른 html 파일 또는 직접 작성해보세요!
```
---
layout: archive
---
```

### _sass
scss파일들은 <u>모듈화된 기능</u>들을 모아둔 것 입니다.

#### <span style="font-size: medium;">***minimal-mistakes.scss📜***</span>
모듈화된 scss파일들을 <u>분류</u>하고 <u>import(불러오는)</u>하는 역활을 합니다.  

#### <span style="font-size: medium;">***mini.../skins📁***</span>
minimal-mistakes에서 제공하는 <u>스킨 설정 시트</u>들입니다.  
고르신 테마에 .scss에 들어 가시면 <u>직접 커스텀</u>이 가능합니다.  
<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">🌠 테마 색, 텍스트 색, 코드 블럭 색 등 다양한 색을 바꿀 수 있습니다! </span>
</div>

<hr>

#### <span style="font-size: medium;">***mini.../.scss📜***</span>
minimal-mistakes에서 제공되는 다양한 기능(기본 글꼴, 검색, 사이드 바 등)의 기본 설정 값을 확인해 볼 수 있습니다.

대표적으로 `.variables.scss`에서 원하는 글꼴로 바꿀 수 있습니다.  
```scss
$serif: "Nanum Gothic Coding", Georgia, Times, serif !default;
$sans-serif: "Gowun Batang", -apple-system, BlinkMacSystemFont, "Roboto", "Segoe UI",
  "Helvetica Neue", "Lucida Grande", Arial, sans-serif !default;
$monospace: Monaco, Consolas, "Lucida Console", monospace !default;
```
<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">🌠 폰트를 바꾸는 방법은 나중에 포스팅하도록 하겠습니다. </span>
</div>

<hr>

### asset

|구성 폴더📁
|:-
|`images`|`css`||`js`

#### <span style="font-size: medium;">***images📁***</span>
이미지를 사용하시려면 images에 파일을 넣어주세요!

<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">🌠 css와 js 폴더는 수정할 일이 없어서 넘어가겠습니다!</span>
</div>

## 2. 구성 폴더
### _posts⭐
블로그 글을 <u>포스팅</u>할 때, 작성할 **YYYY-MM-DD-TITLE.md**을 이 폴더에서 관리합니다.  
_posts폴더가 없다면 만들어 보세요!

```
ex) 2024-07-11-MinimalMistakes-Directory.md
```

### _pages
블로그에 카테고리를 추가할 때, 카테고리 관련 파일을 관리합니다.
_pages없다면 만들어 보세요!

<br>

## 3. 기본 파일
### _config.yml⭐
블로그의 테마, 홈페이지(Title, name, description, links, etc.), 댓글 등 다양한 환경변수를 수정할 수 있습니다.
```yml
# 테마 스킨
minimal_mistakes_skin    : "dark" # "air", "aqua", "contrast", "dark", "dirt", "neon", "mint", "plum", "sunrise"
# 지역 설정(언어 관련)
locale                   : "en-US" # en-US, ko-KR
# 홈페이지 타이틀
title                    : "일단 해보는 블로그. do it"
# 홈페이지 서브 타이틀
subtitle                 : "We'll do it together." # site tagline that appears below site title in masthead
# 저장소 설정
repository               : loplio/loplio.github.io # GitHub username/repo-name e.g. "mmistakes/minimal-mistakes"
# 분류 EX) Home / Blog / ...
breadcrumbs              : true # true, false (default)
# 댓글 기능(자세한 내용은 추후 포스팅하겠습니다!🌙)
comments:
  provider               : "utterances" # false (default), "disqus", "discourse", "facebook", "staticman", "staticman_v2", "utterances", "giscus", 
  utterances:
    theme                : "github-dark" # "github-light" (default), "github-dark"
    issue_term           : "pathname" # "pathname" (default)
# 블로그 분석(조회수, 방문자 분석 등. 자세한 내용은 추후 포스팅하겠습니다!🌙)
analytics:
  provider               : "google-gtag" # false (default), "google", "google-universal", "google-gtag", "custom"
  google:
    tracking_id          : "G-ZCT1FENABE"
    anonymize_ip         : "false" # true, false (default)
# 왼쪽 프로필 설정
author:
  name             : "Lo-plio"
  avatar           : # path of avatar image, e.g. "/assets/images/bio-photo.jpg"
  bio              : "게임 코딩의 모든 것."
  location         : # "Somewhere"
  links:
    - label: "Email"
      icon: "fas fa-fw fa-envelope-square"
      url: "mailto:jgh210@naver.com"
    - label: "GitHub"
      icon: "fab fa-fw fa-github"
      url: "https://github.com/loplio"
# 페이지 당 출력 포스트
paginate: 5 
# 페이지 번호
paginate_path: /page:num/
# 기본 설정 관련(출력 여부 - [author_profile, show_date, comments, etc.], 사이드 바 등).
defaults:
# 날짜 형식을 따로 지정하고 싶다면 date_format을 추가해주세요.
date_format: "%Y.%m.%d"
```
<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">⭐ _config.yml는 localhost로 테스트를 하실 때, 사이트에서 새로고침해도 바로 적용되지 않습니다! 다시 켜주세요. </span>
</div>

### Gemfile
Gemfile은 gem들의 <u>버전을 정의</u>하고 개발 환경에 따라 <u>구분</u>하는 역활을 합니다.  
gem은 루비의 라이브러리/패키지입니다.  
추가적으로 <u>Bundler</u>는 이 gem을 **설치**하고 **관리**하는 역활을 합니다.  

### index.html
홈페이지의 <u>레이아웃</u>을 **설정**하는 곳입니다.  
홈페이지를 꾸미고 싶다면 원하는 형식으로 수정해보세요! 

___


{: .notice}
✨개인 공부 글입니다! 언제든지 질문/지적 해주세요!✨