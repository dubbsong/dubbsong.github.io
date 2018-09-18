---
layout: post
title: "(Text 04) font-weight 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS font-weight Property

###### font-weight 속성

<br>

- The font-weight controls the boldness or thickness of the text.
  - font-weight는 텍스트의 굵기 또는 두께를 제어한다.
- The values can be set as `normal` (default size), `bold`, `bolder`, and `lighter`.
  - 값은 `보통`(기본 사이즈), `굵게`, `더 굵게`, `얇게`로 설정할 수 있다.

<br>

- HTML:

```html
<p class="light">This is a font with a "lighter" weight. </p>
<p class="bold">This is a font with a "bold" weight. </p>
<p class="bolder">This is a font with a "bolder" weight. </p>
```

<br>

- CSS:

```css
p.light {
   font-weight: lighter;
}

p.bold {
   font-weight: bold;
}

p.bolder {
   font-weight: bolder;
}
```

[코드 실행 확인](https://code.sololearn.com/516/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-04-01.png)

<br>

- You can also define the font weight with a number from `100` (thin) to `900` (thick), according to how thick you want the text to be.
  - 텍스트가 얼마나 두꺼운지에 따라 글꼴 두께를 100(얇음)에서 900(두꺼움)까지의 숫자로 정의할 수도 있다.
- 400 is the same as normal, and 700 is the same as bold.
  - 400은 보통과 같고, 700은 굵게 표시된다.

<br>

- HTML:

```html
<p class="light">This is a font with a "lighter" weight. </p>
<p class="thick">This is a font with a "bold" weight. </p>
<p class="thicker">This is a font with a "700" weight. </p>
```

<br>

- CSS:

```css
p.light {
   font-weight: lighter;
}

p.thick {
   font-weight: bold;
}

p.thicker {
   font-weight: 700;
}
```

[코드 실행 확인](https://code.sololearn.com/517/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-04-02.png)

<br>

> The HTML `<strong>` tag also makes the text `bold`.
>
> HTML `<strong>` 태그도 텍스트를 `bold(굵게)` 표시한다.

------

<br>

## QUIZ

- Which CSS property is used for bolding the text?
  - 텍스트를 강조하기 위해 사용되는 CSS 속성은 무엇인가?

> `font-weight`

<br>

- What numeric values are used for the font-weight property?
  - font-weight 속성에는 어떤 숫자 값이 사용되는가?

> `100 - 900`

<br>
