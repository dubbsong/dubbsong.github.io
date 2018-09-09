---
layout: post
title: "05. Cascade & 상속 (The Basics)"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Style Cascade & Inheritance

###### cascade & 상속

------

<br>

<br>

## Cascade

- The final appearance of a webpage is a result of different styling rules.
  - 웹페이지의 최종 모양은 다른 style 규칙의 결과이다.

<br>

- The three main sources of style information that form a cascade are:
  - cascade를 형성하는 style 정보의 세 가지 주요 소스는 다음과 같다.

<br>

1. The style sheet created by the `author of the page`
   - `페이지의 작성자`가 생성한 style sheet
2. The `browser's default styles`
   - `브라우저의 기본 style`
3. Styles specified `by the user`
   - `사용자`가 지정한 style

<br>

> CSS is an acronym for Cascading Style Sheets.
>
> CSS는 Cascading Style Sheets의 약자이다.

------

<br>

## Inheritance

###### 상속

<br>

- Inheritance refers to the way properties flow through the page.
  - 상속은, 속성이 페이지를 통해 흐르는 방식을 나타낸다.
- A child element will usually take on the characteristics of the parent element unless otherwise defined.
  - 자식 element는 다른 정의가 없는 한, 대개 부모 element의 특성을 사용한다.

<br>

- For example:

```html
<html>
   <head>
      <style>
         body {
            color: green;
            font-family: Arial;
         }
      </style>
   </head>
   <body>
      <p>
         This is a text inside the paragraph.
      </p>
   </body>
</html>
```

<br>

- Result:

![img](/assets/img/css-sololearn-the basics-05-01.png)

<br>

> Since the paragraph tag (child element) is inside the body tag (parent element), it takes on any styles assigned to the body tag.
>
> 토막글 태그(자식 element)는 body 태그(부모 element) 내에 있으므로, body 태그에 지정된 모든 style을 사용한다.

------

<br>

## QUIZ

- Which three different sources are responsible for the styles you see on the webpage?
  - 어떤 세 가지 다른 소스가 웹페이지에서 볼 수 있는 style을 담당하는가?

> [ ] `the default styles of the browser itself`
>
> [ ] `the stylesheet created by the author of the page`
>
> [ ] the styles provided by Google
>
> [ ] `the user customized style selections, if any`

<br>

- What color does the paragraph have?
  - 토막글에는 어떤 색상이 있는가?

```html
<style>
   body { color: green; }
   .mydiv { color: red; }
</style>
<body>
   <div class="mydiv">
      <p>Some text</p>
   </div>
</body>
```

> `red`

<br>