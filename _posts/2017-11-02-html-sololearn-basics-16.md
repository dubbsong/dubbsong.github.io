---
layout: post
title: "SoloLearn HTML 번역 - 16. HTML Colors (Basics)"
categories: dev
tags: html
---

## HTML Colors

###### HTML 색상

<br>

- HTML colors are expressed as hexadecimal values.
  - HTML 색상은 16진수 값으로 표현된다.
- `0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F`

<br>

> As you can see, there are 16 values there, 0 through F.
>
> 보다시피, 0에서 F까지 16개의 값이 있다.

> Zero represents the lowest value, and F represents the highest.
>
> 0은 가장 낮은 값을 나타내고, F는 가장 높은 값을 나타낸다.

------

<br>

## HTML Color Model

###### HTML 색상 모델

<br>

- Colors are displayed in combinations of `red`, `green`, and `blue` light (`RGB`).
  - 색상은 `빨강`, `초록`, `파랑` 빛(`RGB`) 조합으로 표시된다.

<br>

- Hex values are written using the hashtag symbol (#), followed by either three or six hex characters.
  - 16진수 값은 해시태그 기호(#)를 사용해서 작성되고, 직후에 3개 또는 6개의 16진수 문자를 입력한다.
- As shown in the picture below, the circles overlap, forming new colors:
  - 아래 그림과 같이, 원이 겹쳐서 새로운 색상을 만든다.

![sololearn img](/assets/img/sololearn-html-basics-16-01.png)

------

<br>

## Color Values

###### 색상 값

<br>

- All of the possible `red`, `green`, and `blue` combinations potentially number over 16 million.
  - 가능한 모든 `빨강`, `초록`, `파랑` 조합은 잠재적으로 1,600만 개가 넘는다.

<br>

- Here are only a few of them:
  - 다음은 그 중 일부이다.

![sololearn img](/assets/img/sololearn-html-basics-16-02.png)

<br>

- We can mix the colors to form additional colors:
  - 색상을 혼합해서 추가 색상을 만들 수 있다.
- Orange and red mix:

![sololearn img](/assets/img/sololearn-html-basics-16-03.png)

------

<br>

## Background and Font Colors

###### 배경과 폰트 색상

<br>

- The `bgcolor` attribute can be used to change the web page's background color.
  - `bgcolor` 속성을 사용해서 웹 페이지의 배경 색상을 변경할 수 있다.

<br>

- This example would produce a dark blue background with a white headline:
  - 이 예제는 하얀 제목과 함께 진한 파란색 배경을 만든다.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body bgcolor="#000099">
      <h1>
         <font color="#FFFFFF"> White headline </font>
      </h1>
   </body>
</html>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-basics-16-04.jpeg)

------

<br>

## QUIZ

- What characters does the hexadecimal system consist of?
  - 16진수 시스템은 어떤 문자로 구성되는가?

> [ ] a - z
>
> [ ] 0 - z
>
> [ ] 0 - 9
>
> [x] `0 - f`

<br>

- Which color model does HTML use?
  - HTML은 어떤 색상 모델을 사용하는가?

> [ ] HSB
>
> [ ] HSLA
>
> [x] `RGB`
>
> [ ] CMYK

<br>

- What would be the value of the color black in HTML, expressed by 6 hex characters?
  - 6자리 16진수로 표현되는 HTML의 검정색 값은 무엇인가?

> \#000000

<br>

- Set the background color to white:
  - 배경 색상을 흰색으로 설정해라.

```html
<body bgcolor="#FFFFFF">
```

<br>