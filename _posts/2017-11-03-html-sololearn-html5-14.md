---
layout: post
title: "SoloLearn HTML 번역 - 14. Canvas (HTML5)"
categories: dev
tags: html
---

## The \<canvas> Element

- The HTML canvas is used to draw graphics that include everything from simple lines to complex graphic objects.
  - HTML canvas는 간단한 선에서 복잡한 그래픽 객체에 이르기까지 모든 것을 포함하는 그래픽을 그리는 데 사용된다.

<br>

- The `<canvas>` element is defined by:
  - `<canvas>` element는 다음에 의해 정의된다.
  - `<canvas>`: Used to draw graphics, on the fly, via scripting (usually JavaScript)

```html
<canvas id="canvas1" width="200" height="100">
</canvas>
```

<br>

> The \<canvas> element is only a container for graphics.
>
> \<canvas> element는 그래픽의 컨테이너일 뿐이다.

> You must use a script to actually draw the graphics (usually JavaScript).
>
> 스크립트를 이용해서 실제로 그래픽을 그려야 한다(일반적으로 JavaScript).

<br>

- The `<canvas>` element must have an `id attribute` so it can be referred to by JavaScript.
  - `<canvas>` element는 JavaScript에서 참조할 수 있도록 `id 속성`을 가져야 한다.

```html
<html>
   <head>
   </head>
   <body>
      <canvas id="canvas1" width="400" height="300">
      </canvas>
      
      <script>
      	var can = document.getElementById("canvas1");
         var ctx = can.getContext("2d");
      </script>
   </body>
</html>
```

<br>

- `getContext()` returns a drawing context on the canvas.
  - `getContext()`는 canvas에서 드로잉 컨텍스트를 반환한다.

<br>

> Basic knowledge of JavaScript is required to understand and use the Canvas.
>
> Canvas를 이해하고 사용하려면 JavaScript에 대한 기본 지식이 필요하다.

------

<br>

## Canvas Coordinates

###### canvas 좌표

<br>

- The HTML canvas is a two-dimensional grid.
  - HTML canvas는 2차원 격자이다.
- The upper-left corner of the canvas has the coordinates (0, 0).
  - canvas의 왼쪽 위 모서리는 좌표 (0, 0)을 가진다.

<br>

- X coordinate increases to the right.
  - X 좌표는 오른쪽으로 증가한다.
- Y coordinate increases toward the bottom of the canvas.
  - Y 좌표는 canvas 아래쪽으로 갈수록 커진다.

![sololearn img](/assets/img/sololearn-html-html5-14-01.jpeg)

------

<br>

## Drawing Shapes

###### 도형 그리기

<br>

- The `fillRect(x, y, w, h)` method draws a "filled" rectangle, in which w indicates width and h indicates height.
  - `fillRect(x, y, w, h)` 메소드는 채워진 사각형을 그린다.
  - 여기서 w는 width를 나타내고, h는 height를 나타낸다.
- The default fill color is black.
  - 기본 채우기 색상은 검은색이다.

<br>

- A black 100*100 pixel rectangle is drawn on the canvas at the position (20, 20):
  - 검은 100*100 픽셀 사각형이 canvas의 위치 (20, 20)에 그려진다.

```html
var c = document.getElementById("canvas");
var ctx = c.getContext("2d");
ctx.fillRect(20, 20, 100, 100);
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-html5-14-02.jpeg)

<br>

- The `fillStyle` property is used to set a color, gradient, or pattern to fill the drawing.
  - `fillStyle` property는 도면을 채울 색상, 그라디언트, 패턴을 설정하는 데 사용된다.
- Using this property allows you to draw a green-filled rectangle.
  - 이 property를 사용하면 초록생으로 채워진 사각형을 그릴 수 있다.

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-html5-14-03.jpeg)

<br>

- The canvas supports various other methods for drawing:
  - canvas는 다양한 그리기 method를 지원한다.

<br>

#### Draw a Line

- `moveTo(x, y)`: Defines the starting point of the line
  - 선의 시작점을 정의한다.
- `lineTo(x, y)`: Defines the ending point of the line.
  - 선의 끝나는 점을 정의한다.

<br>

#### Draw a Circle

- `beginPath()`: Starts the drawing.
  - 그리기를 시작한다.
- `arc(x, y, r, start, stop)`: Sets the parameters of the circle.
  - 원의 매개변수를 설정한다.
- `stroke()`: Ends the drawing.
  - 그리기를 종료한다.

<br>

#### Gradients

- `createLinearGradient(x, y, x1, y1)`: Creates a linear gradient.
  - 선형 그라디언트를 생성한다.
- `createRadialGradient(x, y, r, x1, y1, r1)`: Create a radial/circular gradient.
  - 방사형/원형 그라디언트를 생성한다.

<br>

#### Drawing Text on the Canvas

- `Font`: Defines the font properties for the text.
  - 텍스트의 font propetry를 정의한다.
- `fillText(text, x, y)`: Draws "filled" text on the canvas.
  - canvas에 "채워진" 텍스트를 그린다.
- `strokeText(text, x, y)`: Draws text on the canvas (no fill).
  - canvas에 텍스트를 그린다(채우기가 없다).

<br>

> There are many other methods aimed at helping to draw shapes and images on the canvas.
>
> canvas에 도형과 이미지를 그리는 데 도움이 되는 많은 다른 방법이 있다.

------

<br>

## QUIZ

- You can draw on the canvas using...
  - ..를 사용해서 canvas에 그릴 수 있다.

> [ ] CSS
>
> [ ] head tags
>
> [x] `JavaScript`
>
> [ ] shape tags

<br>

- X and Y are...

> [ ] ...coordinates from lower left corner
>
> [ ] ...the height and the width of an item
>
> [ ] ...coordinates from upper right corner
>
> [x] `...coordinates from upper left corner`

<br>

- fillRect(36, 10, 22, 12) indicates a rectagle with a height of...
  - fillReact(36, 10, 22, 12)는 높이가 ..인 사각형을 나타낸다.

> [ ] 10
>
> [ ] 36
>
> [ ] 22
>
> [x] `12`

<br>