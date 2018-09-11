---
layout: post
title: "(Basics 06) HTML 속성"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Attributes

###### HTML 속성

<br>

- Attributes provide `additional information` about an element or a tag, while also `modifying` them.
  - 속성은 element나 태그에 대한 `추가 정보`를 제공하는 동시에, element나 태그를 `수정`한다.
- Most attributes have a value; the value modifies the attribute.
  - 대부분의 속성은 값을 가진다.
  - 값은 속성을 수정한다.

```html
<p align="center">
   이 텍스트는 가운데 정렬된다.
</p>
```

[코드 실행 확인](https://code.sololearn.com/15/#html)

<br>

- In this example, the value of "center" indicates that the content within the p element should be aligned to the center:
  - 이 예제에서 "center" 값은 p element 내의 content가 가운데에 정렬되어야 함을 나타낸다.

![img](/assets/img/html-sololearn-html basics-06-01.jpeg)

<br>

> Attributes are always specified in the start tag, and they appear in name="value" pairs.
>
> 속성은 항상 시작 태그에 지정되며, name="value" 쌍으로 나타낸다.

------

<br>

## Attribute Measurements

###### 측정 속성

<br>

- As an example, we can modify the horizontal line so it has a width of 50 pixels.
  - 예를 들어, 가로줄을 50 픽셀 너비로 수정할 수 있다.

<br>

- This can be done by using the width attribute:
  - 너비 속성을 사용해서 이 작업을 수행할 수 있다.

```html
<hr width="50px" />
```

[코드 실행 확인](https://code.sololearn.com/16/#html)

<br>

- An element's width can also be defined using percentages:
  - element의 너비는 백분율을 사용해서 정의할 수도 있다.

```html
<hr width="50%" />
```

[코드 실행 확인](https://code.sololearn.com/17/#html)

------

<br>

## The Align Attribute

###### 정렬 속성

<br>

- The `align` attribute is used to specify how the text is aligned.
  - `align` 속성은 텍스트를 어떻게 정렬할지 지정하는 데 사용된다.

<br>

- In the example below, we have a paragraph that is aligned to the center, and a line that is aligned to the right.
  - 아래 예제에는 가운데에 정렬된 토막글과, 오른쪽에 정렬된 가로줄이 있다.

```html
<html>
   <head>
      <title>Attributes</title>
   </head>
   <body>
      <p align="center">This is a text <br />
         <hr width="10%" align="right" /> This is also a text
      </p>
   </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/18/#html)

<br>

> The align attribute of \<p> is not supported in HTML5.
>
> \<p>의 align 속성은 HTML5에서 지원되지 않는다.

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

[코드 실행 확인](https://code.sololearn.com/19/#html)

<br>

![img](/assets/img/html-sololearn-html basics-06-02.png)

<br>

> The align attribute of \<p> is not supported in HTML5.
>
> \<p>의 align 속성은 HTML5에서 지원되지 않는다.

------

<br>

## QUIZ

- What is the role of an attribute in HTML?
  - HTML에서 속성의 역할은 무엇인가?

> `it modifies the tag`
>
> 태그를 수정한다

<br>

- What measurement units can be used for the width attribute?
  - 너비 속성에는 어떤 측정 단위를 사용할 수 있는가?

> `pixel & %`

<br>

- What attribute is used to align the contents of an element to the right, center or left?
  - element의 content를 오른쪽, 가운데, 왼쪽으로 정렬하는 데 사용되는 속성은 무엇인가?

> `align`

<br>

- Which attribute is used to align the content of a paragraph to the right?
  - 토막글의 content를 오른쪽 정렬하는 데 사용하는 속성은 무엇인가?

> `<p align="right">`

<br>