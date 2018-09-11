---
layout: post
title: "05. HTML Element (Basics)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Element

- HTML documents are made up of HTML elements.
  - HTML 문서는 HTML element로 구성된다.
- An HTML element is written using a `start tag` and an `end tag`, and with the `content` in between.
  - HTML element는 `시작 태그`와 `종료 태그`를 사용해서, 그 사이에 `content`가 작성된다.

<br>

- HTML documents consist of nested HTML elements.
  - HTML 문서는 중첩된 HTML element로 구성된다.
- In the example below, the body element includes the \<p> tags, the \<br /> tag and the content, "This is a paragraph".
  - 아래 예제에서 body element는 \<p> 태그, \<br /> 태그, "This is a paragraph" contentfmf 포함한다.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body>
      <p>This is a paragraph <br /></p>
   </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/13/#html)

<br>

<br>

- Some elements are quite small.
  - 일부 element는 아주 작다.
- Since you can't put contents within a break tag, and you don't have an opening and closing break tag, it's a separate, single element.
  - \<br /> 태그 내에 content를 넣을 수 없고, 여는 break 태그와 닫는 break 태그가 없기 때문에, \<br /> 태그는 별도의 단일 element이다.

<br>

- So HTML is really scripting with elements within elements.
  - 그래서 HTML은 element 내의 element로 스크립팅 한다.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body>
      <p>This is a paragraph </p>
      <p>This is a <br />line break </p>
   </body>
</html>
```

[코드 실행 확인](https://code.sololearn.com/14/#html)

<br>

> Some HTML elements (like the `<br />` tag) do not have end tags.
>
> 일부 HTML element에는 종료 태그가 없다.
>
> (예: `<br />` 태그)

------

<br>

## QUIZ

- General HTML elements consist of:
  - 일반적인 HTML element는 다음과 같이 구성된다.

> `opening tag, content, closing tag`
>
> 여는 태그, content, 닫는 태그

<br>