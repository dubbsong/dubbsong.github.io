---
layout: post
title: "02. CSS 속성 (Manipulating CSS)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com) jQuery 번역

<br>

# CSS Properties

###### CSS 속성

<br>

- Similar to the `html()` method, the `css()` method can be used to get and set CSS property values.
  - `html()` 메소드와 마찬가지로, CSS 속성 값을 가져오고 설정하는 데 `css()` 메소드를 사용할 수 있다.

<br>

- HTML:

```html
<p>Some text</p>
```

<br>

- CSS:

```css
p {
   background-color: red;
   color: white;
}
```

<br>

- JS:

```js
$(function() {
   alert($("p").css("background-color"));
   $("p").css("background-color", "blue");
});
```

[코드 실행 확인 링크](https://code.sololearn.com/1118/#js)

<br>

> The code above alerts the background-color property of the paragraph and then sets it to blue.
>
> 위의 코드는 p의 background-color 속성을 알린 다음, 파란색으로 설정한다.

------

<br>

## Multiple Properties

###### 여러 속성들

<br>

- To set multiple CSS properties, the `css()` method uses `JSON` syntax, which is:
  - 여러 CSS 속성들을 설정하려면, `css()` 메소드는 다음과 같은 `JSON` 구문을 사용한다.
  - `JSON`: a format for storing and transporting data

```json
css({"property":"value", "property":"value", ...});
```

<br>

- As you can see, the syntax consists of `"property":"value"` pairs, which are comma separated and enclosed in curly brackets {}.
  - 보다시피, 구문은 `"property":"value"`의 쌍으로 구성되며, 쉼표로 구분되고, 중괄호{}로 묶는다.

<br>

- For example:

```js
$("p").css({"color":"red", "font-size":"200%"});
```

<br>

- This will set the `color` and `font-size` properties of the paragraph.
  - 위 코드는 p의 `color`와 `font-size` 속성을 설정한다.

<br>

> You can specify any number of properties using the `JSON` syntax.
>
> `JSON` 구문을 사용해서 원하는 수만큼 속성을 지정할 수 있다.

------

<br>

## QUIZ

- Fill in the blanks to set the font size and color of the paragraph:
  - 빈칸을 채워서 p의 font size와 color를 설정해라.

```js
$("p").css("font-size", "16pt");
$("p").css("color", "blue");
```

<br>

- Fill in the blanks to set the color and width property of the div.
  - 빈칸을 채워서 div의 color와 width 속성을 설정해라.

```js
$("div").css({"color":"red", "width":"50px"});
```

<br>