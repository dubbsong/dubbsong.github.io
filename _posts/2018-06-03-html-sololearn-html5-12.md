---
layout: post
title: "(HTML5 12) SVG"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 SVG

------

<br>

<br>

## Drawing Shapes

###### 도형 그리기

<br>

- `SVG` stands for `S`calale `V`ector `G`raphics, and is used to draw shapes with HTML-style markup.
  - `SVG`는 `S`calale `V`ector `G`raphics의 약자로, HTML-style의 마크업으로 사용해서 도형을 그릴 때 사용된다.

<br>

- It offers several methods for drawing paths, boxes, circles, text, and graphic images.
  - SVG는 경로, 상자, 원, 텍스트, 그래픽 이미지를 그리는 여러 가지 방법을 제공한다.

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

<br>

> SVG defines vector-based graphics in XML format.
>
> SVG는 벡터 기반 그래픽을 XML 형식으로 정의한다.

------

<br>

## Drawing a Circle

###### 원 그리기

<br>

- To draw shapes with SVG, you first need to create an `SVG` element tag with two attributes: width and height.
  - SVG로 도형을 그리려면 먼저 너비와 높이 두 가지 속성을 가진 `SVG` element 태그를 생성해야 한다.

```html
<svg width="1000" height="1000"></svg>
```

<br>

- To create a circle, add a `<circle>` tag:
  - 원을 만들려면 `<circle>` 태그를 추가해라.

```html
<svg width="2000" height="2000">
   <circle cx="80" cy="80" r="50" fill="green" />
</svg>
```

[코드 실행 확인](https://code.sololearn.com/49/#html)

<br>

- `cx` pushes the center of the circle further to the right of the screen.
  - `cx`는 원의 중심을 화면의 오른쪽으로 더 push 한다.
- `cy` pushes the center of the circle further down from the top of the screen.
  - `cy`는 원의 중심을 화면의 상단에서 아래로 더 push 한다.
- `r` defines the radius.
  - `r`은 반지름을 정의한다.
- `fill` determines the color of our circle.
  - `fill`은 원의 색상을 결정한다.
- `stroke` adds an outline to the circle.
  - `stroke`는 원에 윤곽을 추가한다.

<br>

- Result:

![img](/assets/img/html-sololearn-html5-12-01.jpeg)

<br>

> Every element and every attribute in SVG files can be animated.
>
> SVG 파일의 모든 element와 모든 속성을 애니메이션 할 수 있다.

------

<br>

## Other Shape Elements

###### 다른 도형 element

<br>

- `<rect>` defines a rectangle:
  - `<rect>`는 사각형을 정의한다.

```html
<svg width="2000" height="2000">
   <rect width="300" height="100" x="20" y="20" fill="green" />
</svg>
```

[코드 실행 확인](https://code.sololearn.com/50/#html)

<br>

- The following code will draw a green-filled rectangle.
  - 다음 코드는 초록색으로 채워진 사각형을 그린다.

![img](/assets/img/html-sololearn-html5-12-02.jpeg)

<br>

- `<line>` defines a line segment:
  - `<line>`은 선분을 정의한다.

```html
<svg width="400" height="410">
   <line x1="10" y1="10" x2="200" y2="100"
         style="stroke:#000000; stroke-linecap:round; stroke-width:20" />
</svg>
```

[코드 실행 확인](https://code.sololearn.com/51/#html)

<br>

- (x1, y1) define the start coordinates(x2, y2) define the end coordinates.
  - (x1, y1)은 시작 좌표를 정의하고, (x2, y2)는 끝 좌표를 정의한다.

![img](assets/img/html-sololearn-html5-12-03.jpeg)

<br>

- `<polyline>` defines shapes built from multiple line definitions:
  - `<polyline>`은 여러 줄 정의로 작성된 도형을 정의한다.

```html
<svg width="2000" height="500">
   <polyline style="stroke-linejoin:miter; stroke:black;
                    stroke-width:12; fill:none;"
             points="100 100, 150 150, 200 100" />
</svg>
```

[코드 실행 확인](https://code.sololearn.com/52/#html)

<br>

- Points are the polyline's coordinates.
  - points는 polyline의 좌표이다.
- The code below will draw a black check sign:
  - 위 코드는 검은색 체크 표시를 그린다.

![img](/assets/img/html-sololearn-html5-12-04.jpeg)

<br>

> The width and height attributes of the \<rect> element define the height and the width of the rectangle.
>
> \<rect> element의 width와 height 속성은 사각형의 너비와 높이를 정의한다.

------

<br>

## \<ellipse> and \<polygon>

###### \<ellipse> & \<polygon>

<br>

#### Ellipse

- The `<ellipse>` is similar to the `<circle>`, with one exception:
  - `<ellipse>`는 `<circle>`과 비슷하지만, 한 가지 예외가 있다.
- You can independently change the horizontal and vertical axes of its radius, using the `rx` and `ry` attributes.
  - `rx`와 `ry` 속성을 사용해서 반지름의 수평과 수직 축을 독립적으로 변경할 수 있다.

```html
<svg height="500" width="1000">
   <ellipse cx="200" cy="100" rx="150" ry="70" style="fill:green" />
</svg>
```

[코드 실행 확인](https://code.sololearn.com/53/#html)

<br>

#### Polygon

- The `<polygon>` element is used to create a graphic with at least three sides.
  - `<polygon>` element는 최소한 세 면이 있는 그래픽을 생성하는 데 사용된다.
- The polygon element is unique because it automatically closes off the shape for you.
  - polygon element는 자동으로 도형을 닫아주기 때문에 특별하다.

```html
<svg width="2000" height="2000">
   <polygon points="100 100, 200 200, 300 0"
            style="fill:green; stroke:black;" />
</svg>
```

[코드 실행 확인](https://code.sololearn.com/54/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-html5-12-05.jpeg)

<br>

> Polygon comes from Greek.
>
> polygon은 그리스어에서 유래한다.

> "Poly" means "many" and "gon" means "angle".
>
> "poly"는 "many"를 의미하고, "gon"은 "angle"을 의미한다.

------

<br>

## QUIZ

- What does SVG stand for?
  - SVG는 무엇을 의미하는가?

> `scalable vector graphics`
>
> 확장 가능한 벡터 그래픽

<br>

- Fill in the blanks to add "my.svg" to the page:
  - "my.svg" 를 페이지에 추가해라.

```html
<img src="my.svg" width="300px" alt="" />
```

<br>

- Fill in the blanks to create a red circle at the position X=50, Y=240:
  - X=50, Y=240 위치에 빨간색 원을 생성해라.

```html
<svg width="1000" height="1000">
   <circle cx="50" cy="240" r="10" fill="red" />
</svg>
```

<br>

- Fill in the blanks to add a line to the page, starting from coordinates 10, 20 and ending at 50, 100:
  - 10, 20 좌표에서 시작해 50, 100 좌표로 끝나는 선을 페이지에 추가해라.

```html
<svg width="500" height="500">
   <line x1="10" y1="20" x2="50" y2="100" />
</svg>
```

<br>

- Which of the following is an HTML5 SVG shape?
  - HTML5 SVG 도형은 무엇인가?

> `polygon`

<br>
