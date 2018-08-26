---
layout: post
title: "04. 외부 JavaScript (Overview)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# External JavaScript

###### 외부 JavaScript

<br>

- Scripts can also be placed in `external files`.
  - script를 `외부 파일`에 위치시킬 수도 있다.
- External scripts are useful and practical when the same code is used in a number of different web pages.
  - 외부 script는 동일한 코드가 여러 다른 웹페이지에서 사용될 때 유용하고 실용적이다.
- JavaScript files have the file extension `.js`.
  - JavaScript 파일의 파일 확장자는 `.js`이다.

<br>

- Below, we've created a new `text file`, and called it `demo.js`.
  - 아래에서, `demo.js`라는 새로운 `텍스트 파일`을 생성했다.

![sololearn img](/assets/img/sololearn-js-overview-04-01.png)

<br>

<br>

- To use an external script, put the name of the script file in the `src` (source) attribute of the \<script> tag.
  - 외부 script를 사용하려면, script 파일의 이름을 \<script> 태그의 `src` 속성에 넣어라.

<br>

- Example:

```html
<html>
   <head>
      <title></title>
      <script src="demo.js"></script>
   </head>
   <body>
   </body>
</html>
```

<br>

- Your `demo.js` file includes the following JavaScript.
  - `demo.js` 파일에는 다음 JavaScript가 포함되어 있다.

```js
alert("This is an alert box!");
```

<br>

> External scripts cannot contain \<script> tags.
>
> 외부 script는 \<script> 태그를 포함할 수 없다.

<br>

<br>

- The result of the previous example will be identical to the result when we included the JavaScript within the HTML file.
  - 이전 예제의 결과는 JavaScript를 HTML 파일에 포함시켰을 때의 결과와 동일하다.

![sololearn img](/assets/img/sololearn-js-overview-04-02.png)

<br>

> Placing a JavaScript in an external file has the following advantages:
>
> JavaScript를 외부 파일에 위치시키면, 다음과 같은 이점이 있다.

> It separates HTML and code.
>
> HTML과 코드를 분리한다.

> It makes HTML and JavaScript easier to read and maintain.
>
> HTML과 JavaScript를 읽고 유지하기가 더 쉽다.

> Cached JavaScript files can speed up page loads.
>
> 캐시된 JavaScript 파일은 페이지 로딩 속도를 높일 수 있다.

------

<br>

## QUIZ

- What extension is used for the JavaScript file?
  - JavaScript 파일에는 어떤 확장자가 사용되는가?

> `.js`

<br>

- What attribute of the script tag is used for adding the external JavaScript file?
  - script 태그의 어떤 속성이 외부 JavaScript 파일을 추가하는 데 사용되는가?

> `src`

<br>

- Add the corresponding keywords to add the external sample.js file to the webpage.
  - 해당 키워드를 추가해서, 웹페이지에 외부 sample.js 파일을 추가해라.

```html
<script type="text/javascript" src="sample.js"></script>
```

<br>
