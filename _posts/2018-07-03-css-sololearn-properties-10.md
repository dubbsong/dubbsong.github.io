---
layout: post
title: "(Properties 10) Styling the Tables"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Styling the Tables

------

<br>

<br>

## The Table Properties

###### Table 속성

<br>

- The look of an HTML table can be greatly improved with CSS.
  - CSS를 사용하면 HTML table의 모양을 크게 개선할 수 있다.

<br>

- The `border-collapse` property specifies whether the table borders are collapsed into a single border or separated as default.
  - `border-collapse` 속성은 table border를 하나의 border로 collapse 할지, 또는 기본값으로 구분할지를 지정한다.
- If the borders are separate, the `border-spacing` property can be used to change the spacing.
  - border가 구분된 경우, `border-spacing` 속성을 사용해서 간격을 변경할 수 있다.

<br>

- HTML:

```html
<table border="1">
   <tr>
      <td>Red</td>
      <td>Green</td>
   </tr>
   <tr>
      <td>Blue</td>
      <td>Yellow</td>
   </tr>
</table>
```

<br>

- CSS:

```css
table {
   border-collapse: separate;
   border-spacing: 20px 40px;
}
```

[코드 실행 확인](https://code.sololearn.com/556/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-10-01.png)

------

<br>

## The caption-side Property

###### caption-side 속성

<br>

- The `caption-side` property specifies the position of a table caption.
  - `caption-side` 속성은 table caption의 위치를 지정한다.
  - `caption`: 사진삽화 등에 붙인 설명
- The values can be set as `top` or `bottom`.
  - 값은 `top` 또는 `bottom`으로 설정할 수 있다.
- In the example below, we specify the placement of a table caption to `top`.
  - 아래 예제에서는 table caption의 위치를 `top`으로 지정한다.

<br>

- HTML:

```html
<table border="1">
   <caption>Some of Our Courses</caption>
   <tr>
      <th>Course name</th>
      <th>Lessons</th>
      <th>Quizzes</th>
   </tr>
   <tr>
      <td>C++</td>
      <td>81</td>
      <td>363</td>
   </tr>
   <tr>
      <td>JavaScript</td>
      <td>48</td>
      <td>144</td>
   </tr>
   <tr>
      <td>HTML</td>
      <td>38</td>
      <td>119</td>
   </tr>
   <tr>
      <td>CSS</td>
      <td>70</td>
      <td>174</td>
   </tr>
</table>
```

<br>

- CSS:

```css
caption {
   caption-side: top;
}
```

[코드 실행 확인](https://code.sololearn.com/557/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-10-02.png)

------

<br>

## The empty-cells Property

###### empty-cells 속성

<br>

- The `empty-cells` property specifies whether or not to display borders and background on empty cells in a table.
  - `empty-cells` 속성은 table의 빈 cell에 테두리와 배경을 표시할지 여부를 지정한다.

<br>

- `show`: the borders of an empty cell are rendered
  - 빈 cell의 border가 렌더링 된다.
- `hide`: the borders of an empty cell are not drawn
  - 빈 cell의 border를 그리지 않는다.

<br>

- Here is the empty-cells property that is used to hide borders of empty cells in the \<table> element.
  - 다음은 \<table> element에서 빈 cell의 border를 숨기는 데 사용되는 empty-cells 속성이다.

<br>

- HTML:

```html
<table border="1">
   <tr>
      <td>HTML</td>
      <td>CSS</td>
   </tr>
   <tr>
      <td>JavaScript</td>
      <td></td>
   </tr>
</table>
```

<br>

- CSS:

```css
table {
   border-collapse: separate;
   empty-cells: hide;
}
```

[코드 실행 확인](https://code.sololearn.com/558/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-10-03.png)

------

<br>

## The table-layout Property

###### table-layout 속성

<br>

- The `table-layout` specifies how the width of table columns is calculated.
  - `table-layout`은 table column의 너비를 계산하는 방법을 지정한다.

<br>

- `auto`: when column or cell width are not explicitly set, the column width will be in proportion to the amount of content in the cells that make up the column
  - column 또는 cell의 너비가 명시적으로 설정되지 않은 경우, column의 너비는 column을 구성하는 cell의 content 양에 비례한다.
- `fixed`: when column or cell width are not explicitly set, the column width will not be affected by the amount of content in the cells that make up the column.
  - column 또는 cell의 너비가 명시적으로 설정되지 않은 경우, column의 너비는 column을 구성하는 cell의 content 양에 영향을 받지 않는다.

<br>

- The table layout is set to `auto` by default.
  - table layout은 기본적으로 `auto`로 설정된다.
- The example below shows the difference between auto and fixed.
  - 아래 예제는 auto와 fixed의 차이점을 보여준다.

<br>

- HTML:

```html
<p>Table-layout is set to <strong>auto</strong></p>
<table class="auto">
   <tr>
      <td width="10%">500.000.000.000.000</td>
      <td width="90%">20.000</td>
   </tr>
</table>

<p>Table-layout is set to <strong>fixed</strong></p>
<table class="fixed">
   <tr>
      <td width="10%">500.000.000.000.000</td>
      <td width="90%">20.000</td>
   </tr>
</table>
```

<br>

- CSS:

```css
table {
   border-collapse: separate;
   width: 100%;
   border: 1px solid gray;
}

td {
   border: 1px solid gray;
}

table.auto {
   table-layout: auto;
}

table.fixed {
   table-layout: fixed;
}
```

[코드 실행 확인](https://code.sololearn.com/559/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-10-04.png)

------

<br>

## QUIZ

- The properties regarding table borders are:
  - table border에 관련된 속성은 다음과 같다.

> [ ] `border-collapse`
>
> [ ] border-length
>
> [ ] table-border-style
>
> [ ] `border-spacing`

<br>

- Fill in the blanks to position the caption of the table at the bottom:
  - table의 caption을 bottom에 위치시켜라.

```css
caption {
   caption-side: bottom;
}
```

<br>

- Fill in the blanks to hide the empty cells of the table.
  - table의 빈 cell을 숨겨라.

```css
table {
   empty-cells: hide;
}
```

<br>

- What is the default value of the table-layout property?
  - table-layout 속성의 기본값은 무엇인가?

> `auto`

<br>