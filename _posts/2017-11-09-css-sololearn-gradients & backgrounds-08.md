---
layout: post
title: "(Gradients & Backgrounds 08) Module 6 Quiz"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

## QUIZ

- Add a circular radial gradient to produce red and blue, with color-stops accordingly at 15 pixels and 25 pixels.
  - 15 픽셀과 25 픽셀에 따라 color-stops를 사용해서, 빨간색과 파란색을 생성하는 원형 radial(방사형) gradient를 추가해라.

```css
background: radial-gradient(50px 50px, red 15px, blue 25px);
```

<br>

- In the background-clip property, which value allows for the creation of transparent borders?
  - background-clip 속성에서 투명한 테두리를 생성할 수 있는 값은 무엇인가?

> `padding-box`

<br>

- Drag and drop from the options below to make the background image of the element 100 x 100 pixels in size.
  - element의 배경 이미지를 100 x 100 픽셀 크기로 만들어라.
- Also, set the opacity of the element to 50%:
  - 또한 element의 불투명도를 50%로 설정해라.

```css
#element {
   background-image: url('test.jpg');
   background-size: 100px 100px;
   opacity: 0.5;
}
```

<br>

- Drag and drop from the options below to apply 50% opacity to the div, and make it also work in IE:
  - div에 50% 불투명도를 적용하고, IE에서도 작동되게 만들어라.

```css
div {
   opacity: 0.5;
   filter: alpha(opacity=50);
}
```

<br>