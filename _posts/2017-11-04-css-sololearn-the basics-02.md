---
layout: post
title: "02. inline, embedded, external CSS (The Basics)"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# inline, embedded, external CSS

------

<br>

<br>

## Inline CSS

- Using an inline style is one of the ways to insert a style sheet.
  - inline style을 사용하는 것은 style sheet를 삽입하는 방법 중 하나이다.
- With an inline style, a unique style is applied to a single element.
  - inline style에서는, 고유한 style이 하나의 element에 적용된다.

<br>

- In order to use an inline style, add the `style attribute` to the `relevant tag`.
  - inline style을 사용하려면, `관련 태그`에 `style 속성`을 추가해라.

<br>

- The example below shows how to create a paragraph with a gray background and white text:
  - 아래 예제에서는 회색 배경과 흰색 텍스트로 토막글을 어떻게 만드는지를 보여준다.

```html
<p style="color:white; background-color:gray;">
   This is an example of inline styling.
</p>
```

<br>

- Result:

![img](/assets/img/css-sololearn-the basics-02-01.png)

<br>

> The style attribute can contain any CSS property.
>
> style 속성은 모든 CSS 속성을 포함할 수 있다.

------

<br>

## Embedded/Internal CSS

- Internal styles are defined within the `<style>` element, inside the `head` section of an HTML page.
  - internal style은 HTML 페이지의 `head` 섹션 내 `<style>` element에서 정의된다.

<br>

- For example, the following code styles `all` paragraphs:
  - 에를 들어, 다음 코드는 `모든` 토막글의 style을 지정한다.

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
      <p>This is my first paragraph. </p>
      <p>This is my second paragraph. </p>
   </body>
</html>
```

<br>

- All paragraphs have a white font and a gray background:
  - 모든 토막글은 흰색 글꼴과 회색 배경을 가진다.

![img](/assets/img/css-sololearn-the basics-02-02.png)

<br>

> An internal style sheet may be used if one single page has a unique style.
>
> 하나의 단일 페이지에 고유한 style이 있는 경우, internal style이 사용될 수 있다.

------

<br>

## External CSS

- With this method, all styling rules are contained in a single text file, which is saved with the `.css` extension.
  - 이 방법을 사용하면, 모든 style 규칙이 `.css` 확장자로 저장되는 단일 텍스트 파일에 포함된다.

<br>

- This CSS file is then referenced in the HTML using the `<link>` tag.
  - 이 CSS 파일은 `<link>` 태그를 사용해 HTML에서 참조된다.
- The \<link> element goes inside the head section.
  - \<link> element는 head 섹션 내에 있다.

<br>

- The HTML:

```html
<head>
   <link rel="stylesheet" href="example.css">
</head>
<body>
   <p>This is my first paragraph. </p>
   <p>This is my second paragraph. </p>
   <p>This is my third paragraph. </p>
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

[코드 실행 확인](https://code.sololearn.com/502/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-the basics-02-03.png)

<br>

> Both relative and absolute paths can be used to define the `href` for the CSS file.
>
> 상대 경로와 절대 경로를 모두 사용해 CSS 파일의 `href`를 정의할 수 있다.

> In our example, the path is relative, as the CSS file is in the same directory as the HTML file.
>
> 이 예제에서, CSS 파일은 HTML 파일과 동일한 디렉토리에 있으므로, 경로가 상대적이다.

------

<br>

## QUIZ

- Select the attribute that organizes the inline styling:
  - inline style을 구성하는 속성을 선택해라.

> `style`

<br>

- Where should the style tag be declared to organize an internal CSS?
  - internal CSS를 구성하기 위해 style 태그를 선언해야 하는 위치는 어디인가?

> `head`

<br>

- Fill in the blanks to call an external stylesheet called "test.css":
  - "test.css"라는 external style sheet를 호출해라.

```html
<head>
   <link rel="stylesheet" href="test.css"
</head>
```

<br>