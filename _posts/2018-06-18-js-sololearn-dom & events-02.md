---
layout: post
title: "(DOM & Events 02) element 선택하기"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## Selecting Elements

###### element 선택하기

<br>

- All HTML elements are `objects`.
  - 모든 HTML element는 `객체`다.
- And as we know every object has `properties` and `methods`.
  - 모든 객체는 `속성`과 `메소드`를 가진다.
- The `document object` has methods that allow you to select the desired HTML element.
  - `document 객체`에는 원하는 HTML element를 선택할 수 있는 메소드가 있다.
- These three methods are the most commonly used for selecting HTML elements.
  - 아래 세 가지 메소드는 HTML element를 선택하는 데 가장 일반적으로 사용된다.

```js
// id로 element를 찾는다
document.getElementById(id)

// class로 element를 찾는다
document.getElementsByClassName(name)

// tag로 element를 찾는다
document.getElementsByTagName(name)
```

<br>

- In the example below, the `getElementById` method is used to select the element with `id="demo"` and change its content:
  - 아래 예제에서 `getElementById` 메소드는 `id="demo"` element를 선택하고, 그 내용을 변경하는 데 사용된다.

```js
var elem = document.getElementById("demo");
elem.innerHTML = "Hello World!";
```

<br>

> The example above assumes that the HTML contains an element with id="demo", for example \<div id="demo">\</div>.
>
> 위 예제에서는 \<div id="demo">\</div>가 HTML에 포함되어 있다고 가정한다.

<br>

<br>

- The `getElementsByClassName()` method returns a collection of all elements in the document with the specified class name.
  - `getElementsByClassName()` 메소드는 document에서 지정된 class name을 가진 모든 element를 반환한다.
- For example, if our HTML page contained three elements with class="demo", the following code would return all those elements as an array:
  - 예를 들어, HTML 페이지에 세 개의 class="demo" element가 포함된 경우, 다음 코드는 이 모든 element를 배열로 반환한다.

```js
var arr = document.getElementsByClassName("demo");
```

<br>

- Similarly, the `getElementsByTagName` method returns all of the elements of the specified tag name as an array.
  - 마찬가지로, `getElementsByTagName` 메소드는 지정된 tag name의 모든 element를 배열로 반환한다.
- The following example gets all paragraph elements of the page and changes their content:
  - 다음 예제는 페이지의 모든 p element를 가져와서, 그 내용을 변경한다.

```html
<p>hi</p>
<p>hello</p>
<p>hi</p>

<script>
   var arr = document.getElementsByTagName("p");
   
   for (var i = 0; i < arr.length; i++) {
      arr[i].innerHTML = "Hi there";
   }
</script>
```

<br>

- The script will result in the following HTML:
  - script는 다음과 같은 HTML이 된다.

```html
<p>Hi there</p>
<p>Hi there</p>
<p>Hi there</p>
```

<br>

> We used the `length` property of the array to loop through all the selected elements in the above example.
>
> 위 예제에서는 선택한 element를 모두 순환하기 위해서 배열의 `length` 속성을 사용했다.

------

<br>

## Working with DOM

###### DOM 작업

- Each element in the DOM has a set of properties and methods that provide information about their relationships in the DOM:
  - DOM의 각 element에는 DOM에서의 관계에 대한 정보를 제공하는 속성과 메소드 집합이 있다.
- element.`childNodes` returns an array of an element's child nodes.
  - element.`childNodes`는 element의 child(자식) node의 배열을 반환한다.
- element.`firstChild` returns the first child node of an element.
  - element.`firstChild`는 element의 첫 번째 child(자식) node를 반환한다.
- element.`lastChild` returns the last child node of an element.
  - element.`lastChild`는 element의 마지막 child(자식) node를 반환한다.
- element.`hasChildNodes` returns true if an element has any child nodes, otherwise false.
  - element.`hasChildNodes`는 element에 child(자식) node가 있으면 true를 반환하고, 그렇지 않으면 false를 반환한다.
- element.`nextSibling` returns the next node at the same tree level.
  - element.`nextSibling`은 동일한 트리 레벨에서 다음 node를 반환한다.
- element.`previousSibling` returns the previous node at the same tree level.
  - element.`previousSibling`은 동일한 트리 레벨에서 이전 node를 반환한다.
- element.`parentNode` returns the parent node of an element.
  - element.`parentNode`는 element의 parent(부모) node를 반환한다.

<br>

- We can, for example, select all child nodes of an element and change their content:
  - 예를 들어, element의 모든 child(자식) node를 선택하고, 그 내용을 변경할 수 있다.

```html
<html>
   ...
   <body>
      <div id="demo">
         <p>some text</p>
         <p>some other text</p>
      </div>
      
      <script>
         function setText() {
            var a = document.getElementById("demo");
            var arr = a.childNodes;
            
            for (var i = 0; i < arr.length; i++) {
               arr[i].innerHTML = "new text";
            }
         }
         
         setTimeout(setText, 500);
      </script>
   </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/951/#js)

<br>

> The code above changes the text of both paragraphs to "new text".
>
> 위 코드는 두 p의 텍스트를 "new text"로 변경한다.

------

<br>

## QUIZ

- Fill in the blanks to select the element with id="text" and change its content to "Hi".
  - id="text" element를 선택하고, 그 내용을 "Hi"로 변경해라.

```js
var ob = document.getElementById("text");
ob.innerHTML = "Hi";
```

<br>

- Fill in the blanks to select all div elements and alert the content of the third div.
  - 모든 div element를 선택하고, 세 번째 div의 내용을 alert 해라.

```js
var arr = document.getElementsByTagName("div");
alert(arr[2].innerHTML);
```

<br>

- Can a node in the DOM have multiple parent nodes?
  - DOM에서 node는 여러 개의 parent(부모) node를 가질 수 있는가?

> `No`

<br>
