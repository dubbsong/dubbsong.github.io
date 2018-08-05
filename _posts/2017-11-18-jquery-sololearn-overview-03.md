---
layout: post
title: "03. Selectors (Overview)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com) jQuery 번역

<br>

# jQuery Selectors

###### jQuery selector

<br>

- As you have seen in the previous lesson, the jQuery selectors start with the `dollar sign` and `parantheses`: `$` and `()`.
  - 이전 레슨에서 보았듯이, jQuery selector는 `$`와 `()`로 시작한다.
- The most basic selector is the element selector, which selects all the elements based on the element name.
  - 가장 기본적인 selector는 element selector이며, element name을 기반으로 모든 element를 선택한다.

```js
$("div")	// selects all <div> elements
```

<br>

- Next are the id and class selectors, which select the elements by their id and class name:
  - 다음은 id name과 class name으로 element를 선택한다.

```js
$("#test")	// select the element with the id="test"
$(".menu")	// selects all elements with class="menu"
```

<br>

- You can also use the following syntax for selectors:
  - selector에 대해서 다음 문법을 사용할 수도 있다.

```js
$("div.menu")	// all <div> elements with class="menu"
$("p:first")	// the first <p> element
$("h1, p")	// all <h1> and all <p> element
$("div p")	// all <p> elements that are descendants of a <div> element
$("*")		// all elements of the DOM
```

<br>

> Selectors make accessing HTML DOM elements easy compared to pure JavaScript.
>
> selector는 순수 JavaScript에 비해, HTML DOM element에 쉽게 액세스할 수 있다.

------

<br>

## Useful Selectors

###### 유용한 selector

<br>

![sololearn img](/assets/img/sololearn-jquery-overview-03-01.png)

------

<br>

## QUIZ

- Which of the following selects all elements with class="demo"?
  - 모든 class="demo" element를 선택하는 것은 어떤 것인가?

> $("#demo")
>
> $("demo")
>
> `$(".demo")`

<br>

- Select all \<a> links which are inside paragraph tags.
  - p 태그 내의 모든 \<a> 링크를 선택해라.

```js
$("p a")
```

<br>

- Select all elements that are direct children of div elements.
  - div element의 모든 자식 element를 선택해라.

```js
$("div > *")
```

<br>