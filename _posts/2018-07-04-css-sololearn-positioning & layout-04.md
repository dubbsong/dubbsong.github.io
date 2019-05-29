---
layout: post
title: "(Positioning & Layout 04) float 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Floating

- With CSS float, an element can be pushed to the left or right, allowing other elements to wrap around it.
  - CSS float을 사용하면 element를 왼쪽 또는 오른쪽으로 push 할 수 있으므로, 다른 element를 감쌀 수 있다.
- Float is often used with images, but it is also useful when working with layouts.
  - float은 종종 이미지와 함께 사용되지만, layout 작업을 할 때도 유용하다.
- The values for the float property are `left`, `right`, and `none`.
  - float 속성에 대한 값은 `left`, `right`, `none`이다.
- Left and right float elements in those directions, respectively.
  - 왼쪽과 오른쪽 float element는 각각 해당 방향이다.
- `none` (the default) ensures that the element will not float.
  - `none`(기본값)은 element가 float 되지 않도록 한다.
- Below is an example of an image that is floated to the right.
  - 아래는 오른쪽으로 float 되어 있는 이미지의 예제이다.

<br>

- HTML:

```html
<p>
   This paragraph has an image that is floated to the <strong>right.</strong>
   It is highly recommended to add a margin to images so that the text does not get too close to the image.
   If you want your text to be easily read, you should always add a few pixels between words and borders, images, and other content.
</p>
```

<br>

- CSS:

```css
img {
   float: right;
}
```

[코드 실행 확인](https://code.sololearn.com/570/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-04-01.png)

<br>

> Elements are floated horizontally, meaning that an element can only be floated left or right, not up or down.
>
> element는 수평으로 float 된다.
>
> 즉, element는 위쪽이나 아래쪽이 아닌, 왼쪽 또는 오른쪽으로만 float 할 수 있다.

------

<br>

## Elements Next to Each Other

###### 서로 옆에 있는 element

<br>

- If you place several floating elements one after the other, they will float next to each other if there is enough room.
  - 여러 개의 floating element를 차례로 배치하면, 서로 나란히 float 된다.
  - (충분한 공간이 있다면)
- As an example, in a print layout, images may be set into the page such that text wraps around them as needed.
  - 예를 들어, 출력 layout에서 이미지가 페이지에 설정될 수 있다.
  - 필요에 따라 텍스트가 주위를 둘러싼다.

<br>

- CSS:

```css
img {
   float: left;
   width: 120px;
   margin-right: 10px;
}

p {
   width: 120px;
   float: left;
}
```

[코드 실행 확인](https://code.sololearn.com/571/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-04-02.jpeg)

------

<br>

## QUIZ

- In which directions can the elements be floated?
  - 어떤 방향으로 element를 float 할 수 있는가?

> [ ] bottom
>
> [ ] `right`
>
> [ ] top
>
> [ ] `left`

<br>

- What property along with float is used in the example to make the elements float side by side?
  - 예제에서 어떤 속성을 float과 함께 사용해서 element를 나란히 배치할 수 있었는가?

> `width`

<br>