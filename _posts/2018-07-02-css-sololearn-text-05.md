---
layout: post
title: "(Text 05) font-variant"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS font-variant Property

###### font-variant 속성

<br>

- The CSS font-variant property allows you to convert your font to all small caps.
  - CSS font-variant 속성을 사용하면 글꼴을 모두 작은 대문자로 변환할 수 있다.
- The values can be set as `normal`, `small-caps`, and `inherit`.
  - 값은 `normal`, `small-caps`, `inherit`으로 설정할 수 있다.

<br>

- HTML:

```html
<p class="normal">Paragraph font variant set to normal. </p>
<p class="small">Paragraph font variant set to small-caps. </p>
```

<br>

- CSS:

```css
p.normal {
   font-variant: normal;
}

p.small {
   font-variant: small-caps;
}
```

[코드 실행 확인](https://code.sololearn.com/518/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-05-01.png)

<br>

> Not every font supports CSS font-variant, so be sure to test before you publish.
>
> 모든 글꼴이 CSS font-variant를 지원하는 것은 아니므로, 게시하기 전에 테스트를 해야 한다.

------

<br>

## QUIZ

- Make the text of the paragraph small capitals:
  - 토막글의 텍스트를 작은 대문자로 만들어라.

```css
p {
   font-variant: small-caps;
}
```

<br>