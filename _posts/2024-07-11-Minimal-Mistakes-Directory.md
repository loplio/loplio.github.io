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

# Minimal Mistakes Folder

|구성 폴더📁
|:-|:-|:-|:-
|`_data`|`_includes`||`_layouts`
|`_sass`|`asset`||

|생성 폴더📁
|:-
|`_posts`⭐|`_pages`

|구성 파일📜
|:-|:-
|`_config.yml`⭐||`Gemfile`
|`index.html`||`package.json`

## 1. 구성 폴더
### _data
**파일:** `navigation.yml`, `ui-text.yml`  

navigation.yml  
블로그 상단 메뉴 바 관리하는 파일입니다.  

<!-- **\<예제\>** -->

<span style="font-size: x-small;">예제</span>
<hr style="width: 50%; text-align: center; margin-left: auto; margin-right: auto;">

```yml
# main links
main:
  - title: "Home"
    url: https://my-blog-url
  - title: "Github"
    url: https://github.com/git-name
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

## 3. 구성 파일
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
✨잘 모르거나 잘못된 점 있으면 언제든지 말해주세요!✨