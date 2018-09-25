---
layout: post
title: "(Text 14) word-spacing 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS word-spacing Property

###### word-spacing 속성

<br>

- The word-spacing property specifies the `space between words` in a text.
  - word-spacing 속성은 텍스트의 `단어 사이 간격`을 지정한다.
- Just like the letter-spacing property, you can set the word-spacing values as `normal`, `length`, and `inherit`.
  - letter-spacing 속성과 마찬가지로, word-spacing 값을 `normal`, `length`, `inherit`으로 설정할 수 있다.

<br>

- HTML:

```html
<p class="normal">This paragraph has no additional word-spacing applied. </p>
<p class="px">This paragraph is word-spaced at 30px. </p>
```

<br>

- CSS:

```css
p.normal {
   word-spacing: normal;
}

p.px {
   word-spacing: 30px;
}
```

[코드 실행 확인](https://code.sololearn.com/533/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-14-01.png)

<br>

> When a weird spacing is used, and it is necessary to keep the selected paragraph with normal word spacing, the `normal` option is usually used.
>
> 간격을 이상하게 사용하고, 선택한 토막글을 normal 단어 간격으로 유지해야 하는 경우, 일반적으로 `normal` 옵션이 사용된다.

------

<br>

## Measurement Units

###### 측정 단위

<br>

- To define an extra space between words, you can use positive measurement values like `px`, `pt`, `pc`, `cm`, `mm`, `inches`, `em`, and `ex`.
  - 단어 사이에 여분의 간격을 정의하려면, `px`, `pt`, `pc`, `cm`, `mm`, `inches`, `em`, `ex`와 같은 양수 측정 값을 사용할 수 있다.
- Negative values are also permitted.
  - 음수 값도 허용된다.

<br>

- HTML:

```html
<p class="positive">This paragraph is word-spaced at 20px. </p>
<p class="negative">This paragraph is word-spaced at -5px. </p>
```

<br>

- CSS:

```css
p.positive {
   word-spacing: 20px;
}

p.negative {
   word-spacing: -5px;
}
```

[코드 실행 확인](https://code.sololearn.com/534/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-14-02.png)

------

<br>

## QUIZ

- Fill in the blanks to make the word-spacing 15px:
  - word-spacing을 15px로 만들어라.

```css
p {
   word-spacing: 15px;
}
```

<br>

- Which measurement units cannot be used with the word-spacing property?
  - word-spacing 속성과 함께 사용할 수 없는 측정 단위는 무엇인가?

> [ ] pixels
>
> [ ] cm, mm, inches
>
> [ ] `feet, yards`
>
> [ ] points

<br>