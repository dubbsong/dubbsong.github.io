---
layout: post
title: "SoloLearn 번역 - 02. Inline, Embedded, External CSS (The Basics)"
categories: dev
tags: css
---

## Inline CSS (Inline 스타일)

- Using an inline style is one of the ways to insert a style sheet.
  - inline 스타일을 사용하는 것은 스타일 시트를 삽입하는 방법 중 하나이다.
- With an inline style, a unique style is applied to a single element.
  - inline 스타일에서는, 고유한 스타일이 단일 element에 적용된다.

<br>

- In order to use an inline style, add the **style attribute** to the **relevant tag**.
  - inline 스타일을 사용하려면, **관련 태그**에 **스타일 속성**을 추가해라.

<br>

- The example below shows how to create a paragraph with a gray background and white text:
  - 아래 예제는 회색 배경과 흰색 텍스트로 단락을 만드는 방법을 보여준다.

```html
<p style="color:white; background-color:gray;">
   This is an example of inline styling.
</p>
```

<br>

- Result:

![SoloLearn img](/assets/img/sololearn-css-the basics-02-01.png)

------

<br>

## Embedded/Internal CSS (Embedded/Internal 스타일)

- Internal styles are defined within the **\<style>** element, inside the **head** section of an HTML page.
  - 내부 스타일은 HTML 페이지의 **head** 섹션 안에 있는 **\<style>** element 내에 정의된다.

<br>

- For example, the following code styles **all** paragraphs:
  - 예를 들어, 다음 코드는 **모든** 단락의 스타일을 지정한다.

```html
<html>
   <head>
      <style>
         p {
            color: white;
            background-color: gray;
         }
      </style>
   </head>
   <body>
      <p>This is my first paragraph.</p>
      <p>This is my second paragraph.</p>
   </body>
</html>
```

<br>

- All paragraphs have a white font and a gray background:
  - 모든 단락에는 흰색 글꼴과 회색 배경이 있다.

![SoloLearn img](/assets/img/sololearn-css-the basics-02-02.png)

------

<br>

## External CSS (External 스타일)

- With this method, all styling rules are contained in a single text file, which is saved with the **.css** extension.
  - 이 방법을 사용하면, 모든 스타일링 규칙이 **.css** 확장명으로 저장되는 단일 텍스트 파일에 포함된다.

<br>

- This CSS file is then referenced in the HTML using the **\<link>** tag.
  - CSS 파일은 **\<link>** 태그를 사용하여 HTML에서 참조된다.
- The \<link> element goes inside the head section.
  - \<link> element는 head 섹션 안에 들어간다.

<br>

#### Here is an example:

- The HTML:

```html
<head>
   <link rel="stylesheet" href="example.css">
</head>
<body>
   <p>This is my first paragraph.</p>
   <p>This is my second paragraph.</p>
   <p>This is my third paragraph.</p>
</body>
```

<br>

- The CSS:

```css
p {
   color: white;
   background-color: gray;
}
```

<br>

- Result:

![SoloLearn img](/assets/img/sololearn-the basics-02-03.png)

<br>

> Both relative and absolute paths can be used to define the **href** for the CSS file.
>
> 상대적 경로와 절대적 경로를 모두 사용해서 CSS 파일의 **href**를 정의할 수 있다.

> In our example, the path is relative, as the CSS file is in the same directory as the HTML file.
>
> 예제에서, CSS 파일은 HTML 파일과 동일한 디렉토리에 있으므로, 경로는 상대적이다.

------

<br>

## QUIZ

- Select the attribute that organizes the inline styling:
  - **style**
  - class
  - id

<br>

- Where should the style tag be declared to organize an internal CSS?
  - **head**
  - external file
  - body

<br>

- Fill in the blanks to call an external stylesheet called "test.css":

```html
<head>
   <link rel="stylesheet" href="test.css">
</head>
```

<br>