---
layout: post
title: "SoloLearn jQuery 번역 - 04. val() (Attributes and Content)"
categories: dev
tags: jquery
---

## val()

- We have seen in the previous lesson how we can manipulate the content of HTML elements using the `text()` and `html()` methods.
  - 이전 강의에서 `text()`와 `html()` 메소드를 사용해서 HTML element의 내용을 조작할 수 있는 방법을 살펴보았다.
- Another useful method is the `val()` method, which allows us to get and set the values of form fields, such as textboxes, dropdowns, and similar inputs.
  - 또 다른 유용한 메소드는 `val()` 메소드이다.
  - 이 메소드를 사용하면 텍스트 상자, 드랍다운, 유사한 input과 같은 form field의 값을 가져오고 설정할 수 있다.

<br>

- HTML:

```html
<input type="text" id="name" value="Your Name">
```

<br>

- JS:

```js
$(function() {
   alert($("#name").val());
});

// alerts "Your Name"
```

<br>

- Similarly, you can set the value for the field by providing it as a parameter to the `val()` method.
  - 마찬가지로, `val()` 메소드에 매개변수로 제공해서 field의 값을 설정할 수 있다.

<br>

> Getting and setting form field values is very useful when you need to handle form events and validation.
>
> form field 값을 가져와서 설정하면 form 이벤트와 유효성 검사를 처리할 때 매우 유용하다.

------

<br>

## Summary

###### 요약

<br>

- The following jQuery methods are available to get and set content and attributes of selected HTML elements:
  - 선택된 HTML element의 내용과 속성을 가져오고 설정하는 데 사용할 수 있는 jQuery 메소드는 다음과 같다.

<br>

- `text()`: sets or returns the text content of selected elements.
  - 선택한 element의 내용을 설정하거나 반환한다.
- `html()`: sets or returns the content of selected elements (including HTML markup).
  - 선택한 element의 내용을 설정하거나 반환한다. (HTML 마크업 포함)
- `val()`: sets or returns the value of form fields.
  - form field의 값을 설정하거나 반환한다.
- `attr()`: sets or returns the value of attributes.
  - 속성의 값을 설정하거나 반환한다.
- `removeAttr()`: removes the specified attribute.
  - 지정된 속성을 제거한다.

------

<br>

## QUIZ

- Rearrange the code to get the value of the form field and set it as the value of the paragraph with id="demo".
  - 코드를 재정렬해서 form field의 값을 가져오고, id="demo"의 p 값으로 설정해라.

```js
$(function() {
   var t = $("#user").val();
   $("#demo").text(t);
});
```

<br>

- Which method gets the value of an input field?
  - input field의 값을 가져오는 메소드는 어떤 것인가?

> [ ] html()
>
> [ ] attr()
>
> [ ] `val()`

<br>
