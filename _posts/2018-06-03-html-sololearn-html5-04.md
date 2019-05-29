---
layout: post
title: "(HTML5 04) header, nav, footer"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 header, nav, footer

------

<br>

<br>

## The \<header> Element

- In HTML4, we would define a header like this:
  - HTML4에서는 다음과 같이 header를 정의했다.

```html
<div id="header">
```

<br>

- In HTML5, a simple `<header>` tag is used, instead.
  - HTML5에서는 간단한 `<header>` 태그가 대신 사용된다.

<br>

- The \<header> element is appropriate for use inside the body tag.
  - \<header> element는 body 태그 내에서 사용하기에 적합하다.

```html

```

[코드 실행 확인](https://code.sololearn.com/35/#html)

<br>

![img](/assets/img/html-sololearn-html5-04-01.png)

<br>

> Note that the \<header> is completely different from the \<head> tag.
>
> \<header>는 \<head> 태그와 전혀 다르다는 것에 주의해라.

------

<br>

## The \<footer> Element

- The footer element is also widely used.
  - footer element도 널리 사용된다.
- Generally we refer to a section located at the very bottom of the webpage as the footer.
  - 일반적으로 웹페이지 맨 아래 있는 섹션을 footer라고 한다.

```html
<footer>...</footer>
```

<br>

> The following information is usually provided between these tags:
>
> 일반적으로 footer 태그 사이에 다음 정보가 제공된다.

> Contact Information(연락처 정보)
>
> Privacy Policy(개인 정보 정책)
>
> Social Media Icons(소셜 미디어 아이콘)
>
> Terms of Service(서비스 약관)
>
> Copyright Information(저작권 정보)
>
> Sitemap and Related Documents(사이트맵 및 관련 문서)

------

<br>

## The \<nav> Element

- This tag represents a section of a page that links to other pages or to certain sections within the page.
  - 이 태그는 다른 페이지 또는 특정 섹션에 링크되는 페이지를 나타낸다.
- This would be a section with navigation links.
  - 이는 네비게이션 링크가 있는 섹션이다.

<br>

- Here is an example of a major block of navigation links:
  - 다음은 네비게이션 링크의 주요 블록 예이다.

```html
<nav>
   <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">Services</a></li>
      <li><a href="#">About us</a></li>
   </ul>
</nav>
```

[코드 실행 확인](https://code.sololearn.com/36/#html)

<br>

![img](/assets/img/html-sololearn-html5-04-02.png)

<br>

> Not all of the links in a document should be inside a \<nav> element.
>
> 문서의 모든 링크가 \<nav> element 내에 있어야 하는 것은 아니다.

> The \<nav> element is intended only for major blocks of navigation links.
>
> \<nav> element는 네비게이션 링크의 주요 블록에만 사용된다.

> Typically, the \<footer> element often has a list of links that don't need to be in a \<nav> element.
>
> 일반적으로 \<footer> element에는 \<nav> element에 있을 필요가 없는 링크 list가 있다.

------

<br>

## QUIZ

- The header element is appropriate to use...
  - header element는 … 사용하기에 적합하다.

> `...inside of the body tag`
>
> body 태그 내에서

<br>

- Which tag specifies the footer element?
  - footer element를 지정하는 태그는 무엇인가?

> `<footer>`

<br>

- Rearrange the sections to create a generic HTML5 page structure:
  - 아래 코드를 재정렬해서 일반적인 HTML5 페이지 구조를 생성해라.

> \<head>
>
> \<header>
>
> \<nav>
>
> \<footer>

<br>