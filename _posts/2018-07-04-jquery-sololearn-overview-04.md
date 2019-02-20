---
layout: post
title: "(Overview 04) Module 1 Quiz"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## QUIZ

- Type in the symbol used to access jQuery.
  - jQuery에 액세스하는 데 사용되는 심볼을 입력해라.

> `$`

<br>

- Fill in the blanks to run the jQuery manipulations as soon as the document is loaded.
  - document가 로딩되는 즉시 jQuery 조작을 실행해라.

```js
$(function() {
   // jQuery 코드
});
```

<br>

- Fill in the blanks to select the paragraph from the following HTML: \<p id="test">\</p>
  - 다음 HTML에서 p를 선택해라.
  - \<p id="test">\</p>

```js
$("#test");
```

<br>

- Which of the following selects all h1 and h2 elements?
  - 다음 중 h1 element와 h2 element 모두를 선택하는 것은 무엇인가?

> [ ] $("h1 h2")
>
> [ ] $("h1:h2")
>
> [ ] `$("h1, h2")`

<br>

- Fill in the blanks to select all \<p> elements, that are children of the element with id="demo".
  - id="demo" element의 children인 모든 \<p> element를 선택해라.

```js
$("#demo p");
```

<br>