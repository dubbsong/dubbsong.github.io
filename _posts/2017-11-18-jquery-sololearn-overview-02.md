---
layout: post
title: "SoloLearn jQuery 번역 - 02. Getting Started (Overview)"
categories: dev
tags: jquery
---

## Getting Started

###### 시작하기

<br>

- You can download a copy of the jQuery library from www.jquery.com, or, as an alternative, you can include it from a CDN (Content Delivery Network), like Google or Microsoft.
  - www.jquery.com에서 jQuery 라이브러리 사본을 다운로드하거나, Google 또는 Microsoft와 같은 CDN(Content Delivery Network)에서 포함할 수 있다.
- We will use the CDN from the official jQuery website.
  - 공식 jQuery 웹사이트의 CDN을 사용할 것이다.
- To start using jQuery, we first need to add it to the head of our HTML document using the script tag:
  - jQuery를 사용해서 시작하려면, 우선 script 태그를 사용해서 HTML document의 head에 추가해야 한다.

```html
<!DOCTYPE html>
<html>
   <head>
      <title>Page Title</title>
      <script src="https://code.jquery.com/jquery-3.1.1.js"></script>
   </head>
   <body>
   </body>
</html>
```

<br>

> jQuery is a JavaScript library, so it has the `.js` file extension.
>
> jQuery는 JavaScript 라이브러리이므로, `.js` 파일 확장자를 갖는다.

------

<br>

## Getting Started 02

- It is a good practice to wait for the HTML document to be fully loaded and ready before working with it.
  - HTML document가 완전히 로딩되고 준비될 때까지 기다리는 게 좋다.
- For that we use the `ready` event of the document `object`:
  - 이를 위해 document `object`의 `ready` 이벤트를 사용한다.
  - `object`: containers for named values / 지정된 값의 컨테이너

```js
$(document).ready(function() {
   // jQuery code goes here
});
```

<br>

- The `$` is used to access jQuery.
  - `$`는 jQuery에 액세스하는 데 사용된다.
- From here, the code accesses the document object and defines a function to be called when the document's ready event is fired.
  - 여기에서 코드는, document object에 액세스한다.
  - 그리고 document의 ready 이벤트가 발생하면 호출할 함수를 정의한다.
- This prevents any jQuery code from running before the document is finished loading.
  - 이렇게 하면, document의 로딩이 끝나기 전에 jQuery 코드는 실행되지 않는다.
- Since the code above is used in almost all cases when using jQuery, there is a handy shortcut for writing it:
  - 위의 코드는 jQuery를 사용할 때 거의 모든 경우에 사용되므로, 작성하기 편리한 단축코드가 있다.

```js
$(function() {
   // jQuery code goes here
});
```

<br>

- This code performs the same task as the longer code above.
  - 이 코드는 위의 긴 코드와 동일한 작업을 수행한다.

<br>

> If the jQuery syntax seems a little confusing, don't worry, we will cover it in detail.
>
> jQuery 문법이 다소 혼란스러울지라도 걱정하지 마라. 자세히 설명할 것이다.

------

<br>

## Getting Started 03

- Now, having the jQuery library in our head section and having defined the document ready event, we can start our first jQuery manipulation.
  - 이제 head 섹션에 jQuery 라이브러리가 있고, document ready 이벤트를 정의한 후, 첫 번째 jQuery 조작을 시작할 수 있다.
- Let's change the content of the div element.
  - div element의 내용을 변경해보자.

<br>

- The HTML:

```html
<!DOCTYPE html>
<html>
   <head>
      <title>Page Title</title>
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

- The JavaScript:

```js
$(function() {
   $("#start").html("Go!");
});
```

<br>

> This changes the HTML of the element with id="start" to "Go!".
>
> 이렇게 하면 HTML의 id="start" element가 "Go!"로 변경된다.

------

<br>

## Syntax

###### 문법

<br>

- jQuery is used to select (query) HTML elements and perform "actions" on them.
  - jQuery는 HTML element를 select(query)하고, "action"을 수행하는 데 사용된다.
- Basic syntax is: `$("selector").action()`
  - 기본 문법은 `$("selector").action()`이다.

<br>

1. The $ accesses jQuery.
   - $은 jQuery에 액세스한다.
2. The (selector) finds HTML elements.
   - (selector)는 HTML element를 찾는다.
3. The action() is then performed on the element(s).
   - 그런 다음 element에 대해 action()이 수행된다.

<br>

- For example:

```js
$("p").hide()	// hides all <p> elements
$(".demo").hide()	// hides all elements with class="demo"
$("#demo").hide()	// hides the element with id="demo"
```

<br>

- Looking back at the code from our previous example:
  - 이전 예제 코드를 보면 다음과 같다.

```js
$("#start").html("Go!");
```

<br>

- This selects the element with the id="start" and calls the html() method for it.
  - 이 코드는 id="start" element가 선택되고, html() 메소드가 호출된다.
- The html() method is used to change the HTML content of an element.
  - html() 메소드는 element의 HTML 내용을 변경하는 데 사용된다.

<br>

> If you have used CSS before, you will notice that jQuery uses CSS syntax to select elements.
>
> 이전에 CSS를 사용했다면, jQuery가 CSS 문법을 사용해서 element를 선택한다는 것을 알 수 있다.

------

<br>

## QUIZ

- Fill in the blanks to include jQuery in your HTML.
  - 빈간을 채워서 HTML에 jQuery를 포함시켜라.

```html
<html>
   <head>
      <script src="jquery.js"></script>
   </head>
</html>
```

<br>

- Which event is used to prevent any jQuery code from running before the document is finished loading?
  - document가 로딩되기 전에 jQuery 코드가 실행되지 않도록 방지하는 이벤트가 어떤 것인가?

> [ ] function
>
> [ ] `ready`
>
> [ ] start
>
> [ ] load

<br>

- Which symbol is used to access jQuery?
  - jQuery에 액세스하는 데 사용되는 기호는 어떤 것인가?

> [ ] #
>
> [ ] ()
>
> [ ] %
>
> [ ] `$`

<br>

- Fill in the blanks to call the show() function for the element with the id="menu".
  - 빈간을 채워서 id="menu" element에 대해 show() 함수를 호출해라.

```js
$("#menu").show()
```

<br>