---
layout: post
title: "(CSS3 Basics 11) @font-face 규칙"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS @font-face Rule

###### @font-face 규칙

<br>

- The `@font-face` rule allows custom fonts to be loaded into a webpage.
  - `@font-face` 규칙을 사용하면 사용자 정의 글꼴을 웹페이지에 로딩할 수 있다.
- With the help of this rule, designs are no longer limited to the fonts that are installed on a user's computer.
  - 이 규칙을 사용하면, 디자인은 더 이상 사용자의 컴퓨터에 설치된 글꼴로만 제한되지 않는다.

<br>

- In Internet Explorer 8 and earlier, the URL must point to an `Embedded OpenType` (eot) file, while Firefox, Chrome, etc. support `True Type Fonts` (ttf) fonts and `OpenType Fonts` (otf).
  - IE8과 이전 버전에서 Firefox, Chrome 등은 `True Type Fonts`(ttf) 글꼴과 `OpenType Fonts`(otf)를 지원하지만, URL은 `Embedded OpenType`(eot) 파일을 가리켜야 한다.

![img](/assets/img/css-sololearn-css3 basics-11-01.png)

<br>

> In the @font-face rule, you must first define a name for the font (e.g., myFirstFont), and then point to the font file.
>
> @font-face 규칙에서, 글꼴의 이름(예: myFirstFont)을 먼저 정의한 다음 글꼴 파일을 가리켜야 한다.

------

<br>

## Using the @font-face Rule

###### @font-face 규칙 사용하기

<br>

- Each form of the font family must be declared using the `@font-face` rule.
  - font family의 각 form은 `@font-face` 규칙을 사용해서 선언해야 한다.
- In the example below, a custom font called "Delicious" is loaded and used for the heading.
  - 아래 예제에서는 "Delicious"라는 사용자 정의 글꼴이 로딩되고, 머리글에 사용된다.

<br>

- HTML:

```html
<h1>This is Our Headline</h1>
```

<br>

- CSS:

```css
@font-face {
   font-family: Delicious;
   src: url('Delicious-Roman.otf');
}

@font-face {
   font-family: Delicious;
   font-weight: bold;
   src: url('Delicious-Bold.otf');
}

h1 {
   font-family: Delicious, sans-serif;
}
```

<br>

- Internet Explorer has a built-in bug when multiple @font-face rules are defined.
  - IE에는 @font-face 규칙이 여러 개 정의되었을 때 버그가 있다.
- Using `#iefix` as shown below fixes the problem.
  - 아래와 같이 `#iefix`를 사용하면 문제를 해결할 수 있다.

```css
@font-face {
   font-family: Delicious;
   src: url('Delicious-Roman.ttf');
   src: url('Delicious-Roman.eot?#iefix');
}
```

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-11-02.png)

<br>

> The question mark fools IE into thinking the rest of the string is a query string and loads just the EOT file.
>
> 물음표는 나머지 IE 문자열을 query 문자열로 생각하고, EOT 파일만 로딩한다.

> The other browsers follow the spec and select the format they need, based on the src cascade.
>
> 다른 브라우저는 src cascade를 기반으로 spec에 따라 필요한 format을 선택한다.

------

<br>

## QUIZ

- Which two of the following font types are supported in Firefox, Safari, and Chrome?
  - Firefox, Safari, Chrome에서 지원되는 글꼴 type은 다음 중 어느 것인가?

> [ ] .eot
>
> [ ] `.otf`
>
> [ ] `.ttf`

<br>

- Define a new font named "test".
  - "test"라는 이름의 새 글꼴을 정의해라.

```css
@font-face {
   font-family: "test";
   src: url("test.otf");
}
```

<br>