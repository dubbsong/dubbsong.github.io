---
layout: post
title: "SoloLearn jQuery 번역 - 02. Removing Attributes (Attributes and Content)"
categories: dev
tags: jquery
---

## Removing Attributes

###### 속성 제거

<br>

- You can also remove attributes from HTML elements.
  - HTML element에서 속성을 제거할 수도 있다.
- The `removeAttr()` method is used for removing any attribute of an element.
  - `removeAttr()` 메소드는 element의 속성을 제거하는 데 사용된다.
- In the example below we remove the `border` and `class` attributes of the table:
  - 아래 예제에서, table의 `border`와 `class` 속성을 제거한다.

```js
$("table").removeAttr("border");
$("table").removeAttr("class");
```

[코드 실행 확인 링크](https://code.sololearn.com/1111/#js)

------

<br>

## QUIZ

- Drag and drop from the options below to remove the border attribute of the element with id="text".
  - 아래 옵션들에서 drag and drop으로 id="text" element의 border 속성을 제거해라.

```js
$("#text").removeAttr("border");
```

<br>