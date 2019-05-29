---
layout: post
title: "(Text 07) 텍스트 가로 정렬"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Aligning Text Horizontally

###### 텍스트 가로 정렬

------

<br>

<br>

## The text-align Property

###### text-align 속성

<br>

- The text-align property specifies the horizontal alignment of text in an element.
  - text-align 속성은 element에서 텍스트의 가로 정렬을 지정한다.
- By default, text on your website is aligned to the left.
  - 기본적으로 웹사이트의 텍스트는 왼쪽에 정렬된다.
- However, at times you may require a different alignment.
  - 하지만 때로는 다른 정렬이 필요할 수도 있다.

<br>

- text-align property values are as follows: `left`, `right`, and `justify`.
  - text-align 속성 값은 `left`, `right`, `justify`가 있다.

<br>

- HTML:

```html
<p class="left">This paragraph is aligned to <strong>left.</strong></p>
<p class="right">This paragraph is aligned to <strong>right.</strong></p>
<p class="center">This paragraph is aligned to <strong>center.</strong></p>
```

<br>

- CSS:

```css
p.left {
   text-align: left;
}

p.right {
   text-align: right;
}

p.center {
   text-align: center;
}
```

[코드 실행 확인](https://code.sololearn.com/521/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-07-01.png)

<br>

> When text-align is set to `"justify"`, each line is stretched so that every line has equal width, and the left and right margins are straight (as in magazines and newspapers).
>
> text-align이 `"justify"`로 설정되면, 모든 줄이 동일한 너비를 가지고, 왼쪽 및 오른쪽 margin이 똑바로 되도록 각 줄이 늘어난다.

------

<br>

## QUIZ

- Which of the values below is NOT applicable for the text-align property?
  - 다음 중 text-align 속성에 적용할 수 없는 값은 무엇인가?

> [ ] left
>
> [ ] `even`
>
> [ ] right
>
> [ ] center

<br>