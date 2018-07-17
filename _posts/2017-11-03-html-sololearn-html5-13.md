---
layout: post
title: "SoloLearn HTML 번역 - 13. SVG Animations & Paths (HTML5)"
categories: dev
tags: html
---

## Shape Animations

###### 애니메이션 도형

<br>

- SVG animations can be created using the `<animate>` element.
  - SVG 애니메이션은 `<animate>` element를 사용해서 만들 수 있다.
  - `<animate>`: Used to animate an attribute of an SVG shape

<br>

- The example below creates a rectangle that will change its position in 3 seconds and will then repeat the animation twice:
  - 아래 예제는 3초 내에 위치를 변경하고, 애니메이션을 두 번 반복하는 사각형을 만든다.

```html
<svg width="1000" height="250">
	<rect width="150" height="150" fill="orange">
   	<animate attributeName="x" from="0" to="300"
               dur="3s" fill="freeze" repeatCount="2"/>
   </rect>
</svg>
```

[코드 실행 확인 링크](https://code.sololearn.com/55/#html)

<br>

- `attributeName`: Specifies which attribute will be affected by the animation
  - 애니메이션의 영향을 받는 속성을 지정한다.
- `from`: Specifies the starting value of the attribute
  - 속성의 시작 값을 지정한다.
- `to`: Specifies the ending value of the attribute
  - 속성의 종료 값을 지정한다.
- `dur`: Specifies how long the animation runs (duration)
  - 애니메이션이 실행되는 시간(기간)을 지정한다.
- `fill`: Specifies whether or not the attribute's value should return to its intial value when the animation is finished (Values: "remove" resets the value; "freeze" keeps the "to value")
  - 애니메이션이 끝나면 속성의 값을 초기 값으로 되돌릴지 여부를 지정한다.
  - (값 "remove"는 값을 재설정하고, "freeze"는 "to value"를 유지한다)
- `repeatCount`: Specifies the repeat count of the animation
  - 애니메이션의 반복수를 지정한다.

<br>

- In the example above, the rectangle changes its x attribute from 0 to 300 in 3 seconds.
  - 위의 예제에서, 사각형은 3초 내에 x 속성이 0에서 300으로 변경된다.

<br>

> To repeat the animation indefinitely, use the value `"indefinite"` for the repeatCount attribute.
>
> 애니메이션을 무한히 반복하려면, repeatCount 속성에 `"indefinite"` 값을 사용해라.

------

<br>

## Paths

###### 경로

<br>

- The `<path>` element is used to define a path.
  - `<path>` element는 경로를 정의하는 데 사용된다.
  - `<path>`: Defines a path in SVG

<br>

- The following commands are available for path data:
  - 다음 명령을 경로 데이터에 사용할 수 있다.
- `M`: moveto
- `L`: lineto
- `H`: horizontal lineto
- `V`: vertical lineto
- `C`: curveto
- `S`: smooth curveto
- `Q`: quadratic Bézier curve
- `T`: smooth quadratic Bézier curveto
- `A`: elliptical Arc
- `Z`: closepath

<br>

- Define a path using the `d` attribute:
  - `d` 속성을 사용해서 경로를 정의해라.

```html
<svg width="500" height="500">
	<path d="M 0 0 L200 200 L200 0 Z" style="stroke: #000; fill: none;" />
</svg>
```

<br>

- M places our "virtual pen" down at the position 0, 0.
  - M은 "가상 펜"을 0, 0 위치에 놓는다.
- It then moves 200px down and to the right, then moves up to the position 200, 0.
  - 200px 아래 오른쪽으로 이동한 다음, 200, 0 위치로 이동한다.
- The Z command closes the shape, which results in a hypotenuse:
  - Z 명령은 도형을 닫아 빗변을 만든다.

![sololearn img](/aseets/img/sololearn-html-html5-13-01.jpeg)

<br>

> All of the above commands can also be expressed with lower case letters.
>
> 위의 명령은 모두 소문자로도 표현할 수 있다.

> When capital letters are used, it indicates absolute position; lower case indicates relative position.
>
> 대문자를 사용하면 절대 위치(absolute position)를 나타낸다.
>
> 소문자는 상대 위치(relative position)를 나타낸다.

------

<br>

## QUIZ

- Which tag is used to create shape animations?
  - 도형 애니메이션을 만드는 데 사용되는 태그는 어떤 것인가?

> `<animate>`

<br>

- Which shape is indicated by the following path?
  - 어떤 도형이 다음 경로로 표시되는가?

```html
<path d="M0 0 L0 100 L100 100 L100 0 Z" />
```

> [ ] Circle
>
> [x] `Square`
>
> [ ] Nothing
>
> [ ] Triangle

<br>
