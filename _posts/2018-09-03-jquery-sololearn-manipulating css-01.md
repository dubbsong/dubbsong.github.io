---
layout: post
title: "(Manipulating CSS 01) class 추가하기/제거하기"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## Manipulating CSS

###### CSS 조작하기

<br>

- jQuery has several methods for CSS manipulation.
  - jQuery에는 CSS 조작을 위한 몇 가지 메소드가 있다.
- The `addClass()` method adds one or more classes to the selected elements.
  - `addClass()` 메소드는 선택된 element에 하나 이상의 class를 추가한다.

<br>

- HTML:

```html
<div>What's up?</div>
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

[코드 실행 확인](https://code.sololearn.com/1115/#js)

<br>

- The above code assigns the div element the class "header".
  - 위 코드는 div element에 "header" class를 지정한다.

<br>

> To specify multiple classes within the addClass() method, just separate them using spaces: `$("div").addClass("class1 class2 class3")`
>
> class를 공백으로 구분해서, 여러 class를 지정한다.
>
> 예: `$("div").addClass("class1 class2 class3")`

<br>

<br>

- The `removeClass()` method removes one or more class names from the selected elements.
  - `removeClass()` 메소드는 선택된 element에서 하나 이상의 class를 제거한다.

```js
$("div").removeClass("red");
```

[코드 실행 확인](https://code.sololearn.com/1116/#js)

<br>

- The code above removes the class "red" from the div element.
  - 위 코드는 div element에서 "red" class를 제거한다.

------

<br>

### toggleClass()

###### toggleClass() 메소드

<br>

- The `toggleClass()` method toggles between adding/removing classes from the selected elements, meaning that if the specified class exists for the element, it is removed, and if it does not exist, it is added.
  - `toggleClass()` 메소드는 선택된 element의 class를 toggle (추가/제거) 한다.

<br>

- HTML:

```html
<p>What's up?</p>
<button>Toggle</button>
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

<br>

> The code above toggles the class name "red" upon clicking the button.
>
> 위 코드는 버튼을 클릭할 때마다 "red" class를 toggle 한다.

------

<br>

## QUIZ

- Fill in the blanks to add the class names "text" and "menu" to the \<p> element.
  - "text"와 "menu" class를 \<p> element에 추가해라.

```js
$("p").addClass("text menu");
```

<br>

- Which class name will the \<p class="a b">\</p> element have after the following code?
  - \<p class="a b">\</p> element는 다음 코드 후에 어떤 class를 가지는가?

```js
$("p").addClass("c");
$("p").removeClass("a c");
```

> `b`

<br>

- Will the paragraph have a border after this code?
  - 아래 코드 후, p 태그에 테두리가 생기나?

```html
<style>
  .test {
    border-style: solid;
  }
</style>

<p>What's up?</p>

<script>
  $(function() {
    $("p").addClass("test");
    $("p").toggleClass("test");
  });
</script>
```

> `No`

<br>