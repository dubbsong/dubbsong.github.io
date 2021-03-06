---
layout: post
title: "(Overview 02) jQuery 시작하기"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## Getting Started

###### jQuery 시작하기

<br>

- You can download a copy of the jQuery library from www.jquery.com, or, as an alternative, you can include it from a CDN (Content Delivery Network), like Google or Microsoft.
  - www.jquery.com에서 jQuery 라이브러리 사본을 다운로드할 수 있다.
  - Google 또는 Microsoft와 같은 CDN (컨텐츠 전송 네트워크)을 포함시킬 수 있다.
- We will use the CDN from the official jQuery web site.
  - 우리는 공식 jQuery 웹 사이트의 CDN을 사용한다.
- To start using jQuery, we first need to add it to the head of our HTML document using the script tag:
  - jQuery를 사용하려면 먼저, HTML document의 head에 script 태그를 추가해야 한다.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>What's up?</title>
    <script src="https://code.jquery.com/jquery-3.1.1.js"></script>
  </head>
  <body>
    
  </body>
</html>
```

<br>

> jQuery is a JavaScript library, so it has the `.js` file extension.
>
> jQuery는 jS 라이브러리이므로, `.js` 파일 확장자를 사용한다.

<br>

<br>

- It is a good practice to wait for the HTML document to be fully loaded and ready before working with it.
  - HTML document가 완전히 로딩되고 준비될 때까지 기다리는 것이 좋다.
- For that we use the `ready` event of the document object:
  - 이를 위해, document 객체의 `ready` 이벤트를 사용한다.

```js
$(document).ready(function() {
  // jQuery 코드
});
```

<br>

- The `$` is used to access jQuery.
  - `$`는 jQuery에 액세스하는 데 사용된다.
- From here, the code accesses the document object and defines a function to be called when the document's ready event is fired.
  - 위 코드는 document 객체에 액세스하고, document의 ready 이벤트가 발생할 때 호출할 함수를 정의한다.
- This prevents any jQuery code from running before the document is finished loading.
  - 이렇게 하면, document의 로딩이 완료되기 전에는 jQuery 코드가 실행되지 않는다.
- Since the code above is used in almost all cases when using jQuery, there is a handy shortcut for writing it:
  - 위 코드는 jQuery를 사용하는 거의 모든 경우에 사용된다.
  - 그래서 편리하게 작성하기 위한 단축 코드가 있다.

```js
$(function() {
  // jQuery 코드
});
```

<br>

- This code performs the same task as the longer code above.
  - 이 코드는 위의 긴 코드와 동일한 작업을 수행한다.

<br>

<br>

- Let's change the content of the div element.
  - div element의 내용을 변경해보자.

<br>

- HTML:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>What's up?</title>
    <script src="https://code.jquery.com/jquery-3.1.1.js"></script>
  </head>
  <body>
    <div id="start">
      Start
    </div>
  </body>
</html>
```

<br>

- JS:

```js
$(function() {
  $("#start").html("Go");
});
```

[코드 실행 확인](https://code.sololearn.com/1103/#js)

<br>

> This changes the HTML of the element with id="start" to "Go".
>
> 위 코드는 id="start" element의 HTML을 "Go"로 변경한다.

------

<br>

### Syntax

###### jQuery 구문

<br>

- jQuery is used to select (query) HTML elements and perform "actions" on them.
  - jQuery는 HTML element를 선택(query)해서 "action"을 수행하는 데 사용된다.

<br>

- Basic syntax is: `$("selector").action()`
  - 기본 구문: `$("선택자").action()`

- The `$` accesses jQuery.
  - `$`는 jQuery에 액세스한다.
- The `selector` finds HTML elements.
  - `selector`는 HTML element를 선택한다.
- The `action()` is then performed on the element(s).
  - 그런 다음 element에 `action()`이 수행된다.

<br>

- For example:

```js
$("p").hide()	// 모든 <p> element를 감춘다.
$(".demo").hide()	// 모든 class="demo" element를 감춘다.
$("#demo").hide()	// id="demo" element를 감춘다.
```

<br>

> If you have used CSS before, you will notice that jQuery uses CSS syntax to select elements.
>
> jQuery는 element를 선택하기 위해 CSS 구문을 사용한다.

------

<br>

## QUIZ

- Fill in the blanks to include jQuery in your HTML.
  - HTML에 jQuery를 포함시켜라.

```html
<html>
  <head>
    <script src="jquery.js"></script>
  </head>
</html>
```

<br>

- Which event is used to prevent any jQuery code from running before the document is finished loading?
  - document의 로딩이 완료되기 전에 jQuery 코드의 실행을 막는 이벤트는 무엇인가?

> [ ] load
>
> [ ] start
>
> [ ] function
>
> [ ] `ready`

<br>

- Which symbol is used to access jQuery?
  - jQuery에 액세스하는 데 사용되는 기호는 무엇인가?

> `$`

<br>

- Fill in the blanks to call the show() function for the element with the id="menu".
  - id="menu" element를 선택하고, show() 함수를 호출해라.

```js
$("#menu").show();
```

<br>