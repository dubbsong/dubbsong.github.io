---
layout: post
title: "(Overview 03) 선택자(Selector)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## Selectors

###### jQuery 선택자

<br>

- Let's have a look at all jQuery selectors.
  - 모든 jQuery selector를 살펴보자.
- As you have seen in the previous lesson, the jQuery selectors start with the `dollar sign` and `parentheses`: $().
  - jQuery 선택자는 `달러 기호`와 `괄호`로 시작한다: `$()`
- The most basic selector is the element selector, which selects all the elements based on the element neme.
  - 가장 기본 선택자는 element 선택자다.
  - 이는 element 이름을 기반으로 모든 element를 선택한다.

```js
$("div")	// 모든 <div> element를 선택한다
```

<br>

- Next are the id and class selectors, which select the elements by their id and class name:
  - 다음은 id와 class 이름으로 element를 선택한다.

```js
$("#test")	// id="test" element를 선택한다
$(".menu")	// class="menu" element를 선택한다
```

<br>

- You can also use the following syntax for selectors:
  - 선택자에 대해 다음 구문을 사용할 수도 있다.

```js
$("div.menu")	// class="menu"인 모든 <div>를 선택한다
$("p:first")	// 첫 번째 <p> element를 선택한다
$("h1, p")	// 모든 <h1> element와 모든 <p> element를 선택한다
$("div p")	// <div> element의 자손(descendants) 중 모든 <p> element를 선택한다
$("*")	// DOM의 모든 element를 선택한다
```

<br>

> Selectors make accessing HTML DOM elements easy compared to pure JavaScript.
>
> 순수 JavaScript에 비해, 선택자는 HTML DOM element에 쉽게 액세스할 수 있게 한다.

------

<br>

## Useful Selectors

###### 유용한 선택자들

<br>

![img](/assets/img/jquery-sololearn-overview-03-01.png)

------

<br>

## QUIZ

- Which of the following selects all elements with class="demo"?
  - 다음 중 class="demo" element를 선택하는 것은 무엇인가?

> [ ] $("demo")
>
> [ ] $("#demo")
>
> [ ] `$(".demo")`

<br>

- Select all \<a> links which are inside paragraph tags.
  - p 태그 내에 있는 모든 \<a> 링크를 선택해라.

```js
$("p a")
```

<br>

- Select all elements that are direct children of div elements.
  - div element의 자식(children)인 모든 element를 선택해라.

```js
$("div > *")
```

<br>