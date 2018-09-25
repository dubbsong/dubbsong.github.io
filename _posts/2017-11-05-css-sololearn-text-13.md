---
layout: post
title: "(Text 13) letter-spacing 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS letter-spacing Property

###### letter-spacing 속성

<br>

- The letter-spacing property specifies the `space between characters` in a text.
  - letter-spacing 속성은 텍스트의 `문자 사이 간격`을 지정한다.
- The values can be set as:
  - 값은 다음과 같이 설정할 수 있다.

<br>

- `normal`: defines the default style with no extra space between characters
  - 문자 사이에 여분의 간격이 없는 기본 style을 정의한다.
- `length`: defines an extra space between characters using measurement units like px, pt, cm, mm, etc.;
  - px, pt, cm, mm 등과 같은 측정 단위를 사용해서 문자 사이에 여분의 간격을 정의한다.
- `inherit`: inherits the property from its parent element;
  - parent(부모) element에서 속성을 상속받는다.

<br>

- HTML:

```html
<p class="normal">This paragraph has no additional letter-spacing applied. </p>
<p class="positive">This paragraph is letter-spaced at 4px. </p>
```

<br>

- CSS:

```css
p.normal {
   letter-spacing: normal;
}

p.positive {
   letter-spacing: 4px;
}
```

[코드 실행 확인](https://code.sololearn.com/531/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-13-01.png)

------

<br>

## Using Negative Values

###### 음수 값 사용

<br>

- For defining an extra space between characters, negative values are also permitted.
  - 문자 사이에 여분의 간격을 정의하기 위해, 음수 값도 허용이 된다.
- Here is an example demonstrating the difference between `positive` and `negative` values:
  - 다음 예제는 `positive 값(양수)`와 `negative 값(음수)`의 차이점을 보여준다.

<br>

- HTML:

```html
<p class="positive">This paragraph is letter-spaced at 4px </p>
<p class="negative">This paragraph is letter-spaced at -1.5px </p>
```

<br>

- CSS:

```css
p.positive {
   letter-spacing: 4px;
}

p.negative {
   letter-spacing: -1.5px;
}
```

[코드 실행 확인](https://code.sololearn.com/532/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-13-02.png)

<br>

> Always test your result, to ensure the text is readable.
>
> 텍스트를 읽을 수 있도록 항상 결과를 테스트해라.

------

<br>

## QUIZ

- Drag and drop from the options below to set the letter spacing of the paragraph:
  - 토막글의 문자 간격을 설정해라.

```css
p {
   letter-spacing: 4px;
}
```

<br>

- Fill in the blank to make the letter spacing -1cm:
  - 문자 간격을 -1cm로 만들어라.

> `letter-spacing: -1cm;`

<br>