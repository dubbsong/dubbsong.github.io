---
layout: post
title: "(Attributes & Content 04) val() 메소드"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## val() Method

###### val() 메소드

<br>

- Another useful method is the `val()` method, which allows us to get and set the values of form fields, such as textboxes, dropdowns, and similar inputs.
  - 또 다른 유용한 메소드는 `val()` 메소드다.
- 이 메소드를 사용해서 텍스트 상자, 드롭다운, input과 같은 form field의 값을 가져오고 설정할 수 있다.

<br>

- HTML:

```html
<input type="text" id="name" value="Your Name">
```

<br>

- JavaScript:

```js
$(function() {
   alert($("#name").val());
});

// alerts "Your Name"
```

[코드 실행 확인](https://code.sololearn.com/1110/#js)

<br>

- Similarly, you can set the value for the field by providing it as a parameter to the `val()` method.
  - 마찬가지로, field의 값을 `val()` 메소드에 매개변수로 제공해서 설정할 수도 있다.

<br>

> Getting and setting form field values is very useful when you need to handle form events and validation.
>
> form field 값을 가져오고 설정하는 것은, form 이벤트와 유효성 검사를 처리할 때 매우 유용하다.

------

<br>

## Summary

###### 요약

<br>

- The following jQuery methods are available to get and set content and attributes of selected HTML elements:
  - 다음 jQuery 메소드는 선택한 HTML element의 내용과 속성을 가져오고 설정하는 데 사용할 수 있다.

<br>

- `text()`: sets or returns the text content of selected elements.
  - 선택한 element의 텍스트 내용을 설정하거나 반환한다.
- `html()`: sets or returns the content of selected elements (including HTML markup).
  - 선택한 element(HTML 마크업 포함)의 내용을 설정하거나 반환한다.
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
  - form field의 값을 가져와서, id="demo" p의 값으로 설정해라.

```js
$(function() {
   var t = $("#user").val();
   $("#demo").text(t);
})
```

<br>

- Which method gets the value of an input field?
  - input field의 값을 가져오는 메소드는 무엇인가?

> `val()`

<br>