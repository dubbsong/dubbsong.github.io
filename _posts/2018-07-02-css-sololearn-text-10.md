---
layout: post
title: "(Text 10) 텍스트 들여 쓰기"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Indenting the Text

###### 텍스트 들여 쓰기

------

<br>

<br>

## The text-indent Property

###### text-indent 속성

<br>

- The text-indent property specifies how much horizontal space should be left before the beginning of the first line of the text.
  - text-indent 속성은 텍스트의 첫 번째 줄 시작 전에 가로 간격을 얼마나 두어야 하는지를 지정한다.
- Property values are `length` (px, pt, cm, em, etc.), %, and `inherit`.
  - 속성 값은 `length` (px, pt, cm, em 등), %, `inherit`이다.

<br>

- HTML:

```html
<p>
   This is an example of <strong>text-indent</strong> property.
   Fisrt line of our text is indented to the right in 60px.
   Besides pixels you can also use other measurement units,
   like pt, cm, em, etc.
</p>
```

<br>

- CSS:

```css
p {
   text-indent: 60px;
}
```

[코드 실행 확인](https://code.sololearn.com/526/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-10-01.png)

<br>

> Negative values are allowed.
>
> 음수 값은 허용된다.

> The first line will be indented to the left if the value is negative.
>
> 값이 음수라면, 첫 번째 줄은 왼쪽으로 들여 쓰기 된다.

------

<br>

## QUIZ

- The position of which block is specified by the text-indent property?
  - text-indent 속성에 의해 지정된 블록의 위치는 어디인가?

> `The first line of the text block`
>
> 텍스트 블록의 첫 번째 줄

<br>