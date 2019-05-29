---
layout: post
title: "(Properties 04) 너비 & 높이"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Width and Height

###### 너비 & 높이

<br>

- To style a `<div>` element to have a total width and height of `100px`:
  - 전체 너비와 높이가 `100px`이 되도록 `<div>` element style을 지정해보자.

<br>

- HTML:

```html
<div>
   The total width and height of this element is 100px.
</div>
```

<br>

- CSS:

```css
div {
   border: 5px solid green;
   width: 90px;
   height: 90px;
}
```

[코드 실행 확인](https://code.sololearn.com/541/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-04-01.png)

<br>

> The total width and height of the box will be the 90px + 5px(border) + 5px(border) = 100px;
>
> 상자의 전체 너비와 높이는 90px + 5px(border) + 5px(border) = 100px이 된다.

------

<br>

## Width and Height Measurement

###### 너비와 높이 측정

<br>

- The width and height of an element can be also assigned using `percents`.
  - element의 너비와 높이도 `퍼센트`를 사용해서 지정할 수 있다.
- In the example below the width of an element is assigned in percentages, the height is in pixels.
  - 아래 예제에서 element의 너비는 백분율로 지정되고, 높이는 픽셀 단위이다.

<br>

- HTML:

```html
<div>
   The total width of this element is <strong>100%</strong> and the total height is <strong>100px</strong> .
</div>
```

<br>

- CSS:

```css
div {
   border: 5px solid green;
   width: 100%;
   height: 90px;
}
```

[코드 실행 확인](https://code.sololearn.com/542/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-04-02.png)

------

<br>

## The Minimum and Maximum Sizes

###### 최소 & 최대 크기

<br>

- To set the minimum and maximum height and width of an element, you can use the following properties:
  - element의 최소 및 최대 높이와 너비를 설정하려면, 다음 속성을 사용할 수 있다.

<br>

- `min-width`: the minimum width of an element
  - element의 최소 너비
- `min-height`: the minimum height of an element
  - element의 최소 높이
- `max-width`: the maximum width of an element
  - element의 최대 너비
- `max-height`: the maximum height of an element
  - element의 최대 높이

<br>

- In the example below, we set the minimum height and maximum width of different paragraphs to 100px.
  - 아래 예제에서는, 다른 토막글의 최소 높이와 최대 너비를 100px로 설정했다.

<br>

- HTML:

```html
<p class="first">
   The <strong>minimum height</strong> of this paragraph is set to 100px.
</p>
<p class="second">
   The <strong>maximum width</strong> of this paragraph is set to 100px.
</p>
```

<br>

- CSS:

```css
p.first {
   border: 5px solid green;
   min-height: 100px;
}

p.second {
   border: 5px solid green;
   max-width: 100px;
}
```

[코드 실행 확인](https://code.sololearn.com/543/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-04-02)

------

<br>

## QUIZ

- Fill in the blanks to set the height of the div to 50px, the width to 100px:
  - div의 높이를 50px, 너비를 100px로 설정해라.

```css
div {
   border: none;
   width: 100px;
   height: 50px;
}
```

<br>

- Width and height are usually expressed in:
  - 너비와 높이는 일반적으로 다음 단위로 표현된다.

> `pixels and percents`

<br>

- Set the minimum allowable width of the div to 200px:
  - div의 최소 허용 너비를 200px로 설정해라.

```css
div {
   min-width: 200px;
}
```

<br>