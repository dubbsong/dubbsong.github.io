---
layout: post
title: "SoloLearn jQuery 번역 - 01. The DOM (Manipulate DOM)"
categories: dev
tags: jquery
---

## The DOM

###### DOM

<br>

- When you open any webpage in a browser, the HTML of the page is loaded and rendered visually on the screen.
  - 브라우저에서 웹페이지를 열면, 페이지의 HTML이 로딩되고, 화면에서 시각적으로 렌더링 된다.
- To accomplish this, the browser builds the `Document Object Model(DOM)` of that page, which is an object oriented model of its logical structure.
  - 이를 위해 브라우저는 `Document Object Model(DOM)`을 작성한다.
  - 이 페이지는 논리적 구조의 객체 지향 모델이다.
  - `DOM`: Stands for Document Object Model and is a standard object model and programming interface for HTML.
- The DOM of an HTML document can be represented as a nested set of boxes:
  - HTML 문서의 DOM은, 중첩된 상자의 집합으로 표현될 수 있다.

![sololearn img](/assets/img/sololearn-jquery-manipulate dom-01-01.png)

<br>

- The DOM represents a document as a `tree` structure where HTML elements are interrelated nodes in the tree.
  - DOM은 `tree` 구조로 문서를 나타낸다.
  - 여기서 HTML element는 트리에서 상호 연결된 노드이다.
- Nodes can have `child` nodes.
  - 노드는 `하위` 노드를 가질 수 있다.
- Nodes on the same tree level are called `siblings`.
  - 동일한 트리 레벨의 노드를 `형제`라고 한다.
- jQuery `traversing` is the term used to describe the process of moving through the DOM and finding (selecting) HTML elements based on their relation to other elements.
  - jQuery `traversing`은 DOM을 통해 이동하고, 다른 element와의 관계를 기반으로 HTML element를 찾는(선택하는) 과정을 설명하는 데 사용되는 용어이다.

<br>

> jQuery makes it easy to traverse the DOM and work with HTML elements.
>
> jQuery는 DOM을 쉽게 순회할 수 있고, HTML element를 사용해서 쉽게 작업할 수 있다.

------

<br>

## DOM Traversal

###### DOM 순회

<br>

- For example, consider the HTML represented by the following structure:
  - 예를 들어, 다음 구조로 표현된 HTML을 살펴보자.

![sololearn img](/assets/img/sololearn-jquery-manipulate dom-01-02.jpeg)

<br>

- The \<html> element is the `parent` of \<body> and an `ancestor` of everything below it.
  - \<html> element는 \<body>의 `부모`이고, 그 아래에 있는 모든 element의 `조상`이다.
- The \<body> element is the `parent` of the \<h1> and \<a> elements.
  - \<body> element는 \<h1>와 \<a> element의 `부모`이다.
- The \<h1> and \<a> elements are `child` elements of the \<body> element and `descendants` of \<html>.
  - \<h1>과 \<a> element는 \<body> element의 `자식` element이고, \<html>의 `하위` element이다.
- The \<h1> and \<a> elements are `siblings` (they share the same parent).
  - \<h1>과 \<a> element는 `형제`이다.
  - 같은 부모를 공유한다.

<br>

#### Summary

###### 요약

<br>

- An `ancestor` is a parent, grandparent, great-grandparent, and so on.
  - `조상`은 부모, 조부모, 증조부모 등이다.
- A `descendant` is a child, grandchild, great-grandchild, and so on.
  - `자손`은 자식, 손자, 증손자 등이다.
- `Siblings` share the same parent.
  - `형제`는 같은 부모를 공유한다.

<br>

> Understanding the relationship between the DOM elements is important to be able to traverse the DOM correctly.
>
> DOM element 간의 관계를 이해하는 것은, DOM을 올바르게 순회할 수 있도록 하는 것이 중요하다.

------

<br>

## QUIZ

- What kind of structure does the DOM have?
  - DOM에는 어떤 종류의 구조가 있는가?

> [ ] graph
>
> [ ] line
>
> [ ] `tree`

<br>

- Elements that share the same parent are called:
  - 같은 부모를 공유하는 element는 무엇인가?

> [ ] `siblings`
>
> [ ] parents
>
> [ ] ancestors

<br>
