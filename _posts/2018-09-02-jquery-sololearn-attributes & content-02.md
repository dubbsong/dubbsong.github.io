---
layout: post
title: "(Attributes & Content 02) 속성 제거하기"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## Removing Attributes

###### 속성 제거하기

<br>

- You can also remove attributes from HTML elements.
  - HTML element의 속성을 제거할 수도 있다.
- The `removeAttr()` method is used for removing any attribute of an element.
  - `removeAttr()` 메소드는 element의 속성을 제거하는 데 사용된다.
- In the example below we remove the `border` and `class` attributes of the table:
  - 아래 예제는, 테이블의 `border`와 `class` 속성을 제거한다.

```js
$("table").removeAttr("border");
$("table").removeAttr("class");
```

[코드 실행 확인](https://code.sololearn.com/1111/#html)

------

<br>

## QUIZ

- Drag and drop from the options below to remove the border attribute of the element with id="text".
  - id="text" element의 border 속성을 제거해라.

```js
$("#text").removeAttr("border");
```

<br>