---
layout: post
title: "(HTML5 13) SVG 애니메이션 & 경로"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 SVG Animations & Paths

###### SVG 애니메이션 & 경로

------

<br>

<br>

## Shape Animations

###### 도형 애니메이션

<br>

- SVG animations can be created using the `<animate>` element.
  - SVG 애니메이션은 `<animate>` element를 사용해서 생성할 수 있다.

<br>

- The example below creates a rectangle that will change its position in 3 seconds and will then repeat the animation twice:
  - 아래 예제는 3초 내에 위치를 변경하고, 애니메이션을 두 번 반복하는 사각형을 생성한다.

```html
<svg width="1000" height="250">
   <rect width="150" height="150" fill="orange">
      <animate attributeName="x" from="0" to="300"
               dur="3s" fill="freeze" repeatCount="2" />
   </rect>
</svg>
```

[코드 실행 확인](https://code.sololearn.com/55/#html)

<br>

- `attributeName`: Specifies which attribute will be affected by the animation.
  - 애니메이션의 영향을 받는 속성을 지정한다.
- `from`: Specifies the starting value of the attribute.
  - 속성의 시작 값을 지정한다.
- `to`: Specifies the ending value of the attribute.
  - 속성의 종료 값을 지정한다.
- `dur`: Specifies how long the animation runs (duration)
  - 애니메이션이 실행되는 시간(기간)을 지정한다.
- `fill`: Specifies whether or not the attribute's value should return to its initial value when the animation is finished (Values: "remove" resets the value; "freeze" keeps the "to value")
  - 애니메이션이 끝나면 속성의 값을 초기 값으로 되돌릴지 여부를 지정한다.
  - (values: "remove"는 값을 재설정한다. "freeze"는 "to value"를 유지한다.)
- `repeatCount`: Specifies the repeat count of the animation.
  - 애니메이션의 반복 횟수를 지정한다.

<br>

- In the example above, the rectangle changes its x attribute from 0 to 300 in 3 seconds.
  - 위의 예제에서 사각형은 3초 내에 x 속성이 0에서 300으로 변경된다.

<br>

> To repeat the animation indefinitely, use the value `"indefinite"` for the repeatCount attribute.
>
> 애니메이션을 무제한으로 반복하려면, repeatCount 속성에 `"indefinite"` 값을 사용해라.

------

<br>

## Paths

###### 경로

<br>

- The `<path>` element is used to define a path.
  - `<path>` element는 경로를 정의하는 데 사용된다.

<br>

- The following commands are available for path data:
  - 다음 명령어들을 경로 데이터에 사용할 수 있다.

> `M`: moveto
>
> `L`: lineto
>
> `H`: horizontal lineto
>
> `V`: vertical lineto
>
> `C`: curveto
>
> `S`: smooth curveto
>
> `Q`: quadratic Bezier curve
>
> `T`: smooth quadratic Bezier curveto
>
> `A`: elliptical Arc
>
> `Z`: closepath

<br>

- Define a path using the `d` attribute:
  - `d` 속성을 사용해서 경로를 정의해라.

```html
<svg width="500" height="500">
   <path d="M 0 0 L200 200 L200 0 Z" style="stroke:#000; fill:none;" />
</svg>
```

[코드 실행 확인](https://code.sololearn.com/56/#html)

<br>

- M places our "virtual pen" down at the position 0, 0.
  - M은 "가상 펜"을 0, 0 좌표에 놓는다.
- It then moves 200px down and to the right, then moves up to the position 200, 0.
  - 그런 후 200px 오른쪽 아래로 이동한 다음, 200, 0 좌표로 이동한다.
- The Z command closes the shape, which results in a hypotenuse:
  - Z 명령어는 도형을 닫아 빗변을 만든다.

![img](/assets/img/html-sololearn-html5-13-01.jpeg)

<br>

> All of the above commands can also be expressed with lower case letters.
>
> 위의 모든 명령어들은 소문자로 표현할 수도 있다.

> When capital letters are used, it indicates absolute position; lower case indicates relative position.
>
> 대문자를 사용하면 absolute position을 나타낸다.
>
> 소문자를 relative position을 나타낸다.

------

<br>

## QUIZ

- Which tag is used to create shape animations?
  - 도형 애니메이션을 생성하는 데 사용되는 태그는 무엇인가?

> `<animate>`

<br>

- Which shape is indicated by the following path?
  - 어떤 도형이 다음 경로로 나타나는가?

```html
<path d="M0 0 L0 100 L100 100 L100 0 Z" />
```

> `Square`
>
> 사각형

<br>