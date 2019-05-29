---
layout: post
title: "(HTML5 16) canvas 변형"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 canvas Transformations

###### canvas 변형

------

<br>

<br>

## Working with Canvas

###### canvas로 작업하기

<br>

- The canvas element can be transformed.
  - canvas element를 변형할 수 있다.
- As an example, a text is written on the canvas at the coordinates (10, 30).
  - 에를 들어, 텍스트는 canvas 좌표 (10, 30)에 작성된다.

```js
ctx.font = "bold 22px Tahoma";
ctx.textAlign = "start";
ctx.fillText("start", 10, 30);
```

[코드 실행 확인](https://code.sololearn.com/60/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-html5-16-01.jpeg)

<br>

- The `translate(x, y)` method is used to move the Canvas.
  - `translate(x, y)` 메소드는 canvas를 이동하는 데 사용된다.
- x indicates how far to move the grid horizontally, and y indicates how far to move the grid vertically.
  - x는 격자를 수평으로 얼마나 멀리 이동할 것인지를 나타내고, y는 격자를 수직으로 얼마나 멀리 이동할 것인지를 나타낸다.

```js
ctx.translate(100, 150);
ctx.fillText("after translate", 10, 30);
```

[코드 실행 확인](https://code.sololearn.com/61/#html)

<br>

- In this example, the canvas is moved 100px to the right, and 150px down.
  - 이 예제에서는 canvas가 오른쪽으로 100px 이동하고, 아래로 150px 이동한다.

<br>

- Result:

![img](/assets/img/html-sololearn-html5-16-02.jpeg)

<br>

> Canvas has several methods for drawing paths, boxes, circles, text, and adding images.
>
> canvas에는 경로, 상자, 원, 텍스트, 이미지 추가를 위한 여러 가지 방법이 있다.

------

<br>

## The rotate() Method

###### rotate() 메소드

<br>

- The `rotate()` method is used to rotate the HTML5 canvas.
  - `rotate()` 메소드는 HTML5 canvas를 회전시키는 데 사용된다.
- The value must be in radians, not degrees.
  - 값은 degree가 아닌 radian이어야 한다.

<br>

- Here is an example that draws the same rectangle before and after rotation is set:
  - 다음은 회전이 설정되기 전과 후에 동일한 사각형을 그리는 예제이다.

```js
ctx.fillStyle = "#FF0000";
ctx.fillRect(10, 10, 100, 100);

ctx.rotate((Math.PI / 180) * 25);	// rotate 25 degrees

ctx.fillStyle = "#0000FF";
ctx.fillRect(10, 10, 100, 100);
```

[코드 실행 확인](https://code.sololearn.com/62/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-html5-16-03.jpeg)

<br>

> The rotation will only affect drawings made after the rotation is done.
>
> 회전은 회전이 완료된 후에 만들어진 도형에만 적용된다.

------

<br>

## The scale() Method

###### scale() 메소드

<br>

- The `scale()` method scales the current drawing.
  - `scale()` 메소드는 현재 도형의 사이즈를 조정한다.
- It takes two parameters:
  - 이 메소드는 두 개의 매개변수를 취한다.

> The number of times by which the image should be scaled in the X-direction.
>
> X 방향으로 이미지의 사이즈를 조절하는 횟수.

> The number of times by which the image should be scaled in the Y-direction.
>
> Y 방향으로 이미지의 사이즈를 조절하는 횟수.

```js
var canvas = document.getElementById("canvas1");
ctx = canvas.getContext("2d");
ctx.font = "bold 22px Tahoma";
ctx.textAlign = "start";
ctx.fillText("start", 10, 30);
ctx.translate(100, 150);
ctx.fillText("after translate", 0, 0);
ctx.rotate(1);
ctx.fillText("after rotate", 0, 0);
ctx.scale(1.5, 4);
ctx.fillText("after scale", 0, 20);
```

[코드 실행 확인](https://code.sololearn.com/63/#html)

<br>

- This will scale the canvas 1.5 times in the X-direction, and 4 times in Y-direction:
  - 이렇게 하면 canvas가 X 방향으로 1.5배, Y 방향으로 4배 확대된다.

![img](/assets/img/html-sololearn-html5-16-04.jpeg)

<br>

> If you scale a drawing, all future drawings will also be scaled.
>
> 도형의 사이즈를 조정하면, 이후의 모든 도형도 사이즈가 조정된다.

------

<br>

## QUIZ

- Which method is used to move the canvas element?
  - 어떤 메소드가 canvas element를 이동시키는가?

> `translate()`

<br>

- The rotation parameter is in:
  - rotation 매개변수는 … 단위이다.

> `radians`

<br>

- What method is used to increase or decrease the size of the current drawing?
  - 현재 도형의 사이즈를 늘리거나 줄이기 위해 어떤 메소드가 사용되는가?

> `scale`

<br>