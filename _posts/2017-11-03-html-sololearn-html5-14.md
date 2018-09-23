---
layout: post
title: "(HTML5 14) canvas element"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 \<canvas> Element

###### \<canvas> element

<br>

- The HTML canvas is used to draw graphics that include everything from simple lines to complex graphic objects.
  - HTML canvas는 간단한 선에서 복잡한 그래픽 객체까지 모든 것을 포함하는 그래픽을 그리는 데 사용된다.

<br>

- The `<canvas>` element is defined by:
  - `<canvas>` element는 아래처럼 정의된다. 

```html
<canvas id="canvas1" width="200" height="100">
</canvas>
```

<br>

> The \<canvas> element is only a container for graphics.
>
> \<canvas> element는 그래픽 컨테이너일 뿐이다.

> You must use a script to actually draw the graphics (usually JavaScript).
>
> 스크립트를 사용해서 그래픽을 그려야 한다.
>
> (일반적으로 JavaScript)

<br>

- The `<canvas>` element must have an `id attribute` so it can be referred to by JavaScript:
  - `<canvas>` element는 JavaScript에서 참조할 수 있도록 `id 속성`을 가져야 한다.

```html
<html>
   <head></head>
   <body>
      <canvas id="canvas1" width="400" height="300"></canvas>
      
      <sciprt>
         var can = document.getElementById("canvas1");
         var ctx = can.getContext("2d");
      </sciprt>
      
   </body>
</html>
```

<br>

- `getContext()` returns a drawing context on the canvas.
  - `getContext()`는 canvas에서 drawing context를 반환한다.

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
  - Y 좌표는 canvas 아래쪽으로 갈수록 증가한다.

![img](/assets/img/html-sololearn-html5-14-01.jpeg)

<br>

> The \<canvas> element is only a container for graphics.
>
> \<canvas> element는 그래픽의 컨테이너일 뿐이다.

------

<br>

## Drawing Shapes

###### 도형 그리기

<br>

- The `fillRect(x, y, w, h)` method draws a "filled" rectangle, in which w indicates width and h indicates height.
  - `fillRect(x, y, w, h)` 메소드는 "채워진" 사각형을 그린다.
  - w는 width(너비)를 나타내고, h는 height(높이)를 나타낸다.
- The default fill color is black.
  - 기본 채우기 색상은 검은색이다.

<br>

- A black 100*100 pixel rectangle is drawn on the canvas at the position (20, 20):
  - 검은색 100*100 픽셀 사각형이 canvas의 (20, 20) 좌표에 그려진다.

```js
var c = document.getElementById("canvas1");
var ctx = c.getContext("2d");
ctx.fillRect(20, 20, 100, 100);
```

[코드 실행 확인](https://code.sololearn.com/58/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-html5-14-02.jpeg)

<br>

- The `fillStyle` property is used to set a color, gradient, or pattern to fill the drawing.
  - `fillStyle` 속성은 도형을 채울 색상, gradient, 패턴을 설정하는 데 사용된다.
- Using this property allows you to draw a green-filled rectangle.
  - 이 속성을 사용하면 초록색으로 채워진 사각형을 그릴 수 있다.

```js
var canvas = document.getElementById("canvas1");
var ctx=canvas.getContext("2d");
ctx.fillStyle = "rgba(0, 200, 0, 1)";
ctx.fillRect (36, 10, 22, 22);
```

[코드 실행 확인](https://code.sololearn.com/59/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-html5-14-03.jpeg)

<br>

- The canvas supports various other methods for drawing:
  - canvas는 다양한 그리기 방법을 지원한다.

<br>

#### Draw a Line

###### 선 그리기

<br>

- `moveTo(x, y)`: Defines the starting point of the line.
  - 선의 시작점을 정의한다.
- `lineTo(x, y)`: Defines the ending point of the line.
  - 선의 종료점을 정의한다.

<br>

#### Draw a Circle

###### 원 그리기

<br>

- `beginPath()`: Starts the drawing.
  - 그리기를 시작한다.
- `arc(x, y, r, start, stop)`: Sets the parameters of the circle.
  - 원의 매개변수를 설정한다.
- `stroke()`: Ends the drawing.
  - 그리기를 종료한다.

<br>

#### Gradients

###### gradient

<br>

- `createLinearGradient(x, y, x1, y1)`: Creates a linear gradient.
  - 선형 gradient를 생성한다.
- `createRadialGradient(x, y, r, x1, y1, r1)`: Creates a radial/circular gradient.
  - 방사형/원형 gradient를 생성한다.

<br>

#### Drawing Text on the Canvas

###### canvas에 텍스트 그리기

<br>

- `Font`: Defines the font properties for the text.
  - 텍스트의 font 속성을 정의한다.
- `fillText(text, x, y)`: Draws "filled" text on the canvas.
  - canvas에 "채워진" 텍스트를 그린다.
- `strokeText(text, x, y)`: Draws text on the canvas (no fill).
  - canvas에 텍스트를 그린다 (채우기 없이).

<br>

> There are many other methods aimed at helping to draw shapes and images on the canvas.
>
> canvas에 도형과 이미지를 그리는 데 도움이 되는 다른 방법들이 많이 있다.

------

<br>

## QUIZ

- You can draw on the canvas using...
  - canvas를 사용해서 ...를 그릴 수 있다.

> `JavaScript`

<br>

- X and Y are...
  - X와 Y는 ...이다.

> `coordinates from upper left corner`
>
> 왼쪽 상단 모서리로부터의 좌표

<br>

- fillRect(36, 10, 22, 12) indicates a rectangle with a height of ...
  - fillRect(36, 10, 22, 12)는 높이가 ..인 사각형을 나타낸다.

> `12`

<br>