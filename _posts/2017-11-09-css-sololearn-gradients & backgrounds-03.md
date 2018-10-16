---
layout: post
title: "(Gradients & Backgrounds 03) background-size 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS background-size Property

###### background-size 속성

<br>

- The `background-size` property adds new functionality to CSS that allows us to specify the size of background images, using either lengths or percentages.
  - `background-size` 속성은 CSS에 새로운 기능을 추가한다.
  - length 또는 백분율을 사용해서 배경 이미지의 크기를 지정할 수 있다.

<br>

- For example:

```css
div {
   height: 150px;
   width: 200px;
   border: 1px solid #000;
   background: url("css_logo.png") no-repeat 50% 50%;
   background-size: 100px 100px;
}
```

[코드 실행 확인](https://code.sololearn.com/608/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-gradients & backgrounds-03-01.png)

<br>

> The current versions of most popular browsers - including Firefox, Safari, Chrome, Internet Explorer, and Opera - now support background-size, without the need for vendor prefixes.
>
> Firefox, Safari, Chrome, IE, Opera 등 가장 많이 사용되는 브라우저의 최신 버전은 이제 vendor 접두사가 없어도 background-size를 지원한다.

------

<br>

## The background-size Values

###### background-size 값

<br>

- The two other possible values for background size are the keywords `contain` and `cover`.
  - 배경 크기에 대해 가능한 다른 두 값은 `contain`과 `cover` 키워드이다.

<br>

- The `contain` keyword scales the image so that it fits the container.
  - `contain` 키워드는 컨테이너에 맞도록 이미지의 크기를 조절한다.
- In other words, the image will grow or shrink proportionally, but the width and height will not exceed the container's dimensions:
  - 즉, 이미지는 비례해서 늘어나거나 줄어들지만, 너비와 높이는 컨테이너의 치수를 초과하지 않는다.

<br>

- CSS syntax looks like this:
  - CSS 구문은 다음과 같다.

```css
background-size: contain;
```

[코드 실행 확인](https://code.sololearn.com/609/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-gradients & backgrounds-03-02.png)

<br>

- background-size also accepts the `cover` keyword.
  - background-size는 `cover` 키워드도 허용한다.
- The image is scaled to fit the entire container; however, if that has a different aspect ratio, the image will be cropped:
  - 이미지는 전체 컨테이너에 맞도록 크기가 조정된다.
  - 하지만 비율이 다른 경우, 이미지가 잘린다.

<br>

- CSS syntax looks like this:
  - CSS 구문은 다음과 같다.

```css
background-size: cover;
```

[코드 실행 확인](https://code.sololearn.com/610/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-gradients & backgrounds-03-03.png)

------

<br>

## QUIZ

- Resize the background image to a height of 100 pixels and a width of 200 pixels.
  - 배경 이미지의 높이를 100 픽셀, 너비를 200 픽셀로 조정해라.

```css
background-size: 200px 100px;
```

<br>

- Which property scales the image so that both width and height fit inside the content area?
  - 어느 속성이 이미지의 크기를 조절해서 너비와 높이가 content 영역 내에 들어갈 수 있는가?

> `contain`

<br>