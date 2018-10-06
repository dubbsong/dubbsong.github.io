---
layout: post
title: "(Positioning & Layout 07) z-index 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS z-index Property

###### z-index 속성

<br>

- When elements are positioned outside the normal flow, they can overlap other elements.
  - element가 정상 흐름 외부에 배치되면, 다른 element와 겹칠 수 있다.
- The `z-index` property specifies the stack order of an element (which element should be placed in front of, or behind, the others).
  - `z-index` 속성은 element의 스택 순서를 지정한다.
  - (이 element는 다른 element의 앞에 또는 뒤에 있어야 한다)

<br>

- CSS:

```css
.blue {
   background-color: #8EC4D0;
   margin-bottom: 15px;
   width: 120px;
   height: 120px;
   color: #FFF;
}

.red {
   background-color: #FF4D4D;
   position: relative;
   width: 120px;
   height: 120px;
   color: #FFF;
   margin-top: -50px;
   margin-left: 50px;
}
```

[코드 실행 확인](https://code.sololearn.com/577/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-07-01.png)

<br>

> The red box overlaps the blue box, because it was placed `later` in the HTML markup.
>
> 빨간색 box는 파란색 box와 겹친다.
>
> HTML markup에서 나중에 배치되었기 때문이다.

> The `z-index` property can change this order.
>
> `z-index` 속성이 이 순서를 변경할 수 있다.

------

<br>

## Assigning the z-index Property

###### z-index 속성 할당

<br>

- Assigning a higher z-index value to the blue div and a lower z-index value to the red div will result in the following:
  - 파란색 div에 높은 z-index 값을 할당하고, 빨간색 div에 낮은 z-index 값을 할당하면 다음 결과가 나타난다.

<br>

- CSS:

```css
.blue {
   z-index: 3;
   position: relative;
}

.red {
   z-index: 2;
   position: relative;
}
```

[코드 실행 확인](https://code.sololearn.com/578/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-07-02.png)

<br>

> The z-index works `only` on positioned elements (position: absolute, position:relative, or position:fixed).
>
> z-index는 배치된 element에서만 작동한다.
>
> (position:absolute, position:relative, position:fixed)

------

<br>

## QUIZ

- By default which element in the markup will overlap the others when elements begin stacking?
  - 기본적으로 element가 stacking을 시작할 때 markup에서 어떤 element가 다른 element와 겹치게 되는가?

> `the last element`

<br>

- In order to make the z-index property work you must...
  - z-index 속성을 작동시키려면...

> `position elements`
>
> element를 배치해야 한다

<br>