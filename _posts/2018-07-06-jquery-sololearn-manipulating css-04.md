---
layout: post
title: "(Manipulating CSS 04) Module 3 Quiz"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## QUIZ

- Fill in the blanks to set the color and padding properties of the paragraph:
  - p의 color와 padding 속성을 설정해라.

```js
$("p").css({"color": "blue", "padding": "5px"});
```

<br>

- What is the value of outerHeight() for the paragraph after the following code?
  - 다음 코드 다음에, p의 outerHeight() 값은 무엇인가?

```js
$("p").height(84);
$("p").css("margin", 8);
$("p").css("padding", 2);
```

> `88`

<br>

- When specifying multiple class names for the addClass method, we need to separate them using:
  - addClass 메소드에 여러 class 이름을 지정할 때, ...를 사용해서 class 이름을 구분한다.

> `spaces`
>
> 공백

<br>

- Fill in the blanks to create a new \<p> element, set its height to 50px and add it before the element with id="test".
  - 새로운 \<p> element를 생성하고, 높이를 50px로 설정하고, id="test" element 전에 추가해라.

```js
var e = $("<p></p>").text("Some text");
e.height(50);
$("#test").before(e);
```

<br>