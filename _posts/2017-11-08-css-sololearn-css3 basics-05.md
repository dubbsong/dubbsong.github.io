---
layout: post
title: "(CSS3 Basics 05) box-shadow 기법"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS box-shadow Techniques

###### box-shadow 기법

------

<br>

<br>

## Creating an Inner Shadow

###### 내부 그림자 생성

<br>

- The `"inset"` keyword allows to draw an inner shadow in the box.
  - `"inset"` 키워드를 사용하면 box에 내부 그림자를 그릴 수 있다.
- To show an inset shadow, just add the inset keyword:
  - 내부 그림자를 표시하기 위해 inset 키워드를 추가해라.

```css
box-shadow: inset 10px 10px 5px #888888;
```

[코드 실행 확인](https://code.sololearn.com/586/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-05-01.png)

<br>

> You can simultaneously create `inner` and `outer` shadows by separating each shadow with a `comma`.
>
> 각 그림자를 `쉼표`로 구분해서 `내부` 그림자와 `외부` 그림자를 동시에 생성할 수 있다.

------

<br>

## Layering Multiple Shadows

###### 여러 그림자 층

<br>

- You can define as many shadows for the same box as you want by writing all of them `comma-separated` in the same rule.
  - 동일한 규칙에 `쉼표로 구분된` 모든 것을 작성해서, 원하는 만큼 동일한 box에 대해 많은 그림자를 정의할 수 있다.

<br>

- In the example below, two `inner` shadows have been created by separating each shadow with a `comma`.
  - 아래 예제에서, `쉼표`로 각 그림자를 구분해서 두 개의 `내부` 그림자를 생성했다.

```css
box-shadow:
inset 10px 10px 5px #888888,
inset -10px -10px 5px #888888;
```

[코드 실행 확인](https://code.sololearn.com/587/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-05-02.png)

<br>

- In case we specify more than one value, the one which comes last will be positioned at the back of all shadows.
  - 둘 이상의 값을 지정하는 경우, 마지막에 오는 값이 모든 그림자 뒤쪽에 배치된다.

<br>

- For example:

```css
box-shadow: 0 0 10px 4px #FF6347,
0 0 10px 30px #FFDAB9,
30px 0 20px 30px #B0E0E6;
```

[코드 실행 확인](https://code.sololearn.com/588/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-05-03.png)

<br>

> As expected, the blue shadow (\#`B0E0E6`) comes last.
>
> 예상대로, 파란색 그림자(\#`B0E0E6`)가 마지막에 온다.

------

<br>

## QUIZ

- Which keyword is used to create shadow within the element?
  - element 내에서 그림자를 생성하는 데 사용되는 키워드는 무엇인가?

> `inset`

<br>

- Multiple box shadows are separated by ...
  - 여러 box 그림자가 ...에 의해 구분된다.

> `comma(,)`

<br>