---
layout: post
title: "(HTML5 05) article, section, aside"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 article, section, aside

------

<br>

<br>

## The \<article> Element

- `Article` is a self-contained, independent piece of content that can be used and distributed separately from the rest of the page or site.
  - `article`은 자족적이고, 독립적인 content이다.
  - 페이지 또는 사이트의 나머지 부분과 별도로 사용 및 배포할 수 있다.
- This could be a forum post, a magazine or newspaper article, a blog entry, a comment, an interactive widget or gadget, or any other independent piece of content.
  - forum 게시물, 잡지 또는 신문 기사, 블로그 항목, 댓글, 상호 작용 위젯 또는 가젯, 또는 다른 독립적인 content 일 수 있다.

<br>

- The \<article> element replaces the \<div> element that was widely used in HTML4, along with an id or class.
  - \<article> element는 HTML4에서 널리 사용된 \<div> element를 id 또는 class와 함께 대체한다.

```html
<article>
   <h1>The article title </h1>
   <p>Contents of the article element </p>
</article>
```

[코드 실행 확인](https://code.sololearn.com/37/#html)

<br>

> When an \<article> element is nested, the inner element represents an article related to the outer element.
>
> \<article> element가 중첩된 경우, 내부 element는 외부 element와 관련된 article을 나타낸다.

> For example, blog post comments can be \<article> elements nested in the \<article> representing the blog post.
>
> 예를 들어, 블로그 게시물 댓글은 블로그 게시물을 나타내는 \<article> element에 중첩된 \<article> element 일 수 있다.

------

<br>

## The \<section> Element

- `<section>` is a logical container of the page or article.
  - `<section>`은 페이지 또는 article의 논리적 컨테이너이다.
- Sections can be used to divide up content within an article.
  - section을 사용해서 article 내의 content를 나눌 수 있다.
- For example, a homepage could have a section for introducing the company, another for news items, and still another for contact information.
  - 예를 들어, 홈페이지에는 회사 소개 section, 뉴스 항목 section, 연락처 section이 있을 수 있다.

<br>

- Each `<section>` should be identified, typically by including a heading (h1-h6 element) as a child of the \<section> element.
  - 각 `<section>`은 일반적으로 \<section> element의 child(자식)로 제목(h1-h6 element)을 포함시켜 확인해야 한다.

```html
<article>
   <h1>Welcome </h1>
   <section>
      <h1>Heading </h1>
      <p>content or image </p>
   </section>
</article>
```

[코드 실행 확인](https://code.sololearn.com/38/#html)

<br>

> If it makes sense to separately syndicate the content of a \<section> element, use an \<article> element instead.
>
> \<section> element의 content를 별도로 syndicate하는 것이 합리적이라면, 대신 \<article> element를 사용해라.

------

<br>

## The \<aside> Element

- `<aside>` is secondary or tangential content which could be considered separate from but indirectly related to the main content.
  - `<aside>`는 2차 또는 접선 content로서 별도로 간주될 수 있다.
  - 하지만 간접적으로 주요 content와 관련이 있다.
- This type of content is often represented in sidebars.
  - 이러한 type의 content는 종종 사이드바에 표시된다.
- When an \<aside> tag is used within an \<article> tag, the content of the \<aside> should be specifically related to that article.
  - \<aside> 태그가 \<article> 태그 내에서 사용될 때, \<aside>의 content는 특별히 그 article과 관련이 있어야 한다.

```html
<article>
   <h1>Gifts for everyone </h1>
   <p>This website will be the best place for choosing gifts </p>
   <aside>
      <p>Gifts will be delivered to you within 24 hours </p>
   </aside>
</article>
```

[코드 실행 확인](https://code.sololearn.com/39/#html)

<br>

> When an \<aside> tag is used outside of an \<article> tag, its content should be related to the surrounding content.
>
> \<aside> 태그가 \<article> 태그 외부에서 사용될 때, 그 content는 주변 content와 관련이 있어야 한다.

------

<br>

## QUIZ

- Which element was usually used in HTML4 instead of the article tag?
  - article 태그 대신 HTML4에서 일반적으로 사용되는 element는 무엇인가?

> `<div>`

<br>

- The section element should be used only inside an article element.
  - section element는 article element 내에서만 사용해야 한다.

> `False`

<br>

- The aside element is used to define:
  - aside element는 다음을 정의하는 데 사용된다.

> `secondary content`

<br>
