---
layout: post
title: "(Properties 03) border 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS border Property

###### border 속성

<br>

- The CSS border property allows you to customize the borders of HTML elements.
  - CSS border 속성을 사용하면, HTML element의 border를 사용자 정의할 수 있다.
- In order to add a border to the element, you need to specify the `size`, `style`, and `color` of the border.
  - element에 border를 추가하려면, border의 `size`, `style`, `color`를 지정해야 한다.
- The example below shows how to add a solid green border to the paragraph.
  - 아래 예제에서는 토막글에 solid green border를 추가하는 방법을 보여준다.

<br>

- HTML:

```html
<p>This is an example of a solid border. </p>
```

<br>

- CSS:

```css
p {
   padding: 10px;
   border: 5px solid green;
}
```

[코드 실행 확인](https://code.sololearn.com/537/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-03-01.png)

------

<br>

## Border Width

###### border 너비

<br>

- The properties for the border can be set separately.
  - border의 속성은 별도로 설정할 수 있다.
- The `border-width` property specifies the width of the border:
  - `border-width` 속성은 border의 너비를 지정한다.

<br>

- HTML:

```html
<p class="first">
   Border width of this paragraph is set to 2px.
</p>
<p class="second">
   Border width of this paragraph is set to 5px.
</p>
```

<br>

- CSS:

```css
p.first {
   padding: 10px;
   border-style: solid;
   border-width: 2px;
}

p.second {
   padding: 10px;
   border-style: solid;
   border-width: 5px;
}
```

[코드 실행 확인](https://code.sololearn.com/538/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-03-02.png)

<br>

#### Border Color

###### border 색상

<br>

- The border color of the element can be defined using a color name, RGB, or Hex values.
  - element의 border 색상은 color name, RGB, 16진수 값을 사용해서 정의할 수 있다.

<br>

- HTML:

```html
<p class="first">
   Border color has been created using <strong>color name. </strong>
</p>
<p class="second">
   Border color has been created using <strong>Hex values. </strong>
</p>
<p class="third">
   Border color has been created using <strong>RGB values. </strong>
</p>
```

<br>

- CSS:

```css
p.first {
   padding: 10px;
   border-style: solid;
   border-width: 2px;
   border-color: blue;
}

p.second {
   padding: 10px;
   border-style: solid;
   border-width: 2px;
   border-color: #FF6600
}

p.third {
   padding: 10px;
   border-style: solid;
   border-width: 2px;
   border-color: rgb(0, 153, 0);
}
```

[코드 실행 확인](https://code.sololearn.com/539/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-03-03.png)

<br>

> None of the border properties will have any effect unless the `border-style` property is set.
>
> `border-style` 속성이 설정되어 있지 않으면, 어떤 border 속성도 효과가 없다.

------

<br>

## The border-style Property

###### border-style 속성

<br>

- The default value of border-style is `none`, which defines no border.
  - border-style의 기본값은 `none`이며, border를 정의하지 않는다.
- There are various styles supported for the border-style property: `dotted`, `dashed`, `double`, etc.
  - border-style 속성에는 `dotted`, `dashed`, `double` 등 다양한 style이 지원된다.
- The example below illustrates the differences between them.
  - 아래 예제는 이들 간의 차이점을 보여준다.

<br>

- HTML:

```html
<p class="none">This paragraph has no border. </p>
<p class="dotted">This is a dotted border. </p>
<p class="dashed">This is a dashed border. </p>
<p class="double">This is a double border. </p>
<p class="groove">This is a grooved border. </p>
<p class="ridge">This is a ridged border. </p>
<p class="inset">This is an inset border. </p>
<p class="outset">This is an outset border. </p>
<p class="hidden">This is a hidden border. </p>
```

<br>

- CSS:

```css
p.none { border-style: none; }
p.dotted { border-style: dotted; }
p.dashed { border-style: dashed; }
p.double { border-style: double; }
p.groove { border-style: groove; }
p.ridge { border-style: ridge; }
p.inset { border-style: inset; }
p.outset { border-style: outset; }
p.hidden { border-style: hidden; }
```

[코드 실행 확인](https://code.sololearn.com/540/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-03-04.png)

<br>

> In CSS, it is possible to specify different borders for different sides, using the following properties: border-top-style, border-right-style, border-bottom-style, and border-left-style for the corresponding sides.
>
> CSS에서는 border-top-style, border-right-style, border-bottom-style, and border-left-style 속성을 사용해서 각 면에 서로 다른 border를 지정할 수 있다.

------

<br>

## QUIZ

- The three properties describing the border are:
  - border를 설명하는 세 가지 속성은 다음과 같다.

> [ ] `color`
>
> [ ] position
>
> [ ] `size`
>
> [ ] `style`

<br>

- Drag and drop from the options below to set the border style of the element to solid and make it 5px:
  - element의 border style을 단색으로, 5px로 설정해라.

```css
p {
   border-style: solid;
   border-width: 5px;
   border-color: #FF6600;
}
```

<br>