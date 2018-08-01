---
layout: post
title: "SoloLearn jQuery 번역 - 01. Adding & Removing Classes (Manipulating CSS)"
categories: dev
tags: jquery
---

## Manipulating CSS

###### CSS 조작하기

<br>

- jQuery has several methods for CSS manipulation.
  - jQuery에는 CSS 조작을 위한 몇 가지 메소드가 있다.
- The `addClass()` method adds one or more classes to the selected elements.
  - `addClass()` 메소드는 하나 이상의 class를 선택한 element에 추가한다.

<br>

- HTML:

```html
<div>
   Some text
</div>
```

<br>

- CSS:

```css
.header {
   color: blue;
   font-size: x-large;
}
```

<br>

- JS:

```js
$("div").addClass("header");
```

[코드 실행 확인 링크](https://code.sololearn.com/1115/#js)

<br>

- The above code assigns the div element the class "header".
  - 위의 코드는 div element에 "header" class를 할당한다.

<br>

> To specify multiple classes within the addClass() method, just separate them using spaces.
>
> addClass() 메소드 내에 여러 class를 지정하려면, 빈칸을 사용해서 class를 구분하면 된다.

> For example, $("div").addClass("class1 class2 class3").
>
> 예를 들어, $("div").addClass("class1 class2 class3").

------

<br>

## Manipulating CSS 02

- The `removeClass()` method removes one or more class names from the selected elements.
  - `removeClass()` 메소드는 하나 이상의 class name을 선택한 element에서 제거한다.

<br>

- For example:

```js
$("div").removeClass("red");
```

<br>

- The code above removes the class "red" from the div element.
  - 위의 코드는 div element에서 "red" class를 제거한다.

<br>

> Again, multiple class names can be specified by separating them using spaces.
>
> 다시 말하지만, 여러 class name은 빈칸을 사용해서 구분해 지정할 수 있다.

------

<br>

## toggleClass()

- The `toggleClass()` method toggles between adding/removing classes from the selected elements, meaning that if the specified class exists for the element, it is removed, and if it does not exist, it is added.
  - `toggleClass()` 메소드는 선택한 element에서 class를 추가/삭제로 토글한다.
  - 즉, 지정된 class가 element에 존재하면 삭제되고, 존재하지 않으면 추가된다.
- To demonstrate this in action, we will handle a button click event to toggle a class.
  - 이 동작을 보여주기 위해, 버튼 클릭 이벤트를 처리해서 class를 토글한다.

<br>

- HTML:

```html
<p>Some text</p>
<button>Toggle Class</button>
```

<br>

- CSS:

```css
.red {
   color: red;
   font-weight: bold;
}
```

<br>

- JS:

```js
$(function() {
   $("button").click(function() {
      $("p").toggleClass("red");
   });
});
```

[코드 실행 확인 링크](https://code.sololearn.com/1117/#js)

<br>

> The code above toggles the class name "red" upon clicking the button.
>
> 위의 코드는 버튼을 클릭할 때 class name "red"를 토글한다.

------

<br>

## QUIZ

- Fill in the blanks to add the class names "text" and "menu" to the \<p> element.
  - 빈칸을 채워서 \<p> element에 "text"와 "menu"라는 class name을 추가해라.

```js
$("p").addClass("text menu");
```

<br>

- Which class name will the \<p class="a b">\</p> element have after the following code?
  - \<p class="a b">\</p> element는 다음 코드 뒤에 어떤 class name이 있는가?

```js
$("p").addClass("c");
$("p").removeClass("a c");
```

> [ ] a
>
> [ ] `b`
>
> [ ] c

<br>

- Will the paragraph have a border after this code?
  - 이 코드 다음에서 p 뒤에 테두리가 생기는가?

```html
<style>
   .test {
      border-style: solid;
   }
</style>

<p>Some text</p>

<script>
   $(function() {
      $("p").addClass("test");
      $("p").toggleClass("test");
   });
</script>
```

> [ ] Yes
>
> [ ] `No`

<br>