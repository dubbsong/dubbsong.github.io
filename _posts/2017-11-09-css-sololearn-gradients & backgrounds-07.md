---
layout: post
title: "(Gradients & Backgrounds 07) opacity 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS opacity Property

###### opacity 속성

<br>

- CSS `opacity` property provides an excellent means of adding opacity to any element.
  - CSS `opacity` 속성은 모든 element에 불투명도를 추가하는 훌륭한 수단을 제공한다.
- In the example below, we set different levels of opacity to the same picture, so you can clearly see the difference.
  - 아래 예제에서는 동일한 그림에 대해 서로 다른 level의 불투명도를 설정하므로, 차이점을 명확하게 볼 수 있다.

<br>

- CSS:

```css
#img1 {
   opacity: 1;
}

#img2 {
   opacity: 0.5;
}

#img3 {
   opacity: 0.25;
}
```

[코드 실행 확인](https://code.sololearn.com/617/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-gradients & backgrounds-07-01.png)

<br>

> The opacity property value must be a number between 0.0 (fully transparent) and 1.0 (fully opaque).
>
> opacity 속성 값은 0.0(완전 투명)과 1.0(완전 불투명) 사이의 숫자여야 한다.

------

<br>

## Opacity in Internet Explorer

###### IE에서의 불투명도

<br>

- To have the opacity property work in all versions of IE, use the `filter.alpha(opacity=x)` along with the opacity property.
  - 모든 IE 버전에서 opacity 속성을 작동시키려면, opacity 속성과 함께 `filter.alpha(opacity=x)`를 사용해라.
- x can take a value from 0 to 100.
  - x는 0에서 100까지의 값을 취할 수 있다.
- The value 0 results in a completely transparent element (i.e., 100% transparent), whereas the value 100 makes the element completely opaque (i.e., 0% transparent).
  - 값 0은 완전히 투명한 element(즉, 100% 투명)를 생성하는 반면, 값 100은 element를 완전히 불투명(즉, 0% 투명)하게 만든다.

<br>

- For example, in order to have the code work properly with IE, when the opacity of the image is set at 0.5, it should look like this:
  - 예를 들어 IE에서 코드가 제대로 작동하기 위해, 이미지의 불투명도를 0.5로 설정한다면 다음과 같다.

```css
#img {
   opacity: 0.5;
   filter: alpha(opacity=50);
}
```

[코드 실행 확인](https://code.sololearn.com/618/#css)

<br>

> The alpha filter is a Microsoft-only property, not a standard CSS property.
>
> alpha filter는 표준 CSS 속성이 아닌 Microsoft 전용 속성이다.

------

<br>

## QUIZ

- Set the element's opacity at 30%.
  - element의 불투명도를 30%로 설정해라.

> `opacity: 0.3;`

<br>

- Fill in the blank to add support for IE8.
  - IE8에 대한 지원을 추가해라.

> `filter: alpha(opacity=30);`

<br>