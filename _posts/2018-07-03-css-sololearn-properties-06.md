---
layout: post
title: "(Properties 06) background-image 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS background-image Property

###### background-image 속성

<br>

- The `background-image` property sets one or several background images in an element.
  - `background-image` 속성은 하나 이상의 배경 이미지를 element에 설정한다.

- Let's set a background-image for the \<body> element.
  - \<body> element의 배경 이미지를 설정해보자.

<br>

- CSS:

```css
body {
   background-image: url("css_logo.png");
   background-color: #e9e9e9;
}
```

[코드 실행 확인](https://code.sololearn.com/546/#css)

<br>

> The `url` specifies the path to the image file.
>
> `url`은 이미지 파일의 경로를 지정한다.

> Both relative and absolute paths are supported.
>
> 상대 경로와 절대 경로 모두 지원된다.

<br>

- Result:

![img](/assets/img/css-sololearn-properties-06-01.png)

<br>

> By default, a background-image is placed at the top-left corner of an element, and is repeated both vertically and horizontally to cover the entire element.
>
> 기본적으로 background-image는 element의 상단 왼쪽 모서리에 배치된다.
>
> 전체 element를 포함하도록 세로와 가로로 반복된다.

<br>

<br>

- Background-image can be set not only for the whole page, but for individual elements, as well.
  - background-image는 전체 페이지뿐만 아니라, 개별 element에 대해서도 설정할 수 있다.
- Below we set a background image for the \<p> element.
  - 아래에서는 \<p> element에 대한 배경 이미지를 설정한다.

<br>

- HTML:

```html
<p>This paragraph has a background image. </p>
```

<br>

- CSS:

```css
p {
   padding: 30px;
   background-image: url("green_photo.jpg");
   color: white;
}
```

[코드 실행 확인](https://code.sololearn.com/547/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-06-02.png)

<br>

> To specify more than one image, just separate the URLs with `commas`.
>
> 이미지를 두 개 이상 지정하려면, `쉼표`로 URL을 구분하면 된다.

------

<br>

## QUIZ

- What is the correct format for the image path of the background-image property:
  - background-image 속성의 이미지 경로에 올바른 형식은 무엇인가?

> [ ] "pix/weave1.png"
>
> [ ] url:pix/weave1.png
>
> [ ] `url("pix/weave1.png")`

<br>
