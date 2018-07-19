---
layout: post
title: "SoloLearn jQuery 번역 - 01. Get & Set Attribute Values (Attributes and Content)"
categories: dev
tags: jquery
---

## Attributes

###### 속성

<br>

- We can manipulate attributes assigned to HTML elements easily through jQuery.
  - jQuery를 통해서 HTML element에 할당된 속성을 쉽게 조작할 수 있다.
- `href`, `src`, `id`, `class`, `style` are all examples of HTML attributes.
  - `href`, `src`, `id`, `class`, `style`은 모두 HTML 속성의 예이다.

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
> 위의 코드에서 \<a> element의 `href` 속성 값을 선택하고 alert 하도록 했다.

------

<br>

## Attributes 02

- The `attr()` method also allows us to set a value for an attribute by specifying it as the second parameter.
  - `attr()` 메소드를 사용하면, 두 번째 매개변수로 속성을 지정해서 값을 설정할 수도 있다.

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
> 이렇게 하면 \<a> element의 `href` 속성이 제공된 값으로 변경된다.

------

<br>

## QUIZ

- Which of the following are HTML attributes?
  - 다음 중 HTML 속성은 어떤 것인가?
  - Select all that apply

> [ ] img
>
> [ ] `src`
>
> [ ] `class`
>
> [ ] div

<br>

- Fill in the blanks to change the image to the file "1.jpg".
  - 빈칸을 채워서 이미지를 "1.jpg" 파일로 변경해라.

```js
$("img").attr("src", "1.jpg");
```

<br>
