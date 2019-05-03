---
layout: post
title: "(Overview 03) 선택자"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## Selectors

###### 선택자

<br>

- The most basic selector is the element selector, which selects all the elements based on the element name.
  - 가장 기본적인 선택자는 element 선택자이다.
  - element 이름을 기반으로 모든 element를 선택한다.

```js
$("div")	// 모든 <div> element를 선택한다.
```

<br>

- Next are the id and class selectors, which select the elements by their id and class name:
  - 다음은 id와 class 선택자이다.
  - id와 class 이름으로 element를 선택한다.

```js
$("#test")	// id="test" element를 선택한다.
$(".menu")	// class="menu" element를 선택한다.
```

<br>

- You can also use the following syntax for selectors:
  - 선택자로 다음 구문을 사용할 수도 있다.

```js
$("div.menu")	// 모든 class="menu" <div> element를 선택한다.
$("p:first")	// 첫 번째 <p> element를 선택한다.
$("h1, p")	// 모든 <h1> element와 모든 <p> element를 선택한다.
$("div p")	// <div> element의 자손인 모든 <p> element를 선택한다.
$("*")	// DOM의 모든 element를 선택한다.
```

<br>

> Selectors make accessing HTML DOM elements easy compared to pure JavaScript.
>
> 선택자는 순수 JS에 비해 HTML DOM element에 쉽게 액세스할 수 있다.

------

<br>

### Useful Selectors

###### 유용한 선택자들

<br>

```js
$("*")	// 모든 element를 선택한다.
$("#div")	// id="div" element를 선택한다.
$(".div")	// 모든 class="div" element를 선택한다.
$("p")	// 모든 <p> element를 선택한다.
$("h1, h2, h3")	// 모든 <h1>, <h2>, <h3> element를 선택한다.
$("h1:first")	// 첫 번째 <h1> element를 선택한다.
$("h1:last")	// 마지막 <h1> element를 선택한다.
$("b:first-child")	// 부모의 첫 번째 자식인 모든 <b> element를 선택한다.
$("b:last-child")	// 부모의 마지막 자식인 모든 <b> element를 선택한다.
$("div:nth-child(2)")	// 부모의 두 번째 자식인 모든 <div> element를 선택한다.
$("div > p")	// <div> element의 직접적인 자식인 모든 <p> element를 선택한다.
$("span p")	// <span> element의 자손인 모든 <p> element를 선택한다.
$("ul li:eq(2)")	// list의 세 번째 element를 선택한다.
$(":contains('solo')")	// 'solo' 텍스트를 포함하는 모든 element를 선택한다.
$("[src]")	// 모든 src 속성 element를 선택한다.
$(":input")	// 모든 input element를 선택한다.
$(":text")	// 모든 type="text" input element를 선택한다.
```

------

<br>

## QUIZ

- Which of the following selects all elements with class="demo"?
  - 모든 class="demo" element를 선택하는 것은 무엇인가?

> [ ] $("#demo")
>
> [ ] $("demo")
>
> [ ] `$(".demo")`

<br>

- Select all \<a> links which are inside paragraph tags.
  - p 태그 내의 모든 \<a> 링크를 선택해라.

> `$("p a")`

<br>

- Select all elements that are direct children of div elements.
  - div element의 직접적인 자식인 모든 element를 선택해라.

> `$("div > *")`

<br>