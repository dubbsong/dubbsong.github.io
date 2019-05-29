---
layout: post
title: "(Text 06) color 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS color Property

###### color 속성

<br>

- The CSS `color` property specifies the color of the text.
  - CSS `color` 속성은 텍스트의 색상을 지정한다.
- One method of specifying the color of the text is using a `color name`: like red, green, blue, etc.
  - 텍스트의 색상을 지정하는 한 가지 방법은 빨간색, 초록색, 파란색 등의 `색상 이름`을 사용하는 것이다.

<br>

- HTML:

```html
<p class="example">The text inside the paragraph is green. </p>
The text outside the paragraph is black (by default).
토막글 외부의 텍스트는 기본적으로 검정색이다.
```

<br>

- CSS:

```css
p.example {
   color: green;
}
```

[코드 실행 확인](https://code.sololearn.com/519/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-06-01.png)

<br>

<br>

- Another way of defining colors is using `hexadecimal values` and `RGB`.
  - 색상을 정의하는 또 다른 방법은 `16진수 값`과 `RGB`를 사용하는 것이다.
- Hexadecimal form is a pound sign (\#) followed by at most, `6 hex values` (0-F).
  - 16진수 form은 pound 기호(\#) 다음에, 기껏해야 `6개의 16진수 값`(0-F)이 온다.
- RGB defines the individual values for `Red`, `Green`, and `Blue`.
  - RGB는 `Red`, `Green`, `Blue`의 각 값을 정의한다.

<br>

- In the example below, we use hexadecimal value to set the heading color to blue, and RGB form to make the paragraph red.
  - 아래 예제에서는 16진수 값을 사용해서 heading 색상을 파란색으로 설정하고, RGB form을 사용해서 토막글을 빨간색으로 설정한다.

<br>

- HTML:

```html
<h1>This is a heading </h1>
<p class="example">This is a paragraph </p>
```

<br>

- CSS:

```css
h1 {
   color: #0000FF;
}

p.example {
   color: rgb(255, 0, 0);
}
```

[코드 실행 확인](https://code.sololearn.com/520/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-06-02.png)

------

<br>

## QUIZ

- Drag and drop from the options below to make the text of the "colored" class green:
  - "colored" class의 텍스트를 초록색으로 만들어라.

```css
p.colored {
   color: green;
}
```

<br>

- Which of the following options are accepted by the color property?
  - 다음 중 color 속성에서 허용되는 옵션은 무엇인가?

> [ ] octal
>
> [ ] `color names`
>
> [ ] `hexadecimal`

<br>