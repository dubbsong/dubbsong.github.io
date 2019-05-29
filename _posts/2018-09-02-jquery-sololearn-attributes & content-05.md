---
layout: post
title: "(Attributes & Content 05) 내용 추가하기"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## Adding Content

###### 내용 추가하기

<br>

- As we have seen in the previous lessons, the `html()` and `text()` methods can be used to get and set the content of a selected element.
  - 이전 레슨에서 보았듯이, `html()`과 `text()` 메소드는 선택된 element의 내용을 가져오고 설정하는 데 사용할 수 있다.
- However, when these methods are used to set content, the existing content is lost.
  - 하지만 이러한 메소드를 사용해서 내용을 설정하면 기존 내용이 손실된다.
- jQuery has methods that are used to add new content to a selected element without deleting the existing content:
  - jQuery에는 기존 내용을 제거하지 않고 선택된 element에 새로운 내용을 추가하는 데 사용되는 메소드들이 있다.

<br>

- `append()` inserts content at the end of the selected elements.
  - `append()`는 선택된 element의 끝 부분에 내용을 삽입한다.
- `prepend()` inserts content at the beginning of the selected elements.
  - `prepend()`는 선택된 element의 시작 부분에 내용을 삽입한다.
- `after()` inserts content after the selected elements.
  - `after()`는 선택된 element 뒤에 내용을 삽입한다.
- `before()` inserts content before the selected elements.
  - `before()`는 선택된 element 앞에 내용을 삽입한다.

<br>

<br>

- The `append()` method inserts content AT THE END of the selected HTML element.
  - `append()` 메소드는 선택된 HTML element의 끝 부분에 내용을 삽입한다.

<br>

- HTML:

```html
<p id="demo">What's up,</p>
```

<br>

- JS:

```js
$(function() {
  $("#demo").append('bro?');
});

// What's up, bro?
```

[코드 실행 확인](https://code.sololearn.com/1112/#js)

<br>

> Similarly, the `prepend()` method inserts content AT THE BEGINNING of the selected element.
>
> `prepend()` 메소드는 선택된 element의 시작 부분에 내용을 삽입한다.

> You can also use HTML markup for the content.
>
> 내용에 HTML 마크업을 사용할 수도 있다.

<br>

<br>

- The jQuery `after()` and `before()` methods insert content AFTER and BEFORE the selected HTML element.
  - jQuery `after()`와 `before()` 메소드는 선택된 HTML element의 전과 후에 내용을 삽입한다.

<br>

- HTML:

```html
<p id="demo">CSS</p>
```

<br>

- JS:

```js
$(function() {
  $("#demo").before("<i>HTML</i>");
  $("#demo").after("<b>JS</b>");
});
```

[코드 실행 확인](https://code.sololearn.com/1113/#js)

------

<br>

### Adding New Elements

###### 새 element 추가하기

<br>

- The `append()`, `prepend()`, `before()` and `after()` methods can also be used to add newly created elements.
  - `append()`, `prepend()`, `before()`, `after()` 메소드는 새로 생성한 element를 추가하는 데 사용할 수도 있다.
- The easiest way of creating a new HTML element with jQuery is the following:
  - jQuery로 새로운 HTML element를 생성하는 가장 쉬운 방법은 다음과 같다.

```js
var txt = $("<p></p>").text("What's up?");
```

<br>

- The code above creates a new `<p>` element, which contains the text What's up? and assigns it to a variable called `txt`.
  - 위 코드는 What's up? 텍스트를 포함하는 새로운 `<p>` element를 생성하고, `txt`라는 변수에 할당한다.
- Now, we can use that variable as a parameter of the above mentioned methods to add it to our HTML.
  - 이제 위의 변수를 메소드의 매개변수로 사용해서 추가할 수 있다.

<br>

- HTML:

```html
<p id="demo">What's up?</p>
```

<br>

- JS:

```js
$(function() {
  var txt = $("<p></p>").text("All good?");
  $("#demo").after(txt);
});
```

[코드 실행 확인](https://code.sololearn.com/1114/#js)

<br>

- This will insert the newly created \<p> element after the \#demo paragraph.
  - 새로 생성한 \<p> element가 \#demo p 태그 뒤에 삽입된다.
- You can also specify multiple elements as arguments for the `before()`, `after()`, `append()`, `prepend()` methods by separating them using commas: `$("#demo").append(var1, var2, var3)`
  - 쉼표로 구분해서 여러 element를 인수로 지정할 수도 있다.
  - `$("#demo").append(var1, var2, var3)`

------

<br>

## QUIZ

- Which method is used to insert content at the beginning of the selected element?
  - 선택된 element의 시작 부분에 내용을 삽입하는 메소드는 무엇인가?

> `prepend()`

<br>

- What is the result of the following code if the HTML contains \<p>1\</p>?
  - HTML이 \<p>1\</p>라면, 아래 코드의 결과는 무엇인가?

```js
$("p").append("2");
$("p").prepend("1");
```

> `112`

<br>

- Can you use HTML markup for the after() method?
  - after() 메소드에 HTML 마크업을 사용할 수 있나?

> [ ] No
>
> [ ] `Yes`

<br>

- Fill in the blanks to create a new \<span> element and append it to the element with id="txt".
  - 새로운 \<span> element를 생성해서, id="txt" element에 append 해라.

```js
var a = $("<span></span>");
$("#txt").append(a);
```

<br>