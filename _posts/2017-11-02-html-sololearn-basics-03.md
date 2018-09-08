---
layout: post
title: "03. Headings, 가로선, 주석 (Basics)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Headings

###### HTML headings

<br>

- HTML includes six levels of headings, which are ranked according to importance.
  - HTML은 중요도에 따라 순위가 매겨진 여섯 가지 레벨의 headings를 포함한다.

> headings: `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`

<br>

- The following code defines all of the headings:
  - 다음 코드는 모든 headings를 정의한다.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body>
      <h1>This is heading 1</h1>
      <h2>This is heading 2</h2>
      <h3>This is heading 3</h3>
      <h4>This is heading 4</h4>
      <h5>This is heading 5</h5>
      <h6>This is heading 6</h6>
   </body>
</html>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-basic-03-01.jpeg)

<br>

> It is not recommended that you use headings just to make the text big or bold, because search engines use headings to index the web page structure and content.
>
> 검색 엔진이 headings를 사용해서 웹 페이지 구조와 내용을 인덱스하기 때문에, headings를 크게 또는 굵게 만드는 것은 권장되지 않는다.

------

<br>

## Horizontal Lines

###### 가로선

<br>

- To create a horizontal line, use the `<hr/>` tag.
  - 가로선을 만들려면, `<hr/>` 태그를 사용해라.
  - `<hr/>`: Defines a horizontal line. 가로선을 정의한다.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body>
      <h1>This is heading 1</h1>
      <h2>This is heading 2</h2>
      <h3>This is heading 3</h3>
      <h4>This is heading 4</h4>
      <h5>This is heading 5</h5>
      <h6>This is heading 6</h6>
      <p>This is a paragraph</p>
      <hr/>
      <p>This is a paragraph</p>
   </body>
</html>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-basic-03-02.jpeg)

------

<br>

## Comments

###### 주석

<br>

- The browser does not display comments, but they help document the HTML and add descriptions, reminders, and other notes.
  - 브라우저는 주석을 표시하지 않지만, HTML을 문서화하는 데 도움을 준다.
  - 그리고 설명, 미리 알림, 기타 메모를 추가하는 데 도움을 준다.

```html
<!-- Your comment goes here -->
```

<br>

- Example:

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body>
      <p>This is a paragraph</p>
      <hr/>
      <p>This is a paragraph</p>
      <!-- This is a comment -->
   </body>
</html>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-basic-03-03.jpeg)

<br>

- As you can see, the comment is not displayed in the browser.
  - 보다시피, 주석은 브라우저에 표시되지 않는다.

<br>

> There is an exclamation point (!) in the opening tag, but not in the closing tag.
>
> 여는 태그에는 느낌표(!)가 있지만, 닫는 태그에는 없다.

------

<br>

## QUIZ

- What tags are used to indicate headings?
  - headings를 나타내는 데 사용되는 태그는 무엇인가?

> [ ] heading
>
> [x] `h1 - h6`
>
> [ ] header
>
> [ ] head

<br>

- How do you create a horizontal line in HTML?
  - HTML에서 가로선을 어떻게 만드는가?

> \<hr/>

<br>

- Make the text an HTML comment:
  - 텍스트를 HTML 주석으로 만들어라.

```html
<!-- This is a comment -->
```

<br>