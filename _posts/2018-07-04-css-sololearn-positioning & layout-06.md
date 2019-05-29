---
layout: post
title: "(Positioning & Layout 06) overflow 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS overflow Property

###### overflow 속성

<br>

- As discussed earlier, every element on the page is a `box`.
  - 앞에서 살펴본 것처럼, 페이지의 모든 element는 `box`이다.
- If the height of the box is not set, the height of that box will grow as large as necessary to accommodate the content.
  - box의 높이가 설정되지 않은 경우, 해당 box의 높이가 content를 수용할 만큼 커진다.

<br>

- HTML:

```html
<div>
   This text is inside the div element, which has a blue
   background color and is floated to the left.
   We set a specific height and width for the div element,
   and as you can see, the content cannot fit.
</div>
```

<br>

- CSS:

```css
div {
   width: 150px;
   height: 150px;
   background-color: LightBlue;
   float: left;
}
```

[코드 실행 확인](https://code.sololearn.com/574/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-06-01.png)

<br>

> The CSS `overflow` property specifies the behavior that occurs when an element's content overflows the element's box.
>
> CSS `overflow` 속성은 element의 content가 element의 box를 overflow 할 때 발생하는 동작을 지정한다.

------

<br>

## The overflow Property Values

###### overflow 속성 값

<br>

- There are four values for the overflow property: `visible` (the default value), `scroll`, `hidden`, and `auto`.
  - overflow 속성에는 `visible`(기본값), `scroll`, `hidden`, `auto`의 네 가지 값이 있다.

<br>

- The value `scroll` results in clipped overflow, but a scrollbar is added, so the rest of the content may be seen.
  - `scroll` 값을 사용하면 잘린 overflow가 발생하지만, scrollbar가 추가되므로 나머지 content가 표시될 수 있다.

<br>

- CSS:

```css
div {
   width: 150px;
   height: 150px;
   background-color: LightBlue;
   float: left;
   overflow: scroll;
}
```

[코드 실행 확인](https://code.sololearn.com/575/#css)

<br>

- The code above will produce both `horizontal` and `vertical` scrollbars:
  - 위 코드는 `가로`와 `세로` scrollbar를 생성한다.

![img](/assets/img/css-sololearn-positioning & layout-06-02.png)

------

<br>

## auto and hidden

###### auto & hidden 값

<br>

- `auto`: If overflow is clipped, a scroll-bar should be added to make it possible to see the rest of the content.
  - overflow가 잘린 경우, content의 나머지 부분을 볼 수 있도록 scrollbar를 추가해야 한다.
- `hidden`: The overflow is clipped, and the rest of the content will be invisible.
  - overflow가 잘리고, content의 나머지 부분은 보이지 않는다.

<br>

- CSS:

```css
div {
   width: 150px;
   height: 150px;
   background-color: LightBlue;
   float: left;
   overflow: hidden;
}
```

[코드 실행 확인](https://code.sololearn.com/576/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-06-03.png)

<br>

> The default value for the overflow property is `visible`.
>
> overflow 속성의 기본값은 `visible`이다.

------

<br>

## QUIZ

- The "overflow" property is used to:
  - "overflow" 속성은 다음 작업에 사용된다.

> `Specify the behavior that occurs when the content overflows the element's box`
>
> content가 element의 box를 overflow 할 때 발생하는 동작을 지정한다

<br>

- Fill in the blanks to produce horizontal and vertical scrollbars:
  - 가로와 세로 scrollbar를 생성해라.

```css
div {
   width: 150px;
   height: 150px;
   background-color: LightBlue;
   float: left;
   overflow: scroll;
}
```

<Br>

- What is the default value of the overflow property?
  - overflow 속성의 기본값은 무엇인가?

> `visible`

<br>
