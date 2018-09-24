---
layout: post
title: "(Text 08) 텍스트 세로 정렬"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Aligning Text Vertically

###### 텍스트 세로 정렬

------

<br>

<br>

## The vertical-align Property

###### vertical-align 속성

<br>

- The vertical-align property sets an element's vertical alignment.
  - vertical-align 속성은 element의 세로 정렬을 설정한다.
- Commonly used values are `top`, `middle`, and `bottom`.
  - 일반적으로 사용되는 값은 `top`, `middle`, `bottom`이다.

<br>

- The example below shows how to vertically align the text between the table.
  - 아래 예제는 테이블 사이에서 텍스트를 어떻게 세로 정렬하는지 보여준다.

<br>

- HTML:

```html
<table border="1" cellpadding="2" cellspacing="0" style="height: 150px;">
   <tr>
      <td class="top">Top</td>
      <td class="middle">Middle</td>
      <td class="bottom">Bottom</td>
   </tr>
</table>
```

<br>

- CSS:

```css
td.top {
   vertical-align: top;
}

td.middle {
   vertical-align: middle;
}

td.bottom {
   vertical-align: bottom;
}
```

[코드 실행 확인](https://code.sololearn.com/522/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-08-01.png)

<br>

<br>

- The vertical-align property also takes the following values: `baseline`, `sub`, `super`, % and `px` (or pt, cm).
  - vertical-align 속성에는 `baseline`, `sub`, `super`, %, `px`(or pt, cm) 값도 사용된다.
- The example below shows the difference between them.
  - 아래 예제는 이것들의 차이점을 보여준다.

<br>

- HTML:

```html
<P>This is an <span class="baseline">inline text</span>example. </P>
<P>This is a <span class="sub">sub line text</span>example. </P>
<P>This is a <span class="super">super line text</span>example. </P>
<P>This is a <span class="pixel">pixel</span>example. </P>
```

<br>

- CSS:

```css
span.baseline {
   vertical-align: baseline;
}

span.sub {
   vertical-align: sub;
}

span.super {
   vertical-align: super;
}

span.pixel {
   vertical-align: -10px;
}
```

[코드 실행 확인](https://code.sololearn.com/523/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-08-02.png)

<br>

> Instead of `px` values, you can use `pt` (points), `cm` (centimeters) and % (percentage) values.
>
> `px` 값 대신, `pt`, `cm`, % 값을 사용할 수 있다.

<br>

<br>

- Vertical align property does not act the same way for all elements.
  - 세로 정렬 속성은 모든 element에 대해 동일한 방식으로 동작하지 않는다.
- For example, some additional CSS styling is needed for div elements.
  - 예를 들어, div element에는 CSS style이 추가로 필요하다.

<br>

- HTML:

```html
<div class="main">
   <div class="paragraph">
      This text is aligned to the middle
   </div>
</div>
```

<br>

- CSS:

```css
.main {
   height: 150px; width: 400px;
   background-color: LightSkyBlue;
   display: inline-table;
}

.paragraph {
   display: table-cell;
   vertical-align: middle;
}
```

[코드 실행 확인](https://code.sololearn.com/524/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-08-03.jpeg)

<br>

- `display: inline-table;` and `display: table-cell;` styling rules are applied to make the vertical-align property work with divs.
  - `display: inline-table;`과 `display: table-cell;` style 규칙을 적용해서, div에 vertical-align 속성을 적용한다.

------

<br>

## QUIZ

- Fill in the blanks to set the vertical alignment of all elements having class="test" to bottom:
  - class="test"를 갖는 모든 element의 세로 정렬을 bottom으로 설정해라.

```css
.test {
   vertical-align: bottom;
}
```

<br>

- Negative values can be used with the vertical-align property.
  - 음수 값은 vertical-align 속성과 함께 사용할 수 있다.

> `True`

<br>

- Does the vertical-align property act the same way for all elements?
  - vertical-align 속성이 모든 element에 대해 동일한 방식으로 동작하는가?

> `No`

<br>