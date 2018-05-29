---
layout: post
title: "SoloLearn 번역 - 03. Adding JavaScript to a Web Page (Overview)"
categories: javascript
tags: JS
---

## JavaScript in \<head>

- You can place any number of scripts in an HTML document.
  - 원하는 수의 script를 HTML 문서에 위치시킬 수 있다.
- Typically, the script tag is placed in the head of the HTML document:
  - 일반적으로, script 태그는 HTML 문서의 head에 위치한다.

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

- Alternatively, include the JavaScript in the \<body> tag.
  - 다른 대안으로는, \<body> 태그에 JavaScript를 포함시켜라.

```html
<html>
   <head> </head>
   <body>
      <script>
      </script>
   </body>
</html>
```

<br>

> It's a good idea to place scripts at the bottom of the \<body> element.
>
> \<body> 요소의 맨 아래에 script를 두는 것이 좋다.

> This can improve page load, because HTML display is not blocked by scripts loading.
>
> HTML 표시가 script 로딩으로 인해 차단되지 않으므로, 페이지 로드가 향상될 수 있다.

- `사족`: 웹 브라우저가 HTML 문서를 해석(parsing)할 때 `<script>` 태그를 만나면 그 안의 JS의 처리가 끝날 때까지 다른 HTML의 해석을 멈추기 때문에 더 오래 걸리게 된다. 그래서 CSS, HTML 해석이 먼저 완료되고 나서 JS를 수행하는 것이 더 빠르기 때문에 HTML 문서의 마지막(`</body>` 직전)에 두는 것을 권한다.

------

<br>

## The \<script> Tag

- The \<script> tag can take two attributes, **language** and **type**, which specify the script's type:
  - \<script> 태그는 script의 타입을 지정하는 두 가지 속성인 **language**와 **type**을 사용할 수 있다.

```html
<script language="javascript" type="text/javascript">

</script>
```

<br>

> The **language** attribute is deprecated, and should not be used.
>
> **language** 속성은 더 이상 사용되지 않아야 한다.

<br>

- In the example below, we created an alert box inside the script tag, using the **alert()** function.
  - 아래 예제에서, **alert()** 함수를 사용해서 script 태그 안에 경고 상자를 만들었다.

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

<br>

- Result:

![SoloLearn img4](/assets/img/sololearn img4.png)

<br>

> The **type** attribute: <script type="text/javascript>" is also no longer required, as JavaScript is the default HTML scripting language.
>
> JavaScript가 기본 HTML 스크립트 언어이므로, **type** attribute: <script type="text/javascript>"도 더 이상 필요하지 않다.

------

<br>

## QUIZ

- Where is the "script" tag typically placed?
  - **Inside the HEAD tag**
  - Before the HTML tag
  - After the closing HTML tag

<br>

- Where else is the "script" tag typically placed?
  - Inside the form element
  - Inside the table element
  - **Inside the BODY tag**

<br>

- What attribute and what value is used along with the script tag?

```html
<script type="text/javascript">
```

<br>