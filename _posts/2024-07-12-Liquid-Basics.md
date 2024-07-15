---
title:  "[Blog] 테마 사용자 설정을 위한 Liquid 문법 정리."
excerpt: ""
categories:
  - Blog
tags:
  - [Blog, Jekyll, Minimal Mistakes, Markdown, Liqiud]

toc: true
toc_label: "List"
toc_icon: "bars"
toc_sticky: true
 
date: 2024-07-12
last_modified_at: 2024-07-12
---

<br>

# <span style="color:rgb(0, 220, 220)">Liquid 기본 문법</span>
<span style="font-size: large">블로그를 직접 커스텀하려면 Html, Liquid 문법의 기본은 알아야 편합니다.  
저는 웹 개발자가 아니지만, 간단한 문법만 살펴보려 합니다.</span>

## ✔️먼저읽기✔️
`{ { .. } }`는 출력하고 싶은 <u>변수</u>를 템플릿에 **렌더링**하는 일을 합니다.  
`{ % .. % }`는 <u>논리/제어</u>를 **결정** 하는 일을 합니다.  
`{ { .. | .. } }` 필터는 <u>변수</u>를 **변경**하는 역활을 합니다.

## 참고자료
잘 정리 된 문서라 <u>자세히</u> 알고 싶거나, <u>직관적인 출력 값</u>을 보려면 참고하세요!  
📌 [ Liquid 문서 ](https://shopify.dev/docs/api/liquid/) 📌

<br>

# Basic
`{ { .. } }`는 출력하고 싶은 <u>변수</u>를 템플릿에 **렌더링**하는 일을 합니다.

## 1. 연산자
### 기본 연산자
기본 연산자는 `==, !=, >, <, >=, <=, or, and`로 사용합니다.

### 연산 순서
연산 순서는 <u>오른쪽에서 왼쪽</u>으로 실행합니다.  
또한 괄호로 연산 순서를 변경할 수 없습니다.

### Contains
말 그대로 **`포함하니?`**의 의미를 갖고 문자열이 있는지 확인합니다.  

```liquid
{% raw %}{% if product.title contains "Pack" %}
  Milk Pack.
{% endif %}{% endraw %}
```

## 2. 타입

|타입| 설명
|-:|-:
|String| `{ % assign my_string = "Hello" % }`
|Number| `{ % assign my_num = 123 % }`
|Boolean| `{ % assign my_bool = true % }`
|Nil| 빈 값, 반환된 출력이 비어있다면 페이지에 그려지지 않습니다.
|Array| Split필터로 배열 초기화 가능. 접근은 [ ] 인데스로.
|Empty| `{ % if pages.about-us == empty % } .. { % endif % }`

<br>

# Tags
태그는 템플릿의 <u>논리/제어</u>를 **결정** 하는 일을 합니다.   
형식은 `{ % .. % }`입니다.

## 1. 제어 흐름

|<u>unless</u>는 **if not**|<u>elsif/else</u>는 **several if**|<u>case/when</u>은 **case by case**와 같습니다.

|조건| 설명
|-:|-:
|if| `{ % if product.title = "Shoes" % } ... { % endif % }`
|unless| `{ % unless product.title = "Shoes" % } ... { % endunless % }`
|elsif/else| `{ % if obj.color == "red" % } .. { % elsif obj.color == "blue" % } .. { % else obj.color % } .. { % endif % }`
|case/when| `{ % case handle % }{ % when "cake" % } .. { % when "cookie", "biscuit" % } .. { % else % } .. { % endcase % }`

## 2. 반복
### for

|조건| 설명
|-:|-:
|for| `{ % for obj in collection.objs % } {{ ... }} { % endif % }`
|break| 반복 중지 - `{ % break % }`
|continue| 현재 루프 넘기기 - `{ % continue % }`
|etc.| 루프 반복 횟수 제한(limit) / 지정된 오프셋부터 루프(offset) / 반복 범위 지정(range) / 루프 역순(reversed)

### cycle
문자열 그룹이 n개라면, 매 루프마다 문자열을 하나씩 이동하며 순환.
```liquid
{% raw %}{% cycle "one", "two", "three" %}
{% cycle "one", "two", "three" %}
{% cycle "one", "two", "three" %}
{% cycle "one", "two", "three" %}{% endraw %}

루프 4번 이후 결과.
one
two
three
one
```

### tablerow
tablerow는 html에 <table></table>을 이용하여 배열의 행과 열을 html의 결과로 출력합니다.

```liquid
<table>
{% raw %}{% tablerow product in collection.products %}
  {{ product.title }}
{% endtablerow %}{% endraw %}
</table>

결과.
<table>
  <tr class="row1">
    <td class="col1">
      Cool Shirt
    </td>
    <td class="col2">
      Alien Poster
    </td>
  </tr>
</table>
```

## 3. 템플릿
### Render/Include
***Render***는 <u>스니펫(snippet)</u>이나 <u>앱 블록(app block)</u>을 **출력**하는 역활을 합니다.  
***Include***도 **출력**이지만, 효율이 떨어져 ***Render***로 대체됐습니다.  
***But***, <u>Minimal-Mistakes파일</u>는 **Include를 사용**하고 있으니 기억해주세요.
<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">🌠 Snippet은 작은 조각이란 뜻이고, 재사용 가능한 소스 코드, 기계어, 텍스트의 작은 부분을 뜻합니다.</span>
</div>
```liquid
{% raw %}{% render 'filename' %}

{% include 'filename' %}{% endraw %}
```

### Other
그 외에도 다양한 템플릿들이 있습니다. 관심이 있다면 찾아보세요!

|template| 설명
|-:|-:
|Comment| 주석 처리 - `{ % comment % } ... { % endcomment % }`
|Echo| 태그에서 변수 출력 - `{ % liquid echo ... % }`
|Liquid| 구분 기호 없이 Liquid 블록 사용 - `{ % Liquid ... % }`
|Raw| 모든 Liquid 코드를 날 것으로 출력 - `{ % raw % } ... { % endraw % }`

```liquid
<Liquid Example>
{% raw %}{%
  assign product_type = product.type | downcase
  assign message = ''

  case product_type
    when 'health'
      assign message = 'This is a health potion!'
    when 'love'
      assign message = 'This is a love potion!'
    else
      assign message = 'This is a potion!'
  endcase

  echo message
%}{% endraw %}


<Raw Input>
{ % raw % }
  { { 2 | plus: 2 } } equals 4.
{ % endraw % }

<Original Output>
equals 4.

<Raw Output>
{ { 2 | plus: 2 } } equals 4.
```

## 4. 변수 할당
### Assign
<u>변수</u>를 **생성**합니다.
```liquid
{%raw%}{% assign variable_name = value %}{%endraw%}
```

### Capture
<u>문자열</u> 또는 <u>텍스트 블록</u>을 변수에 **저장**합니다.
```liquid
{%raw%}{% capture my_variable %}
  Hello, {{ user_name }}!
{% endcapture %}{%endraw%}

<Input>
{%raw%}{{ my_variable }}{%endraw%}

<Output>
Hello, user_name
```

<br>

# Filters
<span style="font-size: large">필터는 <u>변수</u>를 **변경**하는 역활을 합니다.  
`{ { .. | .. } }`로 중간에 `|`파이프 문자가 여러 개 들어갈 수 있습니다.</span>

<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">🌠 데이터를 가공하는 역활!</span>
</div>

## 1. 필터 종류
### 문자열

|필터| 설명
|-:|-:
|append| 문자열 끝에 문자열 추가 - `{ { "Hello" | append: " World" } }`
|capitalize| 문자열 첫 글자 대문자 변환 - `{ { "hello" | capitalize } }`
|upcase| 문자열 소문자 변환 - `{ % Liquid ... % }`
|truncate| 문자열 지정 길이만큼 자름- `{ { "Hello, world!" | truncate: 5 } }`

### 숫자

|필터| 설명
|-:|-:
|plus| 더함 - `{ { 5 | plus: 3 } }`
|times| 곱 - `{ { 5 | times: 3 } }`
|divided_by| 나눔 - `{ { 10 | divided_by: 2 } }`
|round| 숫자 반올림- `{ { 4.567 | round: 2 } }`

### 그 외

|필터| 설명
|-:|-:
|replace| 문자열 바꾸기 - `{ { "Hello, world!" | replace: "world", "Liquid" } }`
|date| 곱 - 날짜 형식 바꾸기`{ { "2024-07-12" | date: "%B %d, %Y" } }`

그 밖에 배열, 폰트, 색상, 수평선 등 수많은 필터를 적용할 수 있으니 원하는 필터를 찾아 사용해보세요.

## 2. 적용 예시
```liquid
{%raw%}<Data>
{
  "product": {
    "title": "Health potion"
  }
}

<Input_1>
{{ product.title | upcase }}

<Output_1>
HEALTH POTION

<Input_2>
{{ product.title | upcase | remove: 'HEALTH' }}

<Output_2>
POTION{%endraw%}
```
<u>필터가 여러 개</u>라면, **왼쪽부터 오른쪽**으로 적용이 순차적으로 됩니다.

<br>

<hr>

<div class="notice--info" style="font-weight: normal;">
  <span style="font-size: medium;">✨개인 공부 글입니다! 언제든지 질문/지적 해주세요!✨</span>
</div>


<script src="https://utteranc.es/client.js"
        repo="loplio/loplio.github.io"
        issue-term="pathname"
        theme="github-dark"
        crossorigin="anonymous"
        async>
</script>