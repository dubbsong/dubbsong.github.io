---
layout: post
title: "(Manipulating CSS 03) Dimensions(치수)"
categories: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

# jQuery Dimensions

###### 치수

<br>

- The `width()` and `height()` methods can be used to get and set the width and height of HTML elements.
  - `width()`와 `height()` 메소드는 HTML element의 너비와 높이를 가져오고 설정하는 데 사용할 수 있다.

<br>

- Let's set both the width and height of a div to 100px, as well as set a background color for it:
  - div의 width와 height를 100px로 설정하고, 배경색도 지정해보자.

```js
$(function() {
   $("div").css('background-color', 'red');
   $("div").width(100);
   $("div").height(100);
});
```

[코드 실행 확인](https://code.sololearn.com/1120/#js)

<br>

<br>

- The `width()` and `height()` methods get and set the dimensions without the padding, borders and margins.
  - `width()`와 `height()` 메소드는 padding, border, margin 없이 치수를 가져오고 설정한다.
- The `innerWidth()` and `innerHeight()` methods also include the padding.
  - `innerWidth()`와 `innerHeight()` 메소드는 padding이 포함된다.
- The `outerWidth()` and `outerHeight()` methods include the padding and borders.
  - `outerWidth()`와 `outerHeight()` 메소드는 padding과 border가 포함된다.
- Check out this image to understand how they work:
  - 이것들이 어떻게 작동하는지를 이해하기 위해 아래 이미지를 확인해보자.

![img](/assets/img/jquery-sololearn-manipulating css-03-01.png)

<br>

- The following example demonstrates how the methods work:
  - 다음 예제는 메소드가 어떻게 작동하는지를 보여준다.

<br>

- HTML:

```html
<div></div>
```

<br>

- CSS:

```css
div {
   width: 300px;
   height: 100px;
   padding: 10px;
   margin: 20px;
   border: 3px solid blue;
   background-color: red;
   color: white;
}
```

<br>

- JS:

```js
$(function() {
   var txt = "";
   txt += "width: " + $("div").width() + " ";
   txt += "height: " + $("div").height() + "<br/>";
   txt += "innerWidth: " + $("div").innerWidth() + " ";
   txt += "innerHeight: " + $("div").innerHeight() + "<br/>";
   txt += "outerWidth: " + $("div").outerWidth() + " ";
   txt += "outerHeight: " + $("div").outerHeight();
   
   $("div").html(txt);
});
```

[코드 실행 확인](https://code.sololearn.com/1121/#js)

<br>

> Run the code to see the values returned by the dimension methods.
>
> 코드를 실행해 dimension 메소드에서 반환한 값을 확인해보자.

------

<br>

## QUIZ

- Fill in the blanks to set the height of the paragraph with the id="demo" to 68px.
  - id="demo" \<p>의 height를 68px로 설정해라.

```js
$("#demo").height(68);
```

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```html
<div style="width:200px"></div>

<script>
   $(function() {
      $("div").css('padding', '5px');
      alert($("div").innerWidth());
   });
</script>
```

> `210`

<br>