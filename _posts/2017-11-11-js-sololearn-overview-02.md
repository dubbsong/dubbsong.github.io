---
layout: post
title: "02. 첫 번째 JavaScript 만들기 (Overview)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# Creating Your First JavaScript

###### 첫 번째 JavaScript 만들기

<br>

- Let's start with adding JavaScript to a webpage.
  - 웹페이지에 JavaScript를 추가하는 것으로 시작해보자.
- JavaScript on the web lives inside the `HTML` document.
  - 웹상의 JavaScript는 `HTML` 문서 내에 존재한다.
- In HTML, JavaScript code must be inserted between `<script>` and `</script>` tags:
  - HTML에서, `<script>` 태그와 `</script>` 태그 사이에 JavaScript 코드를 삽입해야 한다.

```html
<script>
	...
</script>
```

<br>

- JavaScript can be placed in the HTML page's `<body>` and `<head>` sections.
  - JavaScript는 HTML 페이지의 `<body>`와 `<head>` 섹션에 위치시킬 수 있다.
- In the example below, we placed it within the `<body>` tag.
  - 아래 예제에서는, `<body>` 태그 내에 위치시켰다.

![sololearn img](/assets/img/sololearn-js-overview-02-01.png)

------

<br>

## Output

###### 출력

<br>

- Let's use JavaScript to print "Hello World" to the browser.
  - JavaScript를 사용해서 "Hello World"를 브라우저에 출력해보자.

```html
<html>
   <head></head>
   <body>
      <script>
      	document.write("Hello World!");
      </script>
   </body>
</html>
```

[코드 실행 확인 링크](https://code.sololearn.com/642/#js)

<br>

- The `document.write()` function writes a string into our HTML document.
  - `document.write()` 함수는 HTML 문서에 문자열을 작성한다.
- This function can be used to write text, HTML, or both.
  - 이 함수는 text, HTML, 또는 둘 다 작성하는 데 사용할 수 있다.

<br>

- The above code displays the following result:
  - 위의 코드는 다음 결과를 보여준다.

![sololearn img](/assets/img/sololearn-js-overview-02-02.png)

<br>

> The `document.write()` method should be used only for testing.
>
> `document.write()` 메소드는 테스트용으로만 사용해야 한다.

------

<br>

## Formatting Text

###### 텍스트 서식 지정

<br>

- Just like in HTML, we can use HTML tags to format text in JavaScript.
  - HTML과 마찬가지로, HTML 태그를 사용해서 JavaScript의 텍스트 서식을 지정할 수 있다.
- For example, we can output the text as a heading.
  - 예를 들어, 텍스트를 heading(표제)으로 출력할 수 있다.

```html
<html>
   <head></head>
   <body>
      <script>
      	document.write("<h1>Hello World!</h1>");
      </script>
   </body>
</html>
```

[코드 실행 확인 링크](https://code.sololearn.com/643/#js)

<br>

- Result:

![sololearn img](/assets/img/sololearn-js-overview-02-03.png)

------

<br>

## QUIZ

- What tag contains the JavaScript code?
  - JavaScript 코드가 포함되는 태그는 무엇인가?

> `script`

<br>

- Type in a code to output the "Hello world!" text on the screen.
  - "Hello world!" 텍스트를 화면에 출력하는 코드를 입력해라.

```html
<script>
	document.write("Hello world!");
</script>
```

<br>

- Which choice can be added within the text to be displayed?
  - 표시할 텍스트 내에 어떤 선택을 추가할 수 있는가?

> `Formatting tags`

<br>