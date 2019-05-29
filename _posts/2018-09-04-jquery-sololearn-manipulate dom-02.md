---
layout: post
title: "(Manipulate DOM 02) DOM 순회"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## DOM Traversal

###### DOM 순회

<br>

- jQuery has many useful methods for DOM traversal.
  - jQuery에는 DOM 순회를 위한 여러 유용한 메소드가 있다.
- The `parent()` method returns the direct parent element of the selected element.
  - `parent()` 메소드는, 선택된 element의 직접적인 parent element를 반환한다.

<br>

- HTML:

```html
<div> div element
  <p>paragraph</p>
</div>
```

<br>

- JS:

```js
var e = $("p").parent();
e.css("border", "2px solid red");
```

[코드 실행 확인](https://code.sololearn.com/1122/#js)

<br>

<br>

- The `parent()` method can only traverse a single level up the DOM tree.
  - `parent()` 메소드는 DOM tree의 한 level만 순회할 수 있다.
- To get all ancestors of the selected element you can use the `parents()` method.
  - 선택된 element의 모든 ancestors를 가져오기 위해, `parents()` 메소드를 사용한다.

<br>

- HTML:

```html
<body> body
  <div style="width:300px"> div
    <ul> ul
      <li> li
        <p>paragraph</p>
      </li>
    </ul>
  </div>
</body>
```

<br>

- JS:

```js
$(function() {
  var e = $("p").parents();
  e.css("border", "2px solid red");
});
```

[코드 실행 확인](https://code.sololearn.com/1123/#js)

<br>

- Some of the most used traversal methods are presented below:
  - 가장 많이 사용되는 순회 메소드는 다음과 같다.

<br>

- `parent()`: direct parent element of the selected element
  - 선택된 element의 직접적인 parent element를 선택한다.
- `parents()`: all ancestor elements of the selected element
  - 선택된 element의 모든 ancestor(조상) element를 선택한다.
- `children()`: all direct children of the selected element
  - 선택된 element의 모든 직접적인 children(자식) element를 선택한다.
- `siblings()`: all sibling elements
  - 모든 sibilng(형제) element를 선택한다.
- `next()/nextAll()`: next/all next sibling element/s
  - 선택된 element의 다음/모든 다음 sibling(형제) element를 선택한다.
- `prev()/prevAll()`: previous/all previous sibling element of the selected element
  - 선택된 element의 이전/모든 이전 sibling(형제) element를 선택한다.
- `eq()`: element with a specific index number of the selected elements
  - 선택된 element의 특정 index 번호를 가지는 element를 선택한다.

<br>

<br>

- The `eq()` method can be used to select a specific element from multiple selected elements.
  - `eq()` 메소드는, 여러 선택된 element에서 특정 element를 선택하는 데 사용할 수 있다.
- For example, if the page contains multiple div elements and we want to select the third one:
  - 예를 들어, 페이지에 여러 div element가 있고, 세 번째 element를 선택하려는 경우는 다음과 같다.

```js
$("div").eq(2);
```

<br>

> The index numbers start at 0, so the first element will have the index number 0.
>
> index는 0에서 시작하므로, 첫 번째 element는 index 0을 가진다.

------

<br>

## QUIZ

- Which element is the parent of the \<p> element in the following HTML?
  - 다음 HTML에서 \<p> element의 parent는 무엇인가?

```html
<div><ul>
<li><p></p></li>
</ul></div>
```

> `<li>`

<br>

- Fill in the blanks to select all siblings of the div element and call the hide() method on them.
  - div element의 모든 siblings(형제)를 선택하고, hide() 메소드를 호출해라.

```js
var items = $("div").siblings();
items.hide();
```

<br>

- What is the output of this code?
  - 다음 코드의 출력은 무엇인가?

```html
<p>a</p><p>b</p><p>c</p>

<script>
  alert($("p").eq(1).text());
</script>
```

> `b`

<br>