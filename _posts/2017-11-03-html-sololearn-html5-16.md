---
layout: post
title: "SoloLearn HTML 번역 - 16. Canvas Transformations (HTML5)"
categories: dev
tags: html
---

## Working with Canvas

###### canvas로 작업하기

<br>

- The Canvas element can be transformed.
  - Canvas element를 변형할 수 있다.
- As an example, a text is written on the canvas at the coordinates (10, 30).
  - 예를 들어, 텍스트는 canvas의 좌표 (10, 30)에 쓰여진다.

```js
ctx.font="bold 22px Tahoma";
ctx.textAlign="start";
ctx.fillText("start", 10, 30);
```

<br>

- Result

![sololearn img](/assets/img/sololearn-html-html5-16-01.jpeg)

<br>

- The `translate(x, y)` method is used to move the Canvas.
  - `translate(x, y)` 메소드는 Canvas를 이동하는 데 사용된다.
- x indicates how far to move the grid horizontally, and y indicates how far to move the grid vertically.
  - x는 격자를 수평으로 얼마나 멀리 이동시킬 것인지를 나타내며, y는 격자를 수직으로 얼마나 멀리 이동시킬 것인지를 나타낸다.

```js
ctx.translate(100, 150);
ctx.fillText("after translate", 10, 30);
```

<br>

- In this example, the canvas is moved 100px to the right, and 150px down.
  - 이 예제에서는 canvas가 오른쪽으로 100px 이동하고, 아래로 150px 이동한다.

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-html5-16-02.jpeg)

------

<br>

## The rotate() Method

- The `rotate()` method is used to rotate the HTML5 Canvas.
  - `rotate()` 메소드는 HTML5 Canvas를 회전시키는 데 사용된다.
- The value must be in radians, not degrees.
  - 값은 각도가 아닌 호도(라디안)이어야 한다.

<br>

- Here is an example that draws the same rectangle before and after rotation is set:
  - 다음은 동일한 사각형의 회전이 설정되기 전과 후를 그리는 예제이다.

```js
ctx.fillStyle = "#FF0000";
ctx.fillRect(10, 10, 100, 100);

ctx.rotate((Math.PI / 180) * 25);	// rotate 25 degrees

ctx.fillStyle = "#0000FF";
ctx.fillRect(10, 10, 100, 100);
```

<br>

![sololearn img](/assets/img/sololearn-html-html5-16-03.jpeg)

------

<br>

## The scale() Method

- The `scale()` method scales the current drawing.
  - `scale()` 메소드는 현재 드로잉의 크기를 조절한다.

<br>

- The number of times by which the image should be scaled in the X-direction.
  - 이미지가 X 방향으로 축적되어야 하는 횟수이다.
- The number of times by which the image should be scaled in the Y-direction.
  - 이미지가 Y 방향으로 축적되어야 하는 횟수이다.

```js
var canvas = document.getElementById('canvas1');

ctx = canvas.getContext('2d');
ctx.font = "bold 22px Tahoma";
ctx.textAlign = "start";
ctx.fillText("start", 10, 30);
ctx.translate(100, 150);
ctx.fillText("after translate", 0, 0);
ctx.rotate(1);
ctx.fillText("after rotate", 0, 0);
ctx.scale(1.5, 4)
ctx.fillText("after scale", 0, 20);
```

<br>

- This will scale the canvas 1.5 times in the X-direction, and 4 times in Y-direction:
  - 위 코드는 canvas가 X 방향으로 1.5배, Y 방향으로 4배로 크기가 조정된다.

![sololearn img](/assets/img/sololearn-html-html5-16-04.jpeg)

------

<br>

## QUIZ

- Which method is used to move the canvas element?
  - 어떤 방법으로 canvas element를 이동하는가?

> [ ] transformation()
>
> [ ] move()
>
> [ ] location()
>
> [x] `translate()`

<br>

- The rotation parameter is in:
  - rotation 매개변수는 다음에 있다.

> [ ] Radians & degrees
>
> [x] `Radians`
>
> [ ] Degrees

<br>

- What method is used to increase or decrease the size of the current drawing?
  - 현재 드로잉의 크기를 늘리거나 줄이기 위해 어떤 방법이 사용되는가?

> `scale`

<br>
