---
layout: post
title: "(DOM & Events 03) element 변경하기"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## Changing Attributes

###### 속성 변경하기

<br>

- Once you have selected the element(s) you want to work with, you can change their attributes.
  - 작업하려는 element를 선택했다면, 속성을 변경할 수 있다.
- We can change the text content of an element using the `innerHTML` property.
  - `innerHTML` 속성을 사용해서 element의 텍스트 내용을 변경할 수 있다.
- Similarly, we can change the attributes of elements.
  - 마찬가지로, element의 속성도 변경할 수 있다.
- For example, we can change the `src` attribute of an image:
  - 예를 들어, 이미지의 `src` 속성을 변경할 수 있다.

```html
<img id="myimg" src="orange.png" alt="" />

<script>
   var el = document.getElementById("myimg");
   el.src = "apple.png";
</script>
```

<br>

- We can change the `href` attribute of a link:
  - 링크의 `href` 속성을 변경할 수 있다.

```html
<a href="https://www.example.com">Some link</a>

<script>
   var el = document.getElementsByTagName("a");
   el[0].href = "https://www.sololearn.com";
</script>
```

[코드 실행 확인](https://code.sololearn.com/956/#js)

<br>

> Practically all attributes of an element can be changed using JavaScript.
>
> element의 거의 모든 속성은 JavaScript를 사용해서 변경할 수 있다.

------

<br>

## Changing Style

###### style 변경하기

<br>

- The style of HTML elements can also be changed using JavaScript.
  - HTML element의 style은 JavaScript를 사용해서 변경할 수도 있다.
- All style attributes can be accessed using the `style object` of the element.
  - 모든 style 속성은 element의 `style 객체`를 사용해서 액세스할 수 있다.

```html
<div id="demo" style="width:200px">
   some text
</div>

<script>
   var x = document.getElementById("demo");
   x.style.color = "6600FF";
   x.style.width = "100px";
</script>
```

[코드 실행 확인](https://code.sololearn.com/957/#js)

<br>

- The code above changes the text `color` and `width` of the div element.
  - 위 코드는 div element의 텍스트 `color`와 `width`를 변경한다.

<br>

> All CSS properties can be set and modified using JavaScript.
>
> 모든 CSS 속성은 JavaScript를 사용해서 설정하고 수정할 수 있다.

> Just remember, that you cannot use dashes (-) in the property names: there are replaced with camelCase versions, where the compound words begin with a capital letter.
>
> 속성 이름에는 dash(-)를 사용할 수 없다.
>
> 복합어가 대문자로 시작하는 camelCase 버전으로 대체된다.

> For example: the `background-color` property should be referred to as `backgroundColor`.
>
> 예: `background-color` 속성은 `backgroundColor`로 나타내야 한다.

------

<br>

## QUIZ

- Fill in the blanks to select all images of the page and change their src attribute.
  - 페이지의 모든 이미지를 선택하고, src 속성을 변경해라.

```js
var arr = document.getElementsByTagName("img");

for (var i = 0; i < arr.length; i++) {
   arr[i].src = "demo.jpg";
}
```

<br>

- Fill in the blanks to change the background color of all span elements of the page.
  - 페이지 내 모든 span element의 배경색을 변경해라.

```js
var s = document.getElementsByTagName("span");

for (var i = 0; i < s.length; i++) {
   s[i].style.backgroundColor = "#20a19c";
}
```

<br>