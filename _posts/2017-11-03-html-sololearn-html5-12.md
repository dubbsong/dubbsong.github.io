---
layout: post
title: "SoloLearn HTML 번역 - 12. SVG (HTML5)"
categories: dev
tags: html
---

## Drawing Shapes

###### 도형 그리기

<br>

- `SVG` stands for `S`calable `V`ector `G`raphics, and is used to draw shapes with HTML-style markup.
  - `SVG`는 `S`calable `V`ector `G`raphics(확장 가능한 벡터 그래픽)의 약자로, HTML 스타일의 마크업으로 도형을 그릴 때 사용된다.

<br>

- It offers several methods for drawing paths, boxes, circles, text, and graphic images.
  - SVG는 path, box, circle, text, graphic image를 그리는 여러 방법을 제공한다.

<br>

> SVG is not pixel-based, so it can be magnified infinitely with no loss of quality.
>
> SVG는 픽셀 기반이 아니므로, 품질 손실 없이 무한히 확대할 수 있다.

------

<br>

## Inserting SVG Images

###### SVG 이미지 삽입

<br>

- An SVG image can be added to HTML code with just a basic image tag that includes a source attribute pointing to the image:
  - SVG 이미지는 이미지를 가리키는 source 속성을 포함하는 기본 이미지 태그만으로 HTML 코드에 추가될 수 있다.

```html
<img src="image.svg" alt="" height="300" />
```

------

<br>

## Drawing a Circle

###### 원 그리기

<br>

- To draw shapes with SVG, you first need to create an `SVG` element tag with two attributes: width and height.
  - SVG로 도형을 그리려면, 먼저 width와 height라는 두 속성을 가진 `SVG` element 태그를 만들어야 한다.

```html
<svg width="1000" height="1000"></svg>
```

<br>

- To create a circle, add a `<circle>` tag:
  - 원을 만들려면, `<circle>` 태그를 추가해라.

```html
<svg width="2000" height="2000">
	<circle cx="80" cy="80" r="50" fill="green" />
</svg>
```

<br>

- `cx` pushes the center of the circle further to the right of the screen
  - `cx`는 원의 중심을 화면의 오른쪽으로 더 밀어 넣는다.
- `cy` pushes the center of the circle further down from the top of the screen
  - `cy`는 원의 중심을 화면의 상단에서 더 아래로 내린다.
- `r` defines the radius
  - `r`은 반지름을 정의한다.
- `fill` determines the color of our circle
  - `fill`이 원의 색상을 결정한다.
- `stroke` adds an outline to the circle
  - `stroke`가 원에 윤곽을 추가한다.

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-html5-12-01.jpeg)

------

<br>

## Other Shape Elements

###### 다른 도형 element

<br>

- `<rect>` defines a rectangle:
  - `<rect>`는 사각형을 정의한다.

```html
<svg width="2000" height="2000">
	<rect width="300" height="100"
         x="20" y="20" fill="green" />
</svg>
```

<br>

- The following code will draw a green-filled rectangle.
  - 위의 코드는 초록색으로 채워진 사각형을 그린다.

![sololearn img](/assets/img/sololearn-html-html5-12-02.jpeg)

<br>

- `<line>` defines a line segment:
  - `<line>`은 선분을 정의한다.
  - `<line>`: Defines a line segment in SVG

```html
<svg width="400" height="410">
	<line x1="10" y1="10" x2="200" y2="100"
         style="stroke: #000000; stroke-linecap: round; stroke-width: 20" />
</svg>
```

<br>

- (x1, y1) define the start coordinates, (x2, y2) define the end coordinates.
  - 시작(x1, y1) 좌표와 끝(x2, y2) 좌표를 정의한다.

![sololearn img](/assets/img/sololearn-html-html5-12-03.jpeg)

<br>

- `<polyline>` defines shapes built from multiple line definitions:
  - `<polyline>`은 여러 줄 정의에서 만들어진 도형을 정의한다.
  - `<polyline>`: Defines a set of connected straight line segments in SVG

```html
<svg width="2000" height="500">
	<polyline style="stroke-linejoin: miter; stroke: black;
                    stroke-width: 12; fill: none;"
             points="100 100, 150, 150, 200 100" />
</svg>
```

- Points are the polyline's coordinates.
  - points는 polyline의 좌표다.
- The code below will draw a black check sign:
  - 위 코드는 검은색 체크 기호를 그린다.

![sololearn img](/assets/img/sololearn-html-html5-12-04.jpeg)

------

<br>

## \<ellipse> and \<polygon>

###### \<ellipse>와 \<polygon>

<br>

#### Ellipse

- The `<ellipse>` is similar to the `<circle>`, with one exception:
  - `<ellipse>`는 `<circle>`과 비슷하지만, 하나의 예외가 있다.
- You can independently change the horizontal and vertical axes of its radius, using the `rx` and `ry` attributes.
  - `rx`와 `ry` 속성을 사용해서 반지름의 수평 및 수직 축을 독립적으로 변경할 수 있다.

```html
<svg height="500" width="1000">
	<ellipse cx="200" cy="100" rx="150" ry="70" style="fill: green" />
</svg>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-html5-12-05.jpeg)

<br>

#### Polygon

- The `<polygon>` element is used to create a graphic with at least three sides.
  - `<polygon>` element는 최소한 세 면이 있는 그래픽을 만드는 데 사용된다.
- The polygon element is unique because it automatically closes off the shape for you.
  - polygon element는 자동으로 도형을 닫아주기 때문에 독특하다.

```html
<svg width="2000" height="2000">
	<polygon points="100 100, 200 200, 300 0"
            style="fill: green; stroke: black;" />
</svg>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-html5-12-06.jpeg)

------

<br>

## QUIZ

- What does SVG stand for?
  - SVG는 무엇을 의미하는가?

> scalable vector graphics
>
> 확장 가능한 벡터 그래픽

<br>

- Fill in the blanks to add "my.svg" to the page:
  - 빈칸을 채워서 "my.svg"를 추가해라.

```html
<img src="my.svg" width="300px" alt="" />
```

<br>

- Fill in the blanks to create a red circle at the position X=50, Y=240:
  - X=50, Y=240 위치에 빨간색 원을 만들기 위해서 빈칸을 채워라.

```html
<svg width="1000" height="1000">
	<circle cx="50" cy="240"
           r="10" fill="red" />
</svg>
```

<br>

- Fill in the blanks to add a line to the page, starting from coordinates 10, 20 and ending at 50, 100:
  - 좌표 10, 20부터 50, 100으로 끝나는 선을 페이지에 추가해라.

```html
<svg width="500" height="500">
	<line x1="10" y1="20"
         x2="50" y2="100" />
</svg>
```

<br>

- Which of the following is an HTML5 SVG shape?
  - 다음 중 HTML5 SVG 도형은 무엇인가?

> [ ] prism
>
> [ ] star
>
> [ ] ball
>
> [x] `polygon`

<br>