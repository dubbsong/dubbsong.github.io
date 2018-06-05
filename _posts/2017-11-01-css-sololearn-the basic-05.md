---
layout: post
title: "SoloLearn 번역 - 05. Style Cascade and Inheritance (The Basic)"
categories: dev
tags: css
---

## Cascade (종속, 연속, 직렬)

- The final appearance of a web page is a result of different styling rules.
  - 웹 페이지의 최종 모양은 다른 스타일 규칙의 결과이다.
- The three main sources of style information that form a cascade are:
  - cascade를 형성하는 스타일 정보의 세 가지 주요 소스는 다음과 같다.

<br>

1. The stylesheet created by the **author of the page**
   - **페이지 작성자**가 만든 스타일 시트
2. The **browser's default styles**
   - **브라우저의 기본 스타일**
3. Styles specified **by the user**
   - **사용자**가 지정한 스타일

------

<br>

## Inheritance (상속)

- Inheritance refers to the way properties flow through the page.
  - 상속은 속성이 페이지를 통해 흐르는 방식을 나타낸다.
- A child element will usually take on the characteristics of the parent element unless otherwise defined.
  - 자식 element는 다른 정의가 없는 한 대개 부모 element의 특성을 사용한다.

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

![SoloLearn img](/assets/img/sololearn-css-the basics-05-01.png)

<br>

> Since the paragraph tag (child element) is inside the body tag (parent element), it takes on any styles assigned to the body tag.
>
> p 태그(자식 element)는 body 태그(부모 element) 안에 있기 때문에, body 태그에 할당된 모든 스타일을 사용한다.

------

<br>

## QUIZ

- Which three different sources are responsible for the styles you see on the web page?
  - **the stylesheet created by the author of the page**
  - **the default styles of the browser itself**
  - **the user customized style selections, if any**
  - the styles provided by Google

<br>

- What color does the paragraph have?
  - **red**
  - green
  - black

```html
<style>
   body {color: green;}
   .mydiv {color: red;}
</style>
<body>
   <div class="mydiv">
      <p>Some text</p>
   </div>
</body>
```

<br>