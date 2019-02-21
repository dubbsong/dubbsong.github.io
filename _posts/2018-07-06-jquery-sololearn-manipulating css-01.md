---
layout: post
title: "(Manipulating CSS 01) class 추가하기 & 제거하기"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## Manipulating CSS

###### CSS 조작하기

- jQuery has several methods for CSS manipulation.
  - jQuery에는 CSS 조작을 위한 몇 가지 메소드가 있다.
- The `addClass()` method adds one or more classes to the selected elements.
  - `addClass()` 메소드는 하나 이상의 class를 선택한 element에 추가한다.

<br>

- HTML:

```html
<div>Ssup bro?</div>
```

<br>

- CSS:

```css
.color_blue {
   color: blue;
   font-size: x-large;
}
```

<br>

- JS:

```js
$("div").addClass("color_blue");
```

[코드 실행 확인](https://code.sololearn.com/1115/#js)

<br>

- The above code assigns the div element the class "color_blue".
  - 위 코드는 "color_blue" class를 div element에 지정한다.

<br>

> To specify multiple classes within the addClass() method, just separate them using spaces: `$("div").addClass("class1 class2 class3")`
>
> addClass() 메소드 내에서 여러 class를 지정하려면, 공백을 사용해서 class를 구분하면 된다.
>
> 예: `$("div").addClass("class1 class2 class3")`

<br>

<br>

- The `removeClass()` method removes one or more class names from the selected elements.
  - `removeClass()` 메소드는 선택한 element에서 class 이름을 제거한다.

```js
$("div").removeClass("red");
```

[코드 실행 확인](https://code.sololearn.com/1116/#js)

<br>

- The code above removes the class "red" from the div element.
  - 위 코드는 div element에서 "red" class를 제거한다.

------

<br>

## toggleClass()

###### toggleClass() 메소드

<br>

- The `toggleClass()` method toggles between adding/removing classes from the selected elements, meaning that if the specified class exists for the element, it is removed, and if it does not exist, it is added.
  - `toggleClass()` 메소드는 선택한 element에서 class 추가/제거를 toggle 한다.
  - 즉, 지정된 class가 element에 존재하면 제거되고, 존재하지 않으면 추가된다.

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

[코드 실행 확인](https://code.sololearn.com/1117/#js)

------

<br>

## QUIZ

- Fill in the blanks to add the class names "text" and "menu" to the \<p> element.
  - "text"와 "menu" class 이름을 \<p> element에 추가해라.

```js
$("p").addClass("text menu");
```

<br>

- Which class name will the \<p class="a b">\</p> element have after the following code?
  - \<p class="a b">\</p> element는 다음 코드 다음에 어떤 class 이름을 가지는가?

```js
$("p").addClass("c");
$("p").removeClass("a c");
```

> `b`

<br>

- Will the paragraph have a border after this code?
  - 아래 코드 다음에 p가 테두리를 가지는가?

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

> `No`

<br>