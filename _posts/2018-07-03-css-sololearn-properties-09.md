---
layout: post
title: "(Properties 09) Styling the Lists"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Styling the Lists

------

<br>

<br>

## The list-style-type Property

###### list-style-type 속성

<br>

- The CSS list properties allow us to set different list item markers.
  - CSS list 속성을 사용해서 다른 list item marker를 설정할 수 있다.
- In HTML, there are two types of lists.
  - HTML에는 두 가지 type의 list가 있다.

<br>

- `unordered lists <ul>`: the list items are marked with bullets
  - list item이 글 머리 기호로 표시된다.
- `ordered lists <ol>`: the list items are marked with numbers or letters
  - list item이 숫나자 문자로 표시된다.

<br>

- With CSS, lists can be styled further, and images can be used as the list item marker.
  - CSS를 사용하면 list를 더 styling하게, 이미지를 list item marker로 사용할 수 있다.
- One of the ways is to use the `list-style-type` property, which can be set to `circle`, `square`, `decimal`, `disc`, `lower-alpha`, etc.
  - 한 가지 방법은, `circle`, `square`, `decimal`, `disc`, `lower-alpha` 등으로 설정할 수 있는 `list-style-type` 속성을 사용하는 것이다.

<br>

- HTML:

```html
<ol class="lower-alpha">
   <li>Red</li>
   <li>Green</li>
   <li>Blue</li>
</ol>
<ul class="circle">
   <li>Red</li>
   <li>Green</li>
   <li>Blue</li>
</ul>
<ul class="square">
   <li>Red</li>
   <li>Green</li>
   <li>Blue</li>
</ul>
```

<br>

- CSS:

```css
ol.lower-alpha {
   list-style-type: lower-alpha;
}

ul.circle {
   list-style-type: circle;
}

ul.square {
   list-style-type: square;
}
```

[코드 실행 확인](https://code.sololearn.com/553/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-09-01.png)

<br>

> Some of the values are for unordered lists, and some for ordered lists.
>
> 값 중 일부는 unordered(정렬되지 않은) list에 대한 값이고, 일부는 ordered(정렬된) list에 대한 값이다.

------

<br>

## The List Image and Position

###### list 이미지 & 위치

<br>

- There are also other list properties, such as:
  - 다음과 같은 다른 list 속성도 있다.

<br>

- `list-style-image`: specifies an image to be used as the list item marker.
  - list item marker로 사용할 이미지를 지정한다.
- `list-style-position`: specifies the position of the marker box (inside, outside).
  - marker 상자의 위치를 지정한다.

<br>

- In the example below, we use an image as the list item marker, and specify the position to be inside of the content flow.
  - 아래 예제에서는 이미지를 list item marker로 사용하고, content flow 내에 위치를 지정한다.

<br>

- HTML:

```html
<p>The following list has list-style-position: <strong>inside</strong>.</p>

<ul>
   <li>Red</li>
   <li>Green</li>
   <li>Blue</li>
</ul>
```

<br>

- CSS:

```css
ul {
   list-style-image: url("logo.jpg");
   list-style-position: inside;
}
```

[코드 실행 확인](https://code.sololearn.com/554/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-09-02.png)

<br>

> "list-style-position: `outside`" is the default value.
>
> "list-style-position: `outside`"가 기본값이다.

------

<br>

## The list-style Property

###### list-style 속성

<br>

- The `list-style` property is a shorthand property for setting list-style-type, list-style-image and list-style-position.
  - `list-style` 속성은 list-style-type, list-style-image, list-style-position을 설정하기 위한 shorthand(속기, 약칭) 속성이다.
- It is used to set all of the list properties in one declaration:
  - 하나의 선언에서 모든 list 속성을 설정하는 데 사용된다.

```html
ul {
list-style: square outside none;
}
```

<br>

- This would be the same as the longhand version.
  - 이는 longhand(일반) 버전과 동일하다.

```html
ul {
list-style-type: square;
list-style-position: outside;
list-style-image: none;
}
```

[코드 실행 확인](https://code.sololearn.com/555/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-09-03.png)

<br>

> If one of the property values are missing, the default value for the missing property will be inserted, if any.
>
> 속성 중 하나가 누락된 경우, 누락된 속성에 기본값이 삽입된다.

------

<br>

## QUIZ

- list-style-type applies to:
  - list-style-type은 …에 적용된다.

> `the bullets or numberings of the list`
>
> list의 글 머리 기호 또는 번호 매기기에

<br>

- Which keyword is used to specify the image location address for the list-style-image property?
  - list-style-image 속성에 대한 이미지 위치 주소를 지정하는 데 사용되는 키워드는 무엇인가?

> `url`

<br>