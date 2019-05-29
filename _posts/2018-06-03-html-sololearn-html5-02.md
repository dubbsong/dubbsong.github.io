---
layout: post
title: "(HTML5 02) Content 모델"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 Content Models

###### HTML5 content 모델

<br>

- In HTML, elements typically belonged in either the block level or inline content model.
  - HTML에서 element는 일반적으로 block lever 또는 inline content 모델에 속한다.
- HTML5 introduces `seven` main content models.
  - HTML5는 7가지 주요 content 모델을 소개한다.

<br>

1. Metadata
2. Embedded
3. Interactive
4. Heading
5. Phrasing
6. Flow
7. Sectioning

<br>

> The HTML5 content models are designed to make the markup structure more meaningful for both the browser and the web designer.
>
> HTML5 content 모델은 브라우저와 웹 디자인 모두에게 마크업 구조를 더 의미 있게 디자인한다.

<br>

#### Metadata:

- Content that sets up the presentation or behavior of the rest of the content.
  - content의 나머지 부분의 표현이나 동작을 설정하는 content이다.
- These elements are found in the `head` of the document.
  - 이러한 element는 문서의 `head` 부분에서 찾을 수 있다.
- Elements: `<base>`, `<link>`, `<meta>`, `<noscript>`, `<script>`, `<style>`, `<title>`

<br>

#### Embedded:

- Content that imports other resources into the document.
  - 다른 resource를 문서로 가져오는 content이다.
- Elements: `<audio>`, `<video>`, `<canvas>`, `<iframe>`, `<img>`, `<math>`, `<object>`, `<svg>`

<br>

#### Interactive:

- Content specifically intended for user interaction.
  - 특히 사용자 상호작용을 위한 content이다.
- Elements: `<a>`, `<audio>`, `<video>`, `<button>`, `<details>`, `<embed>`, `<iframe>`, `<img>`, `<input>`, `<label>`, `<object>`, `<select>`, `<textarea>`

<br>

#### Heading:

- Defines a section header.
  - header 섹션을 정의한다.
- Elements: `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`, `<hgroup>`

<br>

#### Phrasing:

- This model has a number of inline level elements in common with HTML4.
  - 이 모델에는 HTML4와 관련된 여러 inline level element가 있다.
- Elements: `<img>`, `<span>`, `<strong>`, `<label>`, `<br />`, `<small>`, `<sub>`

<br>

> The same element can belong to more than one content model.
>
> 동일한 element는 둘 이상의 content 모델에 속할 수 있다.

<br>

#### Flow content:

- Contains the majority of HTML5 elements that would be included in the normal flow of the document.
  - 문서의 일반적인 흐름에 포함될 HTML5 element의 대부분을 포함한다.

<br>

#### Sectioning content:

- Defines the scope of headings, content, navigation, and footers.
  - 제목, content, 네비게이션, footer의 범위를 정의한다.
- Elements: `<article>`, `<aside>`, `<nav>`, `<section>`

<br>

![img](/assets/img/html-sololearn-html5-02-01.jpeg)

<br>

> The various content models overlap in certain areas, depending on how they are being used.
>
> 다양한 content 모델은 사용 방법에 따라 특정 영역에서 겹친다.

------

<br>

## QUIZ

- How many content models does HTML5 offer?
  - HTML5는 몇 개의 content 모델을 제공하는가?

> `7`

<br>

- Where is the metadata located in an HTML5 document?
  - metadata는 HTML5 문서의 어디에 있는가?

> `head`

<br>

- Which content model contains almost all of the others?
  - 거의 다른 모든 것을 포함하는 content 모델은 무엇인가?

> `Flow`

<br>