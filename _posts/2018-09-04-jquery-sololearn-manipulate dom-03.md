---
layout: post
title: "(Manipulate DOM 03) element 제거하기"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## Remove Elements

###### element 제거하기

<br>

- We remove selected elements from the DOM using the `remove()` method.
  - `remove()` 메소드를 사용해서, DOM에서 선택한 element를 제거한다.

<br>

- HTML:

```html
<p style="color:red">Red</p>
<p style="color:green">Green</p>
<p style="color:blue">Blue</p>
```

<br>

- JS:

```js
$("p").eq(1).remove();
```

[코드 실행 확인](https://code.sololearn.com/1124/#js)

<br>

- This removes Green, the second paragraph element.
  - 위 코드는 두 번째 p element인 Green을 제거한다.
- You can also use the `remove()` method on multiple selected elements.
  - `remove()` 메소드를 선택한 여러 element에 사용할 수도 있다.
- `$("p").remove()` removes all paragraphs.
  - `$("p").remove()`는 모든 p element를 제거한다.

<br>

> The jQuery remove() method removes the selected element(s), as well as its `child` elements.
>
> jQuery remove() 메소드는 선택한 element뿐만 아니라, 그 `child(자식)` element도 제거한다.

------

<br>

### Removing Content

###### 내용 제거하기

<br>

- The `empty()` method is used to remove the child elements of the selected element(s).
  - `empty()` 메소드는, 선택한 element의 chlid(자식) element를 제거하는 데 사용된다.

<br>

- HTML:

```html
<div>
  <p style="color:red">Red</p>
  <p style="color:green">Green</p>
  <p style="color:blue">Blue</p>
</div>
```

<br>

- CSS:

```css
div {
  background-color: aqua;
  width: 300px;
  height: 200px;
}
```

<br>

- JS:

```js
$("div").empty();
```

[코드 실행 확인](https://code.sololearn.com/1125/#js)

<br>

> This removes all the three child elements of the div, leaving it empty.
>
> 위 코드는 div의 세 child element 모두를 제거한다.

------

<br>

## QUIZ

- Fill in the blanks to remove all siblings of the element with id="txt".
  - id="txt" element의 모든 siblings를 제거해라.

```js
$("#txt").siblings().remove();
```

<br>

- Fill in the blanks to empty the second child element of the element with id="nav".
  - id="nav" element의 두 번째 child element를 제거해라.

```js
var e = $("#nav").children();
e.eq(1).empty();
```

<br>