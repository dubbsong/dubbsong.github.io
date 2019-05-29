---
layout: post
title: "(Manipulating CSS 04) QUIZ"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## QUIZ

- Fill in the blanks to set the color and padding properties of the paragraph:
  - p 태그의 color와 padding 속성을 설정해라.

```js
$("p").css({"color":"blue","padding":"5px"});
```

<br>

- What is the value of outerHeight() for the paragraph after the following code?
  - 아래 코드 후, p 태그의 outerHeight() 값은 무엇인가?

```js
$("p").height(84);
$("p").css("margin", 8);
$("p").css("padding", 2);
```

> `88`

<br>

- When specifying multiple class names for the addClass method, we need to separate them using:
  - addClass 메소드에 여러 class를 지정할 때에는 ...로 구분해야 한다.

> `spaces`

<br>

- Fill in the blanks to create a new \<p> element, set its height to 50px and add it before the element with id="test".
  - 새로운 \<p> element를 생성하고, 높이를 50px로 설정한 후, id="test" element 앞에 추가해라.

```js
var e = $("<p></p>").text("What's up?");
e.height(50);
$("#test").before(e);
```

<br>