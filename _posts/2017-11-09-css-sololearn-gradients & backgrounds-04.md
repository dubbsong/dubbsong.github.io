---
layout: post
title: "(Gradients & Backgrounds 04) background-clip 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS background-clip Property

###### background-clip 속성

<br>

- The `background-clip` property specifies the painting area of the background.
  - `background-clip` 속성은 배경의 painting 영역을 지정한다.

<br>

- The property takes three different values:
  - 속성에는 세 가지 다른 값이 사용된다.

<br>

- `border-box`: (default) the background is painted to the outside edge of the border
  - (기본값) 배경이 border의 바깥쪽 가장자리에 칠해진다.
- `padding-box`: the background is painted to the outside edge of the padding
  - 배경이 padding의 바깥쪽 가장자리에 칠해진다.
- `content-box`: the background is painted within the content box
  - 배경은 content 상자 내에 칠해진다.

<br>

- In the example below, the first div with background-clip is set to `padding-box`; in the second div it's set to `content-box`.
  - 아래 예제에서 background-clip이 있는 첫 번째 div는 `padding-box`로 설정된다.
  - 두 번째 div는 `content-box`로 설정된다.

```css
#first {
   border: 2px dotted black;
   padding: 20px;
   background: LightBlue;
   background-clip: padding-box;
}

#second {
   border: 2px dotted black;
   padding: 20px;
   background: LightBlue;
   background-clip: content-box;
}
```

[코드 실행 확인](https://code.sololearn.com/611/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-gradients & backgrounds-04-01.png)

------

<br>

## background-clip with Images

###### 이미지 background-clip

<br>

- background-clip also applies to background images.
  - background-clip은 배경 이미지에도 적용된다.

<br>

- CSS:

```css
div {
   background-image: url("css-logo.png");
   background-clip: content-box;
}
```

[코드 실행 확인](https://code.sololearn.com/612/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-gradients & backgrounds-04-02.png)

------

<br>

## QUIZ

- Which value is not used with the background-clip property?
  - background-clip 속성에 사용되지 않는 값은 무엇인가?

> [ ] content-box
>
> [ ] padding-box
>
> [ ] `text-box`
>
> [ ] border-box

<br>

- Does background-clip work with images?
  - background-clip이 이미지에서도 작동하는가?

> `Yes`

<br>
