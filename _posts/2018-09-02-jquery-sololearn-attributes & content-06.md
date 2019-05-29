---
layout: post
title: "(Attributes & Content 05) QUIZ"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## QUIZ

- Fill in the blanks to set the alt attribute of the image with id="img", and alert the value of its src attribute.
  - id="img" 이미지의 alt 속성을 설정하고, src 속성의 값을 alert 해라.

```js
$("#img").attr("alt", "Demo");
alert($("#img").attr("src"));
```

<br>

- The text() method returns the text content of the element, including the HTML markup.
  - text() 메소드는 HTML 마크업을 포함한 element의 텍스트 내용을 반환한다.

> [ ] true
>
> [ ] `false`

<br>

- Fill in to get the value of the form field with id="name" and set it as the text of the paragraph with id="txt".
  - id="name" form field의 값을 id="txt" p 태그의 텍스트로 설정해라.

```js
var v = $("#name").val();
$("#txt").text(v);
```

<br>

- What is the output of this code if the HTML code is \<p>a\<span>b\</span>\</p>?
  - HTML 코드가 \<p>a\<span>b\</span>\</p>라면, 다음 코드의 출력은 무엇인가?

```js
$(function() {
  $("p span").text("a");
});
```

> `aa`

<br>

- Fill in the blanks to create a new div element with the text "Hi" and insert it before the element with id="demo".
  - 새로운 "Hi" div element를 생성해서, id="demo" element 전에 삽입해라.

```js
var a = $("<div></div>").text("Hi");
$("#demo").before(a);
```

<br>