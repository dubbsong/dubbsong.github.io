---
layout: post
title: "웹페이지, 웹사이트, 웹 서버, 검색 엔진의 차이점"
categories: dev
tags: basics
---

###### [MDN web docs](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Pages_sites_servers_and_search_engines) 번역

<br>

## Summary

###### 요약

- As with any area of knowledge, the web comes with a lot of jargon.
  - 모든 지식 영역과 마찬가지로, 웹에는 많은 전문 용어가 딸려 있다.
- Don't worry, we won't overwhelm you with all of it (we have a [glossary](https://developer.mozilla.org/en-US/docs/Glossary) if you're curious).
  - 걱정하지 않아도 된다. 억누르지 않을 것이다. (궁금하다면, [용어집](https://developer.mozilla.org/en-US/docs/Glossary)을 참조할 수 있다)
- However, there are a few basic terms you need to understand at the outset, since you'll hear these expressions all the time as you read on.
  - 하지만 처음에 이해해야 할 몇 가지 기본 용어가 있다.
  - 이 글을 읽는 내내 계속 이런 표현들을 들을 것이다.
- It's easy to confuse these terms sometimes since they refer to related but different functionalities.
  - 종종 이 용어들을 혼동하기 쉽다.
  - 다른 기능들을 가지고 있지만, 관련있는 것으로 언급되기 때문이다.
- In fact, you'll sometimes see these terms misused in news reports and elsewhere, so getting them mixed up is understandable!
  - 사실 종종 뉴스 기사 등에서 잘못 사용된 이런 용어들을 볼 수 있을 것이다.
  - 그래서 이 용어들이 혼동되는 것은 당연하다.

<br>

<br>

#### web page (웹 페이지)

- A document which can be displayed in a web browser such as Firefox, Google Chrome, Opera, Microsoft Internet Explorer or Edge, or Apple's Safari.
  - Firefox, Google Chrome, Opera, Microsoft의 IE 또는 Edge, Apple의 Safari와 같은 웹 브라우저에서 보여지는 문서이다.
- These are also often called just "pages".
  - 이를 "페이지"라고도 한다.

<br>

#### website (웹사이트)

- A collection of web pages which are grouped together and usually connected together in various ways.
  - 서로 다양한 방법으로 그룹화되고 연결되는 웹 페이지의 모음이다.
- Often called a "web site" or simply a "site".
  - "웹 사이트" 또는 "사이트"라고도 한다.

<br>

#### web server (웹 서버)

- A computer that hosts a website on the Internet.
  - 인터넷에서 웹사이트를 호스팅하는 컴퓨터이다.

<br>

#### search engine (검색 엔진)

- A web service that helps you find other web pages, such as Google, Bing, Yahoo, or DuckDuckGo.
  - Google, Bing, Yahoo, DuckDuckGo와 같은 웹 서비스이다.
  - 다른 웹 페이지를 찾는 데 도움이 된다.
- Search engines are normally accessed through a web browser or through a web page.
  - 검색 엔진은 일반적으로 웹 브라우저 또는 웹 페이지를 통해 액세스 된다.

<br>

<br>

- Let's look at a simple analogy \- a public library.
  - 공공 도서관이라는 간단한 비유를 해보자.
- This is what you would generally do when visiting a library:
  - 도서관을 방문할 때, 일반적으로 하는 일은 다음과 같다.

<br>

1. Find a search index and look for the title of the book you want.
   - 검색 색인(index)을 사용해서 원하는 책의 제목을 찾는다.
2. Make a note of the catalog number of the book.
   - 책의 카탈로그 번호를 기억(메모)한다.
3. Go to the particular section containing the book, find the right catalog number, and get the book.
   - 책이 있는 섹션으로 가서 올바른 카탈로그 번호를 찾아 책을 얻는다.

<br>

<br>

- Let's compare the library with a web server:
  - 도서관을 웹 서버와 비교해보자.

- The library is like a web server.
  - 도서관은 웹 서버와 같다.
- It has several sections, which is similar to a web server hosting multiple websites.
  - 여러 웹사이트를 호스팅하는 웹 서버와 유사한 여러 섹션이 있다.
- The different sections (science, math, history, etc.) in the library are like websites.
  - 도서관의 다른 섹션들(과학, 수학, 역사 등)은 웹사이트와 같다.
- Each section is like a unique website (two sections do not contain same books).
  - 각 섹션은 고유한 웹사이트와 같다.
  - (두 섹션에는 동일한 책이 포함되지 않는다)
- The books in each section are like web pages.
  - 각 섹션의 책은 웹 페이지와 같다.
- One website may have several web pages, e.g., the Science section (the website) will have books on heat, sound, thermodynamics, statics, etc. (the web pages).
  - 하나의 웹사이트에는 여러 웹 페이지들이 있을 수 있다.
  - 예를 들어, 과학 섹션(웹사이트)에는 열, 소리, 열역학, 정역학 등(웹 페이지들)의 책이 있다.
- Web pages can each be found at a unique location (URL).
  - 웹 페이지는 각각 고유한 위치(URL)에서 찾을 수 있다.
- The search index is like the search engine.
  - 검색 색인은 검색 엔진과 같다.
- Each book has its own unique location in the library (two books cannot be kept at the same place) which is specified by the catalog number.
  - 각 책은 도서관에서 고유한 위치를 가진다.
  - 카탈로그 번호로 지정된 두 권의 책을 같은 곳에 보관할 수 없다.

<br>

<br>