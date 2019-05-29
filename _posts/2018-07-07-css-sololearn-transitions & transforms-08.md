---
layout: post
title: "(Transitions & Transforms 08) Module 7 Quiz"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

## QUIZ

- Which of these is a valid CSS3 transformation statement?
  - 다음 중 올바른 CSS3 변환 문은 무엇인가?

> [ ] modify()
>
> [ ] simulate()
>
> [ ] skip()
>
> [ ] `scale()`

<br>

- How will an element with a statement transform: translate(0, 100px) behave?
  - 다음 명령문이 있는 element는 어떻게 변환하는가?

```css
translate(0, 100px);
```

> `Pushed down 100 pixels`

<br>

- Which transformation does not exist in CSS3?
  - CSS3에는 어떤 변환이 존재하는가?

> [ ] rotate3D
>
> [ ] `skewB`
>
> [ ] rotateX
>
> [ ] translateZ

<br>

- Fill in the blanks to rotate the object with the id "ball" 45 degrees counter-clockwise.
  - id="ball"이 45도인 객체를 시계 반대 방향으로 회전시켜라.

```css
#ball {
   transform: rotate(-45deg);
}
```

<br>

- Fill in the blanks to make the first letter of the paragraph red and bold.
  - 토막글의 첫 번째 글자를 빨간색과 굵은 글씨로 만들어라.
- Also, flip the paragraph upside down.
  - 토막글을 거꾸로 뒤집어라.

```css
p {
   transform: rotate(180deg);
}

p::first-letter {
   color: red;
   font-weight: bold;
}
```

<br>