---
layout: post
title: "03. HTML 페이지 생성하기 (Overview)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# Creating HTML Page

###### HTML 페이지 생성하기

------

<br>

<br>

## The HTML File

###### HTML 파일

<br>

- HTML files are text files, so you can use any `text editor` to create your first webpage.
  - HTML 파일은 텍스트 파일이므로, 아무 `텍스트 에디터`를 사용해서 첫 웹페이지를 만들 수 있다.
- There are some very nice HTML editors available; you can choose the one that works for you.
  - 아무 멋진 HTML 에디터를 고를 수 있다.
- For now let's write our examples in `Notepad`.
  - 이제 예제를 `메모장`에 작성해보자.

![sololearn img](/assets/img/sololearn-html-overview-03-01.jpeg)

<br>

<br>

- Add the basic HTML structure to the text editor with "This is a line of text" in the body section.
  - 텍스트 에디터를 사용해서 기본 HTML 구조와, body 섹션에 "This is a line of text"를 추가해라.

```html
<html>
   <head>
   </head>
   <body>
      This is a line of text.
   </body>
</html>
```

<br>

> Don't forget to save the file.
>
> 파일을 저장하는 것을 잊지 마라.

> HTML file names should end in either `.html` or `.htm`
>
> HTML 파일 이름은 `.html` 또는 `.htm`으로 끝나야 한다.

<br>

- In our example, the file is saved as `first.html`.
  - 이 예제에서는 파일이 `first.html`로 저장된다.
- When the file is opened, the following result is displayed in the web browser.
  - 파일을 열면, 다음 결과가 웹 브라우저에 표시된다.

![sololearn img](/assets/img/sololearn-html-overview-03-02.jpeg)

------

<br>

## The \<title> Tag

- To place a title on the tab describing the web page, add a `<title>` element to your head section:
  - 웹페이지를 설명하는 탭에 타이틀을 배치하려면, head 섹션에 `<title>` element를 추가해라.
  - `<title>`: Defines a title for the document. 문서의 제목을 정의한다.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body>
      This is a line of text.
   </body>
</html>
```

<br>

- This will produce the following result:
  - 위 코드는 다음과 같은 결과를 나타낸다.

![sololearn img](/assets/img/sololearn-html-overview-03-03.jpeg)

<br>

> The title element is important because it describes the page and is used by search engines.
>
> title element는 페이지를 설명하고 검색 엔진에서 사용되기 때문에 중요하다.

------

<br>

## QUIZ

- What type of editor is used to edit HTML code?
  - HTML 코드를 편집하는 데 사용되는 에디터의 타입은 무엇인가?

> text editor

<br>

- What is the correct extension for HTML files?
  - HTML 파일의 올바른 확장명은 무엇인가?

> [ ] .css
>
> [ ] .txt
>
> [ ] .exe
>
> [x] `.html`

<br>

- Where should you put the title tag?
  - title 태그는 어디에 놓아야 하는가?

> [x] `Between the head tags`
>
> [ ] Between the body tags
>
> [ ] Before the html tag
>
> [ ] After the closing html tag

<br>