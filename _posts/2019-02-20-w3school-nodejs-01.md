---
layout: post
title: "(Node.js 01) 시작하기"
categories: dev
tags: nodejs
---

###### [w3schools Node.js](https://www.w3schools.com/nodejs/) 번역

<br>

- Node.js is an open source server environment.
  - Node.js는 오픈 소스 서버 환경이다.
- Node.js allows you to run JavaScript on the sever.
  - Node.js를 사용하면 서버에서 JS를 실행할 수 있다.

<br>

#### For example:

```js
var http = require('http');

http.createServer(function(req, res) {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('Hello World');
}).listen(8080);
```

> http://localhost:8080: `Hello World`

<br>

<br>