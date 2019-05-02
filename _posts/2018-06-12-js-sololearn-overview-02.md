---
layout: post
title: "(Overview 02) JS 처음 생성하기"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## Creating Your First JavaScript

###### JS 처음 생성하기

<br>

- Let's start with adding JavaScript to a web page.
  - 웹 페이지에 JS를 추가하는 것으로 시작해보자.
- JavaScript on the web lives inside the `HTML` document.
  - 웹 상의 JS는 `HTML` document 내에 있다.
- In HTML, JavaScript code must be inserted between `<script>` and `</script>` tags:
  - JS 코드는 HTML의 `<script>`와 `</script>` 태그 사이에 삽입되어야 한다.

```html
<script>
  ...
</script>
```

<br>

- JavaScript can be placed in the HTML page's `<body>` and `<head>` sections.
  - JS는 HTML 페이지의 `<body>` 및 `<head>` 섹션에 위치할 수 있다.
- In the example below, we placed it within the `<body>` tag.
  - 아래 예제에서는, `<body>` 태그 내에 위치시켰다.

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

> Remember that the script, which is placed in the head section, will be executed before the \<body> is rendered.
>
> head 섹션에 위치한 script는, \<body>가 렌더링 되기 전에 실행된다.

> If you want to get elements in the body, it's a good idea to place your script at the end of the body tag.
>
> body 내의 element를 사용하는 경우, script를 body 태그의 끝에 위치시키는 게 좋다.

------

<br>

### Output

###### 출력하기

<br>

- Let's use JavaScript to print `Hello World!` to the browser.
  - JS를 사용해서 브라우저에 `Hello World!`를 출력해보자.

```html
<html>
  <head>
    
  </head>
  <body>
    <script>
      document.write('Hello World!');
    </script>
  </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/642/#js)

<br>

- The `document.write()` function writes a string into our HTML document.
  - `document.write()` 함수는 HTML document에 문자열을 작성한다.
- This function can be used to write text, HTML, or both.
  - 이 함수는 텍스트나 HTML, 또는 둘 다 작성하는 데 사용할 수 있다.

<br>

- The above code displays the following result:
  - 위 코드는 다음 결과를 보여준다.

![img](/assets/img/js-sololearn-overview-02-01.png)

<br>

> The `document.write()` method should be used only for testing.
>
> `document.write()` 메소드는 테스트용으로만 사용해야 한다.

------

<br>

### Formatting Text

###### 텍스트 서식 지정

<br>

- Just like in HTML, we can use HTML tags to format text in JavaScript.
  - HTML과 마찬가지로, HTML 태그를 사용해서 JS의 텍스트 서식을 지정할 수 있다.
- For example, we can output the text as a heading.
  - 예를 들어, 텍스트를 제목 서식으로 출력할 수 있다.

```html
<html>
  <head>
    
  </head>
  <body>
    <script>
      document.write('<h1>Hello World!</h1>');
    </script>
  </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/643/#js)

<br>

- Result:

![img](/assets/img/js-sololearn-overview-02-02.png)

<br>

> You can output almost everything in the web page using JavaScript.
>
> JS를 사용하면 웹 페이지에서 거의 모든 것을 출력할 수 있다.

------

<br>

## QUIZ

- What tag contains the JavaScript code?
  - JS 코드를 담는 태그는 무엇인가?

> `script`

<br>

- Please type in a code to output the "Hello World!" text on the screen.
  - 화면에 "Hello World!"를 출력하는 코드를 작성해라.

```html
<script>
  document.write('Hello World!');
</script>
```

<br>

- Which choice can be added within the text to be displayed?
  - 표시할 텍스트 내에 어떤 것을 추가할 수 있는가?

> `Formatting tags`

<br>