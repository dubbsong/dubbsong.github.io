---
layout: post
title: "(Basics 11) HTML 테이블"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Table

###### HTML 테이블

------

<br>

<br>

## Creating a Table

###### 테이블 생성

<br>

- Tables are defined by using the `<table>` tag.
  - 테이블은 `<table>` 태그를 사용해서 정의된다.
- Tables are divided into table rows with the `<tr>` tag.
  - 테이블은 `<tr>` 태그가 있는 테이블 row로 나뉜다.
- Table rows are divided into table columns (table data) with the `<td>` tag.
  - 테이블 row는 `<td>` 태그가 있는 테이블 column(테이블 데이터)으로 나뉜다.

<br>

- Here is an example of a table with `one row` and `three columns`:
  - 다음은 `하나의 row`와 `세 개의 column`이 있는 테이블의 예이다.

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
> 테이블 데이터 태그 \<td>는, 테이블 내에서 데이터 컨테이너 역할을 한다.

> They can contain all sorts of HTML elements, such as text, images, lists, other tables, and so on.
>
> 테이블에는 텍스트, 이미지, list, 다른 데이블 등과 같은 모든 종류의 HTML element가 포함될 수 있다.

------

<br>

## The border and colspan Attributes

###### border & colspan 속성

<br>

- A border can be added using the `border` attribute:
  - 테두리는 `border` 속성을 사용해서 추가할 수 있다.

```html
<table border="2">
```

<br>

- A table `cell` can span two or more columns:
  - 테이블 `cell`은 두 개 이상의 column에 걸쳐있을 수 있다.

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

[코드 실행 확인](https://code.sololearn.com/27/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-basics-11-01.jpeg)

<br>

> The border attribute is not supported in HTML5.
>
> border 속성은 HTML5에서 지원되지 않는다.

------

<br>

## Colspan Color

###### colspan 색상

<br>

- The example below demonstrates the `colspan` attribute in action:
  - 아래 예제는 동작 중인 `colspan` 속성을 보여준다.

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

[코드 실행 확인](https://code.sololearn.com/28/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-basics-11-02.jpeg)

<br>

- You can see that the cell containing "Orange" spans two cells.
  - "Orange"를 포함하는 cell이 두 개의 cell에 걸쳐있음을 볼 수 있다.

<br>

> To make a cell span more than one row, use the `rowspan` attribute.
>
> 하나의 row를 확장한 cell로 만들려면, `rowspan` 속성을 사용해라.

------

<br>

## The align and bgcolor Attributes

###### align & bgcolor 속성

<br>

- To change your table's position, use the `align` attribute inside your table tag:
  - 테이블의 위치를 변경하려면, 테이블 태그 내에 `align` 속성을 사용해라.

```html
<table align="center">
```

<br>

- Now let's specify a background color of red for a table cell.
  - 이제 테이블 cell에 빨간색 배경색을 지정해보자.
- To do that, just use the bgcolor attribute.
  - 그러기 위해서는, bgcolor 속성을 사용해라.

```html
<table border="2">
   <tr>
      <td bgcolor="red">Red</td>
      <td>Blue</td>
      <td>Green</td>
   </tr>
   <tr>
      <td>Yellow</td>
      <td colspan="2">Orange</td>
   </tr>
</table>
```

[코드 실행 확인](https://code.sololearn.com/29/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-basics-11-03.jpeg)

<br>

> In the case of styling elements, CSS is more effective than HTML.
>
> style element의 경우, CSS가 HTML보다 효과적이다.

------

<br>

## QUIZ

- What tag is used to create columns in a row?
  - row의 column을 만드는 데 사용되는 태그는 무엇인가?

> `td`

<br>

- What attribute is used to expand a cell for two or more cells?
  - 두 개 이상의 cell을 확장하는 데 사용되는 속성은 무엇인가?

> `colspan`

<br>

- What attribute is used to change the color of a cell?
  - cell의 색상을 변경하는 데 사용되는 속성은 무엇인가?

> `bgcolor`

<br>
