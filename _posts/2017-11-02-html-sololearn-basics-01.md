---
layout: post
title: "01. HTML <p> element (Basics)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML \<p> Element

- To create a paragraph, simply type in the `\<p>` element with its opening and closing tags:
  - 단락을 만들려면, `\<p>` element에 여는 태그와 닫는 태그를 입력하기만 하면 된다.
  - `<p>`: Defines a paragraph. 단락을 정의한다.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body>
      <p>This is a paragraph.</p>
      <p>This is another paragraph.</p>
   </body>
</html>
```

<br>

- The result:

![sololearn img](/assets/img/sololearn-html-basic-01-01.jpeg)

<br>

> Browsers automatically add an empty line before and after a paragraph.
>
> 브라우저는 단락의 앞뒤에 빈 줄을 자동으로 추가한다.

------

<br>

## Single Line Break

- Use the `<br/>` tag to add a single line of text without starting a new paragraph:
  - 새 단락을 시작하지 않고, `<br/>` 태그를 사용해서 한 줄의 텍스트를 추가해라.
  - `<br/>`: Defines a single line break. 단일 줄 바꿈을 정의한다.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body>
      <p>This is a paragraph.</p>
      <p>This is another paragraph.</p>
      <p>This is <br/>a line break.</p>
   </body>
</html>
```

<br>

> The \<br/> element is an empty HTML element.
>
> \<br/> element는 빈 HTML element이다.

> It has no end tag.
>
> 끝 태그가 없다.

<br>

<br>

- Opening the HTML file in the browser shows that a single line break has been added to the paragraph:
  - 브라우저에서 HTML 파일을 열면 단일 줄 바꿈이 단락에 추가되었음을 알 수 있다.

![sololearn img](/assets/img/sololearn-html-basic-01-02.jpeg)

------

<br>

## QUIZ

- Drag and drop from the options below to create paragraphs:
  - 단락을 만들기 위해서 아래 옵션에서 드래그 앤 드랍해라.

```html
<p>HTML is easy!</p>
<p>HTML is fun!</p>
```

<br>

- What tag is used to create a line-break without an extra space between the text blocks?
  - 텍스트 블록 사이에 공간을 추가하지 않고 줄 바꿈을 만들 때 사용되는 태그는 무엇인가?

> [x] `br`
>
> [ ] linebreak
>
> [ ] break
>
> [ ] lb

<br>

- Fill in the blanks:
  - 빈칸을 채워라.

```html
<html>
   <body>
      <p>This is a paragraph</p>
      <p>This is <br/>a line break</p>
   </body>
</html>
```

<br>