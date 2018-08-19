---
layout: post
title: "01. jQuery란 무엇인가? (Overview)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

# What is jQuery?

###### jQuery란 무엇인가?

<br>

- `jQuery` is a fast, small, and feature-rich `JavaScript library`.
  - `jQuery`는 빠르고, 작고, 기능이 풍부한 `JavaScript 라이브러리`이다.
- It makes things like HTML document traversal and manipulation, event handling, and animation much simpler.
  - HTML 문서 순회 및 조작, 이벤트 핸들링, 애니메이션을 훨씬 단순하게 만든다.

<br>

- All the power of jQuery is accessed via JavaScript, so having a strong grasp of JavaScript is essential for understanding, structuring, and debugging your code.
  - jQuery의 모든 기능은 JavaScript를 통해 액세스 된다.
  - 그래서 JavaScript에 대한 코드를 이해하고, 구조화하고, 디버깅하는 깊은 이해가 필수적이다.

<br>

<br>

- First, let's take a look at an example HTML manipulation with `JavaScript`.
  - 먼저, `JavaScript`로 HTML을 조작하는 예제를 살펴보자.
- To get the element with the id="start" and change its html to "Go" we will need to do the following:
  - id="start" element를 가져오고, html을 "Go"로 변경하려면 다음을 수행해야 한다.

```js
var el = document.getElementById("start");
el.innerHTML = "Go";
```

<br>

- To do the same manipulation with `jQuery`, we need just a single line of code:
  - `jQuery`를 사용해서 동일한 조작을 수행하려면, 한 줄의 코드만 있으면 된다.

```js
$("#start").html("Go");
```

<br>

- You will learn about the new syntax in the coming lessons, but as you can see, the code is much shorter and easier to understand.
  - 앞으로의 레슨에서 새로운 구문을 배우게 될 것이다.
  - 보다시피, 코드가 더 짧고 이해하기 쉽다.

<br>

> Another great advantage of jQuery is that you do not need to worry about browser support, your code will run exactly the same in all major browser, including Internet Explorer 6.
>
> jQuery의 또 다른 장점은, 브라우저 지원에 대해서 걱정할 필요가 없다는 것이다.
>
> Internet Explorer 6(IE6)를 포함한 모든 주요 브라우저에서 코드가 동일하게 실행된다.

------

<br>

## QUIZ

- What is jQuery?
  - jQuery란 무엇인가?

> `JS Library`

<br>

- Fill in the blanks to change the elements HTML to "Test" using pure JavaScript.
  - 순수 JavaScript를 사용해서 HTML element를 "Test"로 변경해라.

```js
var e = document.getElementById("test");
e.innerHTML = "Test";
```

<br>