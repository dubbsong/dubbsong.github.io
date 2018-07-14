---
layout: post
title: "SoloLearn HTML 번역 - 02. Content Models (HTML5)"
categories: dev
tags: html
---

## The List of Content Models

###### content model 리스트

<br>

- In HTML, elements typically belonged in either the block level or inline content model.
  - HTML에서 element는 일반적으로 block level 또는 inline content model에 속한다.
- HTML5 introduces `seven` main content models.
  - HTML5는 `7가지` 주요 content model을 소개한다.

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
> HTML5 content model은 브라우저와 웹 디자이너 모두에게 마크업 구조를 보다 의미있게 만들어준다.

------

<br>

## Content Models

#### Metadata:

- Content that sets up the presentation or behavior of the rest of the content.
  - content 나머지 부분의 표현이나 동작을 설정하는 content이다.
- These elements are found in the `head` of the document.
  - 이 element들은 문서의 `head`에 있다.
- Elements:
  - `<base>`: Specifies the base URL/target for all relative URLs in a document
  - `<link>`: Defines the relationship between a document and an exteranl resouce (most used to link to style sheets)
  - `<meta>`: Defines metadata for an HTML document
  - `<noscript>`: Defines an alternate content for users that do not support client-side scripts
  - `<script>`: Defines a client-side script
  - `<style>`: Defines style information for a document
  - `<title>`: Defines a title for the document

<br>

#### Embedded:

- Content that imports other resouces into the document.
  - 다른 리소스를 문서로 가져오는 content이다.
- Elements:
  - `<audio>`: Defines sound content
  - `<video>`: Defines video content
  - `<canvas>`: Used to draw graphics, on the fly, via scripting (usually JavaScript)
  - `<iframe>`: Defines an inline frame
  - `<img>`: Defines an image
  - `<math>`: 
  - `<object>`: Defines an embedded object
  - `<svg>`: Container for SVG graphics

<br>

#### Interactive:

- Content specifically intended for user interaction.
  - 특히 사용자 상호 작용을 위한 content이다.
- Elements:
  - `<a>`: Defines a hyperlink
  - `<audio>`: Defines sound content
  - `<video>`: Defines video content
  - `<button>`: Defines a clickable button
  - `<details>`: 
  - `<embed>`: Defines a container for an external (non-HTML) application
  - `<iframe>`: Defines an inline frame
  - `<img>`: Defines an image
  - `<input>`: Defines an input control
  - `<label>`: Defines a label for an \<input> element
  - `<object>`: Defines an embedded object
  - `<select>`: Defines a drop-down list
  - `<textarea>`: Defines a multiline input control (text area)

<br>

#### Heading:

- Defines a section header.
  - 섹션 header를 정의한다.
- Elements:
  - `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`, `<hgroup>`

<br>

#### Phrasing:

- This model has a number of inline level elements in common with HTML4.
  - 이 model에는 HTML4와 공통인 inline level element가 많이 있다.
- Elements:
  - `<img>`: Defines an image
  - `<span>`:
  - `<strong>`: Defines important text
  - `<label>`: Defines a label for an \<input> element
  - `<br />`: Defines a single line break
  - `<small>`: Defines smaller text
  - `<sub>`: Defines subscripted text

<br>

> The same element can belong to more than one content model.
>
> 동일한 element는 둘 이상의 content model에 속할 수 있다.

------

<br>

# Content Models 02

#### Flow content:

- Contains the majority of HTML5 elements that would be included in the normal flow of the document.
  - 문서의 정상적인 흐름에 포함되는 대부분의 HTML5 element를 포함한다.

<br>

#### Sectioning content:

- Defines the scope of headings, content, navigation, and footers.
  - heading, content, navigation, footer의 범위를 정의한다.
- Elements:
  - `<article>`: Defines an article
  - `<aside>`: Defines content aside from the page content
  - `<nav>`: Defines navigation section
  - `<section>`: Defines a section in a document

![sololearn img](/assets/img/sololearn-html-html5-02-01.jpeg)

<br>

> The various content models overlap in certain areas, depending on how they are being used.
>
> 다양한 content model은 사용 방법에 따라 특정 영역에서 겹친다.

------

<br>

## QUIZ

- How many content models does HTML5 offer?
  - HTML5는 몇 개의 content model을 제공하는가?

> 7

<br>

- Where is the metadata located in an HTML5 document?
  - 메타데이터는 HTML5문서 어디에 있는가?

> [ ] paragraph
>
> [ ] body
>
> [ ] link
>
> [x] `head`

<br>

- Which content model contains almost all of the others?
  - 어떤 것이 거의 모든 content model을 포함하고 있는가?

> [x] `Flow`
>
> [ ] Metadata
>
> [ ] Heading
>
> [ ] Interactive

<br>