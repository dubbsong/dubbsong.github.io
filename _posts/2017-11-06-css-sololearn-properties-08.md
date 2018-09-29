---
layout: post
title: "(Properties 08) background-attachment 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS background-attachment Property

###### background-attachment 속성

<br>

- The background-attachment property sets whether a background image is fixed or scrolls with the rest of the page.
  - background-attachment 속성은 배경 이미지가 고정되어 있는지 또는 나머지 페이지와 함께 스크롤 되는지를 설정한다.

- Even if an element has a scrolling mechanism, a "fixed" background doesn't move with the element.
  - element에 scrolling mechanism이 있어도, "고정된" 배경은 element와 함께 움직이지 않는다.

<br>

- CSS:

```css
body {
   background-image: url("css_logo.png");
   background-repeat: no-repeat;
   background-attachment: fixed;
}
```

[코드 실행 확인](https://code.sololearn.com/551/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-08-01.png)

------

<br>

## The background-attachment Values

###### background-attachment 값

<br>

- You can also set the background-attachment to `inherit` or `scroll`.
  - `inherit` 또는 `scroll` 하도록 background-attachment를 설정할 수도 있다.
- When you set the background-attachment to `inherit`, it will inherit the value from its parent element.
  - `inherit(상속)`할 background-attachment를 설정하면, parent(부모) element의 값을 상속받는다.

<br>

- When you set the background-attachment to `scroll`, the background image will scroll with the rest of the content.
  - scroll할 background-attachment를 설정하면, 배경 이미지가 나머지 content와 함께 scroll 된다.

<br>

- CSS:

```css
body {
   background-image: url("css_logo.png");
   background-repeat: no-repeat;
   background-attachment: scroll;
}
```

[코드 실행 확인](https://code.sololearn.com/552/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-08-02.png)

------

<br>

## QUIZ

- When setting a background image, which property is obligatory?
  - 배경 이미지를 설정할 때 어떤 속성이 필수적인가?

> `background-image`

<br>

- The background-attachment property accepts the following values: inherit, fixed and:
  - background-attachment 속성은 inherit, fixed, …값을 허용한다.

> `scroll`

<br>