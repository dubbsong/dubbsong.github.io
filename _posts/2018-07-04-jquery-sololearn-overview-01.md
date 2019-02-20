---
layout: post
title: "(Overview 01) What is jQuery?"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## What is jQuery?

- `jQuery` is a fast, small, and feature-rich `JavaScript library`.
  - `jQuery`는 빠르고, 작고, 기능이 풍부한 `JavaScript 라이브러리`다.
- It makes things like HTML document traversal and manipulation, event handling, and animation much simpler.
  - HTML document 순회 및 조작, 이벤트 핸들링, 애니메이션을 보다 단순하게 만든다.

<br>

- All the power of jQuery is accessed via JavaScript, so having a strong grasp of JavaScript is essential for understanding, and debugging your code.
  - jQuery의 모든 기능은 JavaScript를 통해 액세스 된다.
  - 그러므로 JavaScript에 대한 이해, 구조, 디버깅이 필수적이다.

<br>

<br>

- First, let's take a look at an example HTML manipulation with `JavaScript`.
  - 먼저, `JavaScript`로 HTML을 조작하는 예제를 살펴보자.
- To get the element with the id="start" and change its html to "Go" we will need to do the following:
  - id="start" element를 가져와 html을 "Go"로 변경하려면 다음을 수행해야 한다.

```js
var el = document.getElementById("start");
el.innerHTML = "Go";
```

<br>

- To do the same manipulation with `jQuery`, we need just a single line of code:
  - `jQuery`로 동일한 조작을 수행하기 위해서는, 코드 한 줄만 필요하다.

```js
$("#start").html("Go");
```

<br>

- As you can see, the code is much shorter and easier to understand.
  - 보다시피, 코드가 훨씬 짧고 이해하기 쉽다.

<br>

> Another great advantage of jQuery is that you do not need to worry about browser support, your code will run exactly the same in all major browsers, including Internet Explorer 6.
>
> jQuery의 또 다른 장점은, 브라우저 지원에 대해 걱정할 필요가 없다는 것이다.
>
> IE6를 포함한 모든 주요 브라우저에서 코드가 동일하게 실행된다.

------

<br>

## QUIZ

- What is jQuery?
  - jQuery란 무엇인가?

> `JS Library`
>
> JavaScript 라이브러리

<br>

- Fill in the blanks to change the elements HTML to "Test" using pure JavaScript.
  - 순수 JavaScript를 사용해서 HTML을 "Test"로 변경해라.

```js
var e = document.getElementById("test")
e.innerHTML = "Test";
```

<br>