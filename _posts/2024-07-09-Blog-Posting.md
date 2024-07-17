---
title:  "[Blog] 깃허브 블로그(Github.io)에 포스팅해 보자"
excerpt: ""
#classes: wide
categories:
  - Blog
tags:
  - [Blog, Visual Studio Code, jekyll, Github, Git]

toc: true
toc_label: "List"
toc_icon: "bars"
toc_sticky: true
 
date: 2024-07-09
last_modified_at: 2024-07-09
---

<br>

# <span style="color:rgb(0, 180, 180)">블로그 포스팅.</span>
여러분의 Github에 블로그 글을 올리기 전에 <u>미리 테스트</u> 해보세요!  
아무 경로에서 <u>cmd(명령창)</u>을 열어서 다음과 같이 실행하세요.
```
gem install bundler jekyll
```
<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">🌠 이후 `jekyll -v`과 `bundle -v`으로 설치되었는지 확인하세요!</span>
</div>

<hr>

<u>임의의 블로그 셋</u>을 만들어 <u>로컬 호스트(127.0.0.1)</u>를 이용하여 미리 포스팅된 결과를 보는 것입니다.
```
jekyll new my-blog
cd my-blog
bundle exec jekyll serve
```
<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">🌠 로컬 호스트는 네트워크 기능을 시험할 때 사용하며, 자신의 주소를 가르키고 있습니다. </span>
</div>

<hr>

![jekyll-serve-error](https://github.com/user-attachments/assets/ca4b0026-5d55-4f1a-9123-75774e2f3831)  
동일한 오류가 나오면 생성한 블로그 경로의 `Gemfile`로 들어갑니다.  

<hr>

![gemfile-wdm-error](https://github.com/user-attachments/assets/71a79166-21b9-4d86-a656-bdfc7acb42dd)  
다음 내용을 주석처리해주세요.

<hr>
![server-running](https://github.com/user-attachments/assets/7c6d5e93-425c-41d3-bb7d-7ca2e709ba33)
다음과 같이 <u>Server running...</u>이 뜬다면 **성공**입니다.

🪄 ***미리 보는 결과***
![my-blog-hoom](https://github.com/user-attachments/assets/835b1d43-7ad4-459d-af84-cb16b6b58609)

## 참고자료
로컬에서 작성한 <u>포스팅 글</u>을 **미리 볼 수 있는** 방법입니다!  
📌 [ Jekyll Docs ](https://jekyllrb-ko.github.io/) 📌

<br>

# 1. 포스팅 폴더 생성.
**블로그 테마**를 적용하셨다면 `user-name.github.io📁` 안에  

| `_data📁`, `_includes📁`, `_layouts📁`, `_sass📁`, `asset📁`  

폴더들이 있는데, 여기에 블로그 포스팅을 작성한 파일을 모아둘 `_posts` **폴더를 생성**해 주세요.

<br>

# 2. 포스팅 파일 형식.
```
2024-07-16-blogtest.md
```
기본 블로그 포스팅 형식은 `YYYY-MM-DD-BLOG-TITLE.md`입니다.  
`YYYY-MM-DD-` 뒤에 나오는 Title은 `https://`의 마지막 주소가 됩니다.

<hr>
🪄 ***확장자 표시***  
![extension-name](https://github.com/user-attachments/assets/769df888-08c6-4cf9-b89d-6d2f68f0f907){: width="70%" height="70%"}  
`_posts📁`에 텍스트 파일을 생성하고 <u>확장자를 표시</u>한 후, test.txt를 2024-7-09-test.md로 바꿔 주시면 됩니다.

<hr>

마지막으로 .md파일을 수정하기 위해 통합 개발 환경이 필요한데, 저는 Visual studio Code로 작성하기로 했습니다.
링크 - 📌 [ Visual Studio Code Download ](https://code.visualstudio.com/download) 📌

<br>

# 3. 마크다운 간단 작성 방법.
`---`안에 있는 글의 정보를 포괄하는 메타데이터를 작성합니다.
본문의 내용은 <u>메타데이터</u>를 **출력하지 않습니다**.
```markdown
---
title:  "[Blog] 깃허브 블로그(Github.io)에 포스팅해 보자"
excerpt: "간단한 테스트 용 글"
#classes: wide
categories:
  - Blog
tags:
  - [Blog, Visual Studio Code, jekyll, Github, Git]

toc: true
toc_label: "List"
toc_icon: "bars"
toc_sticky: true
 
date: 2024-07-09
last_modified_at: 2024-07-09
---

# Test
text...
```

|형식|설명
|:-|:-
|toc|`목차 true/false`
|toc_label|`목차 이름`
|toc_icon|`목차 아이콘 이름`
|toc_sticky|`목차 고정 true/false`
|title|`포스팅 글 제목`
|excerpt|`포스팅 글 발췌`
|classes|`글의 가로 범위 넓게 - wide`
|categories|`카테고리 분류`
|tags|`태그 분류`
|date|`글 작성 일정`
|last_modified_at|`마지막 수정 일정`

<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">🌠 글의 본문은 # Test부터 들어 갑니다! </span>
</div>

<br>

# 4. 서버에 포스팅 올리기.
```bash
git add .
git commit -m "Commit content"
git push origin main
```
다음과 같이 마무리하면, `user-name.github.io`에 <u>적용</u>됩니다.