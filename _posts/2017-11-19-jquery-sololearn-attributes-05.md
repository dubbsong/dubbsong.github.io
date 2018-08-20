---
layout: post
title: "05. 내용 추가하기 (Attributes and Content)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

# Adding Content

###### 내용 추가하기

<br>

- As we have seen in the previous lessons, the `html()` and `text()` methods can be used to get and set the content of a selected element.
  - 이전 레슨에서 보았듯이, `html()`과 `text()` 메소드를 사용해서 선택한 element의 내용을 가져오고 설정할 수 있다.
- However, when these methods are used to set content, the existing content is lost.
  - 하지만 이러한 방법을 사용해서 내용을 설정하면, 기존의 내용을 유지할 수 없다.
- jQuery has methods that are used to add new content to a selected element without deleting the existing content:
  - jQuery에는 기존의 내용을 삭제하지 않고 선택한 element에서 내용을 추가하는 데 사용되는 메소드가 있다.

<br>

> `append()`: inserts content at the end of the selected elements.
>
> 선택한 element의 끝에 내용을 삽입한다.

> `prepend()`: inserts content at the beginning of the selected elements.
>
> 선택한 element의 시작에 내용을 삽입한다.

> `after()`: inserts content after the selected elements.
>
> 선택한 element의 뒤에 내용을 삽입한다.

> `before()`: inserts content before the selected elements.
>
> 선택한 element의 앞에 내용을 삽입한다.

<br>

<br>

- The `append()` method inserts content AT THE END of the selected HTML element.
  - `append()` 메소드는 선택된 HTML element의 끝에 내용을 삽입한다.

<br>

- HTML:

```html
<p id="demo">
   Hi
</p>
```

<br>

- JS:

```js
$(function() {
   $("#demo").append("David");
});

// Outputs "Hi David"
```

[코드 실행 확인 링크](https://code.sololearn.com/1112/#js)

> Similarly, the `prepend()` method inserts content AT THE BEGINNING of the selected element.
>
> 마찬가지로, `prepend()` 메소드는 선택한 element의 시작에 내용을 삽입한다.

<br>

<br>

- The jQuery `after()` and `before()` methods insert content AFTER and BEFORE the selected HTML element.
  - jQuery `after()`와 `before()` 메소드는 선택한 HTML element의 앞과 뒤에 내용을 삽입한다.

<br>

- HTML:

```html
<p id="demo">
   Hi
</p>
```

<br>

- JS:

```js
$(function() {
   $("#demo").before("<i>Some Title</li>");
   $("#demo").after("<b>Welcome</b>");
});
```

[코드 실행 확인 링크](https://code.sololearn.com/1113/#js)

------

<br>

## Adding New Element

###### 새로운 element 추가하기

<br>

- The `append()`, `prepend()`, `before()` and `after()` methods can also be used to add newly created elements.
  - `append()`, `prepend()`, `before()`, `after()` 메소드를 사용해서 새로 생성한 element를 추가할 수도 있다.
- The easiest way of creating a new HTML element with jQuery is the following:
  - jQuery로 새로운 HTML element를 생성하는 가장 쉬운 방법은 다음과 같다.

```js
var txt = $("<p></p>").text("Hi");
```

<br>

- The code above creates a new `<p>` element, which contains the text Hi and assigns it to a variable called `txt`.
  - 위의 코드는 Hi라는 텍스트를 포함하는 새로운 `<p>` element를 생성하고, 이를 `txt`라는 변수에 지정한다.
- Now, we can use that variable as a parameter of the above mentioned methods to add it to our HTML.
  - 이제 변수를 위에서 언급한 메소드의 매개변수로 사용해서 HTML에 추가할 수 있다.

<br>

- HTML:

```html
<p id="demo">
   Hello
</p>
```

<br>

- JS:

```js
$(function() {
   var txt = $("<p></p>").text("Hi");
   $("#demo").after(txt);
});
```

[코드 실행 확인 링크](https://code.sololearn.com/1114/#js)

<br>

- This will insert the newly created \<p> element after the \#demo paragraph.
  - \#demo p 뒤에 새로 생성한 \<p> element가 삽입된다.
- You can also specify multiple elements as arguments for the `before()`, `after()`, `append()`, `prepend()` methods by separating them using commas: $("#demo").append(var1, var2, var3).
  - `before()`, `after()`, `append()`, `prepend()`를 쉼표로 구분해서 여러 element를 인수로 지정할 수도 있다.
  - $("#demo").append(var1, var2, var3)

<br>

> The above mentioned syntax for creating elements can be used to create any new HTML element, for example `$("<div></div>")` creates a new div.
>
> 예를 들어 `$("<div></div>")`는 새로운 div를 생성하는 것처럼, 새로운 HTML element를 생성하는 데 사용할 수 있다.

------

<br>

## QUIZ

- Which method is used to insert content at the beginning of the selected element?
  - 선택한 element의 시작에 내용을 삽입하는 메소드는 무엇인가?

> `prepend()`

<br>

- What is the result of the following code if the HTML contains \<p>1\</p>?
  - HTML에 \<p>1\</p>가 포함된 경우, 다음 코드의 출력은 무엇인가?

```js
$("p").append("2");
$("p").prepend("1");
```

> `112`

<br>

- Can you use HTML markup for the after() method?
  - after() 메소드에 HTML 마크업을 사용할 수 있나?

> `Yes`

<br>

- Fill in the blanks to create a new \<span> element and append it to the element with id="txt".
  - 새로운 \<span> element를 생성하고, id="txt" element에 append 해라.

```js
var a = $("<span></span>");
$("#txt").append(a);
```

<br>
