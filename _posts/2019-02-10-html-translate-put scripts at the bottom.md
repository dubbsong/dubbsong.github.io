---
layout: post
title: "(번역) Put Scripts at the Bottom"
categories: dev
tags: basic
---

###### [YAHOO! 개발자 네트워크](https://developer.yahoo.com/performance/rules.html#js_bottom) 번역

<br>

### Put Scripts at the Bottom

###### Script를 맨 아래에 놓아라

<br>

- The problem caused by scripts is that they block parallel downloads.
  - scripts로 인해 발생하는 문제는, 병렬 다운로드를 차단한다는 것이다.
- The [HTTP/1.1 specification](https://www.w3.org/Protocols/rfc2616/rfc2616-sec8.html#sec8.1.4) suggests that browsers download no more than two components in parallel per hostname.
  - [HTTP/1.1 명세](https://www.w3.org/Protocols/rfc2616/rfc2616-sec8.html#sec8.1.4)는 브라우저가 hostname당 두 개의 컴포넌트를 병렬로(동시에) 다운로드하지 않는다고 제시한다.
- If you serve your images from multiple hostnames, you can get more than two downloads to occur in parallel.
  - 여러 hostname에서 이미지를 제공하는 경우, 두 개 이상의 다운로드가 동시에 발생할 수 있다.
- While a script is downloading, however, the browser won't start any other downloads, even on different hostnames.
  - 하지만 script가 다운로드되는 동안, 브라우저는 다른 hostname에서도 다른 다운로드를 시작하지 않는다.

<br>

- In some situations it's not easy to move scripts to the bottom.
  - 일부 상황에서는 script를 맨 아래로 이동시키는 게 쉽지 않다.
- If, for example, the script uses `document.write` to insert part of the page's content, it can't be moved lower in the page.
  - 예를 들어 script가 `document.write`를 사용해서 페이지 내용의 일부를 삽입하면, 페이지에서 더 아래로 이동할 수 없게 된다.
- There might also be scoping issues.
  - 범위 문제가 있을 수도 있다.
- In many cases, there are ways to workaround these situations.
  - 대부분의 경우, 이러한 상황을 해결할 수 있는 방법이 있다.

<br>

- An alternative suggestion that often comes up is to use deferred scripts.
  - 자주 제시되는 대안은, 지연(거치) script를 사용하는 것이다.
- The `DEFER` attribute indicates that the script does not contain document.write, and is a clue to browsers that they can continue rendering.
  - `DEFER` 속성은 script에 document.write가 포함되어 있지 않고, 브라우저에서 렌더링을 계속할 수 있다는 실마리를 나타낸다.
- Unfortunately, Firefox doesn't support the `DEFER` attribute.
  - 유감스럽게도, Firefox는 `DEFER` 속성을 지원하지 않는다.
- In Internet Explorer, the script may be deferred, but not as much as desired.
  - IE에서 script는 지연(거치)될 수 있지만, 바라는 만큼 실행되지 않을 수 있다.
- If a script can be deferred, it can also be moved to the bottom of the page.
  - script가 지연(거치)될 수 있으면, 페이지의 맨 아래로 이동시킬 수도 있다.
- That will make your web pages load faster.
  - 그렇게 하면, 웹 페이지가 더 빨리 로딩된다.

<br>