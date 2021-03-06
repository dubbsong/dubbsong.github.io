---
layout: post
title: "(Manipulating CSS 03) 크기"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## Dimensions

###### 크기

<br>

- The `width()` and `height()` methods can be used to get and set the width and height of HTML elements.
  - `width()`와 `height()` 메소드는, HTML element의 너비와 높이를 가져오고 설정하는 데 사용할 수 있다.

```js
$("div").css("background-color", "red");
$("div").width(100);
$("div").height(100);
```

[코드 실행 확인](https://code.sololearn.com/1120/#js)

<br>

<br>

- The `width()` and `height()` methods get and set the dimensions without the padding, borders and margins.
  - `width()`와 `height()` 메소드는 padding, border, margin 없이 크기를 가져오고 설정한다.
- The `innerWidth()` and `innerHeight()` methods also include the padding.
  - `innerWidth()`와 `innerHeight()` 메소드에는 padding이 포함된다.
- The `outerWidth()` and `outerHeight()` methods include the padding and borders.
  - `outerWidth()`와 `outerHeight()` 메소드는 padding과 border가 포함된다.

<br>

- For example:

![img](/assets/img/js-sololearn-manipulating css-03-01.png)

------

<br>

## QUIZ

- Fill in the blanks to set the height of the paragraph with the id="demo" to 68px.
  - id="demo" p 태그의 높이를 68px로 설정해라.

```js
$("#demo").height(68);
```

<br>

- What is the output of this code?
  - 아래 코드의 출력은 무엇인가?

```html
<div style="width:200px"></div>

<script>
  $(function() {
    $("div").css("padding", "5px");
    alert($("div").innerWidth());
  });
</script>
```

> `210`

<br>