---
layout: post
title: "03. 웹페이지에 JavaScript 추가하기 (Overview)"
categories: dev
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# Adding JavaScript to a Webpage

###### 웹페이지에 JavaScript 추가하기

------

<br>

<br>

## JavaScript in \<head>

###### \<head>의 JavaScript

<br>

- Typically, the script tag is placed in the head of the HTML document:
  - 일반적으로, script 태그는 HTML 문서의 head에 위치시킨다.

```html
<html>
   <head>
      <script>
      </script>
   </head>
   <body>
   </body>
</html>
```

------

<br>

## JavaScript in \<body>

###### \<body>의 JavaScript

<br>

- Alternatively, include the JavaScript in the \<body> tag.
  - 또는 \<body> 태그에 JavaScript를 포함시킨다.

```html
<html>
   <head></head>
   <body>
      <script>
      </script>
   </body>
</html>
```

<br>

> It's a good idea to place scripts at the bottom of the \<body> element.
>
> \<body> element의 맨 아래에 script를 위치시키는 게 좋다.

> This can improve page load, because HTML display is not blocked by scripts loading.
>
> 이렇게 하면, HTML 표시가 script 로딩으로 인해 차단되지 않으므로, 페이지 로딩이 향상된다.

------

<br>

## The \<script> Tag

###### \<script> tag

<br>

- The \<script> tag can take two attributes, `language` and `type`, which specify the script's type:
  - \<script> 태그는 script의 타입을 지정하는 두 가지 속성인 `language`와 `type`을 사용할 수 있다.

```html
<script language="javascript" type="text/javascript">

</script>
```

<br>

> The `language` attribute is deprecated, and should not be used.
>
> `language` 속성은 더 이상 사용되지 않아야 한다.

<br>

- In the example below, we created an alert box inside the script tag, using the `alert()` function.
  - 아래 예제에서는, `alert()` 함수를 사용해서 script 태그 내에 alert box를 생성했다.

```html
<html>
   <head>
      <title></title>
      <script type="text/javascript">
      	alert("This is an alert box!");
      </script>
   </head>
   <body>
   </body>
</html>
```

[코드 실행 확인 링크](https://code.sololearn.com/644/#js)

<br>

- Result:

![sololearn img](/assets/img/sololearn-js-overview-03-01.png)

<br>

> The `type` attribute: \<script type="text/javascript"> is also no longer required, as JavaScript is the default HTML scripting language.
>
> JavaScript가 기본 HTML 스크립팅 언어이므로, `type` 속성: \<script type="text/javascript">도 더 이상 필요하지 않다.

------

<br>

## QUIZ

- Where is the "script" tag typically placed?
  - 일반적으로 "script" 태그는 어디에 위치시키나?

> `Inside the HEAD tag`

<br>

- Where else is the "script" tag typically placed?
  - 또 다르게 일반적으로 "script" 태그는 어디에 위치시키나?

> `Inside the BODY tag`

<br>

- What attribute and what value is used along with the script tag?
  - script 태그와 함께 어떤 속성과 값이 사용되는가?

```html
<script type="text/javascript">
```

<br>