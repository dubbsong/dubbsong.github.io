---
layout: post
title: "(Positioning & Layout 01) display 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS display Property

###### display 속성

------

<br>

<br>

## display: block

- Every element on a webpage is a rectangular box.
  - 웹페이지의 모든 element는 직사각형 상자이다.
- The `display` property determines how that rectangular box behaves.
  - `display` 속성은 사각형 상자의 동작을 결정한다.
- A block element is an element that takes up the fullest width available, with line breaks before and after.
  - block element는 사용 가능한 최대 너비를 차지하는 element이며, 앞뒤에 줄 바꿈이 있다.
- The style rules in the following example display the inline \<span> elements as block-level elements:
  - 다음 예제의 style 규칙은, inline \<span> element를 block-level element로 표시한다.

<br>

- HTML:

```html
<span>First paragraph. </span>
<span>Second paragraph. </span>
<span>Third paragraph. </span>
<span>Fourth paragraph. </span>
<span>Fifth paragraph. </span>
```

<br>

- CSS:

```css
span {
   display: block;
}
```

[코드 실행 확인](https://code.sololearn.com/562/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-01-01.png)

------

<br>

## display: inline

- An `inline` element only takes up as much width as necessary, and does not force line breaks.
  - `inline` element는 필요한 만큼만 너비를 차지하며, 줄 바꿈을 강제하지 않는다.

<br>

- CSS:

```css

```

[코드 실행 확인](https://code.sololearn.com/563/#css)

<br>

- The code above will produce the following result:
  - 위 코드는 다음 결과를 생성한다.

![img](/assets/img/css-sololearn-positioning & layout-01-02.png)

<br>

> Setting the display property of an element only changes how the element is displayed, not what kind of element it is.
>
> element의 display 속성을 설정하면 element의 종류가 아닌, element의 표시 방법만 변경된다.

> So, an inline element with `display:block` is not allowed to to have other block elements inside it.
>
> 따라서, `display:block`이 있는 inline element는 그 안에 다른 block element를 가질 수 없다.

------

<br>

## display: none

- `display: none` hides an element, so it does not take up any space.
  - `display: none`은 element를 숨기므로, 어떤 공간도 차지하지 않는다.
- The element will be hidden, and the page will be displayed as if the element is not there.
  - element가 숨겨지고, element가 없는 것처럼 페이지가 표시된다.

<br>

- HTML:

```html
<h1>값을 none으로 설정하면, 이 텍스트는 표시되지 않는다. </h1>
<p>값을 none으로 설정했기 때문에, 이 토막글의 제목은 표시되지 않는다. </p>
```

<br>

- CSS:

```css
h1 {
   display: none;
}
```

[코드 실행 확인](https://code.sololearn.com/564/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-01-03.png)

<br>

> There are plenty of other display values, such as `list-item`, `table`, `table-cell`, `table-column`, `grid`, etc.
>
> `list-item`, `table`, `table-cell`, `table-column`, `grid` 등과 같은 많은 display 값들이 있다.

------

<br>

## QUIZ

- What value of the "display" property makes the inline element act as a blocking level element?
  - "display" 속성의 어떤 값으로 inline element가 block-level element의 역할을 하는가?

> `block`

<br>

- What value of the "display" property makes the block level element act as an inline element?
  - "display" 속성의 어떤 값으로 block level element가 inline element의 역할을 하는가?

> `display: inline;`

<br>

- Make the element with the id="mystyle" disappear:
  - id="mystyle" element를 안 보이게 해라.

```css
#mystyle {
   display: none;
}
```

<br>