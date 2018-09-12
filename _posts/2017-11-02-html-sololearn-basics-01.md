---
layout: post
title: "(Basics 01) 토막글(paragraph)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Paragraphs

###### 토막글

------

<br>

<br>

## The \<p> Element

###### \<p> element

<br>

- To create a paragraph, simply type in the \<p> element with its opening and closing tags:
  - 토막글을 만들려면, \<p> element에 여는 태그와 닫는 태그를 입력하면 된다.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body>
      <p>This is a paragraph. </p>
      <p>This is another paragraph. </p>
   </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/7/#html)

<br>

- The result:

![img](/assets/img/html-sololearn-basics-01-01.jpeg)

<br>

> Browsers automatically add an empty line before and after a paragraph.
>
> 브라우저는 토막글 앞뒤에 빈 줄을 자동으로 추가한다.

------

<br>

## Single Line Break

###### 줄 바꿈

<br>

- Use the \<br /> tag to add a single line of text without starting a new paragraph:
  - 새 토막글을 시작하지 않고, \<br /> 태그를 사용해서 새 줄 텍스트를 추가해라.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body>
      <p>This is a paragraph. </p>
      <p>This is another paragraph. </p>
      <p>This is <br /> a line break </p>
   </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/8/#html)

<br>

> The \<br /> element is an empty HTML element.
>
> \<br /> element는 빈 HTML element이다.

> It has no end tag.
>
> \<br />은 닫는 태그가 없다.

<br>

<br>

- Opening the HTML file in the browser shows that a single line break has been added to the paragraph:
  - 브라우저에서 HTML 파일을 열면, 줄 바꿈이 토막글에 추가되었음을 알 수 있다.

![img](/assets/img/html-sololearn-basics-01-02.jpeg)

<br>

> The \<br /> element has no end tag.
>
> \<br /> element는 닫는 태그가 없다.

------

<br>

## QUIZ

- Drag and drop from the options below to create paragraphs:
  - 토막글을 생성해라.

```html
<p>HTML is easy. </p>
<p>HTML is fun. </p>
```

<br>

- What tag is used to create a line-break without an extra space between the text blocks?
  - 텍스트 블록 간에 공간을 추가하지 않고 줄 바꿈할 때 사용되는 태그는 무엇인가?

> `br`

<br>