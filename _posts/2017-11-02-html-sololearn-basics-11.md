---
layout: post
title: "SoloLearn HTML 번역 - 11. Tables (Basics)"
categories: dev
tags: html
---

## Creating a Table

###### 테이블 만들기

<br>

- Tables are defined by using the `<table>` tag.
  - 테이블은 `<table>` 태그를 사용해서 정의된다.
- Tables are divided into table rows with the `<tr>` tag.
  - 테이블은 `<tr>` 태그를 사용해서 테이블 행으로 나눠진다.
  - `<tr>`: Defines a row in a table
- Table rows are divided into table columns (table data) with the `<td>` tag.
  - 테이블 행은 `<td>` 태그를 사용해서 테이블 열로 나눠진다.
  - `<td>`: Defines a cell in a table

<br>

- Here is an example of a table with `one row` and `three columns`:
  - 다음은 `하나의 행`과 `세 개의 열`이 있는 테이블의 예제이다.

```html
<table>
   <tr>
   	<td></td>
      <td></td>
      <td></td>
   </tr>
</table>
```

<br>

> Table data tags \<td> act as data containers within the table.
>
> 테이블 데이터 태그 \<td>는 테이블 내에서 데이터 컨테이너 역할을 한다.

> They can contain all sorts of HTML elements, such as text, images, lists, other tables, and so on.
>
> \<td>에는 텍스트, 이미지, 리스트, 다른 테이블 등과 같은 모든 종류의 HTML element가 포함될 수 있다.

------

<br>

## The Border and Colspan Attributes

###### border와 colspan 속성

<br>

- A border can be added using the `border` attribute:
  - 테두리는 `border` 속성을 사용해서 추가할 수 있다.

```html
<table border="2">
```

<br>

- A table `cell` can span two or more columns:
  - 테이블 `cell`은 두 개 이상의 열에 걸쳐 있을 수 있다.

```html
<table border="2">
   <tr>
   	<td>Red</td>
      <td>Blue</td>
      <td>Green</td>
   </tr>
   <tr>
   	<td><br /></td>
      <td colspan="2"><br /></td>
   </tr>
</table>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-basics-11-01.jpeg)

------

<br>

## Colspan Color

###### colspan 색

<br>

- The example below demonstrates the `colspan` attribute in action:
  - 아래 예제는 작동 중인 `colspan` 속성을 보여준다.

```html
<table border="2">
   <tr>
   	<td>Red</td>
      <td>Blue</td>
      <td>Green</td>
   </tr>
   <tr>
   	<td>Yellow</td>
      <td colspan="2">Orange</td>
   </tr>
</table>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-basics-11-02.jpeg)

<br>

- You can see that the cell containing "Orange" spans two cells.
  - "Orange"가 포함되어 있는 cell이 두 개의 cell에 걸쳐 있는 것을 볼 수 있다.

<br>

> To make a cell span more than one row, use the `rowspan` attribute.
>
> 한 행 이상의 cell 범위를 만들려면, `rowspan` 속성을 사용해라.

------

<br>

## The align and bgcolor Attributes

###### align과 bgcolor 속성

<br>

- To change your table's position, use the `align` attribute inside your table tag:
  - 테이블의 위치를 변경하려면, 테이블 태그 내에서 `align` 속성을 사용해라.

```html
<table align="center">
```

<br>

- Now let's specify a background color of red for a table cell.
  - 이제 테이블 cell에 빨간색 배경을 지정해보자.
- To do that, just use the bgcolor attribute.
  - 그렇게 하기 위해서는, bgcolor 속성을 사용해라.

```html
<table border="2">
   <tr>
   	<td bgcolor="red">Red</td>
      <td>blue</td>
      <td>Green</td>
   </tr>
   <tr>
   	<td>Yellow</td>
      <td colspan="2">Orange</td>
   </tr>
</table>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-basics-11-03.jpeg)

<br>

> In the case of styling elements, CSS is more effective than HTML.
>
> 스타일링 element의 경우, CSS가 HTML보다 효과적이다.

> Try our free `"Learn CSS"` course to learn more about CSS and styles.
>
> CSS와 스타일에 대해 더 배우려면 무료 `"Learn CSS"` 코스를 참조해라.

------

<br>

## QUIZ

- What tag is used to create columns in a row?
  - 행에서 열을 만드는 데 사용되는 태그가 무엇인가?

> [x] `td`
>
> [ ] cell
>
> [ ] tc
>
> [ ] column

<br>

- What attribute is used to expand a cell for two or more cells?
  - 두 개 이상의 cell에 대해, cell을 확장하는 데 사용되는 속성은 무엇인가?

> [ ] stretch
>
> [x] `colspan`
>
> [ ] rowspan
>
> [ ] width

<br>

- Fill in the blanks:
  - 빈칸을 채워라.

```html
<table>
   <tr>
   	<td>Text 1</td>
      <td>Text 2</td>
   </tr>
</table>
```

<br>

- What attribute is used to change the color of a cell?
  - cell의 색을 변경하는 데 사용되는 속성은 무엇인가?

> [ ] color
>
> [ ] cellColor
>
> [x] `bgcolor`
>
> [ ] background

<br>