---
layout: post
title: "(Positioning & Layout 03) Positioning Elements"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Positioning Elements

###### Positioning Elements

<br>

- The CSS positioning properties allow you to position an element.
  - CSS positioning 속성을 사용하면 element를 배치할 수 있다.
- It can also place an element behind another, and specify what should happen when an element's content is too big.
  - 또한 element를 다른 element 뒤에 배치할 수 있다.
  - 그리고 element의 content가 너무 클 경우, 어떻게 해야 하는지를 지정할 수 있다.

<br>

- Elements can be positioned using the top, bottom, left, and right properties.
  - element는 top, bottom, left, right 속성을 사용해서 배치할 수 있다.
- However, these properties will not work unless the `position` property is set first.
  - 하지만 `position` 속성이 먼저 설정되지 않으면, 이러한 속성이 작동하지 않는다.
- They also work differently depending on the positioning method.
  - 또한 positioning 메소드에 따라 다르게 작동한다.

<br>

#### Static Positioning

###### 정적 positioning

<br>

- HTML elements are positioned `static` by default.
  - HTML element는 기본적으로 `정적`으로 배치된다.
- A static positioned element is always positioned according to the normal flow of the page.
  - 정적으로 배치된 element는, 항상 페이지의 일반적인 flow에 따라 배치된다.

<br>

- HTML:

```html
<p>Paragraph with no position. </p>
<p>Paragraph with no position. </p>
<p>Paragraph with no position. </p>
<p>Paragraph with no position. </p>
<p>Paragraph with no position. </p>
<p class="position_static">이 토막글은 정적인 위치에 있다. </p>
```

<br>

- CSS:

```css
p.position_static {
   position: static;
   top: 30px;
   right: 5px;
   color: red;
}
```

[코드 실행 확인](https://code.sololearn.com/567/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-03-01.png)

<br>

> Static positioned elements are not affected by the top, bottom, left, and right properties.
>
> 정적으로 배치된 element는 top, bottom, left, right 속성의 영향을 받지 않는다.

------

<br>

## Fixed Positioning

###### 고정 positioning

<br>

- An element with a fixed position is positioned relative to the browser window, and will not move even if the window is scrolled.
  - 고정된 위치의 element는 브라우저 창에 상대적으로 배치된다.
  - 창을 스크롤해도 이동하지 않는다.
- The position can be specified using one or more of the properties `top`, `right`, `bottom`, and `left`.
  - 위치는 `top`, `right`, `bottom`, `left` 중 하나 이상의 속성을 사용해서 지정할 수 있다.
- In the example below, the paragraph is fixed to 30px from the top and 5px from the right.
  - 아래 예제에서 토막글은 위쪽에서 30px로 고정되고, 오른쪽에서 5px로 고정된다.

<br>

- CSS:

```css
p.position_fixed {
   position: fixed;
   top: 30px;
   right: 5px;
   color: red;
}
```

[코드 실행 확인](https://code.sololearn.com/568/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-03-02.png)

<br>

> Fixed positioned elements are removed from the normal flow.
>
> 고정된 위치 element는 일반적인 flow에서 제거된다.

> The document and other elements behave like the fixed positioned element does not exist.
>
> 문서 및 다른 element는 고정된 위치 element가 존재하지 않는 것처럼 동작한다.

> Fixed positioned elements can overlap other elements.
>
> 고정된 위치 element는 다른 element와 겹칠 수 있다.

------

<br>

## Relative Positioning

###### 상대적 positioning

<br>

- A relative positioned element is positioned relative to its normal position.
  - 상대적 위치 element는 일반적인 위치에 상대적으로 배치된다.
- The properties `top`, `right`, `bottom`, and `left` can be used to specify how the rendered box will be shifted.
  - `top`, `right`, `bottom`, `left` 속성은 렌더링 된 상자의 변화 방법을 지정하는 데 사용할 수 있다.

<br>

- CSS:

```css
p {
   width: 350px;
   border: 1px black solid;
   position: fixed;
}

span {
   background: green;
   color: white;
   position: relative;
   top: 150px;
   left: 50px;
}
```

[코드 실행 확인](https://code.sololearn.com/569/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-03-03.png)

<br>

- The content of relatively positioned elements can be moved and overlap other elements, but the reserved space for the element is still preserved in the normal flow.
  - 상대적으로 배치된 element의 content는 다른 element와 함께 이동될 수 있지만, element의 예약된 공간은 일반적인 flow에서 계속 유지된다.

<br>

> This value cannot be used for `table cells`, `columns`, `column groups`, `rows`, `row groups`, or `captions`.
>
> 이 값은 `table cells`, `columns`, `column groups`, `rows`, `row groups`, `captions`에 사용할 수 없다.

<br>

#### Absolute Positioning

###### 절대적 positioning

<br>

- An absolute position element is positioned relative to the first parent element that has a position other than static.
  - 절대적 위치 element는 static 이외의 위치에 있는 첫 번째 parent(부모) element를 기준으로 배치된다.
- If no such element is found, the containing block is \<html>.
  - 해당 element가 없으면, 포함하는 블록은 \<html>이다.

<br>

- Absolutely positioned elements are removed from the normal flow.
  - 절대적으로 배치된 element는 일반적인 flow에서 제거된다.
- The document and other elements behave like the absolutely positioned element does not exist.
  - 문서 및 다른 element는 절대적으로 배치된 element가 존재하지 않는 것처럼 동작한다.

<br>

> Absolutely positioned elements can overlap other elements.
>
> 절대적으로 배치된 element는 다른 element와 겹칠 수 있다.

------

<br>

## QUIZ

- Why is the "static" value used in positioning?
  - 왜 "static" 값이 positioning에 사용되는가?

> `To make the element run in the natural order of the page`
>
> element를 페이지의 자연적인 순서대로 실행하기 위해서

<br>

- Drag and drop from the options below to fix the paragraph to 100px from the top and 50px from the left:
  - 토막글을 위쪽에서 100px, 왼쪽에서 50px로 고정해라.

```css
p {
   position: fixed;
   left: 50px;
   top: 100px;
}
```

<br>

- What is the purpose of the "relative" value?
  - "relative" 값의 목적은 무엇인가?

> `It puts the element relative to the normal flow`
>
> element를 일반적인 flow에 상대적으로 배치한다

<br>
