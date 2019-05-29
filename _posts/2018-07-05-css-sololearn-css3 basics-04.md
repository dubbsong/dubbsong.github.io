---
layout: post
title: "(CSS3 Basics 04) box-shadow 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS box-shadow Property

###### box-shadow 속성

<br>

- The CSS3 `box-shadow` property applies shadow to elements.
  - CSS3 `box-shadow` 속성은 element에 그림자를 적용한다.
- Components of the box-shadow property are decoded by browsers in the following manner:
  - box-shadow 속성의 컴포넌트는 다음과 같은 방식으로 브라우저에 해독된다.

<br>

1. The first length for the `horizontal offset` will cast the shadow to the right of the box (required)
   - `horizontal offset`의 첫 번째 length는 box의 오른쪽으로 그림자를 드리운다. (필수)
2. The second length is for the `vertical offset` that will cast the shadow to below the box (required)
   - `vertical offset`의 두 번째 length는 box 아래로 그림자를 드리운다. (필수)
3. The `color` of the shadow (optional)
   - 그림자의 `color`. (선택 사항)

<br>

- In the example below, the horizontal and vertical offsets have been set to 10px:
  - 아래 예제에서 horizontal 및 vertical offset은 10 픽셀로 설정되었다.

```css
div {
   width: 300px;
   height: 100px;
   background-color: #9ACD32;
   box-shadow: 10px 10px #888888;
}
```

[코드 실행 확인](https://code.sololearn.com/583/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-04-01.png)

------

<br>

## Blur and Spread

###### blur & spread

<br>

- Besides color, there are also two optional values for the box-shadow element, which are `blur` and `spread`.
  - 색상 외에도, box-shadow element의 두 가지 선택 값인 `blur`와 `spread`가 있다.

<br>

> The blur and spread values should be used before the color value.
>
> blur와 spread 값은 color 값 전에 사용되어야 한다.

<br>

```css
box-shadow: 10px 10px 5px 5px #888888;
```

[코드 실행 확인](https://code.sololearn.com/584/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-04-02.png)

------

<br>

## Negative Values

###### 음수 값

<br>

- `Negative values` can also be used for the box-shadow property.
  - `음수 값`은 box-shadow 속성에도 사용할 수 있다.

<br>

- `horizontal offset`: the shadow will be to the `left` of the box
  - 그림자는 box의 `왼쪽`에 생긴다.
- `vertical offset`: the shadow will be `above` the box
  - 그림자는 box 위에 생긴다.
- `blur radius`: negative values are `not allowed`
  - 음수 값은 `허용되지 않는다`.
- `spread radius`: negative values will cause the shadow to `shrink`
  - 음수 값을 지정하면 그림자가 줄어든다.

<br>

- For example:

```css
box-shadow: -10px -10px 5px -5px #888888;
```

[코드 실행 확인](https://code.sololearn.com/585/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-04-03.png)

------

<br>

## QUIZ

- Add the box-shadow property for a result of 10 pixels vertical offset, 20 pixels horizontal offset, and red for the color.
  - 10 픽셀 vertical offset, 20 픽셀 horizontal offset, 빨간 color의 결과에 box-shadow 속성을 추가해라.

> `box-shadow: 20px 10px red;`

<br>

- Which two choices indicate optional values for the box-shadow?
  - 어떤 두 가지 선택이 box-shadow의 선택 값을 나타내는가?

> [ ] Horizontal offset
>
> [ ] Vertical offset
>
> [ ] `Blur distance`
>
> [ ] `Spread distance`

<br>

- Place the box-shadow property values in the correct order.
  - box-shadow 속성 값을 올바른 순서로 배치해라.

> Horizontal offset
>
> Vertical offset
>
> Blur
>
> Spread
>
> Color

<br>
