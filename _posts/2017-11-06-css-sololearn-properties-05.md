---
layout: post
title: "(Properties 05) background-color 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS background-color Property

###### background-color 속성

<br>

- The `background-color` property is used to specify the background color of an element.
  - `background-color` 속성은 element의 배경색을 지정하는 데 사용된다.

<br>

- HTML:

```html
<p>
   The background color of this page is set to LightSkyBlue.
</p>
```

<br>

- CSS:

```css
body {
   background-color: #87CEFA;
}
```

[코드 실행 확인](https://code.sololearn.com/544/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-05-01.png)

------

<br>

## The Background Color Values

###### 배경색 값

<br>

- The color of the background can be defined using three different formats: a `color name`, `hexadecimal values`, and `RGB`.
  - 배경의 색상은 `color name`, `16진수 값`, `RGB`의 세 가지 형식을 사용해서 정의할 수 있다.

<br>

- In the example below, the body, h1, and p elements are assigned different background colors:
  - 아래 예제에서 body, h1, p element는 서로 다른 배경색이 지정된다.

<br>

- HTML:

```html
<h1>This is a heading </h1>
<p>This is a paragraph </p>
```

<br>

- CSS:

```css
body {
   background-color: #C0C0C0;
}

h1 {
   background-color: rgb(135, 206, 235);
}

p {
   background-color: LightGreen;
}
```

[코드 실행 확인](https://code.sololearn.com/545/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-05-02.png)

------

<br>

## QUIZ

- What property is used to describe the background color?
  - 배경색을 설명하는 데 사용되는 속성은 무엇인가?

> `background-color`

<br>

- Fill in the blanks to make the background color of the element with id="mystyle" black using hexadecimal color definition.
  - id="mystyle" element의 배경색을 16진수 색상 정의를 사용해서 검정색으로 만들어라.

```css
#mystyle {
   background-color: #000000;
}
```

<br>