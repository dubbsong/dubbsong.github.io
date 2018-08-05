---
layout: post
title: "06. Module 2 Quiz (Attributes and Content)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com) jQuery 번역

<br>

## QUIZ

- Fill in the blanks to set the alt attribute of the image with id="img", and alert the value of its src attribute.
  - 빈칸을 채워서 id="img"로 이미지의 alt 속성을 설정하고, src 속성의 값을 alert 해라.

```js
$("#img").attr("alt", "Demo");
alert($("#img").attr("src"));
```

<br>

- The text() method returns the text content of the element, including the HTML markup.
  - text() 메소드는 HTML 마크업을 포함해서 element의 텍스트 내용을 반환한다.

> [ ] true
>
> [ ] `false`

<br>

- Fill in to get the value of the form field with id="name" and set it as the text of the paragraph with id="txt".
  - form field의 값을 id="name"으로 채우고, id="txt"인 p의 텍스트로 설정해라.

```js
var v = $("#name").val();
$("#txt").text(v)
```

<br>

- What is the output of this code if the HTML code is \<p>a\<span>b\</span>\</p>?
  - HTML 코드가 \<p>a\<span>b\</span>\</p>인 경우, 이 코드의 출력은 무엇인가?

```js
$(function() {
   $("p span").text("a");
});
```

> [ ] a
>
> [ ] `aa`
>
> [ ] ab

<br>

- Fill in the blanks to create a new div element with the text "Hi" and insert it before the element with id="demo".
  - 빈칸을 채워서 텍스트 "Hi로" 새로운 div element를 생성하고, id="demo" element 앞에 삽입해라.

```js
var a = $("<div></div>").text("Hi");
$("#demo").before(a);
```

<br>