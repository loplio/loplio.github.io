---
title:  "[Blog] 깃허브 블로그(Github.io)를 만들어 보자"
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
 
date: 2024-07-08
last_modified_at: 2024-07-08
---

<br>

# 1. Github Blog용 Repository 생성.
![create-repository](https://github.com/user-attachments/assets/6624e882-d474-47c3-a997-1fd983378d57){: width="70%" height="70%"}

<br>

# 2. 로컬에 Blog Repository 복제.
- 원하시는 경로에서 우클릭 - `Git Bash Here`  
- git clone 저장소 - `git clone https://github.com/user-name/user-name.github.io.git`  
![git-bash](https://github.com/user-attachments/assets/a8bc1380-2feb-4504-b797-a8b367114974){: width="25%" height="25%"} **=>** ![git-bash](https://github.com/user-attachments/assets/5fcd9be0-75fa-473d-ba60-73d6d4d0604b){: width="50%" height="50%"}
<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">🌠 Git이 깔려 있어야 합니다!</span>
</div>

<br>

# 3. Ruby 설치.
1. 최신 `Ruby+Devkit`을 설치  
[![ruby-installer](https://github.com/user-attachments/assets/fc9c4c98-5a41-4695-a126-c723eafaf8c0)](https://rubyinstaller.org/downloads/)  
👆<cite>Link</cite>👆

2. - [X] `MSYS2 development toolchain` 체크해주세요.
![ruby-install1](https://github.com/user-attachments/assets/a74f654c-11bc-418d-8239-04567bcfa87b){: width="50%" height="50%"}![ruby-install2](https://github.com/user-attachments/assets/5ddbbcd8-91b3-4f40-ac1b-a2993de48d7c){: width="50%" height="50%"}  

3. Enter눌러서 1, 3번 둘다 깔아주시면 됩니다.  
![ruby-install3](https://github.com/user-attachments/assets/16c76e03-3420-4a94-b538-837fd4bd99a6)

<br>

# 4. 원하는 테마 고르기.
저는 Minimal-Mistakes를 선택했습니다.  
[![minimal-mistakes-github](https://github.com/user-attachments/assets/906d572a-55a1-46c6-a812-243036eb9f4e)](https://github.com/mmistakes/minimal-mistakes)  
👆<cite>Link</cite>👆

minimal-mistakes를 기준으로로는 `docs`, `test`, `.git`을 제외하고 모두 붙여주시면 됩니다.  
![minimal-mistakes-folder](https://github.com/user-attachments/assets/713b7ffa-953c-4207-a20f-9b05a04dd5f6)

<br>

# 5. Github blog에 반영.
여러분이 생성한 git blog 로컬 경로로 가서 git bash를 켜줍니다.
```bash
git add .
git commit -m "First Commit"
git push origin main
```

🪄 user-name.github.io에 접속하시면 테마가 적용된 블로그가 반영됩니다!
<!-- ☀️☁️☂️☃️⭐🌙🌠🔥💧✨🗨️🎁🎄🎲🪄✔️🕶️🔔📢🎧🎵💡📜📄📌✒️📁 -->

<!-- <span style="font-size: x-small;">font-size: large, larger, medium, small, x-large</span> 
<hr style="width: 50%; text-align: center; margin-left: auto; margin-right: auto;">

나만의 포스팅 형식.
1.**전체를 포괄**하는 문단(#) 또는 **둘이나 셋으로 나눈 문단(#)**으로 글 구성.
2.문단의 시작은 포스팅 **주제를 왜 다루는지** 또는 **의도와 전반적인 내용**을 포괄
3.글의 문단(#)의 시작에 **주의 사항이나 참고자료**를 첨언.
5.글의 정보(##)는 왠만하면 번호를 붙이고 이후에 간단한 설명으로 시작. ##간은 <br>로 한칸 띄움
6.글의 세부정보(###) 간의 <br>을 쓰지 않음.
7.설명할 예제는 작은 수평선으로 구분
8.인라인 코드는 핵심 정보를 강조할 때 사용
9.강조는 내용의 핵심을 구분할 때 사용
10.이미지 링크 - 👆<cite>Link</cite>👆, 링크 - 📌 [ ... ](https://...) 📌
11.공지 - {: .notice} ✨...✨
12.글의 세부의 내부 정보는(###)안에 문단을 나눌 때는 #### <span style="font-size: medium;">***...***</span>를 사용하자. -->

<!-- 나만의 템플릿 -->
<!-- <span style="font-size: small; color:orange">***⭐핵심 키워드를 중점으로 보세요!⭐***</span> -->
<!-- 만약 이미지를 간단히 설명할 제목이 필요 하다면 
🪄 ... 형식을 이미지 위에 붙인다. -->

<!-- 마지막으로 딱딱한 내용의 블로그를 만들고 싶지 않으니
최대한 쉽게 설명하거나 비유를 이용하여 쉽게 이해되게 설명할 예정.
이때 설명할 내용의 앞에는 🌠를 사용하자. 
만약 notice를 사용했을 때, 다음 문단과 붙어 있어 어색하다면 <hr>을 이용해 분리해주자.
<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">🌠 ...</span>
</div>-->

<!-- 댓글
<script src="https://utteranc.es/client.js"
        repo="loplio/loplio.github.io"
        issue-term="pathname"
        theme="github-dark"
        crossorigin="anonymous"
        async>
</script> -->