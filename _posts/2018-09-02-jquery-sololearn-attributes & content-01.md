---
layout: post
title: "(Attributes & Content 01) 속성 값 가져오기/설정하기"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

### Attributes

###### 속성

- We can manipulate attributes assigned to HTML elements easily through jQuery.
  - jQuery를 통해, HTML element에 지정된 속성을 쉽게 조작할 수 있다.
- `href`, `src`, `id`, `class`, `style` are all examples of HTML attributes.
  - `href`, `src`, `id`, `class`, `style`은 모두 HTML 속성이다.

<br>

- The `attr()` method is used for getting the value of an attribute.
  - `attr()` 메소드는 속성 값을 가져오는 데 사용된다.

<br>

- HTML:

```html
<a href="www.sololearn.com">Click here</a>
```

<br>

- JS:

```js
$(function() {
  var val = $("a").attr("href");
  alert(val);
});

// alert "www.sololearn.com"
```

[코드 실행 확인](https://code.sololearn.com/1104/#js)

<br>

<br>

- The `attr()` method also allows us to set a value for an attribute by specifying it as the second parameter.
  - `attr()` 메소드의 두 번째 매개변수로 속성 값을 설정할 수도 있다. 

```html
<html>
  <head>
    
  </head>
  <body>
    <a href="https://www.sololearn.com">Click here</a>
    
    <script>
      $(function() {
        $("a").attr("href", "https://jquery.com")
      });
    </script>
  </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/1105/#js)

<br>

> This will change the `href` attribute of the \<a> element to the provided value.
>
> 위 코드는 \<a> element의 `href` 속성을 제공된 값으로 변경한다.

------

<br>

## QUIZ

- Which of the following are HTML attributes?
  - 다음 중 HTML 속성은 무엇인가?
- Select all that apply.
  - 해당되는 모든 것을 선택해라.

> [ ] img
>
> [ ] div
>
> [ ] `class`
>
> [ ] `src`

<br>

- Fill in the blanks to change the image to the file "1.jpg".
  - 이미지를 "1.jpg" 파일로 변경해라.

```js
$("img").attr("src", "1.jpg");
```

<br>