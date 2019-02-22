---
layout: post
title: "(Manipulate DOM 01) The DOM"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## The DOM

- When you open any webpage in a browser, the HTML of the page is loaded and rendered visually on the screen.
  - 브라우저에서 웹페이지를 열면 페이지의 HTML이 로딩되고, 화면에 시각적으로 렌더링 된다.
- To accomplish this, the browser builds the `Document Object Model(DOM)` of that page, which is an object oriented model of its logical structure.
  - 이를 위해 브라우저는 해당 페이지의 `Document 객체 모델(DOM)`을 구축한다.
  - `DOM`은 논리적 구조의 객체 지향 모델이다.
- The DOM of an HTML document can be represented as a nested set of boxes:
  - HTML document의 DOM은 중첩된 상자 집합으로 나타낼 수 있다.

![img](/assets/img/jquery-sololearn-manipulate dom-01-01.png)

<br>

- The DOM represents a document as a `tree` structure where HTML elements are interrelated nodes in the tree.
  - DOM은 document를 `tree` 구조로 나타낸다.
  - HTML element는 tree에서 상호 연결된 node이다.
- Nodes can have `child` nodes.
  - node는 `child(자식)` node를 가질 수 있다.
- Nodes on the same tree level are called `siblings`.
  - 동일한 tree level의 node를 `siblings(형제)`라고 한다.
- jQuery `traversing` is the term used to describe the process of moving through the DOM and finding(selecting) HTML elements based on their relation to other elements.
  - jQuery `순회`는 HTML element를 찾는(선택하는) 과정을 설명하는 용어이다.
  - DOM을 통한 이동과, 다른 element와의 관계를 기반으로 한다.

<br>

> jQuery makes it easy to traverse the DOM and work with HTML elements.
>
> jQuery를 사용하면 DOM을 쉽게 순회할 수 있다.

------

<br>

## DOM Traversal

###### DOM 순회

<br>

- For example, consider the HTML represented by the following structure:
  - 예를 들어, 다음 구조로 나타낸 HTML을 살펴보자.

![img](/assets/img/jquery-sololearn-manipulate dom-01-02.jpeg)

<br>

- The \<html> element is the `parent` of \<body> and an `ancestor` of everything below it.
  - \<html> element는 \<body>의 `parent(부모)`이다.
  - 그리고 그 아래 모든 element의 `ancestor(조상)`이다.
- The \<body> element is the `parent` of the \<h1> and \<a> elements.
  - \<body> element는 \<h1>과 \<a> element의 `parent(부모)`이다.
- The \<h1> and \<a> elements are `child` elements of the \<body> element and `descendants` of \<html>.
  - \<h1>과 \<a> element는 \<body> element의 `child(자식)` element이다.
  - 그리고 \<html>의 `descendants(자손)`이다.
- The \<h1> and \<a> elements are `siblings`.
  - \<h1>과 \<a> element는 `siblings(형제)`이다.

<br>

> Understanding the relationship between the DOM elements is important to be able to traverse the DOM correctly.
>
> DOM을 올바르게 순회하기 위해, DOM element 간의 관계를 이해하는 것이 중요하다.

------

<br>

## QUIZ

- What kind of structure does the DOM have?
  - DOM은 어떤 종류의 구조를 가지는가?

> `tree`

<br>

- Elements that share the same parent are called:
  - 동일한 parent(부모)를 공유하는 element를 ...라고 한다.

> `siblings(형제)`

<br>
