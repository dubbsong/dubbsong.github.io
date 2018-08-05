---
layout: post
title: "04. Module 1 Quiz (Overview)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com) jQuery 번역

<br>

## QUIZ

- Type in the symbol used to access jQuery.
  - jQuery에 액세스하는 데 사용되는 기호를 입력해라.

> `$`

<br>

- Fill in the blanks to run the jQuery manipulations as soon as the document is loaded.
  - document가 로딩되는 즉시 jQuery 조작을 실행해라.

```js
$(function() {
   // jQuery code goes here
});
```

<br>

- Fill in the blanks to select the paragraph from the following HTML: \<p id="test">\</p>
  - HTML \<p id="test">\</p>의 p를 선택해라.

```js
$("#test")
```

<br>

- Which of the following selects all h1 and h2 elements?
  - h1과 h2 element 모두를 선택하는 것은 어떤 것인가?

> $("h1 h2")
>
> $("h1:h2")
>
> `$("h1, h2")`

<br>

- Fill in the blanks to select all \<p> elements, that are children of the element with id="demo".
  - id="demo" element의 자식인 모든 \<p> element를 선택해라.

```js
$("#demo p")
```

<br>