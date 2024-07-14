---
title:  "[Blog] Markdown 기본 문법을 알아보자."
excerpt: ""

categories:
  - Blog
tags:
  - [Blog, Visual Studio Code, Markdown]

toc: true
toc_sticky: true
 
date: 2024-07-09
last_modified_at: 2024-07-10
---

# 1. Markdown 기본 문법
## 단순 문법 요약  

|문법|사용법| 
|:-|:-|
|**줄바꿈**| **(Space Bar x 2 이후 Enter)**  or **(\<br>)**  
|**특수 문자 출력**| 특수문자 앞에 &nbsp; **\\** 를 붙임 or **백틱(``)**를 이용하여 문자열을 감싸면 그대로 출력  
|**공백**| **`&nbsp;`**
|**인라인 코드**| **\` \`**
|**코드 블록**| **\`\`\` \`\`\`**
|**인용 블록**| **`>`**
|**굵게**| **`** **`**
|**기울이기**| **`* *`**
|**취소선**| **`~~ ~~`**
|**밑줄**| **`<u> </u>`**
|**글자 색상**| **`<span style=”color:…”> </span>`**

## 주의 사항 
**여러 행으로 이뤄진 문법**(링크 참조, 이미지 참조, 테이블 등)은 **분리** 되어 있어야 정상 출력됩니다.
```
example text

<링크 참조 문법>
...
...

<테이블>
...
...

example text
```

## 참고자료
마크 다운의 창시자 존 그루버 마크 다운 설명 문서와 식빵맘 포스팅 글을 위주로 참고하였습니다.  
[마크다운 문서](https://daringfireball.net/projects/markdown)  
[식빵맘's Blog(마크다운)](https://ansohxxn.github.io/blog/markdown/)

<br>

# 2. 헤더. Atx와 Setext?
Markdown에서 제목을 강조하고 단계를 설정.  
**(# ~ ######)** 총 **6단계**로 이뤄진 강조 vs **(--- / ===)**으로 총 **2단계**로 이뤄진 강조가 **Atx와 Setext**입니다.

**\<예시\>**  
# ATX (\# ATX)
## ATX (\#\# ATX)
### ATX (\#\#\# ATX)

<br>

SETEXT  
\=\=\=  

SETEXT  
\-\-\-

SETEXT (\=\=\=)  
===

SETEXT (\-\-\-)  
---

**큰 헤더가 작은 헤더의 문단을 포함하게 됨.**

<br>
  
# 3. 블록.
## 인라인 코드
**`** (**Back Quote**) 안에 있는 코드를 **인라인 코드**라 합니다.

**\<예시\>**  
\'Good Bye\' => `Good Bye` 

## 코드 블록  
**언어**에 맞는 **코드 블록**을 생성해줍니다.  
\`\`\` 언어 이름  
~Write  
\`\`\`

**\<예시\>**  
\`\`\` c++  
\#include\<iostream\>  
int main()  
{  
  std::cout << "Hello" << std::endl;  
}  
\`\`\`

**\<결과\>** 
``` c++
#include<iostream>
int main()
{
  std::cout << "Hello" << std::endl;
}
```

## 인용 블록
**'>'**를 이용하면 **인용블록**을 만들 수 있습니다.

**\<예시\>**  
**\>Hi**  
**\>Hello**

**\<결과\>**  
> **Hi**  
> **Hello**

<br>

# 4. 텍스트. (*, \_, ~)
## 강조와 기울이기
**`(* ~ ***)과 (_ ~ ___)`을** 글자 사이에 두면 강조효과를 냅니다.  
문자가 **하나**면, _기울이기_.  
문자가 **둘**이면, __글자굵게__.  
문자가 **셋**이면, ___기울이고굵게___.  

## 취소선
취소선은 **(\~~)둘**이면, **~~글자~~**

## 밑줄
밑줄은 \<u\>와 \</u\>, <u>밑줄</u>

## 글자 색상
**HTML 구문**을 이용하여 **색상**을 바꿔보자.  
**\<span style="color:..."> 색상을 변경할 텍스트... \</span>**

**\<예시\>**  
**\<span style="color:blue"> 파란색.\</span>** => **<span style="color:blue"> 파란색.</span>**

## 텍스트 문법 예시

|문법|예시|  
|:-|:-|
|기울이기| \*R\* => *R* , \_R\_ => _R_  
|강조| \*\*R\*\* => **R** , \_\_R\_\_ => __R__  
|강조와 기울이기| \*\*\*R\*\*\* => ***R*** , \_\_\_R\_\_\_ => ___R___  
|취소선| \~~R\~~ => ~~R~~  
|밑줄| \<u\>R\</u\> => <u>R</u>

<br>

# 5. 리스트.
## Unordered List
__(*, +, -)__ 순서없는 글머리 기호로 활용 가능합니다.  
**SpaceBar x 2**으로 중첩이 가능합니다.
* **Apple** => **\* Apple**
  - **Orange** => **\- Orange**
  + **Grape** => **\+ Grape**

## Ordered List
__(~1.)__ 순서있는 글머리 기호로 활용 가능합니다.  
**SpaceBar x 4**으로 중첩이 가능합니다.
1. **Apple** => **1. Apple**
    1. **Price**  => **1. Price**
    2. **Taste** => **2. Taste**

<br>

글머리 기호 뒤에 줄바꿈이 되면 다음과 같이 들여쓰기가 됩니다.
>- A-B-C-D-E, F-U  
>And your mom and your sister..

## Check List
\- [ &nbsp; ] 안에 **문자 X**의 유무로 체크박스 형성합니다.  

**\<예시\>**  
\- \[X\] Check  
\- \[ &nbsp; ] No Check 

**\<결과\>**
- [X] Check
- [ ] No Check

<br>

# 6. 링크.
링크를 만드는 방식은 **주소\<https://...\>**, **인라인\[\]\(\)** 또는 **참조\[\]\[\]**가 있습니다.

## 주소 링크\<link\>
**첫 번째 방법**, **\<https://...\>**로 인터넷 **주소 입력**으로 링크 연결.  

**\<예제\>** 
```
1. \<https://google.com\>
```
=> **<https://google.com>**

## 인라인 링크\[title\]\(link\)
**두 번째 방법**, **링크 주소(https://google.com)**를 대신할 **[구글]링크 제목** 연결.  

**\<예제\>** 
```
2. This is an [구글](https://google.com)
```
 => **This is an [구글](https://google.com)**

## 참조 링크\[title\]\[ref\]
**세 번째 방법**, **링크 제목[구글]**과 함께 **참조[숫자 or 이름]**를 나열 후, **참조란과 링크 연결**.

**\<예제\>**  
```
3. I get 10 times more traffic from [Google][1] than from
[Naver][2] or [ChatGPT][AI]  

[1]: http://google.com/        "Google"  
[2]: http://naver.com/       "Naver Search"  
[AI]: http://chatgpt.com/    "ChatGPT AI"  
```

**\<결과\>**  
I get 10 times more traffic from [Google][1] than from
[Naver][2] or [ChatGPT][AI].

[1]: http://google.com/        "Google"
[2]: http://naver.com/       "Naver Search"
[AI]: http://chatgpt.com/    "ChatGPT AI"

- 참조란에 설명이 들어간 (" ")내용은 필수로 적을 필요는 없습니다.

<br>

# 7. 이미지. 
**링크와 유사**한 구조이며 **\!**를 붙여 링크와 구분합니다.  

**참고자료**  
[식빵맘's Blog(이미지 삽입)](https://ansohxxn.github.io/blog/insert-image/)  

## 인라인 이미지\!\[name\]\(path\)
**첫 번째 방법**, **이미지 제목\[name\]**과 **이미지 주소\(path\)**를 연결.

**\<예제\>**
```
1. ![name](path) => ![google Logo](https://user-image-link-example/123-abc-zxc)
```

## 참조 이미지\!\[name\]\[ref\]
**두 번째 방법**, **이미지 제목\[name\]**과 함께 **참조\[ref\]**를 나열 후, **참조란과 주소 연결**  

**\<예제\>** 
```
2. ![name][ref] => ![google Logo][logo ref]

[ref]: path => [logo ref]: https://user-image-link-example/123-abc-zxc
```

<br>

**\<결과\>**  

![google logo][google ref]  

[google ref]: https://github.com/loplio/loplio.github.io/assets/51193110/56006d71-7eff-4a00-aea3-d3c16feb71b8

<br>

# 8. 테이블
테이블 문법은 **`|`(테이블 분리)**과 **`:-`(왼쪽 정렬)**, **`-:`(오른쪽 정렬)**을 합쳐 만들 수 있다.  

**\<예제\>** 
```
| 과자 | 가격
|:-|:-
| 칸쵸 | 1500 
| 빼빼로 | 900 
| 바나나킥 | 2000 

| 라면 | 가격 | 수량
|-:|-:|:-
| 신라면 | 1500 | 1
| 삼양라면 | 6000 | 5
| 너구리 | 20000 | 30
```

**\<결과\>** 

| 품목 | 가격
|:-|:-  
| 칸쵸 | 1500 
| 빼빼로 | 900 
| 바나나킥 | 2000 

| 라면 | 가격 | 수량
|-:|-:|:-
| 신라면 | 1500 | 1
| 삼양라면 | 6000 | 5
| 너구리 | 20000 | 30

<br>

# 9. 이모지
마지막은 **Emoji**입니다.
원하는 이모지명을 `:` (colon) 사이에 넣어주시면 됩니다.  
원하는 이모지는 아래 링크에서 확인해보세요!  

**\<예제\>** 
```
:backhand_index_pointing_up: => 👆
```

[![Emoji](https://github.com/loplio/loplio.github.io/assets/51193110/89891cc0-a31c-4666-8e73-7202e6dd7233)](https://www.webfx.com/tools/emoji-cheat-sheet/)
👆<cite>Link</cite>👆

{: .notice}
✨잘 모르거나 잘못된 점 있으면 언제든지 말해주세요!✨