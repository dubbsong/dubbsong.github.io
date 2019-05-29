---
layout: post
title: "(CSS3 Basics 08) Pseudo Class"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Pseudo Class

------

<br>

<br>

## Working with Pseudo-Class

###### pseudo class로 작업하기

<br>

- The CSS pseudo-classes allow us to style elements, or parts of elements, that exist in the document tree without using JavaScript or any other scripts.
  - CSS pseudo(의사) class를 사용하면 JavaScript 또는 다른 스크립트를 사용하지 않고 문서 tree에 있는 element 또는 일부 element의 style을 지정할 수 있다.
- A pseudo-class starts with a ":" (colon).
  - pseudo-class는 ":"(콜론)으로 시작한다.
- The most commonly used pseudo-classes are `:first-child` and `:last-child`.
  - 가장 일반적으로 사용되는 pseudo-class는 `:first-child`와 `:last-child`이다.

<br>

- The `:first-child` pseudo-class matches an element that is the first child element of some other element.
  - `:first-child` pseudo-class는 다른 element의 첫 번째 child element인 element를 찾는다.
- In the following example, the selector matches any \<p> element that is the first child or the div element:
  - 다음 예제에서 selector는 div element의 첫 번째 child인 \<p> element와 일치한다.

<br>

- HTML:

```html
<div id="parent">
   <p>First paragraph </p>
   <p>Second paragraph </p>
   <p>Third paragraph </p>
   <p>Fourth paragraph </p>
</div>
```

<br>

- CSS:

```css
#parent p:first-child {
   color: green;
   text-decoration: underline;
}
```

[코드 실행 확인](https://code.sololearn.com/591/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-08-01.png)

<br>

- The `:last-child` pseudo-class matches an element that is the last child element of some other element.
  - `:last-child` pseudo-class는 다른 element의 마지막 child element인 element를 찾는다.

<br>

- In the example below, the selector will match any \<p> element that is the last child of the div element:
  - 아래 예제에서 selector는 div element의 마지막 child element인 \<p> element와 일치한다.

```css
#parent p:last-child {
   color: green;
   text-decoration: underline;
}
```

[코드 실행 확인](https://code.sololearn.com/592/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-08-02.png)

------

<br>

## QUIZ

- Style the first child of the \<p> element.
  - \<p> element의 첫 번째 child의 style을 지정해라.

```css
p :first-child {
   background-color: yellow;
}
```

<br>