---
layout: post
title: "(Text 09) text-decoration 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS text-decoration Property

###### text-decoration 속성

<br>

- The text-decoration property specifies how the text will be decorated.
  - text-decoration 속성은 텍스트를 어떻게 decorate 할지를 지정한다.

<br>

- Commonly used values are:
  - 일반적으로 사용되는 값은 다음과 같다.

<br>

- `none`: The default value, this defines a normal text
  - 기본값, 일반 텍스트를 정의한다.
- `inherit`: Inherits this property from its parent element
  - parent(부모) element에서 속성을 상속받는다.
- `overline`: Draws a horizontal line above the text
  - 텍스트 위에 가로 줄을 그린다.
- `underline`: Draws a horizontal line below the text
  - 텍스트 아래에 가로 줄을 그린다.
- `line-through`: draws a horizontal line through the text (substitutes the HTML `<s>` tag)
  - 텍스트를 가로지르는 가로 줄을 그린다.
  - (HTML `<s>` 태그를 대신 사용한다)

<br>

- The example below demonstrates the difference between each value.
  - 아래 예제는 각 값의 차이점을 보여준다.

<br>

- HTML:

```html
<p class="none">This is default style of the text (none). </p>
<p class="inherit">This text inherits the decoration of the parent. </p>
<p class="overline">This is overlined text. </p>
<p class="underline">This is underlined text. </p>
<p class="line-through">This is lined-through text. </p>
```

<br>

- CSS:

```css
p.none {
   text-decoration: none;
}

p.inherit {
   text-decoration: inherit;
}

p.overline {
   text-decoration: overline;
}

p.underline {
   text-decoration: underline;
}

p.line-through {
   text-decoration: line-through;
}
```

[코드 실행 확인](https://code.sololearn.com/525/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-09-01.png)

<br>

> You can combine the `underline`, `overline`, or `line-through` values in a space-separated list to add multiple decoration lines.
>
> 공백으로 구분된 list에 `underline`, `overline` 또는 `line-through` 값을 결합해서 여러 개의 decoration 줄을 추가할 수 있다.

<br>

<br>

- Another value of text-decoration property is `blink` which makes the text blink.
  - text-decoration 속성의 또 다른 값은 텍스트를 깜빡이는 `blink`이다.

<br>

- CSS syntax looks like this:
  - CSS 구문은 다음과 같다.

```css
text-decoration: blink;
```

<br>

> This value is valid but is deprecated and most browsers ignore it.
>
> 이 값은 유효하지만 더 이상 사용되지 않으며, 대부분의 브라우저는 이 값을 무시한다.

------

<br>

## QUIZ

- What value of the text-decoration property substitutes the HTML S tag?
  - text-decoration 속성의 어떤 값이 HTML S 태그를 대신하는가?

> `line-through`

<br>

- Fill in the blanks to make the text underlined:
  - 텍스트에 밑줄을 생성해라.

```css
#mystyle {
   text-decoration: underline;
}
```

<br>