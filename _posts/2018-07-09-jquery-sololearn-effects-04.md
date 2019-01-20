---
layout: post
title: "(Effects 04) Module 6 Quiz"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## QUIZ

- Fill in the blanks to hide all paragraphs upon clicking the div element.
  - div element를 클릭할 때, 모든 p를 hide 해라.

```js
$("div").click(function() {
   $("p").hide();
});
```

<br>

- For how many seconds will the following animation group run?
  - 다음 애니메이션 그룹은 몇 초 동안 실행되는가?

```js
$("p").animate({height: "10px"}, 1000);
$("p").animate({width: "10px"}, 1000);
$("p").animate({opacity: 0.5}, 3000);
```

> `5`

<br>