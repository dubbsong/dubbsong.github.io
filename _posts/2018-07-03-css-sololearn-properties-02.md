---
layout: post
title: "(Properties 02) Box Model의 이해"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS: Understanding the Box Model

###### Box Model의 이해

------

<br>

<br>

## More on Box Models

###### Box Model에 대한 추가 정보

<br>

- Every element of the webpage is a `box`.
  - 웹페이지의 모든 element는 하나의 `box`이다.

<br>

- CSS uses the box model to determine how big the boxes are and how to place them.
  - CSS는 box model을 사용해서 상자의 크기와 배치 방법을 결정한다.

<br>

> The box model is also used to calculate the actual width and height of the HTML elements.
>
> box model은 HTML element의 실제 너비와 높이를 계산하는 데도 사용된다.

------

<br>

## Total Width of an Element

###### element의 총 너비

<br>

- When working with boxes, it is important to understand how the total width of an element is calculated.
  - 상자로 작업할 때, element의 전체 너비를 계산하는 방법을 이해하는 것이 중요하다.
- For example, the total width of the box with paddings will be the sum of `width` plus `padding left` and `padding right`.
  - 예를 들어, padding이 있는 상자의 전체 너비는, `padding left`와 `padding right`에 `width`를 더한 합이다.

![img](/assets/img/css-sololearn-properties-01-02.png)

<br>

- Here is another box with margins, border, and paddings.
  - margin, border, padding이 있는 다른 상자가 있다.
- The total width is the sum of `left and right margins, left and right borders, left and right paddings`, and the `actual width` of the content.
  - 총 너비는 `왼쪽과 오른쪽 margin, 왼쪽과 오른쪽 border, 왼쪽과 오른쪽 padding`, 그리고 content의 `실제 너비` 합이다.

![img](/assets/img/css-sololearn-properties-01-03.png)

<br>

> When you set the width and height properties of an element with CSS, you set the width and height of the content area.
>
> CSS를 사용해서 element의 너비와 높이 속성을 설정하면, content 영역의 너비와 높이를 설정한다.

------

<br>

## Total Height of an Element

###### element의 전체 높이

<br>

- The total height of an element is calculated the same way as the width.
  - element의 전체 높이는 너비와 같은 방식으로 계산된다.

![img](/assets/img/css-sololearn-properties-01-04.png)

<br>

> To summarize(요약하면),
>
> Total element height (element의 전체 높이) = height + top padding + bottom padding + top boder + bottom border + top margin + bottom margin

------

<br>

## QUIZ

- According to the box model, every element on a webpage is a:
  - box model에 따르면, 웹페이지의 모든 element는 다음과 같다.

> `box`

<br>

- The background color of the content also covers:
  - content의 배경색은 ...도 포함한다.

> `padding`

<br>

- Enter the total width of an element in pixels, if its width=150px, left and right paddings=5px each, border width=2px and left and right margins=5px each.
  - 너비=150px, 각 왼쪽과 오른쪽 padding=5px, border 너비=2px, 각 왼쪽과 오른쪽 margin=5px인 경우, element의 전체 너비를 px 단위로 입력해라.

> `174px`

<br>