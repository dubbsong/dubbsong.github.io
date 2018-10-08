---
layout: post
title: "(CSS3 Basics 03) 둥근 모서리"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Rounded Corners

###### 둥근 모서리

------

<br>

<br>

## The border-radius Property

###### border-radius 속성

<br>

- With CSS3, you can give any element "rounded corners" by using the `border-radius` property.
  - CSS3와 함께 `border-radius` 속성을 사용해서 "둥근 모서리" element를 지정할 수 있다.

<br>

- CSS:

```css
border-radius: 20px;
background-color: green;
color: white;
```

[코드 실행 확인](https://code.sololearn.com/580/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-03-01.png)

<br>

- Specific border radius values can be applied for the border-radius property in the following order: `top-left`, `top-right`, `bottom-right`, `bottom-left`.
  - 특정 테두리 반경 값은 다음 순서대로  border-radius 속성에 적용할 수 있다.
  - `top-left`, `top-right`, `bottom-right`, `bottom-left`

```css
border-radius: 0 0 20px 20px;
```

[코드 실행 확인](https://code.sololearn.com/581/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-03-02.png)

<br>

> The value of border-radius can also be specified in `percentages`.
>
> border-radius 값은 `백분율`로 지정할 수도 있다.

------

<br>

## Creating a Circle

###### 원 만들기

<br>

- A rectangle can be turned into a circle using only CSS.
  - CSS만 사용해서 직사각형을 원으로 변경할 수 있다.
- To create a circle, the border radius should be half of the height and the width.
  - 원을 만들려면, 테두리 반경이 높이와 너비의 절반이어야 한다.

<br>

- The rectangle in the example below has a width and height of 200px.
  - 아래 예제의 직사각형은 너비와 높이가 200px이다.
- By setting the border radius to `100px`, the corners will be rounded to form a circle:
  - 테두리 반경을 `100px`로 설정하면, 모서리가 둥근 원형이 된다.

```css
div {
   width: 200px;
   height: 200px;
   border-radius: 100px;
   background-color: green;
   color: white;
}
```

[코드 실행 확인](https://code.sololearn.com/582/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-03-03.png)

------

<br>

## QUIZ

- Add the border-radius values to indicate 0 pixels to the top-left, 15pixels to the bottom-left, 10 pixels to the bottom-right, 20 pixels to the top-right:
  - border-radius 값을 추가해서 top-left를 0 픽셀, bottom-left를 15 픽셀, bottom-right를 10 픽셀, top-right를 20 픽셀로 나타내라.

``` css
.test {
   border-radius: 0px 20px 10px 15px;
}
```

<br>

- To make a circle, the border radius should be ...
  - 원을 만들려면, 테두리 반경이 ...해야 한다.

> `equal to half of the height and the width`
>
> 높이와 너비의 절반과 같아야 한다

<br>