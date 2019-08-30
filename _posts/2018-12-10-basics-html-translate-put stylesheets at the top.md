---
layout: post
title: "(번역) Put Stylesheets at the Top"
categories: dev
tags: basics
---

###### [YAHOO! 개발자 네트워크](https://developer.yahoo.com/performance/rules.html#css_top) 번역

<br>

### Put Stylesheets at the Top

###### Stylesheet를 HEAD에 놓아라

<br>

- While researching performance at Yahoo!, we discovered that moving stylesheets to the document HEAD makes pages *appear* to be loading faster.
  - Yahoo!에서 성능에 대한 연구를 하는 동안, stylesheet를 document HEAD로 이동시키면 페이지가 더 빨리 로딩되는 것을 발견했다.
- This is because putting stylesheets in the HEAD allows the page to render progressively.
  - stylesheet를 HEAD에 놓으면, 페이지가 점진적으로 렌더링 될 수 있다.

<br>

- Front-end engineers that care about performance want a page to load progressively; that is, we want the browser to display whatever content it has as soon as possible.
  - 성능에 관심을 가지는 프론트엔드 엔지니어는, 페이지를 점진적으로 로딩하려고 한다.
  - 즉, 되도록 빨리 브라우저에 내용을 표시하려고 한다.
- This especially important for pages with a lot of content and for users on slower Internet connections.
  - 이는 많은 내용이 있는 페이지와, 느린 인터넷 연결을 사용하는 사용자에게 특히 중요하다.
- The importance of giving users visual feedback, such as progress indicators, has been well researched and [documented](https://www.nngroup.com/articles/response-times-3-important-limits/).
  - 사용자에게 시각적 피드백을 제공하는 중요성은 잘 연구되고 문서화되었다.
- When the browser loads the page progressively the header, the navigation bar, the logo at the top, etc. all serve as visual feedback for the user who is waiting for the page.
  - 브라우저가 페이지를 점진적으로 로딩하면 머리말, 네비게이션 바, 상단 로고 등이 모두 페이지를 기다리는 사용자를 위한 시각적 피드백 역할을 한다.
- This improves the overall user experience.
  - 이렇게 하면 전반적으로 사용자 경험이 향상된다.

<br>

- The problem with putting stylesheets near the bottom of the document is that it prohibits progressive rendering in many browsers, including Internet Explorer.
  - document의 맨 아래 근처에 stylesheet를 놓는 문제는, IE를 포함한 많은 브라우저에서 점진적 렌더링을 금지한다는 것이다.
- These browsers block rendering to avoid having to redraw elements of the page if their styles change.
  - 스타일이 변경된 경우, 이러한 브라우저들은 페이지를 다시 그리지 않도록 렌더링을 차단한다.
- The user is stuck viewing a blank white page.
  - 사용자는 비어 있는 흰색 페이지를 보게 된다.

<br>

- The [HTML specification](https://www.w3.org/TR/html4/struct/links.html#h-12.3) clearly states that stylesheets are to be included in the HEAD of the page: "Unlike A, [LINK] may only appear in the HEAD section of a document, although it may appear any number of times."
  - [HTML 명세](https://www.w3.org/TR/html4/struct/links.html#h-12.3)에서는 stylesheets가 페이지의 HEAD에 포함되어야 한다고 확실히 명시한다.
  - "A와 달리 [LINK]는 여러 번 나타날 수 있지만, document의 HEAD 섹션에만 나타날 수 있다."
- Neither of the alternatives, the blanks white screen or flash of unstyled content, are worth the risk.
  - 비어 있는 흰색 화면 또는 스타일이 없는 내용의 플래시는 위험을 감수할 가치가 없다.
- The optimal solution is to follow the HTML specification and load your stylesheets in the document HEAD.
  - 최적의 해결책은, HTML 명세에 따라 document HEAD에서 stylesheet를 로딩하는 것이다.

<br>