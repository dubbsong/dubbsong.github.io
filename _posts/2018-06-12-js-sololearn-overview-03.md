---
layout: post
title: "(Overview 03) 웹 페이지에 JS 추가하기"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

### JavaScript in \<head>

###### \<head> 내의 JS

<br>

- You can place any number of scripts in an HTML document.
  - HTML document에 script를 원하는 만큼 놓을 수 있다.
- Typically, the script tag is placed in the head of the HTML document.
  - 일반적으로, script 태그는 HTML document의 head에 위치한다.

```html
<html>
  <head>
    <script>
      ...
    </script>
  </head>
  <body>
    
  </body>
</html>
```

<br>

> There is also a \<noscript> tag.
>
> \<noscript> 태그도 있다.

> Its content will be shown if the client's browser doesn't support JS scripts.
>
> 클라이언트의 브라우저가 JS 스크립트를 지원하지 않는 경우, 해당 내용이 표시된다.

------

<br>

### JavaScript in \<body>

###### \<body> 내의 JS

<br>

- Alternatively, include the JavaScript in the \<body> tag.
  - 또는 \<body> 태그 내에 JS를 포함시킨다.

```html
<html>
  <head>
    
  </head>
  <body>
    <script>
      ...
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
> script 로딩에 의해 HTML display가 차단되지 않으므로, 페이지 로딩이 향상될 수 있다.

------

<br>

### The \<script> Tag

###### \<script> 태그

<br>

- The \<script> tag can take two attributes, `language` and `type`, which specify the script's type:
  - \<script> 태그는 두 가지 속성을 사용할 수 있다: `language`와 `type`

```html
<script language="javascript" type="text/javascript">
  ...
</script>
```

<br>

> The `language` attribute is deprecated, and should not be used.
>
> `language` 속성은 중요도가 떨어져 더 이상 사용되지 않는다.

<br>

- In the example below, we created an alert box inside the script tag, using the `alert()` function.
  - 아래 예제에서는, `alert()` 함수를 사용해서 script 태그 내에 alert box를 생성했다.

```html
<html>
  <head>
    <script type="text/javascript">
      alert("What's up?")
    </script>
  </head>
  <body>
    
  </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/644/#js)

<br>

- Result:

![img](/assets/img/js-sololearn-overview-03-01.png)

<br>

> The `type` attribute: \<script type="text/javascript"> is also no longer required, as JavaScript is the default HTML scripting language.
>
> JavaScript가 HTML 스크립팅 언어의 기본이므로, 더 이상 `type` 속성도 필요하지 않다.

------

<br>

## QUIZ

- Where is the "script" tag typically placed?
  - 일반적으로 "script" 태그는 어디에 위치하는가?

> [ ] Before the HTML tag
>
> [ ] After the closing HTML tag
>
> [ ] `Inside the HEAD tag`

<br>

- Where else is the "script" tag typically placed?
  - 일반적으로 "script" 태그는 어디에 위치하는가?

> [ ] Inside the form element
>
> [ ] Inside the table element
>
> [ ] `Inside the BODY tag`

<br>

- What attribute and what value is used along with the script tag?
  - 어떤 속성과 어떤 값이 script 태그와 함께 사용되는가?

```html
<script type="text/javascript"></script>
```

<br>