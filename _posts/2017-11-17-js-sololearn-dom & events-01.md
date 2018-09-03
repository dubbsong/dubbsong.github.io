---
layout: post
title: "01. DOM이란 무엇인가? (DOM & Events)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# The DOM

###### DOM

<br>

- When you open any webpage in a browser, the HTML of the page is loaded and rendered visually on the screen.
  - 브라우저에서 웹페이지를 열면, 페이지의 HTML이 로딩되고, 화면에서 시각적으로 렌더링 된다.
- To accomplish that, the browser builds the `Document Object Model` of that page, which is an object oriented model of its logical structure.
  - 이를 달성하기 위해, 브라우저는 해당 페이지의 `문서 객체 모델`을 빌드한다.
  - 이는 논리적 구조의 객체 지향 모델이다.
- The DOM of an HTML document can be represented as a nested set of boxes:
  - HTML 문서의 DOM은 중첩된 상자의 집합으로 나타낼 수 있다.
  - `DOM`: Stands for Document Object Model and is a standard object model and programming interface for HTML (Document Object Model의 약자로, HTML을 위한 표준 객체 모델 및 프로그래밍 인터페이스이다)

![sololearn img](/assets/img/sololearn-js-dom & events-01-01.png)

<br>

> JavaScript can be used to manipulate the DOM of a page dynamically to add, delete and modify elements.
>
> JavaScript를 사용하면, 페이지의 DOM을 동적으로 조작해서 element를 추가, 삭제, 수정할 수 있다.

------

<br>

## DOM Tree

###### DOM 트리

<br>

- The DOM represents a document as a tree structure.
  - DOM은 문서를 트리 구조로 나타낸다.
- HTML elements become interrelated `nodes` in the tree.
  - HTML element는 트리의 상호 연결된 `node`가 된다.
- All those nodes in the tree have some kind of relations among each other.
  - 트리에 있는 모든 node는 서로 간 어떤 종류의 관계가 있다.
- Nodes can have `child` nodes.
  - node는 `child` node를 가질 수 있다.
- Nodes on the same tree level are called `siblings`.
  - 동일한 트리 레벨의 node를 `siblings(형제)`라고 한다.
- For example, consider the following structure:
  - 예를 들어, 다음 구조를 생각해보자.

![sololearn img](/assets/img/sololearn-js-dom & events-01-02.png)

<br>

- \<html> has two children (\<head>, \<body>);
  - \<html>에는 두 개의 children이 있다. 
  - (\<head>, \<body>)
- \<head> has one child (\<title>) and one parent (\<html>);
  - \<head>에는 하나의 child(\<title>)와 하나의 parent(\<html>)가 있다.
- \<title> has one parent (\<head>) and no children;
  - \<title>에는 하나의 parent(\<head>)가 있고, children은 없다.
- \<body> has two children (\<h1> and \<a>) and one parent (\<html>);
  - \<body>에는 두 개의 children(\<h1>과 \<a>)과 하나의 parent(\<html>)이 있다.

<br>

> It is important to understand the relationships between elements in an HTML document in order to be able to manipulate them with JavaScript.
>
> JavaScript로 element를 조작할 수 있으려면, HTML 문서의 element 간의 관계를 이해하는 것이 중요하다.

------

<br>

## The document Object

- There is a predefined `document object` in JavaScript, which can be used to access all elements on the DOM.
  - JavaScript에는 DOM의 모든 element에 액세스하는 데 사용되는 미리 정의된 `문서 객체`가 있다.
- In other words, the `document object` is the owner (or `root`) of all objects in your webpage.
  - 즉, `문서 객체`는 웹페이지에서 모든 객체의 소유권자(또는 `root`)이다.
- So, if you want to access objects in an HTML page, you always start with accessing the document object.
  - 따라서, HTML 페이지의 객체에 액세스하려면, 항상 문서 객체에 액세스하는 것으로 시작해야 한다.

<br>

- For example:

```js
document.body.innerHTML = "Some text";
```

<br>

- As `body` is an element of the DOM, we can access it using the `document object` and change the content of the `innerHTML` property.
  - `body`는 DOM의 element이므로, `document object`를 사용해서 body에 액세스할 수 있고, `innerHTML` 속성의 내용을 변경할 수 있다.
  - `innerHTML`: gets or sets the content of HTML elements (HTML element의 내용을 가져오거나 설정한다)

<br>

> The `innerHTML` property can be used on almost all HTML elements to change its content.
>
> `innerHTML` 속성은 거의 모든 HTML element에서 내용을 변경하는 데 사용할 수 있다.

------

<br>

## QUIZ

- What is DOM?
  - DOM이 무엇인가?

> `Document Object Model`
>
> 문서 객체 모델

<br>

- In the following HTML, which element is the parent of h1?
  - 다음 HTML에서, 어떤 element가 h1의 parent인가?

```html
<body>
   <p><h1>Hi</h1></p>
</body>
```

> `p`

<br>

- Select all that apply:
  - 해당되는 모든 것을 선택해라.

> [ ] `innerHTML is a property`
>
> [ ] innerHTML is a method
>
> [ ] body is the root of the DOM
>
> [ ] `The document object is the root of the DOM`

<br>
