---
layout: post
title: "(Node.js 05) http 모듈"
categories: dev
tags: nodejs
---

###### [w3schools Node.js](https://www.w3schools.com/nodejs/) 번역

<br>

## The Built-in HTTP Module

###### 내장 HTTP 모듈

- Node.js has a built-in module called HTTP, which allows Node.js to transfer data over the Hyper Text Transfer Protocol (HTTP).
  - Node.js에는 HTTP라는 내장 모듈이 있다.
  - 내장 HTTP 모듈은 HTTP(Hyper Text Transfer Protocol)를 통해 데이터를 전송할 수 있다.
- To include the HTTP module, use the `require()` method:
  - HTTP 모듈을 포함시키기 위해 `require()` 메소드를 사용한다.

```js
var http = require('http');
```

<br>

<br>

## Node.js as a Web Server

###### 웹 서버로의 Node.js

- The HTTP module can create an HTTP server that listens to server ports and gives a response back to the client.
  - HTTP 모듈은 HTTP 서버를 생성할 수 있다.
  - 서버 port를 수신 대기(listen)하고, 클라이언트로 response을 제공한다.
- Use the `createServer()` method to create an HTTP server:
  - `createServer()` 메소드를 사용해서 HTTP 서버를 생성한다.

```js
var http = require('http');

// 서버 객체 생성
http.createServer(function(req, res) {
  res.write('Hello World');  // 클라이언트로 response 작성
  res.end();                 // response 종료
}).listen(8080);             // 서버 객체가 port 8080에서 수신 대기(listen)
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs.asp?filename=demo_http)

<br>

- The function passed into the `http.createServer()` method, will be executed when someone tries to access the computer on port 8080.
  - port 8080에 액세스를 시도할 때, `http.createServer()` 메소드로 전달된 함수가 실행된다.
- Save the code above in a file called "demo_http.js", and initiate the file:
  - 위 코드를 "demo_https.js" 파일에 저장하고 실행한다.

```bash
$ node demo_http.js
```

<br>

<br>

## Add an HTTP Header

###### HTTP Header 추가하기

- If the response from the HTTP server is supposed to be displayed as HTML, you should include an HTTP header with the correct content type:
  - HTTP 서버의 response가 HTML로 표시되는 경우, HTTP header를 포함해야 한다.

```js
var http = require('http');

http.createServer(function(req, res) {
  res.writeHead(200, { 'Content-Type': 'text/html' });
  res.write('Hello World');
  res.end();
}).listen(8080);
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs.asp?filename=demo_http_header)

<br>

- The first argument of the `res.writeHead()` method is the status code, 200 means that all is OK, the second argument is an object containing the response headers.
  - `res.writeHead()` 메소드의 첫 번째 인수(argument)는 상태 코드(status code)이다.
  - 200은 모든 것이 정상(OK)임을 의미한다.
  - 두 번째 인수는 response header를 포함하는 객체이다.

<br>

<br>

## Read the Query String

###### Query String 읽기

- The function passed into the `http.createServer()` has a `req` argument that represents the request from the client, as an object (http.IncomingMessage object).
  - `http.createServer()`로 전달된 함수에는, 클라이언트의 request를 객체(http.IncomingMessage 객체)로 나타내는 `req` 인수가 있다.
- This object has a property called "url" which holds the part of the url that comes after the domain name:
  - 이 객체에는 "url"이라는 속성이 있다.
  - 이 속성은 도메인 이름 뒤에 오는 url의 일부를 포함한다.

```js
var http = require('http');

http.createServer(function(req, res) {
  res.writeHead(200, { 'Content-Type': 'text/html' });
  res.write(req.url);
  res.end();
}).listen(8080);
```

<br>

- Save the code above in a file called "demo_http_url.js" and initiate the file:
  - 위 코드를 "demo_http_url.js" 파일에 저장하고 실행한다.

```bash
$ node demo_http_url.js
```

> localhost:8080/summer: `/summer`
>
> localhost:8080/winter: `/winter`

<br>

<br>

## Split the Query String

###### Query String 분리하기

- There are built-in modules to easily split the query string into readable parts, such as the URL module.
  - URL 모듈처럼, query 문자열을 읽을 수 있는 부분으로 쉽게 분리할 수 있는 내장 모듈이 있다.

```js
var http = require('http');
var url = require('url');

http.createServer(function(req, res) {
  res.writeHead(200, { 'Content-Type': 'text/html' });
  var q = url.parse(req.url, true).query;
  var txt = q.year + ' ' + q.month;
  res.end(txt);
}).listen(8080);
```

<br>

- Save the code above in a file called "demo_querystring.js" and initiate the file:
  - 위 코드를 "demo_querystring.js" 파일에 저장하고 실행한다.

```bash
$ node demo_querystring.js
```

> localhost:8080/?year=2019&month=August: `2019 August`

<br>

<br>