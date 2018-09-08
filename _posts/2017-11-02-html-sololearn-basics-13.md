---
layout: post
title: "13. Inline & Block Elements (Basics)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Inline & Block Elements

###### HTML inline & block element

------

<br>

<br>

## Types of Elements

###### element 타입

<br>

- In HTML, most elements are defined as `block level` or `inline` elements.
  - HTML에서 대부분의 element는 `block level` 또는 `inline` element로 정의된다.
- Block level elements start from a new line.
  - block level element는 새 줄에서 시작한다.
- For example: `<h1>`, `<form>`, `<li>`, `<ol>`, `<ul>`, `<p>`, `<pre>`, `<table>`, `<div>`, etc.
  - `<h1>`: HTML headings (h1: the biggest, h6: the smallest)
  - `<form>`: Defines an HTML form for user input
  - `<li>`: Defines a list item
  - `<ol>`: Defines an ordered list
  - `<ul>`: Defines an unordered list
  - `<p>`: Defines a paragraph
  - `<pre>`: Defines preformatted text
  - `<table>`: Defines a table
  - `<div>`: Defines a section in a document

<br>

- Inline elements are normally displayed without line breaks.
  - inline element는 일반적으로 줄바꿈 없이 표시된다.
- For example: `<b>`, `<a>`, `<strong>`, `<img>`, `<input>`, `<em>`, `<span>`, etc.
  - `<b>`: Defines bold text
  - `<a>`: Defines a hyperlink
  - `<strong>`: Defines important text
  - `<img>`: Defines an image
  - `<input>`: Defines an input control
  - `<em>`: Defines emphasized text
  - `<span>`: 

<br>

- The `<div>` element is a block-level element that is often used as a `container for other HTML elements`.
  - `<div>` element는 `다른 HTML element의 컨테이너`로 자주 사용되는 block-level element이다.
- When used together with some CSS styling, the `<div>` element can be used to style blocks of content:
  - CSS 스타일링과 함께 사용한다면, content block의 스타일을 지정하기 위해 `<div>` element가 사용될 수 있다.

```html
<html>
   <body>
      <h1>Headline</h1>
      <div style="background-color: green; color: white; padding: 20px;">
         <p>Some paragraph text goes here.</p>
         <p>Another paragraph goes here.</p>
      </div>
   </body>
</html>
```

<br>

![sololearn img](/assets/img/sololearn-html-basics-13-01.png)

<br>

- Similarly, the `<span>` element is an inline element that is often used as a container for some text.
  - 마찬가지로, `<span>` element는 일부 텍스트의 컨테이너로 자주 사용되는 inline element이다.
- When used together with CSS, the \<span> element can be used to style `parts of the text`:
  - CSS를 함께 사용한다면, `일부 텍스트`의 스타일을 지정하기 위해 \<span> element가 사용될 수 있다.

```html
<html>
   <body>
      <h2>Some
         <span style="color: red">Important</span>
      Message</h2>
   </body>
</html>
```

<br>

![sololearn img](/assets/img/sololearn-html-basics-13-02.png)

<br>

> **Summary**
>
> The \<div> element defines a `block-level` section in a document.
>
> \<div> element는 문서에서 `block-level` 섹션을 정의한다.

> The \<span> element defines an `inline` section in a document.
>
> \<span> element는 문서에서 `inline` 섹션을 정의한다.

<br>

<br>

- Other elements can be used either as block level elements or inline elements.
  - 다른 element들은 block level element나 inline element로 사용될 수 있다.
- This includes the following elements:
  - 다른 element들에는 다음 element들이 포함된다.
  - `APPLET`: embedded Java applet
  - `IFRAME`: Inline frame
  - `INS`: inserted text
  - `MAP`: image map
  - `OBJECT`: embedded object
  - `SCRIPT`: script within an HTML document

<br>

- You can insert inline elements inside block elements.
  - block element 내에 inline element를 삽입할 수 있다.
- For example, you can have multiple `<span>` elements inside a `<div>` element.
  - 예를 들어, `<div>` element 내에 여러 `<span>` element를 가질 수 있다.

<br>

> Inline elements `cannot` contain any block level elements.
>
> inline element는 block level element를 포함할 수 없다.

------

<br>

## QUIZ

- Which of the following are block level elements?
  - 다음 중 block level element는 무엇인가?
  - Select all that apply

> [ ] `h1`
>
> [ ] em
>
> [ ] `div`
>
> [ ] b

<br>

- Can you insert a block element inside an inline element?
  - inline element 내에 block element를 삽입할 수 있는가?

> [ ] Yes
>
> [ ] `No`

<br>