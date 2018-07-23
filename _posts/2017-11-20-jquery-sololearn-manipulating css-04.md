---
layout: post
title: "SoloLearn jQuery 번역 - 04. Module 3 Quiz (Manipulating CSS)"
categories: dev
tags: jquerty
---

## QUIZ

- Fill in the blanks to set the color and padding properties of the paragraph:
  - 빈칸을 채워서 p의 color와 padding 속성을 설정해라.

```js
$("p").css({"color":"blue", "padding":"5px"});
```

<br>

- What is the value of outerHeight() for the paragraph after the following code?
  - 다음 코드 후에, p의 outerHeight() 값은 무엇인가?

```js
$("p").height(84);
$("p").css("margin", 8);
$("p").css("padding", 2);
```

> `88`

<br>

- When specifying multiple class names for the addClass method, we need to separate them using:
  - addClass 메소드에 여러 class name을 지정할 때, 다음을 사용해서 class name을 분류해야 한다.

> [ ] commas
>
> [ ] colons
>
> [ ] `spaces`

<br>

- Fill in the blanks to create a new \<p> element, set its height to 50px and add it before the element with id="test".
  - 빈칸을 채워서 새 \<p> element를 만들고, 높이를 50px로 설정하고, id="test"를 element 앞에 추가해라.

```js
var e = $("<p></p>").text("Some text");
e.height(50);
$("#test").before(e);
```

<br>