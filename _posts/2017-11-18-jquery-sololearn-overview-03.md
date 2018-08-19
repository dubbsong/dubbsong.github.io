---
layout: post
title: "03. selector (Overview)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

# jQuery Selectors

###### jQuery Selector

<br>

- Let's have a look at all jQuery selectors.
  - 모든 jQuery selector를 살펴보자.
- As you have seen in the previous lesson, the jQuery selectors start with the `dolloar sign` and `parentheses`: `$` and `()`.
  - 이전 레슨에서 보았듯이, jQuery selector는 `$`와 `()`로 시작한다.
- The most basic selector is the element selector, which selects all the elements based on the element name.
  - 가장 기본적인 selector는 element 이름을 기반으로 모든 element를 선택하는 element selector이다.

```js
$("div")	// 모든 <div> element를 선택한다
```

<br>

- Next are the id and class selectors, which select the elements by their id and class name:
  - 다음은 id와 class selector로, id와 class 이름으로 element를 선택한다.

```js
$("#test")	// id="test" element를 선택한다
$(".menu")	// class="menu" element를 선택한다
```

<br>

<br>

- You can also use the following syntax for selectors:
  - selector에 대해 다음 문법을 사용할 수도 있다.

```js
$("div.menu")	// 모든 <div> class="menu" element를 선택한다
$("p:first")	// 첫 번째 <p> element를 선택한다
$("h1, p")	// 모든 <h1> element와 모든 <p> element를 선택한다
$("div p")	// <div> element의 자손인 모든 <p> element를 선택한다
$("*")		// DOM의 모든 element를 선택한다
```

<br>

- `DOM`: Stands for Document Object Model and is a standard object model and programming interface for HTML.
  - Document Object Model의 약자로,
  - HTML에 대한 표준 객체 모델 및 프로그래밍 인터페이스이다.

<br>

> Selectors make accessing HTML DOM elements easy compared to pure JavaScript.
>
> selector를 사용하면, 순수 JavaScript에 비해 HTML DOM element에 쉽게 액세스 할 수 있다.

------

<br>

## Useful Selectors

###### 유용한 selector

<br>

![sololearn img](/assets/img/sololearn-jquery-overview-03-01.jpeg)

------

<br>

## QUIZ

- Which of the following selects all elements with class="demo"?
  - 모든 class="demo" element를 선택하는 것은 무엇인가?

> `$(".demo")`

<br>

- Select all \<a> links which are inside paragraph tags.
  - p 태그 안에 있는 모든 \<a> 링크를 선택해라.

> `$("p a")`

<br>

- Select all elements that are direct children of div elements.
  - div element의 바로 하위인 모든 element를 선택해라.

> `$("div > *")`

<br>













