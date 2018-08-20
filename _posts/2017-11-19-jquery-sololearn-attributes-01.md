---
layout: post
title: "01. 속성값 가져오기 & 설정하기 (Attributes and Content)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

# jQuery Get & Set Attribute Values

###### jQuery 속성값 가져오기 & 설정하기

------

<br>

<br>

## Attributes

###### 속성

<br>

- We can manipulate attributes assigned to HTML elements easily through jQuery.
  - jQuery를 통해 HTML element에 지정된 속성을 쉽게 조작할 수 있다.
- `href`, `src`, `class`, `style` are all examples of HTML attributes.
  - `href`, `src`, `class`, `style`은 모두 HTML 속성의 예이다.

<br>

- The `attr()` method is used for getting the value of an attribute.
  - `attr()` 메소드는 속성 값을 가져오는 데 사용된다.

<br>

- HTML:

```html
<a href="www.sololearn.com">
	Click here
</a>
```

<br>

- JavaScript:

```js
$(function() {
   var val = $("a").attr("href");
   alert(val);
});

// alerts "www.sololearn.com"
```

[코드 실행 확인 링크](https://code.sololearn.com/1104/#js)

<br>

> In the code above we selected and alerted the value of the `href` attribute of the \<a> element.
>
> 위의 코드에서 \<a> element의 `href` 속성 값을 선택하고 alert 했다.

<br>

<br>

- The `attr()` method also allows us to set a value for an attribute by specifying it as the second parameter.
  - `attr()` 메소드를 사용하면 두 번째 매개변수로 속성 값을 지정해서 설정할 수 있다.

<br>

- For example:

```js
$(function() {
   $("a").attr("href", "http://www.jquery.com");
});
```

[코드 실행 확인 링크](https://code.sololearn.com/1105/#js)

<br>

> This will change the `href` attribute of the \<a> element to the provided value.
>
> 이렇게 하면, \<a> element의 `href` 속성이 제공된 값으로 변경된다.

------

<br>

## QUIZ

- Which of the following are HTML attributes? Select all that apply.
  - HTML 속성은 어떤 것인가?
  - 해당되는 모든 것을 골라라.

> [ ] `class`
>
> [ ] div
>
> [ ] img
>
> [ ] `src`

<br>

- Fill in the blanks to change the image to the file "1.jpg".
  - 이미지를 "1.jpg" 파일로 변경해라.

```js
$("img").attr("src", "1.jpg");
```

<br>
