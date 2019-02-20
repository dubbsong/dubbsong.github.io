---
layout: post
title: "(Overview 03) jQuery 선택자"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## Selectors

###### jQuery 선택자

<br>

- Let's have a look at all jQuery selectors.
  - 모든 jQuery 선택자를 살펴보자.
- As you have seen in the previous lesson, the jQuery selectors start with the `dollar sign` and `parentheses`: `$()`
  - jQuery 선택자는 `달러 기호`와 `괄호`로 시작한다: `$()`
- The most basic selector is the element selector, which selects all the elements based on the element name.
  - 가장 기본적인 선택자는 element 선택자다.
  - 이는 element 이름을 기반으로 모든 element를 선택한다.

```js
$("div");	// 모든 <div> element를 선택한다.
```

<br>

- Next are the id and class selectors, which select the elements by their id and class name:
  - 다음은 id와 class 선택자다.
  - 이는 id와 class 이름으로 element를 선택한다.

```js
$("#test");	// id="test" element를 선택한다.
$(".menu");	// class="menu" element를 선택한다.
```

<br>

<br>

- You can also use the following syntax for selectors:
  - 선택자로 다음 구문을 사용할 수도 있다.

```js
$("div.menu");	// class="menu"인 모든 <div> element
$("p:first");	// 첫 번째 <p> element
$("h1, p");	// 모든 <h1> element와 모든 <p> element
$("div p");	// <div> element의 자손인 모든 <p> element
$("*");	// DOM의 모든 element
```

<br>

> Selectors make accessing HTML DOM elements easy compared to pure JavaScript.
>
> 선택자를 사용하면 순수 JavaScript에 비해 HTML DOM element에 쉽게 액세스할 수 있다.

------

<br>

## Useful Selectors

###### 유용한 선택자

<br>

```js
$("*");	// 모든 element
$("#div");	// id="div" element
$(".div");	// class="div element
$("p");	// 모든 <p> element
$("h1, h2, h3");	// 모든 <h1>, <h2>, <h3> element
$("h1:first");	// 첫 번째 <h1> element
$("h1:last");	// 마지막 <h1> element
$("b:first-child");	// parent의 첫 번째 child인 모든 <b> element
$("b:last-child");	// parent의 마지막 child인 모든 <b> element
$("div:nth-child(2)");	// parent의 두 번째 child인 모든 <div> element
$("div > p");	// <div> element의 직접적인 child인 모든 <p> element
$("span p");	// <span> element의 자손인 모든 <p> element
$("ul li:eq(2)");	// list의 세 번째 element (index는 0에서 시작)
$(":contains('solo')");	// 텍스트 'solo'가 포함된 모든 element
$("[src]");	// src 속성을 가진 모든 element
$(":input");	// 모든 input element
$(":text");	// type="text"인 모든 input element
```

------

<br>

## QUIZ

- Which of the following selects all elements with class="demo"?
  - 다음 중 모든 class="demo" element를 선택하는 것은 무엇인가?

> [ ] $("#demo")
>
> [ ] $("demo")
>
> [ ] `$(".demo")`

<br>

- Select all \<a> links which are inside paragraph tags.
  - p 태그 내의 모든 \<a> link를 선택해라.

```js
$("p a");
```

<br>

- Select all elements that are direct children of div elements.
  - div element의 직접적인 children인 모든 element를 선택해라.

```js
$("div > *");
```

<br>