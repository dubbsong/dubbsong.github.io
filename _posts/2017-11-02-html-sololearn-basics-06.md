---
layout: post
title: "06. 속성 (Basics)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Attributes

###### HTML 속성

<br>

- Attributes provide `additional information` about an element or a tag, while also `modifying` them.
  - 속성은 element 또는 태그에 대해 `추가 정보`를 제공하는 동시에, `수정`한다.
- Most attributes have a value; the value modifies the attribute.
  - 대부분의 속성에는 값이 있다.
  - 값은 속성을 수정한다.

```html
<p align="center">
   This text is aligned to center
</p>
```

<br>

- In this example, the value of "center" indicates that the content within the p element should be aligned to the center:
  - 이 예제에서, "center" 값은 p element 내의 내용이 가운데에 정렬되어야 함을 나타낸다.

![sololearn img](/assets/img/sololearn-html-basics-06-01.jpeg)

<br>

> Attributes are always specified in the start tag, and they appear in name="value" pairs.
>
> 속성은 항상 시작 태그에 지정되고, name="value" 쌍으로 나타낸다.

------

<br>

## Attribute Measurements

###### 측정 속성

<br>

- As an example, we can modify the horizontal line so it has a width of 50 pixels.
  - 예를 들어, 가로선을 50 픽셀 width로 수정할 수 있다.

<br>

- This can be done by using the width attribute:
  - width 속성을 사용해서 이것이 수행될 수 있다.

```html
<hr width="50px" />
```

<br>

- An element's width can also be defined using percentages:
  - element의 width는 백분율을 사용해서 정의할 수도 있다.

```html
<hr width="50%" />
```

------

<br>

## The Align Attribute

###### 정렬 속성

<br>

- The `align` attribute is used to specify how the text is aligned.
  - `align` 속성은 텍스트를 어떻게 정렬하는지 지정하는 데 사용된다.

<br>

- In the example below, we have a paragraph that is aligned to the center, and a line that is aligned to the right.
  - 아래 예제에서는, 가운데에 정렬된 단락과 오른쪽에 정렬된 단락이 있다.

```html
<html>
   <head>
      <title>Attributes</title>
   </head>
   <body>
      <p align="center">This is a text <br/>
         <hr width="10%" align="right" /> This is also a text.
      </p>
   </body>
</html>
```

------

<br>

## Attributes

###### 속성

<br>

- You may be wondering what happens if you try to apply contradictory attributes within the same element.
  - 동일한 element 내에서 상반되는 속성을 적용하려고 하면 어떤 일이 발생하는지 궁금할 것이다.

```html
<p align="center">
   This is a text.
   <hr width="50%" align="left" />
</p>
```

<br>

![sololearn img](/assets/img/sololearn-html-basics-06-02.png)

------

<br>

## QUIZ

- What is the role of an attribute in HTML?
  - HTML에서 속성의 역할은 무엇인가?

> [x] `it modifies the tag`
>
> [ ] the tag cannot have attributes
>
> [ ] it serves just as a comment

<br>

- What measurement units can be used for the width attribute?
  - width 속성에는 어떤 측정 단위를 사용할 수 있는가?

> [ ] no measurement units are used
>
> [ ] km and meter
>
> [x] `pixel and %`
>
> [ ] all existing measurement units

<br>

- What attribute is used to align the contents of an element to the right, center or left?
  - element의 내용을 오른쪽, 가운데, 왼쪽으로 정렬하는 데 사용되는 속성은 무엇인가?

> [x] `align`
>
> [ ] alignment
>
> [ ] location
>
> [ ] direction

<br>

- Which attribute is used to align the content of a paragraph to the right?
  - 어떤 속성을 사용해서 단락의 내용을 오른쪽으로 정렬하는가?

> \<p align="right">

<br>