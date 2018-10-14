---
layout: post
title: "(CSS3 Basics 12) Module 5 Quiz"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

## QUIZ

- In the following code snippet, what value is given for the bottom-right corner?
  - 다음 코드 조각에서, 오른쪽 하단 모서리에 어떤 값이 주어지는가?

```css
border-radius: 10px 20px 30px 40px;
```

> `30`

<br>

- When defining a new font in CSS3, use...
  - CSS3에서 새 글꼴을 정의할 때 ...을 사용한다.

> `@font-face`

<br>

- Drag and drop from the options below to color the text in the paragraph with id "mytext" red.
  - id가 "mytext"인 토막글의 텍스트를 빨간색으로 만들어라.
- Also, add a black shadow to the text that is 5 pixels to the right and 3 pixels down.
  - 또한, 텍스트의 오른쪽에 5 픽셀, 아래쪽에 3 픽셀의 검은색 그림자를 추가해라.

```css
#mytext {
   text-shadow: 5px 3px #000;
   color: red;
}
```

<br>

- Fill in the blanks so that the first line of the paragraph uses the newly defined font called "test".
  - 토막글의 첫 번째 줄에 "test"라는 새로 정의된 글꼴을 사용해라.

```css
@font-face {
   font-family: "test";
   src: url(test.ttf);
}

p::first-line {
   font-family: "test";
}
```

<br>