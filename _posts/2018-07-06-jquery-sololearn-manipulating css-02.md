---
layout: post
title: "(Manipulating CSS 02) CSS 속성"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## CSS Properties

###### CSS 속성

- Similar to the `html()` method, the `css()` method can be used to get and set CSS property values.
  - `html()` 메소드와 마찬가지로, `css()` 메소드는 CSS 속성 값을 가져오고 설정하는 데 사용할 수 있다.

<br>

- HTML:

```html
<p>What's up?</p>
```

<br>

- CSS:

```css
p {
  background-color: red;
  color: #ffffff;
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

[코드 실행 확인](https://code.sololearn.com/1118/#js)

<br>

> The code above alerts the background-color property of the paragraph and then sets it to blue.
>
> 위 코드는 p 태그의 background-color 속성을 alert하고, blue로 설정한다.

------

<br>

### Multiple Properties

###### 여러 속성 조작하기

<br>

- To set multiple CSS properties, the `css()` method uses JSON syntax.
  - 여러 CSS 속성을 설정하기 위해, `css()` 메소드는 JSON 구문을 사용한다.

```js
css({"property":"value","property":"value",...});
```

<br>

- As you can see, the syntax consists of `"property":"value"` pairs, which are comma separated and enclosed in curly brackets {}.
  - 구문은 `"속성":"값"` 쌍으로 구성된다.
  - 쉼표로 구분하고, 중괄호 {}로 감싼다.

<br>

- For example:

```js
$("p").css({"color":"red","font-size":"200%"});
```

[코드 실행 확인](https://code.sololearn.com/1119/#js)

<br>

- This will set the `color` and `font-size` properties of the paragraph.
  - 위 코드는 p 태그의 `color`와 `font-size` 속성을 설정한다.

<br>

> You can specify any number of properties using this `JSON` syntax.
>
> `JSON` 구문을 사용하면 속성 여러 개를 지정할 수 있다.

------

<br>

## QUIZ

- Fill in the blanks to set the font-size and color of the paragraph:
  - p 태그의 font-size와 color를 설정해라.

```js
$("p").css("font-size", "16pt");
$("p").css("color", "blue");
```

<br>

- Fill in the blanks to set the color and width property of the div.
  - div의 color와 width 속성을 설정해라.

```js
$("div").css({"color":"red","width":"50px"});
```

<br>