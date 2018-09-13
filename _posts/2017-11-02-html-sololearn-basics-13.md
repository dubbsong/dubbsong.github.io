---
layout: post
title: "(Basics 13) inline & block element"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML inline & block element

------

<br>

<br>

## Types of Elements

###### element type

<br>

- In HTML, most elements are defined as `block level` or `inline` elements.
  - HTML에서 대부분의 element는 `block level` 또는 `inline` element로 정의된다.
- Block level elements start from a new line.
  - block level element는 새로운 줄에서 시작한다.
  - `<h1>`, `<form>`, `<li>`, `<ol>`, `<ul>`, `<p>`, `<pre>`, `<table>`, `<div>`, etc.

<br>

- Inline elements are normally displayed without line breaks.
  - inline element는 일반적으로 줄바꿈 없이 표시된다.
  - `<b>`, `<a>`, `<strong>`, `<img>`, `<input>`, `<em>`, `<span>`, etc.

<br>

- The `<div>` element is a block-level element that is often used as a `container for other HTML elements`.
  - `<div>` element는 `다른 HTML element의 컨테이너`로 자주 사용되는 block-level element이다.
- When used together with some CSS styling, the \<div> element can be used to style blocks of content:
  - CSS style과 함께 사용하면, \<div> element를 사용해서 content block style을 지정할 수 있다.

```html
<html>
   <body>
      <h1>Headline</h1>
      <div style="background-color:green; color:white; padding:20px;">
         <p>Some paragraph text goes here. </p>
         <p>Another paragraph goes here. </p>
      </div>
   </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/803/#html)

<br>

![img](/assets/img/html-sololearn-basics-13-01.png)

<br>

- Similarly, the `<span>` element is an inline element that is often used as a container for some text.
  - 마찬가지로, `<span>` element는 일부 텍스트의 컨테이너로 자주 사용되는 inline element이다.
- When used together with CSS, the \<span> element can be used to style `parts of the text`:
  - CSS와 함께 사용하면, \<span> element를 사용해서 텍스트의 style을 지정할 수 있다.

```html
<html>
   <body>
      <h2>Some
         <span style="color:red;">Important</span>
      Message</h2>
   </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/804/#html)

<br>

![img](/assets/img/html-sololearn-basics-13-02.png)

<br>

> Summary
>
> The \<div> element defines a `block-level` section in a document.
>
> \<div> element는 문서에서 `block-level` 섹션을 정의한다.

> The \<span> element defines an `inline` section in a document.
>
> \<span> element는 문서에서 `inline` 섹션을 정의한다.

<br>

<br>

- Other elements can be used deither as block level elements or inline elements.
  - 다른 element는 block level element 또는 inline element로 사용할 수 있다.
- This includes the following elements:
  - 다른 element에는 다음 element들이 포함된다.

<br>

> `APPLET`: embedded Java applet
>
> `IFRAME`: inline frame
>
> `INS`: inserted text
>
> `MAP`: image map
>
> `OBJECT`: embedded object
>
> `SCRIPT`: script within an HTML document

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
  - block level element는 다음 중 어떤 것인가?

> [ ] em
>
> [ ] b
>
> [ ] `div`
>
> [ ] `h1`

<br>

- Can you insert a block element inside an inline element?
  - inline element 내에 block element를 삽입할 수 있는가?

> `No`

<br>