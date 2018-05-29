---
layout: post
title: "SoloLearn 번역 - 02. Creating Your First JavaScript (Overview)"
categories: javascript
tags: JS
---

## Creating Your First JavaScript

- Let's start with adding JavaScript to a webpage.
  - JavaScript를 웹 페이지에 추가하는 것으로 시작해보자.
- JavaScript on the web lives inside the **HTML** document.
  - 웹 상의 JavaScript는 **HTML** 문서 내에 존재한다.
- In HTML, JavaScript code must be inserted between **\<script>** and **\</script>** tags:
  - HTML에서는, **\<script>** 태그와 **\</script>** 태그 사이에 JavaScript 코드를 삽입해야 된다.
  - `<script>`: The \<script> tag is used to define a JavaScript

```html
<script>
...
</script>
```

<br>

- JavaScript can be placed in the HTML page's **\<body>** and **\<head>** sections.
  - JavaScript는 HTML 페이지의 **\<body>** 섹션과 **\<head>** 섹션에 위치할 수 있다.
- In the example below, we placed it within the **\<body>** tag.
  - 아래 예제에서는, **\<body>** 태그 안에 위치해있다.

![SoloLearn img](/assets/img/sololearn img1.png)

------

<br>

## Output

- Let's use JavaScript to print "Hello World" to the browser.
  - JavaScript를 사용해서 "Hello World"를 브라우저에 출력해보자.

```html
<html>
   <haed> </haed>
   <body>
      <script>
      	document.write("Hello World!");
      </script>
   </body>
</html>
```

<br>

- The **document.write()** function writes a string into our HTML document.
  - **document.write()** 함수는 HTML 문서에 문자열을 작성한다.
  - `string`: a series of characters treated as a single unit
- This function can be used to write text, HTML, or both.
  - 이 함수는 텍스트, HTML 또는 둘 다 작성하는 데 사용될 수 있다.

<br>

- The above code displays the following result:
  - 위의 코드는 다음과 같은 결과를 표시한다.

![SoloLearn img2](/assets/img/sololearn img2.png)

<br>

> The **document.write()** method should be used only for testing.
>
> **document.write()** 메소드는 테스트 용으로만 사용되어야 한다.

> Other output mechanisms appear in the upcoming lessons.
>
> 다른 출력 메카니즘은 다가올 강의에서 나타난다.

------

<br>

## Formatting Text (텍스트 서식)

- Just like in HTML, we can use HTML tags to format text in JavaScript.
  - HTML과 마찬가지로, JavaScript에서 텍스트 서식을 지정해서 HTML 태그를 사용할 수 있다.
- For example, we can output the text as a heading.
  - 예를 들어, 텍스트를 표제로 출력할 수 있다.

```html
<html>
   <head> </head>
   <body>
      <script>
      	document.write("<h1>Hello World!</h1>");
      </script>
   </body>
</html>
```

<br>

- Result:

![SoloLearn img3](/assets/img/sololearn img3.png)

------

<br>

## QUIZ

- What tag contains the JavaScript code?
  - code
  - body
  - **script**
  - style

<br>

- Please type in a code to output the "Hello world!" text on the screen.

```html
<script>
document.write("Hello world!");
</script>
```

<br>

- Which choice can be added within the text to be displayed?
  - **Formatting tags**
  - JavaScript commands
  - Folders

<br>