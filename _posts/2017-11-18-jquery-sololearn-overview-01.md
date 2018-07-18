---
layout: post
title: "SoloLearn jQuery 번역 - 01. What is jQuery (Overview)"
categories: dev
tags: html
---

## What is jQuery

###### jQuery란 무엇인가?

<br>

- `jQuery` is a fast, small, and feature-rich `JavaScript library`.
  - `jQuery`는 빠르고, 작고, 기능이 풍부한 `JavaScript 라이브러리`이다.
- It makes things like HTML document traversal and manipulation, event handling, and animation much simpler.
  - HTML document 순회, 조작, 이벤트 핸들러, 애니메이션을 보다 간단하게 한다.

<br>

- All the power of jQuery is accessed via JavaScript, so having a strong grasp of JavaScript is essential for understanding, structuring, and debugging your code.
  - JavaScript를 통해 jQuery의 모든 기능에 접근할 수 있으므로, JavaScript에 대한 깊은 이해, 구조화, 디버깅이 필수적이다.

------

<br>

## What is jQuery 02

- First, let's take a look at an example HTML manipulation with `JavaScript`.
  - 먼저, `JavaScript`를 사용한 HTML 조작 예제를 살펴보자.
- To get the element with the id="start" and change its html to "Go" we will need to do the following:
  - id="start" element를 가져오고, html을 "Go"로 변경하려면, 다음을 수행해야 한다.

```js
var el = document.getElementById("start");
el.innerHTML = "Go";
```

<br>

- To do the same manipulation with `jQuery`, we need just a single line of code:
  - `jQuery`를 사용해서 동일한 조작을 하려면, 한 줄의 코드만 필요하다.

```js
$("#start").html("Go");
```

<br>

- You will learn about the new syntax in the coming lessons, but as you can see, the code is much shorter and easier to understand.
  - 보다시피, 더 짧고 이해하기 쉬운 새로운 구문을 배우게 될 것이다.

<br>

> Another great advantage of jQuery is that you do not need to worry about browser support, your code will run exactly the same in all major browsers, including Internet Explorer 6.
>
> jQuery의 또 다른 장점은, 브라우저 지원에 대한 걱정이 필요가 없고, Internet Explorer 6를 포함한 모든 주요 브라우저에서 코드가 동일하게 실행된다는 것이다.

------

<br>

## QUIZ

- What is jQuery?
  - jQuery가 무엇인가?

> [ ] JS Function
>
> [ ] `JS Library`
>
> [ ] Programming Language

<br>

- Fill in the blanks to change the elements HTML to "Test" using pure JavaScript.
  - 순수한 JavaScript를 사용해서 element HTML을 "Test"로 변경해라.

```js
var e = document.getElementById("text");
e.innerHTML = "Test";
```

<br>
