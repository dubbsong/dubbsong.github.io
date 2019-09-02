---
layout: post
title: "웹 서버란 무엇인가?"
categories: dev
tags: basics
---

###### [MDN web docs](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server) 번역

<br>

## Summary

###### 요약

- "Web server" can refer to hardware or software, or both of them working together.
  - "웹 서버"는 하드웨어나 소프트웨어, 또는 둘 모두를 나타낸다.

<br>

1. On the hardware side, a web server is a computer that stores web server software and a website's component files (e.g. HTML documents, images, CSS stylesheets, and JavaScript files). It is connected to the Internet and supports physical data interchange with other devices connected to the web.
   - 하드웨어 측면에서 웹 서버는, 웹 서버 소프트웨어와 웹사이트의 컴포넌트 파일(예: HTML 문서, 이미지, CSS 스타일시트, JS 파일)을 저장하는 컴퓨터이다.
   - 인터넷에 연결되어 있으며, 웹에 연결된 다른 장치들(devices)과의 물리적 데이터 교환을 지원한다.
2. On the software side, a web server includes several parts that control how web users access hosted files, at minimum an *HTTP server*. An HTTP server is a piece of software that understands URLs (web addresses) and HTTP (the protocol your browser uses to view web pages). It can be accessed through the domain names (like `mozilla.org`) of websites it stores, and delivers their content to the end-user's device).
   - 소프트웨어 측면에서 웹 서버는, 웹 사용자가 어떻게 호스팅된 파일에 액세스하는지를 관리한다.
   - 이 문서에서 웹 서버는 *HTTP 서버*로 국한한다.
   - HTTP 서버는 URL(웹 주소)과 HTTP(브라우저가 웹 페이지를 보는 데 사용하는 프로토콜)를 이해하는 소프트웨어이다.
   - 웹사이트의 도메인 이름(`mozilla.org`와 같은)을 통해 액세스할 수 있으며, 최종 사용자(end-user)의 장치에 해당 내용을 전달한다.

<br>

<br>

- At the most basic level, whenever a browser needs a file which is hosted on a web server, the browser requests the file via HTTP.
  - 가장 기본적인 수준에서, 브라우저가 웹 서버에서 호스팅된 파일이 필요할 때마다 HTTP를 통해 파일을 요청한다.
- When the request reaches the correct web server (hardware), the *HTTP server* (software) accepts request, finds the requested document (if it doesn't then a 404 response is returned), and sends it back to the browser, also through HTTP.
  - 요청(request)이 올바른 웹 서버(하드웨어)에 도달하면, *HTTP 서버*(소프트웨어)가 요청을 수락한다.
  - 그리고 요청된 문서를 찾아(404 응답이 반환되지 않은 경우), HTTP를 통해 브라우저로 다시 보낸다.

![img](/assets/img/mdn-web-server-01.svg)

<br>

- To publish a website, you need either a static or a dynamic web server.
  - 웹사이트를 게시(publish)하려면, 정적 또는 동적 웹 서버가 필요하다.

<br>

- A `static web server`, or stack, consists of a computer (hardware) with an HTTP server (software).
  - `정적 웹 서버` 또는 스택은, HTTP 서버(소프트웨어)가 있는 컴퓨터(하드웨어)로 구성된다.
- We call it "static" because the server sends its hosted files "as-is" to your browser.
  - 서버가 호스팅된 파일을 "있는 그대로" 브라우저로 보내므로, "정적(static)"이라고 한다.

<br>

- A `dynamic web server` consists of a static web server plus extra software, most commonly an *application server* and a *database*.
  - `동적 웹 서버`는, 정적 웹 서버와 추가 소프트웨어로 구성된다.
  - 가장 일반적으로 *애플리케이션 서버*와 *데이터베이스*이다.
- We call it "dynamic" because the application server updates the hosted files before sending them to your browser via the HTTP server.
  - 애플리케이션 서버는 호스팅된 파일을 브라우저로 보내기 전에 업데이트하므로, "동적(dynamic)"이라고 한다.

<br>

- For example, to produce the final web pages you see in the browser, the application server might fill an HTML template with contents from a database.
  - 예를 들어, 브라우저에 보여지는 최종 웹 페이지를 생성하기 위해, 애플리케이션 서버는 데이터베이스의 컨텐츠로 HTML 템플릿을 채울 수 있다.
- Sites like MDN or Wikipedia have many thousands of web pages, but they aren't real HTML documents, only a few HTML templates and a giant database.
  - MDN 또는 Wikipedia와 같은 사이트에는 수천 개의 웹 페이지가 있지만, 실제 HTML 문서는 아니다.
  - 몇몇 HTML 템플릿과 거대한 데이터베이스만 있다.
- This setup makes it easier and quicker to maintain and deliver the content.
  - 이러한 설정을 통해 컨텐츠를 보다 쉽고 빠르게 유지관리하고 전달한다.

<br>

<br>

## Deeper dive

###### 깊게 들어가기

- To fetch a web pages, as we already said, your browser sends a request to the web server, which proceeds to search for the requested file in its own storage space.
  - 이미 말했듯이, 웹 페이지를 가져오기 위해 브라우저가 웹 서버에 요청(request)을 보낸다.
- On finding the file, the server reads it, processes it as needed, and sends it to the browser.
  - 파일을 찾으면 서버는 파일을 읽고, 필요에 따라 처리한 후 브라우저로 보낸다.
- Let's look at those steps in more detail.
  - 이러한 단계를 더 자세히 살펴보자.

<br>

#### Hosting files (호스팅 파일들)

- A web server first has to store the website's files, namely all HTML documents and their related assets, including images, CSS stylesheets, JavaScript files, fonts, and videos.
  - 웹 서버는 먼저 웹사이트의 파일들, 즉 모든 HTML 문서 및 관련 자산을 저장해야 한다.
  - (이미지, CSS 스타일시트, JS 파일, 폰트, 비디오 등)
- Technically, you could host all those files on your own computer, but it's far more convenient to store them all on a dedicated web server.
  - 기술적으로, 모든 파일을 자기 자신의 컴퓨터에서 호스팅 할 수 있다.
  - 하지만 전용 웹 서버에 모두 저장하는 것이 훨씬 편리하다.

<br>

- Dedicated web server that:
  - 전용 웹 서버는:

1. is always up and running
   - 항상 실행 중이다.
2. is always connected to the Internet
   - 항상 인터넷에 연결되어 있다.
3. has the same IP address all the time
   - 항상 동일한 IP 주소를 가진다.
4. is maintained by a third-party provider
   - 제3자(제공 업체)에 의해 관리된다.

<br>

- For all these reasons, finding a good hosting provider is a key part of building your website.
  - 이러한 모든 이유로, 좋은 호스팅 제공 업체를 찾는 것이 웹사이트 구축의 핵심 부분이다.
- Dig through the various services companies offer and choose one that fits your needs and your budget (services range from free to thousands of dollars per month).
  - 다양한 서비스 회사들의 조건을 살펴보고, 당신의 필요와 예산에 맞는 것을 선택해라.
  - (서비스는 무료부터 매달 수천 달러까지 있다)
- Once you set up a web hosting solution, you just have to upload your files to your web server.
  - 웹 호스팅 솔루션을 설정했다면, 파일을 그저 웹 서버에 업로드하면 된다.

<br>

#### Communicating through HTTP (HTTP를 통한 통신)

- Second, a web server provides support for HTTP (`H`yper`t`ext `T`ransfer `P`rotocol).
  - 두 번째로, 웹 서버는 HTTP(인터넷 데이터 통신 규약)를 위한 지원을 한다.
- As its name implies, HTTP specifies how to transfer hypertext (i.e., linked web documents) between two computers.
  - 이름이 암시하듯이, HTTP는 두 컴퓨터 간에 하이퍼텍스트(예: 링크된 웹 문서)를 전송하는 방법을 지정한다.

> **Hypertext:**
>
> 사용자에게 비순차적인 검색을 할 수 있도록 제공되는 텍스트.
>
> 문서 속의 특정 자료가 다른 자료나 데이터베이스와 연결되어 있어, 서로 넘나들며 원하는 정보를 얻을 수 있다.

<br>

- A Protocol is a set of rules for communication between two computers.
  - 프로토콜은 두 컴퓨터 간의 통신을 위한 규칙의 모음이다.
- HTTP is a textual, stateless protocol.
  - HTTP는 문자로 된, 상태 비저장(stateless) 프로토콜이다.

<br>

<br>

###### Textual (문자로 된)

- All commands are plain-text and human-readable.
  - 모든 명령어는 평문(일반 문자)이며, 사람이 읽을 수 있다.

<br>

###### Stateless (상태 비저장)

- Neither the server nor the client remember previous communications.
  - 서버와 클라이언트 모두 이전의 통신을 기억하지 않는다.
- For example, relying on HTTP alone, a server cannot remember a password you typed or what step you're on in a transaction.
  - 예를 들어 HTTP에만 의존한다면, 서버는 당신이 입력한 비밀번호 또는 당신이 처리한 단계를 기억하지 못한다.
- You need an application server for tasks like that.
  - 이러한 일들을 위한 애플리케이션 서버가 필요하다.

<br>

<br>

- HTTP provides clear rules for how a client and server communicate.
  - HTTP는 클라이언트와 서버가 통신하는 방법에 대한 명확한 규칙을 제공한다.
- We'll cover HTTP itself in a technical article later on.
  - 나중에 [technical article](https://developer.mozilla.org/en-US/docs/Web/HTTP)에서 HTTP를 다룰 것이다.
- For now, just be aware of these things:
  - 지금은 아래의 것들만 기억한다.

<br>

1. Only clients can make HTTP requests, and then only to servers. Servers can only respond to a client\'s HTTP request.
   - 클라이언트만 HTTP 요청을 생성할 수 있고, 서버한테만 보낼 수 있다.
   - 서버는 클라이언트의 HTTP 요청에만 응답할 수 있다.
2. When requesting a file via HTTP, clients must provide the file\'s URL.
   - HTTP를 통해 파일을 요청할 때, 클라이언트는 파일의 URL을 제공해야 한다.
3. The web server must answer every HTTP request, at least with an error message.
   - 웹 서버는 적어도 에러 메시지를 포함한 모든 HTTP 요청에 응답해야 한다.

<br>

<br>

- On a web server, the HTTP server is responsible for processing and answering incoming requests.
  - 웹 서버에서, HTTP 서버는 들어오는 요청을 처리하고 응답한다.

<br>

1. On receiving a request, an HTTP server first checks whether the requested URL matches an existing file.
   - 요청을 수신하면, HTTP 서버는 요청된 URL이 기존 파일과 일치하는지 먼저 확인한다.
2. If so, the web server sends the file content back to the browser. If not, an application server builds the necessary file.
   - 일치한다면, 웹 서버는 파일 컨텐츠를 브라우저로 다시 보낸다.
   - 일치하지 않는다면, 애플리케이션 서버는 필요한 파일을 빌드한다.
3. If neither process is possible, the web server returns an error message to the browser, most commonly [404 Not Found](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/404). (That error is so common that many web designers spend quite some time designing [404 error pages](http://www.404notfound.fr))
   - 어떤 프로세스도 가능하지 않는다면, 웹 서버는 브라우저로 에러 메시지를 반환한다.
   - 가장 일반적으로 [404 Not Found](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/404)를 반환한다.
   - (이 에러는 매우 일반적이다. 많은 웹 디자이너가 [404 에러 페이지](http://www.404notfound.fr)를 디자인하는 데 시간을 소비한다)

<br>

<br>

#### Static vs. dynamic content (정적 vs. 동적 컨텐츠)

- Roughly speaking, a server can serve either static or dynamic content.
  - 대충 말하자면, 서버는 정적 또는 동적 컨텐츠를 제공할 수 있다.

<br>

- "Static" means "served as-is".
  - "정적"은 "있는 그대로 제공되는 것(served as-is)"을 의미한다.
- Static websites are the easiest to set up, so we suggest you make your first site a static site.
  - 정적 웹사이트를 설정하는 것이 가장 쉬운 방법이므로, 첫 번째 사이트는 정적 사이트로 생성하는 것이 좋다.

<br>

- "Dynamic" means that the server processes the content or even generates it on the fly from a database.
  - "동적"은 서버가 컨텐츠를 처리하거나, 심지어 데이터베이스에서 즉시 생성함을 의미한다.
- This solution provides more flexibility, but the technical stack becomes more difficult to handle, making it dramatically more complex to build the website.
  - 이 방법은 더 많은 유연성을 제공하지만, 기술적 스택을 처리하기 더 어려지고, 웹사이트 빌드가 더 복잡해진다.

<br>

- Take for example the page you're reading right now.
  - 예를 들어, 지금 읽고 있는 페이지를 살펴보자.
- On the web server hosting it, there is an application server that takes article content from a database, formats it, puts it inside some HTML templates, and sends you the results.
  - 이를 호스팅하는 웹 서버에는 애플리케이션 서버가 있다.
  - 애플리케이션 서버는 데이터베이스에서 기사 컨텐츠를 가져와 구성하고, HTML 템플릿에 넣고, 결과를 보낸다.
- In this case, the application server is called [Kuma](https://developer.mozilla.org/en-US/docs/MDN/Kuma) and is built with Python (using the Django framework).
  - 이 경우, 애플리케이션 서버를 [Kuma](https://developer.mozilla.org/en-US/docs/MDN/Kuma)라고 하며,   Python(Django 프레임워크를 사용)으로 빌드된다.
- The Mozilla team built Kuma for the specific needs of MDN, but there are many similar applications built on many other technologies.
  - Mozilla 팀은 MDN의 특정 요구에 맞게 Kuma를 빌드했다.
  - 하지만 다른 기술을 기반으로 하는 유사한 애플리케이션이 많이 있다.

<br>

- There are so many application servers that it's pretty hard to suggest a particular one.
  - 애플리케이션 서버가 너무 많아서, 특정한 하나를 제안하기 어렵다.
- Some application servers cater to specific website categories like blogs, wikis or e-shops; others, called CMSs (Content Management Systems), are more generic.
  - 일부 애플리케이션 서버는 블로그, wiki, e-shop과 같은 특정 웹사이트에 특화되어 있다.
  - CMS(컨텐츠 관리 시스템)라고도 한다.
- If you're building a dynamic website, take the time to choose a tool that fits your needs.
  - 동적 웹사이트를 구축하는 경우, 필요에 맞는 도구를 선택할 시간을 가져야 한다.
- Unless you want to learn some web server programming (which is an exciting area in itself), you don't need to create your own application server.
  - 웹 서버 프로그래밍 배우기를 원하는 경우가 아니라면, 애플리케이션 서버를 생성할 필요가 없다.
- That's just [reinventing the wheel](https://en.wikipedia.org/wiki/Reinventing_the_wheel).
  - 그것은 단지 [바퀴를 재발명하는 것](https://en.wikipedia.org/wiki/Reinventing_the_wheel)이다.

<br>

<br>