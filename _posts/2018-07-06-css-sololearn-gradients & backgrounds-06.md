---
layout: post
title: "(Gradients & Backgrounds 06) 여러 배경 이미지"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Multiple Background Images

###### 여러 배경 이미지

<br>

- The ability to have multiple background images is a new feature in CSS3.
  - 여러 배경 이미지를 가질 수 있는 기능은, CSS3의 새로운 기능이다.
- Multiple background images are specified using a comma-separated list of values for the background-image property.
  - 여러 배경 이미지는 background-image 속성에 대해 쉼표로 구분된 값 list를 사용해서 지정된다.
- The first image will appear on the top, the last on the bottom.
  - 첫 번째 이미지는 상단에 표시되고, 마지막 이미지는 하단에 표시된다.

<br>

- In the example below, we have two background images: the first is a CSS logo (aligned to the bottom and right); the second is a coding image (aligned to the top-left corner).
  - 아래 예제에는 두 가지 배경 이미지가 있다.
  - 첫 번째 이미지는 CSS 로고(아래 오른쪽 정렬)이다.
  - 두 번째 이미지는 코딩 이미지(위 왼쪽 정렬)이다.

<br>

- CSS:

```css
div {
   width: 400px;
   height: 300px;
   background-image: url(csslogo.png), url(csscode.jpg);
   background-position: right bottom, left top;
   background-repeat: no-repeat;
}
```

[코드 실행 확인](https://code.sololearn.com/614/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-gradients & backgrounds-06-01.png)

<br>

<br>

- The position of the background images can be changed, using the background-position property.
  - 배경 이미지의 위치는 background-position 속성을 사용해서 변경할 수 있다.

```css
div {
   width: 400px;
   height: 300px;
   background-image: url(csslogo.png), url(csscode.jpg);
   background-position: right top, left top;
   background-repeat: no-repeat;
}
```

[코드 실행 확인](https://code.sololearn.com/615/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-gradients & backgrounds-06-02.png)

<br>

> Multiple backgrounds can also be specified using the `background:` shorthand property.
>
> `background:` shorthand 속성을 사용해서 여러 배경을 지정할 수도 있다.

<br>

- CSS:

```css
background: url(csslogo.png) right top no-repeat, url(csscode.jpg) left top no-repeat;
```

[코드 실행 확인](https://code.sololearn.com/616/#css)

------

<br>

## QUIZ

- The last image in the background-image list will appear at the ...
  - background-image list의 마지막 이미지가 …에 표시된다.

> `Bottom`

<br>

- Fill in the blanks to add two background images to the element, with the first positioned at the top left corner, and the other at the top right corner.
  - element에 두 개의 배경 이미지를 추가해라.
  - 첫 번째 이미지는 왼쪽 위 모서리에, 다른 이미지는 오른쪽 상단 모서리에 위치시켜라.

```css
.test {
   background-image: url(1.jpg), url(2.jpg);
   background-repeat: no-repeat;
   background-position: left top, right top;
}
```

<br>