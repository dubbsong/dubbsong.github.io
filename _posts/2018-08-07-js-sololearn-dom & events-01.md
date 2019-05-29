---
layout: post
title: "(DOM & Events 01) What is DOM?"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## The DOM

###### Document Object Model

<br>

- When you open any webpage in a browser, the HTML of the page is loaded and rendered visually on the screen.
  - 브라우저에서 웹페이지를 열면, 페이지의 HTML이 로딩되고 화면에 시각적으로 렌더링 된다.
- To accomplish that, the browser builds the `Document Object Model (DOM)` of that page, which is an object oriented model of its logical structure.
  - 이를 위해 브라우저는 해당 페이지의 `document 객체 모델 (DOM)`을 구축한다.
- The DOM of an HTML document can be represented as a nested set of boxes:
  - HTML document의 DOM은 중첩된 상자 집합으로 나타낼 수 있다.

![img](/assets/img/js-sololearn-dom & events-01-01.png)

<br>

> JavaScript can be used to manipulate the DOM of a page dynamically to add, delete and modify elements.
>
> JavaScript를 사용해서 페이지의 DOM을 동적으로 조작(element 추가, 제거, 수정)할 수 있다.

------

<br>

## DOM Tree

###### DOM 트리

<br>

- The DOM represents a document as a tree structure.
  - DOM은 트리 구조로 document를 나타낸다.
- HTML elements become interrelated `nodes` in the tree.
  - HTML element는 트리에서 상호 연결된 `node`이다.
- All those nodes in the tree have some kind of relations among each other.
  - 트리에서 모든 node는 서로 간 어떤 종류의 관계를 가진다.
- Nodes can have `child` nodes.
  - node는 `child(자식)` node를 가질 수 있다.
- For example, consider the following structure.
  - 예를 들어, 다음 구조로 나타낸 HTML을 살펴보자.

![img](/assets/img/js-sololearn-dom & events-01-02.png)

<br>

- \<html> has two children.
  - \<html>은 두 개의 children(자식)을 가진다.
- \<head> has one child and one parent.
  - \<head>는 하나의 child(자식)과 하나의 parent(부모)를 가진다.
- \<title> has one parent and no children;
  - \<title>은 하나의 parent(부모)를 가지고, children(자식)은 없다.
- \<body> has two children and one parent.
  - \<body>는 두 개의 children(자식)과 하나의 parent(부모)를 가진다.

<br>

> It is important to understand the relationships between elements in an HTML document in order to be able to manipulate them with JavaScript.
>
> JavaScript로 element를 조작하기 위해서는, HTML document의 element 간 관계를 이해하는 것이 중요하다.

------

<br>

## The document Object

###### document 객체

<br>

- There is a predefined `document object` in JavaScript, which can be used to access all elements on the DOM.
  - JavaScript에는 미리 정의된 `document 객체`가 있다.
  - 이는 DOM의 모든 element에 액세스하는 데 사용할 수 있다.
- In other words, the `document object` is the owner (or `root`) of all objects in your webpage.
  - 즉, 웹페이지에서 `document 객체`는 모든 객체의 owner(또는 `root`)다.
- So, if you want to access objects in an HTML page, you always start with accessing the document object.
  - 따라서 HTML 페이지의 객체에 액세스하려면, 항상 document 객체에서 액세스해야 한다.

```js
document.body.innerHTML = "Some text";
```

<br>

- As `body` is an element of the DOM, we can access it using the `document object` and change the content of the `innerHTML` property.
  - `body`는 DOM의 element이므로, `document 객체`를 사용해서 액세스하고 `innerHTML` 속성의 내용을 변경할 수 있다.

<br>

> The `innerHTML` property can be used on almost all HTML elements to change its content.
>
> `innerHTML` 속성은 거의 모든 HTML element에서 내용을 변경하는 데 사용할 수 있다.

------

<br>

## QUIZ

- What is DOM?
  - DOM이란 무엇인가?

> `Document Object Model`

<br>

- In the following HTML, which element is the parent of h1?
  - 다음 HTML에서 어떤 element가 h1의 parent(부모)인가?

```html
<body>
   <p><h1>Hi</h1></p>
</body>
```

> `p`

<br>

- Select all that apply:
  - 해당되는 모든 것을 선택해라.

> [ ] innerHTML is a method
>
> [ ] body is the root of the DOM
>
> [ ] `innerHTML is a property`
>
> [ ] `The document object is the root of the DOM`

<br>
