---
layout: post
title: "웹은 어떻게 동작하는가?"
categories: dev
tags: basics
---

###### [MDN web docs](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works) 번역

<br>

## Clients and servers

###### 클라이언트와 서버

- Computers connected to the web are called `clients` and `servers`.
  - 웹에 연결된 컴퓨터를 `클라이언트`와 `서버`라고 한다.
- A simplified diagram of how they interact might look like this:
  - 클라이언트와 서버가 어떻게 상호 작용하는지에 대한 다이어그램은 다음과 같다.

![img](/assets/img/mdn-web-01.jpg)

<br>

###### Client

- Clients are the typical web user's internet-connected devices (for example, your computer connected to your Wi-Fi, or your phone connected to your mobile network) and web-accessing software available on those devices (usually a web browser like Firefox or Chrome).
  - 클라이언트는 웹 사용자의 인터넷 연결 장치(예를 들어, 와이파이에 연결된 컴퓨터 또는 모바일 네트워크에 연결된 폰) 및 해당 장치(일반적으로 Firefox 또는 Chrome과 같은 웹 브라우저)에서 사용 가능한 웹 접속 소프트웨어이다.

<br>

###### Server

- Servers are computers that store web pages, sites, or apps.
  - 서버는 웹 페이지, 사이트, 애플리케이션을 저장하는 컴퓨터이다.
- When a client device wants to access a web page, a copy of the web page is downloaded from the server onto the client machine to be displayed in the user's web browser.
  - 클라이언트 장치가 웹 페이지에 액세스를 원할 때, 웹 페이지의 사본이 서버에서 클라이언트 컴퓨터로 다운로드되고, 사용자의 웹 브라우저에 표시된다.

<br>

<br>

## The other parts of the toolbox

###### 도구 상자(toolbox)의 다른 부분

- The client and server we've described above don't tell the whole story.
  - 위에서 설명한 클라이언트와 서버가 모든 것을 알려주지는 않는다.
- For now, let's imagine that the web is a road.
  - 웹이 도로라고 생각해보자.
- On one end of the road is the client, which is like your house.
  - 도로의 한쪽 끝은 클라이언트이다.
- On the other end of the road is the server, which is a shop you want to buy something from.
  - 도로의 다른 쪽 끝은 서버이다.

![img](/assets/img/mdn-web-02.jpg)

<br>

- In addition to the client and the server, we also need to say hello to:
  - 클라이언트와 서버 외에도 다른 것들이 있다.

<br>

###### Your internet connection (인터넷 연결)

- Allows you to send and receive data on the web.
  - 웹에서 데이터를 주고 받을 수 있다.
- It's basically like the street between your house and the shop.
  - 기본적으로 클라이언트(집)와 서버(상점) 사이의 거리(street)와 같다.

<br>

###### TCP/IP

- Transmission Control Protocol and Internet Protocol are communication protocols that define how data should travel across the web.
  - 전송 제어 규약(TCP)과 인터넷 규약(IP)은 데이터가 웹을 통해 이동하는 방법을 정의하는 통신 규약이다.
- This is like the transport mechanisms that let you place an order, go to the shop, and buy your goods.
  - 이는 주문을 하고, 상점에 가고, 물건을 사는 운송 메커니즘과 비슷하다.
- In our example, this is like a car or a bike (or however else you might get around).
  - 이 예시에서는, 자동차 또는 자전거와 같다.

<br>

<br>

###### DNS

- Domain Name Servers are like an address book for websites.
  - 도메인 이름 서버(DNS)는 웹사이트의 주소록과 같다.
- When you type a web address in your browser, the browser looks at the DNS to find the website's real address before it can retrieve the website.
  - 브라우저에 웹 주소를 입력하면, 브라우저는 그 웹사이트를 검색하기 전에 DNS를 살펴보고 웹사이트의 진짜 주소를 찾는다.
- The browser needs to find out which server the website lives on, so it can send HTTP messages to the right place (see below).
  - 브라우저는 HTTP 메시지를 올바른 위치로 전송하기 위해, 그 웹사이트가 있는 서버를 찾아야한다.
- This is like looking up the address of the shop so you can access it.
  - 이는 상점의 주소를 찾는 것과 같다.

<br>

###### HTTP

- Hypertext Transfer Protocol is an application protocol that defines a language for clients and servers to speak to each other.
  - 하이퍼텍스트 전송 규약(HTTP)은 클라이언트와 서버가 서로 통신할 수 있게 하기 위한 언어를 정의하는 애플리케이션 규약이다.
- This is like the language you use to order your goods.
  - 이는 물건을 주문할 때 사용하는 언어와 같다.

<br>

###### Component files (컴포넌트 파일)

- A website is made up of many different files, which are like the different parts of the goods you buy from the shop.

  - 하나의 웹사이트는 많은 다른 파일들로 구성된다.
  - 상점에서 구매하는 다양한 종류의 물건과 같다.

  ###### Code files (코드 파일)

  - Websites are built primarily from HTML, CSS, and JavaScript, though you'll meet other technologies a bit later.
    - 웹사이트는 주로 HTML, CSS, JS로 구현된다.
    - 조금 있다가 다른 기술들도 살펴볼 것이다.

  ###### Assets (자원)

  - This is a collective name for all the other stuff that makes up a website, such as images, music, video, Word documents, and PDFs.
    - 이는 이미지, 음악, 비디오, Word 문서, PDF와 같이, 웹사이트를 구성하는 다른 모든 것의 총칭이다.

<br>

<br>

## So what happens, exactly?

###### 그래서 정확히 무슨 일이 일어나는가?

- When you type a web address into your browser (for our analogy that's like walking to the shop):
  - 브라우저에 웹 주소를 입력할 때 (비유하자면, 상점으로 걸어가는 것과 비슷하다):

<br>

1. The browser goes to the DNS server, and finds the real address of the server that the website lives on (you find the address of the shop).
   - 브라우저는 DNS 서버로 가서, 웹사이트가 있는 서버의 진짜 주소를 찾는다.
   - (상점의 주소를 찾는다)
2. The browser sends an HTTP request message to the server, asking it to send a copy of the website to the client (you go to the shop and order your goods). This message, and all other data sent between the client and the server, is sent across your internet connection using TCP/IP.
   - 브라우저는 서버로 HTTP 요청 메시지를 전송한다.
   - 이 요청 메시지는, 웹사이트의 사본을 클라이언트로 보내달라는 것이다.
   - (상점으로 가서 물건을 주문한다)
   - 이 메시지, 그리고 클라이언트와 서버 간 전송된 모든 데이터는, TCP/IP 연결을 통해 전송된다.
3. If the server approves the client's request, the server sends the client a "200 OK" message, which means "Of course you can look at that website! Here it is", and then starts sending the website's files to the browser as a series of small chunks called data packets (the shop gives you your goods, and you bring them back to your house).
   - 서버가 클라이언트의 요청을 승인하면, 서버는 "200 OK" 메시지를 클라이언트로 전송한다.
   - 즉, "당연히 해당 웹사이트를 볼 수 있어! 여기 있어."라는 의미이다.
   - 그런 다음, 서버는 웹사이트의 파일들을 데이터 패킷(일련의 작은 덩어리들)으로 브라우저에 전송하기 시작한다.
   - (상점에서 물건을 당신에게 주고, 당신은 물건을 집으로 가져간다)
4. The browser assembles the small chunks into a complete website and displays it to you (the goods arrive at your door \- new shiny stuff, awesome!).
   - 브라우저는 이 작은 덩어리들을 완전한 웹사이트로 조립하고, 당신에게 보여준다.
   - (물건이 당신의 문에 도착한다)

<br>

<br>

## DNS explained

###### DNS 설명하기

- Real web addresses aren't the nice, memorable strings you type into your address bar to find your favorite websites.
  - 실제 웹 주소들은 멋지지 않다.
  - 기억할 만한 문자가 아니다.
- They are special numbers that look like this: `63.245.215.20`
  - 실제 웹 주소는 다음과 같은 특수한 숫자이다: `63.245.215.20`
- This is called an IP address, and it represents a unique location on the web.
  - 이를 IP 주소라고 한다.
  - 웹에서 고유한 위치를 나타낸다.
- However, it's not very easy to remember, is it?
  - 하지만 기억하기가 쉽지 않다.
- That's why Domain Name Servers were invented.
  - 이것이 DNS가 발명된 이유이다.
- These are special servers that match up a web address you type into your browser (like "mozilla.org") to the website's real (IP) address.
  - DNS는 입력한 웹 주소를 웹사이트의 진짜 주소와 일치시키는 특수한 서버이다.
- Websites can be reached directly via their IP addresses.
  - 웹사이트는 IP 주소를 통해 직접 접근할 수도 있다.
- You can find the IP address of a website by typing its domain into a tool like [IP Checker](https://ipinfo.info/html/ip_checker.php).
  - [IP Checker](https://ipinfo.info/html/ip_checker.php)와 같은 툴에 도메인을 입력해서 웹사이트의 IP 주소를 찾을 수 있다.

<br>

<br>

## Packets explained

###### 패킷 설명하기

- Basically, when data is sent across the web, it is sent as thousands of small chunks, so that many different web users can download the same website at the same time.
  - 데이터가 웹을 통해 전송될 때, 수천 개의 작은 덩어리로 전송된다.
  - 따라서 다양한 웹 사용자들은 동시에 동일한 웹사이트를 다운로드할 수 있다.
- If websites were sent as single big chunks, only one user could download one at a time, which obviously would make the web very inefficient and not much fun to use.
  - 웹사이트가 하나의 큰 덩어리로 전송된다면, 한 번에 한 명의 사용자만 다운로드할 수 있다.
  - 이는 분명히 웹을 아주 비효율적이고 재미없게 만들 것이다.

<br>

<br>