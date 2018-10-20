---
layout: post
title: "(Transitions & Transforms 04) scale() 메소드"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS scale() Method

###### scale() 메소드

<br>

- The `scale()` method increases or decreases the size of an element, according to the parameters given for the width and height.
  - `scale()` 메소드는 너비와 높이에 지정된 매개변수에 따라 element의 크기를 늘리거나 줄인다.
- 1 stands for the original size, 2 for twice the original size, and so on.
  - 1은 원래 크기를 나타내고, 2는 원래 크기의 두 배를 나타낸다.

<br>

- In the example below, we decreased the first div by the factor 0.7 both horizontally and vertically, and increased the second div by a factor of 1.5 horizontally and vertically.
  - 아래 예제에서 첫 번째 div의 가로와 세로 모두 0.7로 줄이고, 두 번째 div의 가로와 세로 모두 1.5로 늘렸다.

```css
div.first {
   width: 200px;
   height: 100px;
   background-color: #8BC34A;
   transform: scale(0.7, 0.7);
   color: white;
}

div.second {
   margin: 60px;
   width: 200px;
   height: 100px;
   background-color: #8bc34a;
   transform: scale(1.5, 1.5);
   color: white;
}
```

[코드 실행 확인](https://code.sololearn.com/628/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-transitions & transforms-04-01.png)

<br>

> If only one parameter is passed to the scale() method, it will apply that factor for both the height and the width.
>
> 하나의 매개변수만 scale() 메소드에 전달된다면, 높이와 너비 모두에 적용된다.

------

<br>

## Multiple Transforms

###### 여러 transform

<br>

- Multiple transforms can be used at once.
  - 한 번에 여러 transform을 사용할 수 있다.
- Rotating and scaling the size of an element at the same time is an example of that.
  - 동일한 시간에 element의 크기를 회전하고 조정하는 것이 그 예이다.
- Applying multiple transforms to an element is simple; just separate them using `spaces`.
  - element에 여러 transform을 적용하는 것은 간단하다.
  - `공백`을 사용해서 구분해라.

<br>

- For example:

```css
transform: rotate(45deg) translate(100px);
```

[코드 실행 확인](https://code.sololearn.com/629/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-transitions & transforms-04-02.png)

<br>

> If you use `commas` to separate the functions, none of the functions will be applied, so keep in mind not to use commas.
>
> `쉼표`를 사용해서 함수를 분리하면 함수가 적용되지 않으므로, 쉼표를 사용하지 않도록 주의해라.

------

<br>

## QUIZ

- Fill in the blank to reduce the element to 20% of its original size.
  - element를 원래 크기의 20%로 줄여라.

```css
transform: scale(0.2);
```

<br>

- When adding multiple transformations in a single transform property, separate them with ...
  - 하나의 transform 속성에 여러 transform을 추가할 때, ...로 구분해라.

> `spaces`

<br>
