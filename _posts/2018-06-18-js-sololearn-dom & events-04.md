---
layout: post
title: "(DOM & Events 04) element 추가 & 제거하기"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## Creating Elements

###### element 생성하기

<br>

- Use the following methods to create new nodes:
  - 새 node를 생성하기 위해 다음 메소드를 사용한다.

<br>

- element.`cloneNode()` clones an element and returns the resulting node.
  - element.`cloneNode()`는 element를 복제하고, 결과 node를 반환한다.
- document.`createElement(element)` creates a new element node.
  - document.`createElement(element)`는 새 element node를 생성한다.
- document.`createTextNode(text)` creates a new text node.
  - document.`createTextNode(text)`는 새 text node를 생성한다.

<br>

- For example:

```js
var node = document.createTextNode("some new text");
```

<br>

- This will create a new text node, but it will not appear in the document until you append it to an existing element with one of the following methods:
  - 이렇게 하면 새 text node가 생성되지만, 다음 메소드 중 하나를 사용해서 기존 element에 추가할 때까지 document에 나타나지 않는다.

<br>

- element.`appendChild(newNode)` adds a new child node to an element as the last child node.
  - element.`appendChild(newNode)`는 새로운 child node를 element에 마지막 child node로 추가한다.
- element.`insertBefore(node1, node2)` inserts node1 as a child before node2.
  - element.`insertBefore(node1, node2)`는 node1을 child node로 node2 앞에 삽입한다.

<br>

- Example:

```html
<div id="demo">
   some content
</div>

<script>
   // 새로운 p 생성하기
   var p = document.createElement("p");
   var node = document.createTextNode("some new text");
   
   // p에 text 추가하기
   p.appendChild(node);
   
   var div = document.getElementById("demo");
   
   // div에 p 추가하기
   div.appendChild(p);
</script>
```

[코드 실행 확인](https://code.sololearn.com/958/#js)

> This creates a new paragraph and adds it to the existing div element on the page.
>
> 이렇게 하면 새 p가 생성되고, 페이지의 기존 div element에 추가된다.

<br>

- Result:

```html
<div id="demo">
   some content
   <p>Some new text</p>
</div>
```

------

<br>

## Removing Elements

###### element 제거하기

<br>

- To remove an HTML element, you must select the parent of the element and use the `removeChild(node)` method.
  - HTML element를 제거하기 위해 element의 parent를 선택하고, `removeChild(node)` 메소드를 사용해야 한다.

```html
<div id="demo">
   <p id="p1">This is a paragraph. </p>
   <p id="p2">This is another paragraph. </p>
</div>

<script>
   var parent = document.getElementById("demo");
   var child = document.getElementById("p1");
   parent.removeChild(child);
</script>
```

[코드 실행 확인](https://code.sololearn.com/958/#js)

<br>

- This removes the paragraph with id="p1" from the page.
  - 이는 id="p1" p가 페이지에서 제거된다.

<br>

> An alternative way of achieving the same result would be the use of the `parentNode` property to get the parent of the element we want to remove:
>
> 동일한 결과를 얻는 또 다른 방법은, `parentNode` 속성을 사용해서 제거하려는 element의 parent를 가져오는 것이다.

> var child = document.getElementById("p1");
>
> child.parentNode.removeChild(child);

------

<br>

## Replacing Elements

###### element 대체하기

<br>

- To replace an HTML element, the element.`replaceChild(newNode, oldNode)` method is used.
  - HTML element를 대체하기 위해 element.`replaceChild(newNode, oldNode)` 메소드가 사용된다.

```html
<div id="demo">
   <p id="p1">This is a paragraph. </p>
   <p id="p2">This is another paragraph. </p>
</div>

<script>
   var p = document.createElement("p");
   var node = document.createTextNode("This is new");
   p.appendChild(node);
   
   var parent = document.getElementById("demo");
   var child = document.getElementById("p1");
   parent.replaceChild(p, child);
</script>
```

[코드 실행 확인](https://code.sololearn.com/960/#js)

<br>

> The code above creates a new paragraph element that replaces the existing p1 paragraph.
>
> 위 코드는 기존 p1 p를 대체하는 새로운 p element를 생성한다.

------

<br>

## QUIZ

- Drag and drop from the options below to add a new \<li> element to the unordered list with id="list".
  - id="list"를 사용해서 ul에 새 \<li> element를 추가해라.

```js
var el = document.createElement("li");
var txt = document.createTextNode("B");
el.appendChild(txt);

var ul = document.getElementById("list");
ul.appendChild(el);
```

<br>

- Drag and drop from the options below to remove the node element from the page (par is node's parent).
  - 페이지에서 node element를 제거해라.
  - (par는 node의 parent이다)

```js
var par = document.getElementById("par");
var node = document.getElementById("node");
par.removeChild(node);
```

<br>

- Which method is used to replace nodes?
  - node를 대체하는 데 사용되는 메소드는 무엇인가?

> `replaceChild`

<br>