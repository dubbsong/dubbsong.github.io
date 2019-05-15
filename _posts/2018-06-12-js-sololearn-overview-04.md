---
layout: post
title: "(Overview 04) 외부 JS"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

### External JavaScript

###### 외부 JS

<br>

- Scripts can also be placed in `external files`.
  - script는 `외부 파일`에 위치시킬 수도 있다.
- External scripts are useful and practical when the same code is used in a number of different web pages.
  - 동일한 코드가 여러 웹 페이지에서 사용될 때, 외부 script는 유용하고 실용적이다.
- JavaScript files have the file extension `.js`.
  - JS 파일은 `.js` 파일 확장자를 가진다.

<br>

> Having JS scripts in separate files makes your code much readable and clearer.
>
> JS script를 별도의 파일에 두면, 코드가 읽기 쉽고 명확해진다.

<br>

<br>

- To use an external script, put the name of the script file in the `src` attribute of the `<script>` tag.
  - 외부 script를 사용하기 위해, script 파일의 이름을 `<script>` 태그의 `src` 속성에 넣는다.

```html
<html>
  <head>
    <title>What's up?</title>
    <script src="demo.js"></script>
  </head>
  <body>
    
  </body>
</html>
```

<br>

> Placing a JavaScript in an external file has the following advantages:
>
> JS를 외부 파일에 위치시키면 다음과 같은 이점이 있다.
>
> It separates HTML and code.
>
> HTML과 JS 코드를 분리한다.
>
> It makes HTML and JavaScript easier to read and maintain.
>
> 가독성이 좋고, 유지가 더 쉽다.
>
> Cached JavaScript files can speed up page loads.
>
> cached JS 파일은 페이지 로딩 속도를 높일 수 있다.

------

<br>

## QUIZ

- What extension is used for the JavaScript file?
  - JS 파일에는 어떤 확장자가 사용되는가?

> `.js`

<br>

- What attribute of the script tag is used for adding the external JavaScript file?
  - script 태그의 무슨 속성이 외부 JS 파일을 추가하는 데 사용되는가?

> `src`

<br>

- Please add the corresponding keywords to add the external sample.js file to the web page.
  - 외부 sample.js 파일을 웹 페이지에 추가해라.

```html
<script type="text/javascript" src="sample.js"></script>
```

<br>