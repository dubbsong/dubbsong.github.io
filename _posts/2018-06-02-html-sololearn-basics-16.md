---
layout: post
title: "(Basics 16) HTML 색상"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Color

###### HTML 색상

<br>

- HTML colors are expressed as hexadecimal values.
  - HTML 색상은 16진수 값으로 표현된다.

<br>

`0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F`

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

- Colors are displayed in combinations of `red`, `green`, `blue` light (`RGB`).
  - 색상은 `빨강 빛`, `초록 빛`, `파랑 빛`(`RGB`)의 조합으로 표시된다.

<br>

- Hex values are written using the hashtag symbol (\#), followed by either three or six hex characters.
  - 16진수 값은 해시태그(\#)를 사용해서 작성하고, 그 뒤에 3 또는 6개의 16진수가 온다.
- As shown in the picture below, the circles overlap, forming new colors:
  - 아래 그림과 같이, 원이 겹쳐서 새로운 색상을 만든다.

![img](/assets/img/html-sololearn-basics-16-01.png)

<br>

> RGB color values are supported in all browsers.
>
> RGB 색상 값은 모든 브라우저에서 지원된다.

------

<br>

## Color Values

###### 색상 값

<br>

- All of the possible `red`, `green`, and `blue` combinations potentially number over 16 million.
  - `빨강`, `초록`, `파랑`의 가능한 모든 조합은 1,600만 개가 넘는다.
- Here are only a few of them:
  - 다음은 그 중 일부이다.

![img](/assets/img/html-sololearn-basics-16-02.png)

<br>

- We can mix the colors to form additional colors:
  - 색상을 혼합해서 추가 색상을 만들 수 있다.
- Orange and red mix:

![img](/assets/img/html-sololearn-basics-16-03.png)

<br>

> Hexadecimal color values are supported in all browsers.
>
> 16진수 색상 값은 모든 브라우저에섯 지원된다.

------

<br>

## Background and Font Colors

###### 배경 & 글꼴 색상

<br>

- The `bgcolor` attribute can be used to change the webpage's background color.
  - `bgcolor` 속성을 사용해서 웹페이지의 배경색을 변경할 수 있다.

<br>

- This example would produce a dark blue background with a white headline:
  - 이 예제는 흰색 제목이 있는 진한 파란색 배경을 생성한다.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body bgcolor="#000099">
      <h1>
         <font color="#FFFFFF">White headline</font>
      </h1>
   </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/34/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-basics-16-04.jpeg)

<br>

> The color attribute specifies the color of the text inside a \<font> element.
>
> color 속성은 \<font> element 내의 텍스트 색상을 지정한다.

------

<br>

## QUIZ

- What characters does the hexadecimal system consist of?
  - 16진수 시스템은 어떤 문자로 구성되는가?

> `0 - f`

<br>

- Which color model does HTML use?
  - HTML은 어떤 색상 모델을 사용하는가?

> `RGB`

<br>

- What would be the value of the color black in HTML, expressed by 6 hex characters?
  - 6자리 16진수로 표현되는 HTML의 검정색 값은 무엇인가?

> `#000000`

<br>

- Set the background color to white:
  - 배경색을 흰색으로 설정해라.

```html
<body bgcolor="#FFFFFF">
```

<br>