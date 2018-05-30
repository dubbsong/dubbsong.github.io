---
Slayout: post
title: "SoloLearn 번역 - 04. External JavaScript (Overview)"
categories: javascript
tags: JS
---

## External JavaScript (외부 JavaScript)

- Scripts can also be placed in **external files**.
  - 스크립트는 **외부 파일**에 위치할 수도 있다.
- External scripts are useful and practical when the same code is used in a number of different web pages.
  - 외부 스크립트는 동일한 코드가 여러 다른 웹 페이지에서 사용될 때 유용하고 실용적이다.
- JavaScript files have the **file extension .js**.
  - JavaScript **파일의 확장자는 .js**이다.

<br>

- Below, we've created a new **text file**, and called it **demo.js**.
  - 아래에서는, 새로운 **텍스트 파일**을 만들고, **demo.js**라고 한다.

![SoloLearn img](/assets/img/sololearn04-1.png)

------

<br>

## External JavaScript 02

- To use an external script, put the name of the script file in the **src** (source) attribute of the \<script> tag.
  - 외부 스크립트를 사용하려면, 스크립트 파일의 이름을 \<script> 태그의  **src**(source) 속성에 넣어라.

<br>

- Here is an example:

```html
<html>
   <head>
      <title> </title>
      <script src="demo.js"></script>
   </head>
   <body>
   </body>
</html>
```

<br>

- Your **demo.js** file includes the following JavaScript:
  - **demo.js** 파일에는 다음 JavaScript가 포함되어 있다.

```javascript
alert("This is an alert box!");
```

<br>

> External scripts cannot contain \<script> tags.
>
> 외부 스크립트는 \<script> 태그를 포함할 수 없다.

------

<br>

## External JavaScript 03

- The result of the previous example will be identical to the result when we included the JavaScript within the HTML file.
  - 이전 예제의 결과는 HTML 파일 내에 JavaScript를 포함시켰을 때의 결과와 동일할 것이다.

![SoloLearn img](/assets/img/sololearn04-2.png)

<br>

- You can place an external script reference in \<head> or \<body>, whichever you prefer.
  - 원하는 대로 \<head> 또는 \<body>에 외부 스크립트 참조를 배치할 수 있다.
- The script will behave as if it were located exactly where the \<script> tag is located.
  - 스크립트는 \<script> 태그가 있는 위치와 정확히 일치하는 것처럼 동작한다.

<br>

> Placing a JavaScript in an external file has the following advantages:
>
> JavaScript를 외부 파일에 배치하면 다음과 같은 이점이 있다:

> - It separates HTML and code.
> - HTML과 코드를 분리한다.

> - It makes HTML and JavaScript easier to read and maintain.
> - HTML과 JavaScript를 읽고 유지하기가 더 쉽다.

> - Cached JavaScript files can speed up page loads.
> - 캐시된 JavaScript 파일은 페이지 로드 속도를 높일 수 있다.

<br>

------

<br>

## QUIZ

- What extension is used for the JavaScript file?
  - **.js**

<br>

- What attribute of the script tag is used for adding the external JavaScript file?
  - **src**

<br>

- Please add the corresponding keywords to add the external sample.js file to the web page.

```html
<script type="text/javascript"
        src="sample.js"></script>
```

<br>