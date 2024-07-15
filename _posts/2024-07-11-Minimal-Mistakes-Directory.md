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

# <span style="color:rgb(0, 220, 220)">Minimal Mistakes Folder</span>

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
|`index.html`||`package.json`

## 참고자료
 <u>파일 구조</u>와 <u>내용</u>을 자세히 보고싶다면 **minimal-mistakes의 Git**을 확인해보세요!
📌 [ Minimal-mistakes Git ](https://github.com/mmistakes/minimal-mistakes) 📌

## 1. 기본 폴더
### _data
테마를 꾸밀 때, 사용되는 데이터를 모은 폴더입니다.  
**파일:** `navigation.yml`, `ui-text.yml`  

#### <span style="font-size: medium;">***navigation.yml📜***</span>
-  블로그 <u>사이드 바</u> or <u>메뉴 바</u> **꾸밀** 수 있습니다.  
-  <u>main</u>은 **상단 메뉴 바**이며, 기본 형식이 적혀 있습니다.
-  docs는 제가 추가한 부분이고, 사이드 바를 넣기 위해 추가헀습니다.

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
- 블로그의 <u>모든 UI의 텍스트</u>를 **수정**할 수 있습니다.
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


### _layouts

### _sass

### _asset

<br>

## 2. 구성 폴더
### _posts⭐
블로그 글을 <u>포스팅</u>할 때, 작성할 **YYYY-MM-DD-TITLE.md**을 이 폴더에서 관리한다.  
_posts폴더가 없다면 만들자!

```
ex) 2024-07-11-MinimalMistakes-Directory.md
```

### _pages
블로그에 카테고리를 추가할 때, 카테고리 관련 파일을 관리한다.
_pages없다면 만들자!

<br>

## 3. 기본 파일
### _config.yml
```yml
paginate: 5 # 페이지 당 출력 포스트
paginate_path: /page:num/ # 페이지 번호
```

### Gemfile

### index.html


### package.json

___


{: .notice}
✨개인 공부 글입니다! 언제든지 질문/지적 해주세요!✨